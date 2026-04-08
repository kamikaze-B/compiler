def get_number(prompt):
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Ошибка: введи число, а не что попало.")


def get_operation():
    while True:
        op = input("Выбери операцию (+, -, *, /): ")
        if op in ["+", "-", "*", "/"]:
            return op
        else:
            print("Ошибка: такой операции нет.")


def calculate(num1, num2, operation):
    if operation == "+":
        return num1 + num2
    elif operation == "-":
        return num1 - num2
    elif operation == "*":
        return num1 * num2
    elif operation == "/":
        if num2 == 0:
            return "Ошибка: деление на ноль!"
        return num1 / num2


def main():
    print("=== КАЛЬКУЛЯТОР ===")

    while True:
        num1 = get_number("Введи первое число: ")
        num2 = get_number("Введи второе число: ")
        operation = get_operation()

        result = calculate(num1, num2, operation)
        print("Результат:", result)

        again = input("Хочешь еще посчитать? (да/нет): ").lower()
        if again != "да":
            print("Пока!")
            break


if __name__ == "__main__":
    main()
