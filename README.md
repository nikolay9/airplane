import java.util.Random;
import java.util.Scanner;

public class MainClass {
  public static void main(String[] args) {
		int sum = 0;
		int number = 0;
		int places[][] = new int[27][6];
		for (int i = 0; i < 27; i++) {
			System.out.print(i + " ");
			for (int k = 0; k < 6; k++) {
				if (k == 3) {
					System.out.print(" ");
				}
				System.out.print(places[i][k]);
			}
			System.out.println();
		}
		System.out.println();
		for (; sum != 162;) {
			Random r = new Random();
			number = r.nextInt(3) + 1;
			System.out.println("Broi putnici v grupata:" + number);
			sum += number;
			if (sum > 162) {
				sum -= number;
			}
			for(int i=0;i<27;i++) {
				for(int k=0;k<6;k++) {
					if(number==1) {
						if(places[i][0]==0) places[i][0]=1;
						else if(places[i][3]==0) places[i][3]=1;
						else break;
					}
					if(number==2) {
						if(places[i][0]==0) {
					 		places[i][0]=1;
							places[i][1]=2;
						}
						else if(places[i][3]==0) {
							places[i][3]=1;
							places[i][4]=2;
						}
						else break;
					}
					if(number==3) {
						if(places[i][0]==0) {
					 		places[i][0]=1;
							places[i][1]=2;
							places[i][2]=3;
						}
						else if(places[i][3]==0) {
							places[i][3]=1;
							places[i][4]=2;	
							places[i][5]=3;	
						}
						else break;
					}
	
					System.out.println("Natisnete Enter");
					Scanner scan = new Scanner(System.in);	
					scan.nextLine();			

					for (i=0;i<27;i++) {
						System.out.print(i + " ");
						for (k=0;k<6;k++) {
							if (k == 3) {
								System.out.print(" ");
							}
							System.out.print(places[i][k]);
						}
						System.out.println();
					}
					System.out.println();
				}
			}
		}
	}
}