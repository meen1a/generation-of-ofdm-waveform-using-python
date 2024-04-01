import numpy as np
import matplotlib.pyplot as plt

# Parameters
num_symbols = 1000
mod_order = 16  # QAM modulation order

# Generate random QAM symbols
qam_symbols = (np.random.rand(num_symbols) - 0.5) + 1j * (np.random.rand(num_symbols) - 0.5)

# Plot the constellation diagram
plt.figure(figsize=(8, 8))

# Plot symbols
plt.scatter(np.real(qam_symbols), np.imag(qam_symbols), color='blue', marker='o', label='QAM Symbols')

# Plot reference constellation points
constellation = np.array([np.sqrt(2) * ((2*i - 1) + 1j * (2*j - 1)) for i in range(int(np.sqrt(mod_order))) for j in range(int(np.sqrt(mod_order)))])
plt.scatter(np.real(constellation), np.imag(constellation), color='red', marker='x', label='Reference Constellation')

plt.xlabel('In-Phase')
plt.ylabel('Quadrature')
plt.title('Constellation Diagram (QAM)')
plt.legend()
plt.grid(True)
plt.axis('equal')  # Equal aspect ratio
plt.tight_layout()
plt.show()
