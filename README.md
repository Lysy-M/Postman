# Postman
Test sprawdzający, czy odpowiedź ma kod statusu 200:

  "name": "Sprawdź kod statusu",
  "test": pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});



  "name": "Sprawdź nagłówek",
  "test": pm.test("Response has 'Content-Type' header", function () {
    pm.response.to.have.header('Content-Type');
});



  "name": "Sprawdź pole w ciele odpowiedzi",
  "test": pm.test("Field 'field_name' exists in JSON response", function () {
    pm.expect(pm.response.json().field_name).to.exist;
});
W powyższym teście zamień field_name na nazwę pola, które chcesz sprawdzić.


Test sprawdzający, czy odpowiedź zawiera oczekiwane wartości dla określonego pola:
  "name": "Sprawdź wartości pola",
  "test": pm.test("Value of 'field_name' matches expected value", function () {
    var expectedValue = "expected_value_here"; // Zastąp 'expected_value_here' rzeczywistą oczekiwaną wartością
    pm.expect(pm.response.json().field_name).to.eql(expectedValue);
});
W powyższym teście zamień field_name na nazwę pola, a expected_value na oczekiwaną wartość.'expected_value_here' rzeczywistą oczekiwaną wartością, którą chcesz porównać z wartością pola field_name

Test sprawdzający, czy odpowiedź zawiera określoną liczbę elementów w tablicy:

  "name": "Sprawdź liczbę elementów w tablicy",
  "test": pm.test("Check the number of elements in the array", function () {
    var expectedLength = expected_length_here; // Zastąp 'expected_length_here' rzeczywistą oczekiwaną długością
    pm.expect(pm.response.json().array_field).to.have.length(expectedLength);
});

W powyższym teście zamień array_field na nazwę pola zawierającego tablicę, a expected_length na oczekiwaną długość tablicy.

Najczęściej używane testy w języku JSON, w Postmanie:

Sprawdź kod statusu odpowiedzi:


  "name": "Sprawdź kod statusu",
  "test": pm.test("Check status code", function () {
    pm.response.to.have.status(200);
});

Ten test sprawdza, czy odpowiedź ma oczekiwany kod statusu (w tym przypadku 200). Możesz zmienić wartość na dowolną inną, np. 201, 400 itp.

Sprawdź, czy odpowiedź zawiera oczekiwany tekst:
  "name": "Sprawdź tekst w odpowiedzi",
  "test": pm.test("Check text in response", function () {
    pm.expect(pm.response.text()).to.include('expected_text');
});
Ten test sprawdza, czy odpowiedź zawiera określony tekst (w tym przypadku 'oczekiwany_tekst'). Możesz zmienić wartość na dowolny inny tekst.

Sprawdź, czy odpowiedź zawiera oczekiwane pole w ciele odpowiedzi:

  "name": "Sprawdź pole w ciele odpowiedzi",
  "test": pm.test("Check field in response body", function () {
    pm.expect(pm.response.json().field_name).to.exist;
});
Ten test sprawdza, czy odpowiedź zawiera określone pole w ciele odpowiedzi. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane wartości dla określonego pola:

  "name": "Sprawdź wartości pola",
  "test": pm.test("Check field value", function () {
    pm.expect(pm.response.json().field_name).to.eql(expected_value);
});
będzie porównywał wartość pola "field_name" w odpowiedzi JSON z oczekiwaną wartością "expected_value".
Ten test sprawdza, czy odpowiedź zawiera oczekiwane wartości dla określonego pola. Zamień field_name na nazwę pola, a expected_value na oczekiwaną wartość.

Sprawdź liczbę elementów w tablicy w odpowiedzi:

  "name": "Sprawdź liczbę elementów w tablicy",
  "test": pm.test("Check array length", function () {
    pm.expect(pm.response.json().array_field).to.have.length(expected_length);
});
Ten skrypt będzie sprawdzał, czy długość tablicy "array_field" w odpowiedzi JSON jest równa oczekiwanej długości "expected_length".
Sprawdza, czy odpowiedź zawiera określoną liczbę elementów w tablicy. Zamień array_field na nazwę pola zawierającego tablicę, a expected_length na oczekiwaną długość tablicy.


