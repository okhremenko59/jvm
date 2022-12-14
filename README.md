# JVM

public class JvmComprehension {          // в момент попытки запуска данного класса будет запущен ClassLoader который будет искать данный класс, если пройдет по всем 3 и не найдет его выкинет ошибку

    public static void main(String[] args) { // создается фрейм
        int i = 1;                      // 1 заносится в созданный фрейм main() значение int равный 1
        Object o = new Object();        // 2 в куче резервируется место под этот объект и в стек передается ссылка на него
        Integer ii = 2;                 // 3 в фрейм main() заносится заносится значение примитива
        printAll(o, i, ii);             // 4 в стеке создается новый фрейм для хранения своих ссылок
        System.out.println("finished"); // 7 в стеке создается новый фрейм для метода с сылкой на String
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5 в фрейм printAll() заносится значение примитива
        System.out.println(o.toString() + i + ii);  // 6 в стеке создается новый фрейм для метода с сылкой на объект о
    } 
}
