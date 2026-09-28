# Diesel-generator-monitoring
# Diesel Generator Monitoring System

MIN_VOLTAGE = 200
MAX_VOLTAGE = 250
MIN_FREQUENCY = 49
MAX_FREQUENCY = 51
MAX_TEMPERATURE = 90
MIN_FUEL = 20
MAX_CURRENT = 100

print("==============================")
print("  DIESEL GENERATOR MONITORING")
print("==============================")

voltage = float(input("Enter generator voltage (V): "))
current = float(input("Enter generator current (A): "))
frequency = float(input("Enter frequency (Hz): "))
temperature = float(input("Enter engine temperature (°C): "))
fuel = float(input("Enter fuel level (%): "))

fault = False

print("\n--- Generator Parameters ---")
print("Voltage    :", voltage, "V")
print("Current    :", current, "A")
print("Frequency  :", frequency, "Hz")
print("Temperature:", temperature, "°C")
print("Fuel Level :", fuel, "%")

# Voltage check
if voltage < MIN_VOLTAGE:
    print("⚠️ Under-voltage detected")
    fault = True
elif voltage > MAX_VOLTAGE:
    print("⚠️ Over-voltage detected")
    fault = True

# Current check
if current > MAX_CURRENT:
    print("⚠️ Overcurrent detected")
    fault = True

# Frequency check
if frequency < MIN_FREQUENCY:
    print("⚠️ Under-frequency detected")
    fault = True
elif frequency > MAX_FREQUENCY:
    print("⚠️ Over-frequency detected")
    fault = True

# Temperature check
if temperature > MAX_TEMPERATURE:
    print("⚠️ Engine overheating detected")
    fault = True

# Fuel check
if fuel < MIN_FUEL:
    print("⚠️ LOW FUEL WARNING")

# Final status
if fault:
    print("\n🔴 GENERATOR ALERT")
    print("⚠️ Abnormal condition detected")
else:
    print("\n🟢 GENERATOR STATUS: NORMAL")
    print("✅ Generator operating normally")

print("\nMonitoring completed.")
