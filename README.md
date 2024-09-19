# comprehensive-calculator
import math
import numpy as np
import matplotlib.pyplot as plt

# Physics operations map (all lowercase keys)
physics_operations = {
    "force": "F = m * a",  # Newton's Second Law
    "kinetic_energy": "KE = 0.5 * m * v^2",  # Kinetic Energy
    "work": "W = F * d",  # Work
    "gravitational_force": "Fg = G * (m1 * m2) / r^2",  # Gravitational Force
    "ohms_law": "V = I * R",  # Ohm's Law
    "electric_potential": "V = k * q / r",  # Electric Potential
    "coulombs_law": "F = k * (q1 * q2) / r^2",  # Coulomb's Law
    "first_law_thermodynamics": "ΔU = Q - W",  # First Law of Thermodynamics
    "heat_capacity": "Q = mcΔT",  # Heat Capacity
    "second_law_thermodynamics": "S = Q / T",  # Second Law of Thermodynamics
    "schrodinger_equation": "iħ ∂ψ/∂t = Ĥψ",  # Schrödinger Equation
    "maxwells_equations": "∇⋅E = ρ/ε₀, ∇×E = -∂B/∂t",  # Maxwell's Equations
    "wave_equation": "∂²ψ/∂t² = c²∇²ψ",  # Wave Equation
    "einstein_field_equations": "Gμν + Λgμν = 8πGTμν",  # Einstein's Field Equations
    "boltzmann_entropy": "S = k_B ln(Ω)",  # Boltzmann Entropy
    "mirror_equation": "1/f = 1/do + 1/di"  # Mirror Equation
}

# Mathematical operations map
mathematical_operations = {
    "quadratic_equation": "ax² + bx + c = 0",  # Quadratic Equation
    "circle_area": "A = π * r²",  # Circle Area
    "circle_circumference": "C = 2 * π * r",  # Circle Circumference
    "rectangular_area": "A = l * w",  # Rectangle Area
    "rectangular_perimeter": "P = 2 * (l + w)",  # Rectangle Perimeter
    "slope_intercept": "y = mx + b",  # Slope-Intercept Form
    "linear_equation": "Ax + By = C"  # Linear Equation
}

# Plot heat capacity vs temperature
def plot_heat_capacity():
    m = float(input("Enter mass (m): "))
    c = float(input("Enter specific heat capacity (c): "))
    ΔT = np.linspace(0, 100, 100)  # Change in temperature from 0 to 100°C
    
    Q = m * c * ΔT
    
    plt.plot(ΔT, Q)
    plt.title("Heat Capacity vs Temperature")
    plt.xlabel("Change in Temperature (ΔT)")
    plt.ylabel("Heat (Q)")
    plt.grid(True)
    plt.show()

# Plot quadratic equation solutions
def plot_quadratic_equation():
    a = float(input("Enter coefficient a: "))
    b = float(input("Enter coefficient b: "))
    c = float(input("Enter coefficient c: "))
    
    x = np.linspace(-10, 10, 400)
    y = a * x**2 + b * x + c
    
    plt.plot(x, y)
    plt.title("Quadratic Equation: ax² + bx + c")
    plt.xlabel("x")
    plt.ylabel("y")
    plt.grid(True)
    plt.show()

# Plot wave equation solutions
def plot_wave_equation():
    x = np.linspace(0, 10, 1000)
    t = float(input("Enter time (t): "))
    c = float(input("Enter wave speed (c): "))
    wavelength = float(input("Enter wavelength (λ): "))
    
    # Wave equation: y(x,t) = A * sin(kx - ωt)
    k = 2 * np.pi / wavelength  # Wave number
    ω = k * c  # Angular frequency
    A = 1  # Amplitude
    
    y = A * np.sin(k * x - ω * t)
    
    plt.plot(x, y)
    plt.title("Wave Equation: y(x,t) = A * sin(kx - ωt)")
    plt.xlabel("x")
    plt.ylabel("y(x,t)")
    plt.grid(True)
    plt.show()

