# GITAM-0287
Software Engineering Lab

TASK 1: USING HARDCODING VARIABLES CODE:
import matplotlib.pyplot as plt
def quadratic_weather_model(time, humidity, pressure, wind_speed):
temperature = humidity * (time ** 2) + pressure * time + wind_speed
return temperature
def main():
humidity = 0.8
pressure = -2
wind_speed = 25
time_values = list(range(0, 11))
temperature_values = [quadratic_weather_model(t, humidity, pressure, wind_speed)
for t in time_values]
plt.figure(figsize=(8, 6))
plt.plot(time_values, temperature_values, marker='o', linestyle='-')
plt.title('Temperature Variation Over Time')
plt.xlabel('Time')
plt.ylabel('Temperature')
plt.grid(True)
plt.xlim(0, 10)
plt.ylim(min(temperature_values) - 5, max(temperature_values) + 5)
plt.show()
if _name_ == "_main_":
main()

TASK 2: USING KEYBOARD INPUT CODE
import matplotlib.pyplot as plt
def quadratic_weather_model(time, humidity, pressure,
wind_speed):
temperature = humidity * (time ** 2) + pressure * time +
wind_speed
return temperature
def main():
humidity = float(input("Enter the value of humidity: "))
pressure = float(input("Enter the value of pressure: "))
wind_speed = float(input("Enter the value of wind_speed: "))
time_values = list(range(0, 11))
temperature_values = [quadratic_weather_model(t, humidity,
pressure, wind_speed) for t in time_values]
plt.figure(figsize=(8, 6))
plt.plot(time_values, temperature_values, marker='o',
linestyle='-')
plt.title('Temperature Variation Over Time')
plt.xlabel('Time')
plt.ylabel('Temperature')
plt.grid(True)
plt.xlim(0, 10)
plt.ylim(min(temperature_values) - 5, max(temperature_values)
+ 5)
plt.show()
if _name_ == "_main_":
main()

TASK 3: FILE INPUT CODE:
import matplotlib.pyplot as plt
def quadratic_weather_model(time, humidity, pressure, wind_speed):
temperature = humidity * (time ** 2) + pressure * time + wind_speed
return temperature
def main():
try:
with open('File.txt', 'r') as file:
lines = file.readlines()
time_values = list(range(0, 11))
plt.figure(figsize=(8, 6))
for line in lines:
coefficients = line.split()[:3] # Take only the first three values
humidity, pressure, wind_speed = map(float, coefficients)
temperature_values = [quadratic_weather_model(t, humidity, pressure,
wind_speed) for t in time_values]
plt.plot(time_values, temperature_values,
marker='o', linestyle='-', label=f'humidity={humidity},
pressure={pressure}, wind_speed={wind_speed}')
plt.title('Temperature Variation Over Time')
plt.xlabel('Time')
plt.ylabel('Temperature')
plt.grid(True)
plt.xlim(0, 10)
plt.legend()
plt.show()
except FileNotFoundError:
print("File not found. Please make sure 'File.txt'
exists.")
if _name_ == "_main_":
main()

TASK 4: USING MULTIPLE SET OF VARIABLES
import matplotlib.pyplot as plt
def quadratic_weather_model(time, humidity, pressure, wind_speed):
temperature = humidity * (time ** 2) + pressure * time + wind_speed
return temperature
def main():
try:
with open('File.txt', 'r') as file:
lines = file.readlines()
time_values = list(range(0, 11))
plt.figure(figsize=(8, 6))
for line in lines:
coefficients = line.split()[:3] # Take only the first three values
humidity, pressure, wind_speed = map(float, coefficients)
temperature_values = [quadratic_weather_model(t, humidity,
pressure,wind_speed) for t in time_values]
plt.plot(time_values, temperature_values, marker='o', linestyle='-',
label=f'humidity={humidity}, pressure={pressure},wind_speed={wind_speed}')
plt.title('Temperature Variation Over Time')
plt.xlabel('Time')
plt.ylabel('Temperature')
plt.grid(True)
plt.xlim(0, 10)
plt.legend()
plt.show()
except FileNotFoundError:
print("File not found. Please make sure 'File.txt' exists.")
if _name_ == "_main_":
main()

TASK 5: CODE
import matplotlib.pyplot as plt
import numpy as np
humidity = int(input("Enter the value of humidity: "))
pressure = int(input("Enter the value of pressure: "))
wind_speed = int(input("Enter the value of wind_speed: "))
x = np.linspace(-10, 10, 400)
y1 = humidity * x**2 + pressure * x + wind_speed
plt.plot(x, y1, label=f'UserInput: {humidity}x^2 + {pressure}x + {wind_speed}')
humidity = 1
pressure = -3
wind_speed = 2
y2 = humidity * x**2 + pressure * x + wind_speed
plt.plot(x, y2, label=f'HardCoded: {humidity}x^2 + {pressure}x + {wind_speed}')
plt.title('Plot of the quadratic functions')
plt.xlabel('x')
plt.ylabel('y')
plt.legend()
plt.grid(True)
plt.show()
