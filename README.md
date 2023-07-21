def convert_units(value, input_unit, output_unit):
    conversion_factors = {
        'meters': 1.0,
        'feet': 3.28084,
        'inches': 39.3701,
        # Add more units and their conversion factors as needed.
    }

    if input_unit not in conversion_factors or output_unit not in conversion_factors:
        raise ValueError("Invalid units.")
    return value * (conversion_factors[output_unit] / conversion_factors[input_unit])


def main():
    print("Welcome to the Unit Converter!")
    
    while True:
        try:
            value = float(input("Enter the value to convert: "))
            input_unit = input("Enter the input unit: ").lower()
            output_unit = input("Enter the output unit: ").lower()

            result = convert_units(value, input_unit, output_unit)
            print(f"{value} {input_unit} is equal to {result} {output_unit}")
        except ValueError as e:
            print("Error:", e)

        choice = input("Do you want to convert another value? (yes/no): ").lower()
        if choice != 'yes':
            break

    print("Thank you for using the Unit Converter!")

if __name__ == "__main__":
    main()
