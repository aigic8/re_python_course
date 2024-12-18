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

## Input Energy + Batteries + Sell

### Parameters Battery Input

- soc_init = 500.0
- soc_max = 500.0
- soc_min = 0.0
- sell_max = 150.0
- input_energy[t]
- price[t]

### Variables Battery Input

- v_sell[t]
- v_soc[t]

### Constraints Battery Input

- v_sell[t] <= sell_max
- v_soc[t] <= soc_max
- v_soc[t] >= soc_min
- v_soc[t-1] + input_energy[t] * model.soc_max - v_sell[t] == model.v_soc[t]

### Objective Function Battery Input

- sum(v_sell[t] * price[t]) (max)

## Grid + Batteries + Sell + Buy

### Parameters Battery Grid

- soc_init = 500.0
- soc_max = 500.0
- soc_min = 0.0
- sell_max = 150.0
- input_energy_max = 100
- price[t]

### Variables Battery Grid

- v_sell[t]
- v_soc[t]
- v_input_energy[t]

### Constraints Battery Grid

- v_sell[t] <= sell_max
- v_input_energy[t] <= model.v_input_energy_max
- v_soc[t] <= soc_max
- v_soc[t] >= soc_min
- soc_init + input_energy[0] - v_sell[0] == model.v_soc[0]
- soc[t-1] + input_energy[t] - v_sell[t] == model.v_soc[t]

### Objective Function Battery Grid

- sum((v_sell[t] - v_input_energy[t]) * price[t]) (max)