# Physics formulas calculator function
def physics_calculator():
    operation = input("Enter the physics operation: ").lower()
    
    if operation == "force":
        m = float(input("Enter mass (m): "))
        a = float(input("Enter acceleration (a): "))
        F = m * a
        print(f"Force (F) = {F} N")
    
    elif operation == "kinetic_energy":
        m = float(input("Enter mass (m): "))
        v = float(input("Enter velocity (v): "))
        KE = 0.5 * m * v**2
        print(f"Kinetic Energy (KE) = {KE} J")
    
    elif operation == "work":
        F = float(input("Enter force (F): "))
        d = float(input("Enter displacement (d): "))
        W = F * d
        print(f"Work (W) = {W} J")
    
    elif operation == "gravitational_force":
        G = 6.67430e-11  # Gravitational constant
        m1 = float(input("Enter mass of first object (m1): "))
        m2 = float(input("Enter mass of second object (m2): "))
        r = float(input("Enter distance between the objects (r): "))
        Fg = G * (m1 * m2) / r**2
        print(f"Gravitational Force (Fg) = {Fg} N")
    
    elif operation == "ohms_law":
        I = float(input("Enter current (I): "))
        R = float(input("Enter resistance (R): "))
        V = I * R
        print(f"Voltage (V) = {V} V")
    
    elif operation == "electric_potential":
        k = 8.99e9  # Coulomb's constant
        q = float(input("Enter charge (q): "))
        r = float(input("Enter distance (r): "))
        V = k * q / r
        print(f"Electric Potential (V) = {V} V")
    
    elif operation == "coulombs_law":
        k = 8.99e9  # Coulomb's constant
        q1 = float(input("Enter charge of first object (q1): "))
        q2 = float(input("Enter charge of second object (q2): "))
        r = float(input("Enter distance between the charges (r): "))
        F = k * (q1 * q2) / r**2
        print(f"Electrostatic Force (F) = {F} N")
    
    elif operation == "first_law_thermodynamics":
        Q = float(input("Enter heat added (Q): "))
        W = float(input("Enter work done (W): "))
        ΔU = Q - W
        print(f"Change in Internal Energy (ΔU) = {ΔU} J")
    
    elif operation == "heat_capacity":
        plot_heat_capacity()
    
    elif operation == "second_law_thermodynamics":
        Q = float(input("Enter heat (Q): "))
        T = float(input("Enter temperature (T): "))
        S = Q / T
        print(f"Entropy (S) = {S} J/K")
    
    elif operation == "schrodinger_equation":
        print("Solving Schrödinger's equation requires quantum mechanics knowledge and complex potentials.")
    
    elif operation == "maxwells_equations":
        print("Maxwell's Equations:")
        print("∇⋅E = ρ/ε₀")
        print("∇×E = -∂B/∂t")
        print("∇⋅B = 0")
        print("∇×B = μ₀(J + ε₀∂E/∂t)")
    
    elif operation == "wave_equation":
        plot_wave_equation()
    
    elif operation == "einstein_field_equations":
        print("Einstein's Field Equations: Gμν + Λgμν = 8πGTμν")
    
    elif operation == "boltzmann_entropy":
        Ω = float(input("Enter the number of microstates (Ω): "))
        k_B = 1.38e-23  # Boltzmann constant
        S = k_B * math.log(Ω)
        print(f"Boltzmann Entropy (S) = {S} J/K")
    
    elif operation == "mirror_equation":
        do = float(input("Enter object distance (do): "))
        di = float(input("Enter image distance (di): "))
        f = 1 / ((1 / do) + (1 / di))
        print(f"Focal Length (f) = {f} m")
    
    else:
        print("Invalid operation. Please try again.")

# Math calculator function
def math_calculator():
    operation = input("Enter the math operation: ").lower()
    
    if operation == "quadratic_equation":
        plot_quadratic_equation()
    
    elif operation == "circle_area":
        r = float(input("Enter the radius (r): "))
        A = math.pi * r**2
        print(f"Area of the circle (A) = {A}")
    
    elif operation == "circle_circumference":
        r = float(input("Enter the radius (r): "))
        C = 2 * math.pi * r
        print(f"Circumference of the circle (C) = {C}")
    
    elif operation == "rectangular_area":
        l = float(input("Enter the length (l): "))
        w = float(input("Enter the width (w): "))
        A = l * w
        print(f"Area of the rectangle (A) = {A}")
    
    elif operation == "rectangular_perimeter":
        l = float(input("Enter the length (l): "))
        w = float(input("Enter the width (w): "))
        P = 2 * (l + w)
        print(f"Perimeter of the rectangle (P) = {P}")
    
    elif operation == "slope_intercept":
        m = float(input("Enter the slope (m): "))
        b = float(input("Enter the y-intercept (b): "))
        print(f"The equation of the line is: y = {m}x + {b}")
    
    elif operation == "linear_equation":
        A = float(input("Enter coefficient A: "))
        B = float(input("Enter coefficient B: "))
        C = float(input("Enter constant C: "))
        print(f"The equation of the line is: {A}x + {B}y = {C}")
    
    else:
        print("Invalid operation. Please try again.")

# Main function for the calculator
def futurista_calculator():
    mode = input("Choose mode: 'basic', 'physics', or 'math': ").lower()
    
    if mode == 'basic':
        print("Basic calculator coming soon...")  # Basic operation function can be added here
    elif mode == 'physics':
        physics_calculator()
    elif mode == 'math':
        math_calculator()
    else:
        print("Invalid mode.")

# Run the calculator
futurista_calculator()

