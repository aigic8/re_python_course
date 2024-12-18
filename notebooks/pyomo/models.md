# Pyomo Models Description

## Basic Model

### Parameters

- grid_buy_price
- demand[t]

### Variables

- v_po_grid[t]

### Constraints

- demand[t] <= v_po_grid[t]

### Objective Function

- sum(v_po_grid[t] * grid_buy_price) => min

## PV + Grid Model

### Parameters PV

- c_array = (7 \* 200 + 1 \* 500) / 20.0
- grid_buy_price = 0.3
- grid_sell_price = 0.2
- demand[t]
- po_array_single[t]

### Variables PV

- v_i_arrays
- v_po_grid[t]
- v_grid_sell[t]

### Constraints PV

- demand_supply: v_po_grid[t] + v_i_arrays * po_array_single[t] == demand[t] + v_grid_sell[t]

- initial cost: v_i_arrays * c_array <= 20_000 / 20

### Objective Function PV

minimize cost

Only once:
pv_init = c_array * v_i_arrays

Multiple times:
grid_buy_price = grid_buy_price \* v_po_grid
grid_sell_income = grid_sell_price \* v_grid_cell

pv_init + grid_buy_price - grid_sell_income

## Grid + Batteries + Variable Price

### Parameters Battery Grid

- input_energy[t]
- price[t]
- soc_init
- soc_max
- soc_min
- sell_max

### Variables Battery Grid

- v_sell[t]
- v_soc[t]

### Constraints Battery Grid

- sell[t] <= sell_max
- soc[t] <= soc_max
- soc[t] >= soc_min
- soc[t] - soc[t-1] = input_energy[t] - sell[t]
- soc[1] - soc_init = input_energy[t] - sell[t]

### Objective Function Battery Grid

- sell[t] * p[t] (max)
