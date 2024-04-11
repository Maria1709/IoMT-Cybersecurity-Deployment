# IoMT-Cybersecurity-Deployment
https://github.com/Maria1709/IoMT-Cybersecurity-Deployment.git
import tkinter as tk
import matplotlib.pyplot as plt
from matplotlib.figure import Figure
from matplotlib.backends.backend_tkagg import FigureCanvasTkAgg

# Survey data
categories = ['Admin', 'Paramedic', 'Cybersecurity', 'IT Support', 'Doctor', 'EMT', 'Nurse', 'Other']
counts = [3, 8, 4, 5, 3, 2, 3, 1]

# Total number of responses
total_responses = 33

# Calculate the proportion of responses for each category
proportions = [count / total_responses for count in counts]

# Define colors for each category
colors = ['blue', 'green', 'red', 'purple', 'orange', 'yellow', 'cyan', 'magenta']

def plot_bar_chart():
    # Create bar plot
    fig = Figure(figsize=(12, 6))  # Increase figure width
    ax = fig.add_subplot(111)
    ax.bar(categories, proportions, color=colors)  # Use proportions instead of counts
    
    # Adding labels and title
    ax.set_xlabel('Job Roles', fontsize=10)  # Reduce font size
    ax.set_ylabel('Proportion of Responses')
    ax.set_title('Survey Results')
    
    # Rotating x-axis labels for better readability
    plt.xticks(rotation=45, ha='right')  # Rotate labels
    
    # Adjust bottom margin to make space for x-axis labels
    fig.subplots_adjust(bottom=0.4)  # Increase bottom margin

    # Display the plot
    canvas = FigureCanvasTkAgg(fig, master=window)
    canvas.draw()
    canvas.get_tk_widget().pack()

# Create window
window = tk.Tk()
window.title("Survey Visualization")

# Button to plot the bar chart
plot_button = tk.Button(window, text="Plot Bar Chart", command=plot_bar_chart)
plot_button.pack()

# Run application
window.mainloop()