seq_numbers = input('Введите числа через пробел: ')
us_number = input('Введите любое число: ')
error = "Введенные данные не верны"

def is_int(str):
    str = str.replace(' ', '')
    try:
        int(str)
        return True
    except ValueError:
        return False

if " " not in seq_numbers:
    print("ОШИБКА!!! (Введите числа, согласно условиям ввода)")
    seq_numbers = input('Введите числа через пробел: ')
if not is_int(seq_numbers):
    print("ОШИБКА!!! (Введите числа, согласно условиям ввода.)")
    us_number = input('Введите целое число: ')
    print(error)
if not is_int(us_number):
    print("ОШИБКА!!! (Введите число, согласно условиям ввода.)")
    print(error)
else:
    seq_numbers = seq_numbers.split()

list_seq_numbers = [int(item) for item in seq_numbers]
u_number = int(us_number)
def merge_sort(L):
    if len(L) < 2:
        return L[:]
    else:
        middle = len(L) // 2
        left = merge_sort(L[:middle])
        right = merge_sort(L[middle:])
        return merge(left, right)

def merge(left, right):
    result = []
    i, j = 0, 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    while i < len(left):
        result.append(left[i])
        i += 1

    while j < len(right):
        result.append(right[j])
        j += 1
    return result

list_seq_numbers = merge_sort(list_seq_numbers)

def binary_search(array, element, left, right):
    try:
        if left > right:
            return False
        middle = (right + left) // 2
        if array[middle] == element:
            return middle
        elif element < array[middle]:
            return binary_search(array, element, left, middle - 1)
        else:
            return binary_search(array, element, middle + 1, right)
    except IndexError:
        return 'Число выходит за границы списка, введите меньшее число.'

print(f'Список чисел по возрастанию: {list_seq_numbers}')

if not binary_search(list_seq_numbers, u_number, 0, len(list_seq_numbers)):
    rI = min(list_seq_numbers, key=lambda x: (abs(x - u_number), x))
    ind = list_seq_numbers.index(rI)
    max_ind = ind + 1
    min_ind = ind - 1
    if rI < u_number:
        print(f'''В списке нет введенного элемента 
Ближайший меньший элемент: {rI}, его индекс: {ind}
Ближайший больший элемент: {list_seq_numbers[max_ind]} его индекс: {max_ind}''')
    elif min_ind < 0:
        print(f'''В списке нет введенного элемента
Следующий больший элемент: {rI}, его индекс: {list_seq_numbers.index(rI)}
В списке нет меньшего элемента''')
    elif rI > u_number:
        print(f'''В списке нет введенного числа
Следующий больший элемент: {rI}, его индекс: {list_seq_numbers.index(rI)}
Следующий меньший элемент: {list_seq_numbers[min_ind]} его индекс: {min_ind}''')
    elif list_seq_numbers.index(rI) == 0:
        print(f'Индекс введенного элемента: {list_seq_numbers.index(rI)}')
else:
    print(f'Индекс введенного элемента: {binary_search(list_seq_numbers, u_number, 0, len(list_seq_numbers))}')


