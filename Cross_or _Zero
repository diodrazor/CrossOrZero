field = [['-' for i in range(4)] for j in range(4)]
field[0][0] = ' '
for i in range(3):
    field[1+i][0] = i
    field[0][1+i] = i

#функция, рисующая поле
def print_field():
    for i in range(4):
        print(*field[i], sep='\t')
    print()


# Далее функция определяющая есть ли победитель
def check_(game_check):
    # Проверим вертикали и горизонтали
    for j in range(1, 4):
        if any([(field[j].count('x') == 3), (field[j].count('o') == 3),
                ([field[i][j] for i in range(1, 4)].count('x') == 3),
                ([field[i][j] for i in range(1, 4)].count('o') == 3)]):
            game_check = False
            break
    # Проверим диагонали
    diag = any([([field[i][i] for i in range(1, 4)].count('x') == 3),
            ([field[i][i] for i in range(1, 4)].count('o') == 3),
            ([field[4 - i][i] for i in range(1, 4)].count('x') == 3),
            ([field[4 - i][i] for i in range(1, 4)].count('o') == 3)])
    if diag:
        game_check = False
    return game_check

cross_or_zero = 'x'

print_field()

game = True

while game:
    print(f'Ход {cross_or_zero}')
    a = int(input('Введите номер строки: '))
    print('---')
    b = int(input('Введите номер столбца: '))
    #Проверяем, что введеные числа удовлетворяют диапазону
    if (a < 0 or a > 2) or (b < 0 or b > 2):
        print()
        print('Вы вышли за пределы поля!')
        print()
    #Если удовлетворяют, то
    else:
        if field[a + 1][b + 1] == '-':
            field[a + 1][b + 1] = cross_or_zero
            print_field()
            if cross_or_zero == 'x':
                cross_or_zero = 'o'
            else:
                cross_or_zero = 'x'
        else:
            print()
            print(f'Нечестно! Здесь уже стоит {field[a + 1][b + 1]}')
            print()
#Проверим не заполнено ли поле
    for i in range(1, 4):
        game = False
        if '-' in field[i]:
            game = True
            break

#Проверим выиграл ли кто-нибудь
    game = check_(game)

game = True
game = check_(game)
#Проверяем было ли просто заполнено поле или кто-то выиграл
if game:
    print('Ничья!')
else:
    if cross_or_zero == 'x':
        cross_or_zero = 'o'
    else:
        cross_or_zero = 'x'
    print(f'Победа {cross_or_zero}!')
