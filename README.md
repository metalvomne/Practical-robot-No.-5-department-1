# Створення словника працівників
employees = {
    "Іванов": "м. Київ, вул. Хрещатик, 10",
    "Петров": "м. Львів, вул. Зелена, 25",
    "Сидоров": "м. Харків, вул. Наукова, 7",
    "Кузін": "м. Дніпро, вул. Центральна, 15",
    "Кульков": "м. Одеса, вул. Французький бульвар, 3",
    "Кудін": "м. Чернігів, вул. Перемоги, 9",
    "Шевченко": "м. Київ, вул. Лесі Українки, 20",
    "Кубиків": "м. Полтава, вул. Київська, 14",
    "Куравльов": "м. Суми, вул. Соборна, 8",
    "Мельник": "м. Рівне, вул. Вишнева, 12"
}

# --- ФУНКЦІЇ ---

# 1. Вивести всі дані словника
def show_all(data):
    for name, address in data.items():
        print(f"{name} — {address}")

# 2. Додати нового працівника
def add_employee(data):
    name = input("Введіть прізвище працівника: ")
    address = input("Введіть адресу працівника: ")
    data[name] = address
    print("✓ Працівника додано!")

# 3. Видалити працівника
def delete_employee(data):
    name = input("Введіть прізвище працівника для видалення: ")
    try:
        del data[name]
        print("✓ Працівника видалено!")
    except KeyError:
        print("!!! Працівника з таким прізвищем не знайдено!")

# 4. Переглянути словник за відсортованими ключами
def show_sorted(data):
    for name in sorted(data.keys()):
        print(f"{name} — {data[name]}")

# 5. Знайти працівників за списком прізвищ
def find_special_employees(data):
    special_names = {"Кузін", "Куравльов", "Кудін", "Кульков", "Кубиків"}
    found = False
    for name in special_names:
        if name in data:
            print(f"{name} працює у фірмі. Адреса: {data[name]}")
            found = True
    if not found:
        print("Ніхто з указаних працівників не працює у фірмі.")

# --- ГОЛОВНЕ МЕНЮ ---
while True:
    print("\nМеню:")
    print("1 – Показати всіх працівників")
    print("2 – Додати працівника")
    print("3 – Видалити працівника")
    print("4 – Показати працівників за алфавітом")
    print("5 – Перевірити прізвища Кузін, Куравльов, Кудін, Кульков, Кубиків")
    print("0 – Вихід")

    choice = input("Оберіть пункт меню: ")

    if choice == "1":
        show_all(employees)
    elif choice == "2":
        add_employee(employees)
    elif choice == "3":
        delete_employee(employees)
    elif choice == "4":
        show_sorted(employees)
    elif choice == "5":
        find_special_employees(employees)
    elif choice == "0":
        print(" Завершення роботи програми.")
        break
    else:
        print("!!! Невірний вибір! Спробуйте ще раз.")
