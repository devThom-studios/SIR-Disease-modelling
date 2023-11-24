# SIR-Disease-modelling
## SIR Model for Malaria Transmission

A simple SIR model to demonstrate the transmission of Malaria. Please note that the parameters used are just for demonstration purposes and as such, the model does not accurately predict the spread of the disease.

### SIR Model Explanation

The SIR model is a simple mathematical model used to understand the spread of infectious diseases in a population. It divides the population into three compartments:

1. **Susceptible (S):** Individuals who are not yet infected but are at risk of becoming infected.
2. **Infected (I):** Individuals who are currently infected and can spread the disease to susceptible individuals.
3. **Recovered (R):** Individuals who have recovered from the disease and are no longer infectious.

### Model Equations

The model is governed by a set of ordinary differential equations (ODEs) which describe the rate of movement between these compartments:

1. **Susceptible Equation:**
   $$ \frac{dS}{dt} = \mu - \frac{\beta S I}{P} - \theta S $$
   - \( $\mu$ \): Number of births per day (adding to the susceptible population).
   - \( $\beta$ \): Transmission rate (how quickly the disease spreads from infected to susceptible).
   - \( $\theta$ \): Natural death rate (not due to the disease).
   - \( S \): Number of susceptible individuals.
   - \( I \): Number of infected individuals.
   - \( P \): Total population.

2. **Infected Equation:**
   $$ \frac{dI}{dt} = \frac{\beta S I}{P} - \theta I - \alpha I - \gamma I $$
   - \( $\alpha$ \): Death rate due to the disease.
   - \( $\gamma$ \): Recovery rate (rate at which infected individuals recover and move to the recovered class).

3. **Recovered Equation:**
   $$ \frac{dR}{dt} = \gamma I - \theta R $$
   - \( R \): Number of recovered individuals.

### Initial Conditions

For the simulation, initial conditions must be defined:

- Initially, almost the entire population is susceptible, except for a small number of infected individuals.
- \( $S_0 = P - I_0 - R_0$ \) (Initial susceptible population).
- \( $I_0$ \): Initial number of infected individuals.
- \( $R_0$ \): Initial number of recovered individuals.

### Simulation and Plotting

- The model is simulated over a time grid (e.g., 365 days).
- The differential equations are solved numerically using `odeint` from `scipy.integrate`.
- The results (S, I, R over time) are plotted to visualize the dynamics of the disease spread and recovery.
