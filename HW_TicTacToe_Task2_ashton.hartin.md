package task2files.hw_tictactoe_task2_ashton.hartin;
import java.util.Scanner;
public class HW_TicTacToe_Task2_ashtonHartin 
{
    public static void main(String[] args) 
    {   
        char[][] board = {{' ', '|', ' ', '|', ' '},
                          {'-', '+', '-', '+', '-'},
                          {' ', '|', ' ', '|', ' '},
                          {'-', '+', '-', '+', '-'},
                          {' ', '|', ' ', '|', ' '}};
        
        char PLAYER = ' ';
        char SYSTEM = ' ';
        
        Scanner scan1  = new Scanner(System.in);
        System.out.println("Please enter which symbol you want to play\n1: X\n2: O\n0: Exit");
        int symbolChoice = scan1.nextInt();
        if(symbolChoice == 1)
        {
            PLAYER = 'X';
            SYSTEM = 'O';
        }
        else if(symbolChoice == 2)
        {
            PLAYER = 'O';
            SYSTEM = 'X';
        }
        else if(symbolChoice == 0)
        {
            System.exit(0);
        }
        
        Scanner scan2 = new Scanner(System.in);
        System.out.println("Do you wish to take the first turn?\nType either YES or NO: ");
        String turnOne = scan2.nextLine();
        if("YES".equals(turnOne) || "Yes".equals(turnOne) || "yes".equals(turnOne))
        {
            printBoard(board);
            
            Scanner scan3 = new Scanner(System.in);
            System.out.println("Enter a position (1-9 or enter 0 to exit game): ");
            int position = scan3.nextInt();
            System.out.println(position);
            if(position == 0)
            {
                System.exit(0);
            }
            
            chooseAndPlaceSymbol(board, position, PLAYER, SYSTEM, "PLAYER");
        }
        else if("NO".equals(turnOne) || "No".equals(turnOne) || "no".equals(turnOne))
        {
            printBoard(board);
            
            int position = 0;
            chooseAndPlaceSymbol(board, position, PLAYER, SYSTEM, "SYSTEM");
        }

        printBoard(board);
    }
    
    public static void printBoard(char[][] board)
    {
        for(char[] row : board)
        {
            for(char i : row)
            {
                System.out.print(i);
            }
            System.out.println();
        }
    }
    
    public static void chooseAndPlaceSymbol(char[][] board, int position, char PLAYER, char SYSTEM, String USER)
    {
        char symbol = ' ';
        
        if(USER.equals("PLAYER"))
        {
            symbol = PLAYER;
        }
        else if(USER.equals("SYSTEM"))
        {
            symbol = SYSTEM;
        }
        
        switch(position)
        {
            case 1:             
                board[0][0] = symbol;
                break;
            
            case 2:             
                board[0][2] = symbol;
                break;
            
            case 3:            
                board[0][4] = symbol;
                break;
            
            case 4:             
                board[2][0] = symbol;
                break;
            
            case 5:             
                board[2][2] = symbol;
                break;
            
            case 6:           
                board[2][4] = symbol;
                break;
            
            case 7:            
                board[4][0] = symbol;
                break;
            
            case 8:             
                board[4][2] = symbol;
                break;
            
            case 9:            
                board[4][4] = symbol;
                break;
            
            case -1:
                Runtime.getRuntime().equals(symbol);
            
            default:
                break;     
        }
    }
}