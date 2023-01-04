try:
    import pyperclip
except ImportError:
    pass

symbols = 'ABCDEFGHIJKLMNOPRSTUVWXYZ'
print('Szyfr Cezara szyfruje litery przez przesunięcie ich o liczbę,')
print('która jest kluczem. Na przykład klucz 2 oznacza,')
print('że litera A jest zmieniona na C, litera B na D i tak dalej.')
print()

while True:
    print('Czy chcesz zaszyfrować - Z cz odszyfrować - O ?')
    response = input('> ').lower()
    if response.startswith('z'):
        mode = 'zaszyfrowania'
        break
    elif response.startswith('o'):
        mode = 'odszyfrowania'
        break
    print('proszę podać literę Z lub O')

while True:
    maxKey = len(symbols) - 1
    print('Proszę podać klucz od (0 do {}).'.format(maxKey))
    response = input('> ').upper()
    if not response.isdecimal():
        continue
    if 0 <= int(response) < len(symbols):
        key = int(response)
        break

print('Wpisz wiadomość do {}.'.format(mode))
message = input('> ')

message = message.upper()

translated = ''

for symbol in message:
    if symbol in symbols:
        num = symbols.find(symbol)
        if mode == 'zaszyfrowania':
            num = num + key
        elif mode == 'odszyfrowania':
            num = num - key

        if num >= len(symbols):
            num = num - len(symbols)
        elif num < 0:
            num = num + len(symbols)

        translated = translated + symbols[num]
    else:
        translated = translated + symbol

print(translated)

try:
    pyperclip.copy(translated)
    print('Tekst przekazany do {} został skopiowany do schowka.'.format(mode))
except:
    pass