Sprawdź, czy odpowiedź zawiera oczekiwane pole typu string:

  "name": "Sprawdź pole typu string",
  "test": pm.test("Check string field type", function () {
    pm.expect(pm.response.json().field_name).to.be.a('string');
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które jest typu string. Zamień field_name na nazwę pola, które chcesz sprawdzić.


Sprawdź, czy odpowiedź zawiera oczekiwane pole o niepustej wartości:
  "name": "Sprawdź pole niepustej wartości",
  "test": "pm.expect(pm.response.json().field_name).to.not.be.empty;"
});

Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które nie jest puste. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o określonej długości:

  "name": "Sprawdź pole długości",
  "test": pm.test("Check field length", function () {
    pm.expect(pm.response.json().field_name).to.have.length(expected_length);
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma oczekiwaną długość. Zamień field_name na nazwę pola, a expected_length na oczekiwaną długość.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o wartości false:

  "name": "Sprawdź pole wartości false",
  "test": pm.test("Check field for false value", function () {
    pm.expect(pm.response.json().field_name).to.be.false;
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma wartość false. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o wartości większej od określonej liczby:

  "name": "Sprawdź pole wartości większej",
  "test": pm.test("Check field for greater value", function () {
    pm.expect(pm.response.json().field_name).to.be.above(expected_value);
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma wartość większą od określonej liczby. Zamień field_name na nazwę pola, a expected_value na oczekiwaną liczbę.


Sprawdź, czy odpowiedź zawiera oczekiwane pole typu liczbowego:

  "name": "Sprawdź pole typu liczbowego",
  "test": pm.test("Check field for number type", function () {
    pm.expect(pm.response.json().field_name).to.be.a('number');
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które jest typu liczbowego. Możesz zmienić field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole typu tablicy:

  "name": "Sprawdź pole typu tablicy",
  "test": pm.test("Check field for array type", function () {
    pm.expect(pm.response.json().field_name).to.be.an('array');
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które jest typu tablicy. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole typu obiektowego:

  "name": "Sprawdź pole typu obiektowego",
  "test": pm.test("Check field for object type", function () {
    pm.expect(pm.response.json().field_name).to.be.an('object');
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które jest typu obiektowego. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o określonej wartości null:


  "name": "Sprawdź pole wartości null",
  "test": pm.test("Check field for null value", function () {
    pm.expect(pm.response.json().field_name).to.be.null;
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma wartość null. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o wartości true:

  "name": "Sprawdź pole wartości true",
  "test": pm.test("Check field for true value", function () {
    pm.expect(pm.response.json().field_name).to.be.true;
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma wartość true. Zamień field_name na nazwę pola, które chcesz sprawdzić.



Sprawdź, czy odpowiedź zawiera oczekiwane pole o wartości mniejszej od określonej liczby:


  "name": "Sprawdź pole wartości mniejszej",
  "test": pm.test("Check field for value below expected", function () {
    pm.expect(pm.response.json().field_name).to.be.below(expected_value);
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma wartość mniejszą od określonej liczby. Zamień field_name na nazwę pola, a expected_value na oczekiwaną liczbę.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o wartości zawierającej określony tekst:


  "name": "Sprawdź pole zawartości tekstowej",
  "test": pm.test("Check field for text content", function () {
    pm.expect(pm.response.json().field_name).to.include('expected_text');
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które zawiera określony tekst (expected_text). Zamień field_name na nazwę pola, a expected_text na oczekiwany tekst.

Sprawdź, czy odpowiedź zawiera oczekiwane pole spełniające określone kryterium:


  "name": "Sprawdź pole spełniające kryterium",
  "test": pm.test("Check field that meets criteria", function () {
    pm.expect(pm.response.json().field_name).to.satisfy(function(value) { return value > 10; });
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które spełnia określone kryterium (w tym przypadku, wartość większa niż 10). Zamień field_name na nazwę pola, a value > 10 na odpowiednie kryterium.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o wartości będącej poprawnym adresem URL:


  "name": "Sprawdź pole adresu URL",
  "test": pm.test("Check URL field", function () {
    pm.expect(pm.response.json().field_name).to.match(/^https?:\/\//);
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które jest poprawnym adresem URL. Zamień field_name na nazwę pola, które chcesz sprawdzić.

Sprawdź, czy odpowiedź zawiera oczekiwane pole o określonej dacie:


  "name": "Sprawdź pole daty",
  "test": pm.test("Check date field", function () {
    pm.expect(pm.response.json().field_name).to.equal('2023-07-01');
});
Ten test sprawdza, czy odpowiedź zawiera pole o nazwie field_name, które ma wartość odpowiadającą określonej dacie (w tym przypadku '2023-07-01'). Zamień field_name na nazwę pola, a '2023-07-01' na oczekiwaną datę.
