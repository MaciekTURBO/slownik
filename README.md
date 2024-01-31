ksiazka1 = {
    'nazwa': 'Chłopcy z placu broni',
    'ilość stron': '240',
    'autor': 'Ferenca Molnara',
    'id': uuid.uuid4()
}

ksiazka2 = {
    'nazwa': 'Pan Tadeusz',
    'ilość stron': '360',
    'autor': 'Adam Mickiewicz',
    'id': uuid.uuid4()
}
ksiazka3 = {
    'nazwa': 'Sigma book',
    'ilość stron': '234',
    'autor': 'Sigma Male',
    'id': uuid.uuid4()
}
biblioteka = [ksiazka1,ksiazka2,ksiazka3]

def informacje(lista:list)->None:
    for slownik in lista:
        for k,v in slownik.items():
            print(f"{k}:   {v}")
        print("==="*20)

def dodaj_ksiazke(lista):
    x = input("podaj tytuł")
    y = input("podaj liczbe stron")
    z = input("podaj autora")
    ksiazka = {
        'nazwa': x,
        'ilość stron': y,
        'autor': z,
        'id': uuid.uuid4()
    }
    lista.append(ksiazka)

def istnieje(lst: list, id: str):
    for i in range(len(lst)):
        if str(lst[i]["id"]) == id:
            return True
    return False

def index(lista: list, id: str):
    for i in range(len(lista)):
        if str(lista[i]["id"]) == id:
            return i
    return -1  

def usun(lista: list) -> None:
    inp = input("Podaj id książki: ")
    if istnieje(lista, inp):
        index = index(lista, inp)
        if index != -1:
            lista.pop(index)
            print("Ksiażka usunięta")
        else:
            print("Nie ma takiej książki")
    else:
        print("Nie ma takiej książki")

def edytowanie(lista:list):
    x = input("Którą książkę chcesz edytować?(podaj id)")
    if istnieje(lista, x):
        idd = index(lista, x)
        z = input("Co chcesz edytować?")
        lista[idd][z] = input("wprwadź dane ")
        print(lista[idd][z])

while True:
    print("i - informacje")
    print("e - edytuj dane")
    print("d - dodaj ksiazke")
    print("u - usun ksiazke")
    dzialanie = input()
    if "i" == dzialanie:
        informacje(biblioteka)
    elif "e" == dzialanie:
        edytowanie(biblioteka)
    elif "u" == dzialanie:
        usun(biblioteka)
    elif "d" == dzialanie:                                     






