import numpy as np   # Importing NumPy for numerical operations
import matplotlib.pyplot as plt  # Importing Matplotlib for plotting

# Define the demand and supply functions
def demand(P, a, b):
    return a - b * P

def supply(P, c, d):
    return c + d * P

# Parameters for the demand and supply functions
a = 100  # Demand intercept
b = 2    # Demand slope
c = 20   # Supply intercept
d = 1    # Supply slope

# Calculate the equilibrium price and quantity
P_eq = (a - c) / (b + d)
Q_eq = demand(P_eq, a, b)  # or supply(P_eq, c, d)

# Generate a range of prices for plotting
P = np.linspace(0, 60, 400)  # Price range from 0 to 60 with 400 points
Q_d = demand(P, a, b)  # Calculate quantity demanded for each price
Q_s = supply(P, c, d)  # Calculate quantity supplied for each price

# Plot the demand and supply curves
plt.figure(figsize=(10, 6))  # Create a new figure with specified size
plt.plot(P, Q_d, label='Demand', color='blue')  # Plot demand curve
plt.plot(P, Q_s, label='Supply', color='orange')  # Plot supply curve
plt.scatter(P_eq, Q_eq, color='red', zorder=5)  # Plot the equilibrium point
plt.text(P_eq, Q_eq, f'Equilibrium\nP={P_eq:.2f}, Q={Q_eq:.2f}', horizontalalignment='right')  # Annotate the equilibrium point
plt.xlabel('Price')  # Label x-axis
plt.ylabel('Quantity')  # Label y-axis
plt.title('Demand and Supply Analysis')  # Add a title
plt.legend()  # Add a legend
plt.grid(True)  # Add a grid
plt.show()  # Display the plot
