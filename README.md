# Програма для введення розділів, перевірки даних, видалення дублікатів і сортування

# запит кількості розділів
while True:
    sections_count = input("Введіть кількість розділів (1-20): ")

    if sections_count.isdigit():  # перевірка, що число ціле
        sections_count = int(sections_count)
        if 1 <= sections_count <= 20:
            break
        else:
            print("Помилка: введіть число від 1 до 20.")
    else:
        print("Помилка: введено дробове або нечислове значення.")

# вибір методу сортування
print("\nМетоди сортування:")
print("1 - сортування за зростанням (A → Z)")
print("2 - сортування за спаданням (Z → A)")
print("3 - без сортування")

while True:
    sort_method = input("Оберіть метод сортування (1/2/3): ")

    if sort_method in ["1", "2", "3"]:
        break
    else:
        print("Помилка: введіть 1, 2 або 3.")

# введення назв розділів
sections = []
for i in range(sections_count):
    name = input(f"Введіть назву розділу {i+1}: ")
    sections.append(name.strip())

# видалення дублікатів
sections = list(set(sections))

# сортування за вибором
if sort_method == "1":
    sections.sort()
elif sort_method == "2":
    sections.sort(reverse=True)

# вивід результату
print("\n--- Результат ---")
for i, name in enumerate(sections, 1):
    print(f"{i}. {name}")
