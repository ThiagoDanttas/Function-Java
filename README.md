# Function - Java

---

# Consumer - Java

---

[Documentação Function\<T, R>](https://docs.oracle.com/javase/10/docs/api/java/util/function/Function.html)


~~~~java
public interface Function<T, R> {
    R apply(T t);
}
~~~~

## Problema exemplo
Fazer um programa que, a partir de uma lista de produtos, gere uma
nova lista contendo os nomes dos produtos em caixa alta.

~~~~java
List<Product> list = new ArrayList<>();
    list.add(new Product("Tv", 900.00));
    list.add(new Product("Mouse", 50.00));
    list.add(new Product("Tablet", 350.50));
    list.add(new Product("HD Case", 80.90));
~~~~

## Nota sobre a função map
• A função "map" (não confunda com a estrutura de dados Map) é uma
função que aplica uma função a todos elementos de uma stream. <br>

• Conversões:<br>
    - List para stream: .stream()<br>
    - Stream para List: .collect(Collectors.toList())<br>

### Versões de implementação Predicate:

• Implementação da interface <br>

~~~~java
public class UpperCaseName implements Function<Product, String> {
    
    @Override
    public String apply (Product p) {
        return p.getName().toUpperCase();
    }
}
~~~~
• Reference method com método estático<br>
• Reference method com método não estático<br>
~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));
        
		List<String> names = list.stream().map(Product::StaticUpperCaseName).collect(Collectors.toList());
        names.forEach(System.ou::println);
	}
}
~~~~
• Expressão lambda declarada<br>

~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));

        Function<Product, String> func = p -> p.getName().toUpperCAse();
        List<String> names = list.stream().map(func).collect(Collectors.toList());
        names.forEach(System.ou::println);
        
	}
}
~~~~

• Expressão lambda inline

~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));
        
                double factor = 1.1; // Permite a utilização de variáveis

        List<String> names = list.stream().map(p -> p.getName().toUpperCAse()).collect(Collectors.toList());
        names.forEach(System.ou::println);
        
		}
	}
~~~~