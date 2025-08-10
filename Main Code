#PROJECT-1


# Bhoomiga - Core Logic Developer
def convert_base(decimal, to_base):
    digits = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    result = ""
    while decimal > 0:
        result = digits[decimal % to_base] + result
        decimal //= to_base
    return result or "0"

# Jyotsna - Input validator and error checker
def is_valid_number(num_str, base):
    if base < 2 or base > 36:
        return False
    valid_chars = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"[:base]
    num_str = num_str.upper()
    for char in num_str:
        if char not in valid_chars:
            return False
    return True

# New helper function for history support
def single_conversion():
    num_str = input("Enter the number to convert: ")
    try:
        from_base = int(input("Enter the base of the number entered (between 2 and 36): "))
        to_base = int(input("Enter the base to convert to (between 2 and 36): "))
    except ValueError:
        print("Base must be an integer!")
        return None

    if from_base < 2 or from_base > 36 or to_base < 2 or to_base > 36:
        print("Base must be between 2 and 36!")
        return None

    if not is_valid_number(num_str, from_base):
        print("Invalid number for the given base!")
        return None

    decimal = int(num_str, from_base)
    result = convert_base(decimal, to_base)
    print(f"\nConverted Result: {result}")
    return f"{num_str} (base {from_base}) → {result} (base {to_base})"

# Shine - Feature enhancer and loop handler
def run_with_history():
    history = []
    while True:
        print("\n=== Base Converter CLI ===")
        choice = input("Enter 'c' to convert, 'h' to view history, or 'exit' to quit: ").strip().lower()

        if choice == 'exit':
            print("\nExiting... Goodbye!")
            break
        elif choice == 'h':
            if not history:
                print("No history yet.")
            else:
                print("\nConversion History:")
                for idx, entry in enumerate(history, start=1):
                    print(f"{idx}. {entry}")
        elif choice == 'c':
            record = single_conversion()
            if record:
                history.append(record)
        else:
            print("Invalid choice. Please enter 'c', 'h', or 'exit'.")

if __name__ == "__main__":
    run_with_history()
