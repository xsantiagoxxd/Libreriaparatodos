package libreria.para.todos;

import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

/**
 *
 * @author 000501913
 */
public class LibreriaParaTodos {


public class LibrosParaTodos {
    public static void main(String[] args) {
        // Definir una base de datos de libros usando un Map
        Map<String, Libro> baseDeDatos = new HashMap<>();
        baseDeDatos.put("Harry Potter y la piedra filosofal", new Libro("J.K. Rowling", "Fantasy", true));
        baseDeDatos.put("Cien años de soledad", new Libro("Gabriel García Márquez", "Magic realism", false));
        baseDeDatos.put("El código Da Vinci", new Libro("Dan Brown", "Mistery", true));
        
        // Solicitar al usuario el título del libro a buscar
        Scanner scanner = new Scanner(System.in);
        System.out.print("Name of the book: ");
        String titulo = scanner.nextLine();
        
        // Buscar el libro en la base de datos y mostrar su información
        Libro libroBuscado = baseDeDatos.get(titulo);
        if (libroBuscado != null) {
            System.out.println("Author: " + libroBuscado.getAutor());
            System.out.println("book genre: " + libroBuscado.getGenero());
            System.out.println("available: " + (libroBuscado.estaDisponible() ? "Yes" : "No"));
        } else {
            System.out.println("the book is not in the data base");
        }
    }
    
    // Definir una clase para representar un libro
    public static class Libro {
        private final String author;
        private String genre;
        private boolean disponible;

        public Libro(String autor, String genero, boolean disponible) {
            this.author = autor;
            this.genre = genero;
            this.disponible = disponible;
        }

        public String getAutor() {
            return author;
        }

        public String getGenero() {
            return genre;
        }

        public boolean estaDisponible() {
            return disponible;
        }
    }
}
}
    
    
