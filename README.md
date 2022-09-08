# Projeto de spring boot seguindo o Spring Quickstart Guide
Realizado seguindo o passo-a-passo descrito em: https://spring.io/quickstart

- O primeiro passo foi criar um projeto web em: https://start.spring.io/
- O segundo passo foi adicionar um código de exemplo para imprimir um "Hello World" na tela, e caso receber uma string como parametro imprimir "Hello string". O arquivo editado foi o "DemoApplication.java" encontrado na pasta "src/main/java/com/example/demo". Ficando da seguinte forma:

package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
public class DemoApplication {

public static void main(String[] args) {
SpringApplication.run(DemoApplication.class, args);
}

@GetMapping("/hello")
public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
return String.format("Hello %s!", name);
}
}

- O terceiro e último passo foi a execução do projeto com o comando "./mvnw spring-boot:run", e com isso a aplicação é executada em um servidor web Apache Tomcat que já é embutido no spring boot. Dessa forma, acessando o endereço "http://localhost:8080/hello" nos é retornado "Hello World!", e caso seja adicionada uma string, como por exemplo "http://localhost:8080/hello?name=string", é impresso na tela "Hello string!"
- Esse projeto é uma aplicação muito simples, mas que já apresenta o básico da forma de utilização do spring boot nos projetos.
