def bisection_method(func, a, b, tolerance=1e-6, max_iterations=100):
    if func(a) * func(b) >= 0:
        print("The function values at the endpoints do not have opposite signs.")
        return None

    iteration = 0
    while iteration < max_iterations:
        c = (a + b) / 2

        if abs(func(c)) < tolerance:
            return c

        if func(c) * func(a) < 0:
            b = c
        else:
            a = c

        iteration += 1

    print("Maximum iterations reached without convergence.")
    return None

def sample_function(x):
    return x**3 - 2*x - 5

a = 2.0
b = 3.0

root = bisection_method(sample_function, a, b)

if root is not None:
    print(f"Approximate root: {root}")
else:
    print("Unable to find root within the specified tolerance.")
