import matplotlib.pyplot as plt

# Define perceptual map axes ranges
plt.figure(figsize=(8,6))
plt.xlim(0, 10)  # Price/Prestige (Low to High)
plt.ylim(0, 10)  # Tech/EV Leadership (Low to High)

# Draw grid and labels
plt.grid(True, linestyle='--', alpha=0.5)
plt.xlabel('Price / Prestige →')
plt.ylabel('Technology / EV Leadership ↑')
plt.title('Perceptual Map: BEV Market Positioning')

# Plot data points
brands = {
    'Toyota BEVs': (4, 8),   # Less costly but high tech (left of Tesla)
    'Tesla': (7, 9),         # Higher price and top tech leadership
    'Luxury EV Brand X': (9, 8),  # Hypothetical ultra-luxury competitor
    'Mass Market EV Y': (3, 5),   # Lower tech, lower price
}

# Plot each brand with label
for brand, (x, y) in brands.items():
    plt.scatter(x, y, s=150)
    plt.text(x+0.1, y, brand, fontsize=12, verticalalignment='center')

# Add annotations or boxes to explain segments if desired
plt.annotate('Premium Mainstream', xy=(4, 7), xytext=(2, 6),
             arrowprops=dict(facecolor='gray', shrink=0.05), fontsize=10, color='gray')

plt.show()

