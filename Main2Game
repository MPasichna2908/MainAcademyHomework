package com.game;

import jline.console.ConsoleReader;
import jline.console.KeyMap;

import java.io.IOException;

public class Main2 {
    public static int x, y;
    public static int a, b = (int) (Math.random() * 9) + (1);

    public static void main(String[] args) throws IOException {
        ConsoleReader reader = new ConsoleReader();
        char[][] array = new char[10][10];
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                array[i][j] = ' ';
            }
        }
        printArray(array, reader);
        while (true) {
            KeyMap map = new KeyMap("");
            map.bind("\u001B[A", "Up");
            map.bind("\u001B[B", "Down");
            map.bind("\u001B[C", "Right");
            map.bind("\u001B[D", "Left");

            Object action = reader.readBinding(map);
            reader.clearScreen();
            reader.flush();

            //  printMonster(array);

            if (action.equals("Up")) {
                up(array);
                printMonster(array);
            }
            if (action.equals("Down")) {
                down(array);
                printMonster(array);
            }
            if (action.equals("Right")) {
                right(array);
                printMonster(array);
            }
            if (action.equals("Left")) {
                left(array);
                printMonster(array);
            }
            printArray(array, reader);
        }
    }

    public static void printArray(char[][] array, ConsoleReader reader) throws IOException {
        String str = "";
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                if (i == 0 & j == 0) str += " ----------\n|";
                str += array[i][j];
            }
            if (i == array.length - 1) {
                str += "|\n";
                str += " ----------";
            } else
                str += "|\n|";
        }
        reader.print(str);
        reader.flush();
    }

    public static char[][] right(char[][] arr) {
        arr[y][x] = ' ';
        if (x < arr[0].length - 1) {
            x++;
        }
        arr[y][x] = 'X';
        return arr;
    }

    public static char[][] left(char[][] arr) {
        arr[y][x] = ' ';
        if (x > 0) {
            x--;
        }
        arr[y][x] = 'X';
        return arr;
    }

    public static char[][] up(char[][] arr) {
        arr[y][x] = ' ';
        if (y > 0) {
            y--;
        }
        arr[y][x] = 'X';
        return arr;
    }

    public static char[][] down(char[][] arr) {
        arr[y][x] = ' ';
        if (y < arr.length - 1) {
            y++;
        }
        arr[y][x] = 'X';
        return arr;
    }

    public static char[][] printMonster(char[][] arr) {
        arr[b][a] = ' ';
        if (b == 0) {
            b = (int) (Math.random() * (2)) + (b);
        }
        if (a == 0) {
            a = (int) (Math.random() * (2)) + (a);
        }
        if (b == arr.length - 1) {
            b = (int) (Math.random() * (2)) + (b - 1);
        }
        if (a == arr.length - 1) {
            a = (int) (Math.random() * (2)) + (a - 1);
        }
        if (a > 0 && a < arr.length - 1) {
            a = (int) (Math.random() * (3)) + (a - 1);
        }
        if (b < arr.length - 1 && b > 0) {
            b = (int) (Math.random() * (3)) + (b - 1);
        }
        arr[b][a] = 'M';
        return arr;

    }
}
