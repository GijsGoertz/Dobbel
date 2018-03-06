# Dobbel
Dobbelsteentjes gooien
package Dobbel;
import javax.swing.JOptionPane;
import java.util.Random;
/**
 *
 * @author E3
 */
public class Test {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
    Object [] aantal = {"1", "2", "3","4"};
    int aantalDobbelstenen = JOptionPane.showOptionDialog(null,
                                            "please select number of dice", "Number of dice",
                                            JOptionPane.DEFAULT_OPTION,
                                            JOptionPane.QUESTION_MESSAGE,
                                            null,
                                            aantal,
                                            aantal[0]);
    Object [] zijden = {"6", "8", "12","20"};
    int aantalZijden = JOptionPane.showOptionDialog(null,
                                            "please select sides of dice", "Sides of dice",
                                            JOptionPane.DEFAULT_OPTION,
                                            JOptionPane.QUESTION_MESSAGE,
                                            null,
                                            zijden,
                                            zijden[0]);    
    int[] geworpenDobbelstenen= new int [aantalDobbelstenen + 1];
    int vlakken = 0;
    switch (aantalZijden){
       case 0:
           vlakken = 6;
           break;
       case 1:
           vlakken = 8;
           break;
       case 2:
           vlakken = 12;
           break;
       case 3:
           vlakken = 20;
           break;
    }
    int worpen = 0;
    while (worpen <= aantalDobbelstenen){
        geworpenDobbelstenen [worpen] = gooitDobbelstenen(vlakken);
        worpen ++;
    }
    uitkomst(geworpenDobbelstenen);
    }
    public static int gooitDobbelstenen (int aantalvlakken){
        Random rand = new Random();
        int worp = rand.nextInt(aantalvlakken)+1;
        return worp;
    }
    public static void uitkomst (int[] geworpenDobbelstenen){
        for (int i = 0; i < geworpenDobbelstenen.length; i++){
            System.out.println("Dice " + (i+1) + " has value: " + geworpenDobbelstenen[i]);
        }  
    }
    }
    
