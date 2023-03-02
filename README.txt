# Python_Unittest
Primeiros passos com testes unitarios
Testes unitarios : Python + Unittest
Para realizar esse projeto é necessário ter instalado o python3

O framework que iremos ussar para os testes é o unittest,foi originalmente inspirado no JUnit e tem um sabor semelhante contendo as principais estruturas de teste de unidades existentes em outras linguagens.
Por que ussar unittest?
Existem várias estruturas de teste de unidade disponíveis para python, mas ‘unittest’ estão integradas na distribuição do python e não precisamos fazer nada ‘pip install’ para usá-lo.

Isso não quer dizer que seja melhor que outros frameworks disponíveis como ‘pytest’, você deve avaliar os frameworks de teste disponíveis e escolher o mais adequado para seus projetos

Criando as funções que seram testadas
# funçao de adição
def add(n1, n2):
    return n1 + n2

# função de subtração
def sub(n1, n2):
    return n1 - n2

# função de multiplicação
def mult(n1, n2):
    return n1 * n2

# função de divisão
def div (n1,n2):
    return n1 / n2

2. Crianção dos testes

import unittest
from main import add,sub,mult,div

class mainTest(unittest.TestCase):

    # test do metodo de adição
    def test_add(self):
        self.assertEqual(add(10,10),20)

    # test do metodo de subitração
    def test_sub(self):
        self.assertEqual(sub(10,5),5)

    #test do metodo de multiplicação
    def test_mult(self):
        self.assertEqual(mult(10,2),20)

    # test do metodp de divisão
    def test_div(self):
        self.assertEqual(div(10,2),5)

    # test ussando 2 metodos (add,div) para gerar uma media esperada
    def test_media_add_div(self):
        self.assertEqual(div(add(10,4),2),7)


if __name__ == '__main__':
    unittest.main()
    
Para usar o unittest, só precisamos escrever a seguinte declaração na primeira linha ‘import unitt’

As funções de teste devem ser feitas dentro de uma classe derivada de ‘unittest.TestCase’

esses são os metodos de afirmação (assert) que podemos chamar dentro do teste de unidade com Python:

assertEqual()- Testa se os dois argumentos são iguais em valor.
assertNotEqual()- Testa se os dois argumentos são desiguais em valor.
assertTrue()- Testa se o argumento tem um valor booleano de True.
assertFalse()- Testa se o argumento tem um valor booleano de False.
assertIs()- Testa se os argumentos avaliam o mesmo objeto.
assertIsNot()- Testa se os argumentos não avaliam o mesmo objeto.
assertIsNone()- Testa se o argumento é avaliado como nenhum.
assertIsNotNone()- Testa se o argumento não é avaliado como nenhum.
assertIn()- Testa se o primeiro argumento está no segundo.
assertNotIn()- Testa se o primeiro argumento não está no segundo.
assertIsInstance()- Testa se o primeiro argumento (objeto) é uma instância do segundo (classe).
assertRaises()- Testa se o Python gera uma exceção quando chamamos o callable com argumentos posicionais/palavras-chave que também passamos para esse método.
3 . Execução dos testes

Ran 5 tests in 0.007s

OK

Process finished with exit code 0
No que diz respeito à execução dos casos de teste, cada função de teste é tratada como um caso de teste independente, o que significa que podemos muito bem escrever todos os casos de teste em uma única classe e isso não afetará a saída.
