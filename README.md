## SIR Model for Malaria Transmission
### FOURTH YEAR - SECOND SEMESTER 2020-2021 ACADEMIC YEAR
### MET 462 BIOMETEOROLOGY AND HUMAN HEALTH
$
{\color{red}Note \space that \space the \space model \space does \space not \space anticipate \space the \space disease's \space spread \space precisely \space because \space the \space parameters \space are \space only \space used \space for \space demonstration.}
$


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
   
$$  \frac{dR}{dt} = \gamma I - \theta R $$
   
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

## SIR Model Epidemic Dynamics

The provided plot is a graphical representation of the SIR (Susceptible, Infected, Recovered) model over the course of one year (365 days). It shows the dynamics of an infectious disease spreading through a population, with three distinct curves corresponding to the different compartments of the model:

### Susceptible Population (Black Curve)

- **Initial State:**
  - Starts at the highest value, indicating the entire population is initially susceptible to the infection.
  
- **Progression:**
  - Declines sharply over time as the disease spreads and individuals move from susceptible to infected.

### Infected Population (Red Curve)

- **Initial State:**
  - Begins with a very low value, reflecting the few infections present at the start.
  
- **Rise to Peak:**
  - Increases rapidly, representing the spread of the infection.
  
- **Decline:**
  - After reaching a peak, it falls as the rate of new infections decreases, which could be due to the depletion of susceptible individuals.

### Recovered Population (Green Curve)

- **Initial State:**
  - Starts at zero since no one has recovered from the infection initially.
  
- **Increase Over Time:**
  - Rises as individuals recover from the infection or are removed from the susceptible and infected categories, leveling off when the outbreak has ended.

### Key Observations

- **Peak of Infection:**
  - The peak of the infected curve is indicative of the most intense point of the outbreak.
  
- **Herd Immunity or Disease Burnout:**
  - The plateauing of the susceptible curve, coupled with the decrease in infections, suggests a form of herd immunity or the burnout of the disease, where there are not enough susceptible individuals to sustain further transmission.

- **Epidemic Conclusion:**
  - The stabilization of all curves indicates the end of the epidemic within the simulated timeframe.

### Conclusion

The plot narrates the course of an infectious disease outbreak, starting with a susceptible population, escalating to a widespread infection, and eventually subsiding as the number of susceptible hosts diminishes, leading to the outbreak's conclusion.




