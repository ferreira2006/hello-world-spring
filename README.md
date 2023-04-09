# hello-world-spring
Quebrando o gelo com o Spring

Como gerar uma aplicação web com spring initializr 
Acesse start.spring.io
Configure conforme a imagem abaixo.
Obs: Não esqueça de adiconar a dependência Spring Web.

![spring initializr](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi6ePZn33R9b_rwJ7n-_KfXpUjQqa4x21bpzABbv5QXH3v5TiH5BlW1hwNbCWlPRImCabxDnHi8io4rJW1Wv8KgeOPcLZhJTENzULfYOmNVQFpwS2-ph6MobiSHgWDd5PuPHOUAb498E0eb0VMIBEmEXvldBgZt7L4_lUJQXpyWPEH3oAwM5OlGDLoH9g/s320/helloWord.PNG)

Clique em GENERATE [Ctrl + Enter]

Descompacte o arquivo helloWord.zip e importe para sua IDE do coração (a minha é eclipse). 

![desconpactar zip](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj9jmFR4vqTfqKLT5VkGQooKe1NnL_dA87OGZb0EzmvnBHYdJR9AKnBayvLAhKYGB69QzM0ayDOFGEC0rC-v8ikDIyaBngDLYjGAne0KIP-OxROEuhheRZg6y92a9ud6xPUjsfCqgiCsgkshF3pkxCnevLGsWvfjDpZaokG3IsE0moFDCzsnfAIrq_8iw/s1600/helloWord2.PNG)

Aguarde o Maven atualizar as dependências e rode a classe HelloWorldApplication.java como um aplicação JAVA

A saída no console deve ser semelhante a exibida na figura abaixo:

![Saída no console](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjED6SxQrbRXil9XmCPRFexxSQo1JVNUHWrV4H4_SpuBEzygJX9NIvoWGWPJlm5T2DVL4GLPdg8_XYmeFnQkjERTwLvyVR12hCZpghHlkJyJv9SSHFToOxrp1Wawu4sNv20wHqhRxJv91f_jX9xjsOvi86RROcSIUyKWtrqm-iJOW8Wwk7W32w1RkvGsg/s320/helloWord2.5.PNG)

Acesse no navegador o endereço da sua aplicação: http://localhost:8080/hello

![Erro que deu certo](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhO-pro3R_sE8QAA6FoKI_H1fGxc9XeysqqocSUBMwXVZQFXl81cBpu0jZlcwGQqVIaz_LZy7QONfbmCknHCYUs3yIPQms5EL2qTnwU9qkbmHnMyZnTFzLn5vjB91OXyDzIgfBjfQTAoNZmhOmIEOn5u9DQXEKuGwBzWUL8vC9BdDqsyWDy2XDP9PmadQ/s320/helloWord3.PNG)

Apesar do erro, sua aplicação SPRING está funcionando.
Obs: o erro é sobre não existir uma página de erro. :)


Altere a classe HelloWorldApplication.java conforme figura abaixo:

```java
package com.estudos.helloWorld;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
public class HelloWorldApplication {
    public static void main(String[] args) {
      SpringApplication.run(HelloWorldApplication.class, args);
    }
    
    @GetMapping("/hello")
    public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
      return String.format("Hello %s!", name);
    }
}
```


Rode a aplicação novamente e verifique no navegador:

![Hello sucesso](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEimMGCC7RMEq0q1oC4JM2N2pi3HNQVGqW-22UT1Z2Kw4bGJ0UrPqmeoeHOiKzthUjnUwGTn_F53WylJGg07Gc6OpkOCD97seSVCxCQHxcli9eSUvPApw1XOEqFccQGvL4WANw2Q_iiyy5Qsj75j6dxce4T8WrdwRt8bjIHmABT2eqA4KEUzU2_qP61YoQ/s320/helloWord4.PNG)

Você pode inclusive passar parâmetros, experimente acessar no navegador:

```
http://localhost:8080/hello?name=Fulano
```
