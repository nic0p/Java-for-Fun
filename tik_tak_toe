// Proyecto 100% skill, no ayuda de intenet, solo yo y mi cabeza, iniciado el 05/09/2021, finalizado 07/09/2021
// Tik Tak Toe Java, still have some bugs but it works, and i'm very happy :)
import java.util.*;
public class TikTakToe {
    public static void main(String[] args) throws Exception {
        int c = -1;                     // Verificador de ganador, Si es 0 gano maquina, si es 0 gano humano
        int conth = 0;                  // Contador de jugadas de humano para ver si es empate
        int [][]matrix = new int[3][3]; // Matriz del juego
        int []lista_disp = new int[9];  // Lista de positions disponibles
        
        generar_vacia_bi(matrix);
        generar_vacia_un(lista_disp);

        while(true){          
            // Jugada Humano
            jugar_humano(matrix,lista_disp,conth++);
            // Imprime tablero
            tablero(matrix);
            // Verifica si gana o hay empate
            if(empate(conth)){
                System.out.println("DRAW");
                break;
            }
            if(ganar(matrix,c)){
                System.out.println("°FINI°");
                break;
            }
            System.out.println("--------------");
            // Jugada Maquina
            jugar_maquina(matrix,lista_disp);
            // Imprime tablero
            tablero(matrix);
            // Verifica si gana o hay empate
            if(empate(conth)){
                System.out.println("DRAW");
                break;
            }
            if(ganar(matrix,c) || empate(conth)){
                System.out.println("°FINI°");
                break;
            }   
            conth++;
        }   
    }

    public static boolean ganar(int matrix[][], int c){
        if(ganar_columna(matrix,c) || ganar_fila(matrix, c)){
            return true;
        }
        return false;

    }

    public static void ganador(int c){
        if(c==1){
            System.out.println("Gano Machine");
        }
        else{
            System.out.println("Gane ");
        }
    }

    public static boolean empate(int conth){
        if(conth > 7){
            return true;
        }
        return false;
    }

    public static void jugar_humano(int list[][], int lista_disp[],int conth){     // The human plays with "O"
        Scanner scan = new Scanner(System.in);
        System.out.println("Juegue: ");
        int x = scan.nextInt();
        

        if(x == 0){
            list[0][0] = 2;
            lista_disp[0]=0;
        }
        if(x == 1){
            list[0][1] = 2;
            lista_disp[1]=0;
        }
        if(x == 2){
            list[0][2] = 2;
            lista_disp[2]=0;
        }
        if(x == 3){
            list[1][0] = 2;
            lista_disp[3]=0;
        }
        if(x == 4){
            list[1][1] = 2;
            lista_disp[4]=0;
        }
        if(x == 5){
            list[1][2] = 2;
            lista_disp[5]=0;
        }
        if(x == 6){
            list[2][0] = 2;
            lista_disp[6]=0;
        }
        if(x == 7){
            list[2][1] = 2;
            lista_disp[7]=0;
        }
        if(x == 8){
            list[2][2] = 2;
            lista_disp[8]=0;
        }

    }

    public static void jugar_maquina(int list[][], int lista_disp[]){              // The human plays with "X"
        int x;
        x = getRandom(0, 9); 
        // Si el aleatorio genera un numero que ya esta ocupado debe generar otro
        if(lista_disp[x]==0){
            
            while(lista_disp[x]==0){
                x = getRandom(0, 9);
            }
        }
        
        if(x == 0){
            list[0][0] = 1;     
            lista_disp[0]=0;
        }
        if(x == 1){
            list[0][1] = 1;
            lista_disp[1]=0;
        }
        if(x == 2){
            list[0][2] = 1;
            lista_disp[2]=0;
        }
        if(x == 3){
            list[1][0] = 1;
            lista_disp[3]=0;
        }
        if(x == 4){
            list[1][1] = 1;
            lista_disp[4]=0;
        }
        if(x == 5){
            list[1][2] = 1;
            lista_disp[5]=0;
        }
        if(x == 6){
            list[2][0] = 1;
            lista_disp[6]=0;
        }
        if(x == 7){
            list[2][1] = 1;
            lista_disp[7]=0;
        }
        if(x == 8){
            list[2][2] = 1;
            lista_disp[8]=0;
        }

    }
        
    public static boolean ganar_fila (int list[][],int c){
        int sum  = 0;
        int sum2  = 0;
        for(int i=0;i<3;i++){
            sum = 0;
            sum2 = 0;
            for(int j=0;j<3;j++){
                if(list[i][j]==1){
                    sum += 1;
                }
                if(list[i][j]==2){
                    sum2 += 1;
                }
                
            }
            if(sum == 3 || sum2 == 3){
                return true;
            }  
        }
        return false;
    }

    public static boolean ganar_columna(int list[][],int c) {
        int sum = 0;
        int sum2  = 0;
        for(int i=0;i<3;i++){
            sum = 0;
            sum2 = 0;
            for(int j=0;j<3;j++){
                if(list[j][i]==2){
                    sum += 1;
                }
                if(list[j][i]==1){
                    sum2 += 1;
                }
            }
            if(sum == 3 || sum2 == 3){
                return true;
            }  
        }
        return false;
    }

    public static boolean ganar_diago(int list[][], int c) {    // NO FUNCIONA; COMPLETAR MAÑANA
        int sum = (list[0][0] + list[1][1] + list[2][2]);   // Diagonal Prin
        int sum2 = (list[0][2] + list[1][1] + list[2][0]);  // Diagonal Sec

        if(sum == 6 || sum == 3){
            return true;
        }
        if(sum2 == 6 || sum2 == 3){
            return true;
        }
        return false;
        
    }
    
    public static int getRandom(int min, int max) {
        Random random = new Random();
        return random.nextInt(max - min) + min;
    }

    public static void generar_vacia_bi (int list[][]){
        for(int i=0;i<3;i++){
            for(int j=0;j<3;j++){
                list[i][j] = -1;
            }
        }
    }

    public static void generar_vacia_un (int list[]){
        for(int i=0;i<9;i++){
            list[i] = 1;
        }
    }

    public static void mostrar(int list[][]){
        for(int i=0;i<3;i++){
            for(int j=0;j<3;j++){
                System.out.println(list[i][j]);
            }
        }
    }

    public static void tablero(int list[][]){
        for(int i=0;i<3;i++){
            for(int j=0;j<3;j++){
                if(list[i][j] == -1){
                    System.out.print("| |");
                }
                if(list[i][j] == 1){
                    System.out.print("|X|");
                }
                if(list[i][j] == 2){
                    System.out.print("|O|");
                }
            }
            System.out.println("\n");
        }
    }

}
