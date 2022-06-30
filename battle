/*
Bridgette Fussman
11/16/2021
creates  a battleship game that the user plays to find the hidden ships using OOP
*/

import java.util.Scanner;
public class TestBattleship {
	public static void main(String[] args) {

		//this class begins the program
		Battleship bs = new Battleship();
		bs.run();
	}
}


//make Battleship quiz
class Battleship{

	public int length;
	public int[][] battleShipsLocation;
	public int[][] matrix;
	public int numOfHits;
	public int start;

	// length of the ship between 2 - 4
	// random variable to determine orientation

	public void run() {

		this.length = length();
		battleShipsLocation = new int[10][10];
		matrix = new int[10][10];

		SetOrientation();
		initialgrid();
		userinput();
		updatedgrid ();
	}

	public int length(){

 		//set random length of ship between 2 and 4
		length = (int) (2 + (Math.random()*3));
		//System.out.println("length is "+ length);

		return length;
	}		

	public void SetOrientation(){
		//set random orientation between 2 numbers
		int orientation =  1+ (int) (Math.random()*2);
		//System.out.println("orientation is "+ orientation);


		
		if (orientation == 1){
			//this is vertical
			//create the number of x's cooresponding to the length
			int row = (int) ((10-length+1) * Math.random());
			//System.out.println(row);	
			int column = (int) (10 * Math.random());
			for (int x = 0; x < length; x++) { 
			battleShipsLocation [row+x][column] = 1;
			

			}
			

		}

		else {
			//this is horizontal
			////create the number of x's cooresponding to the length
			int row = (int) (10 * Math.random());
			//System.out.println(row);	
			int column = (int) ((10-length+1)  * Math.random());
			for (int x = 0; x < length; x++) {
			battleShipsLocation [row][column+x] = 1;
			

			}
		
		}
	}


	public void initialgrid(){
		//this is the code for the initial grid
			System.out.println();
			//print extra line for formatting
			System.out.print("    ");
			for (int j = 0; j < 10; j++)
			{
				//prints out letters
				System.out.print(" " + (char)(65 + j) + "  ");
			}
			System.out.println();
			System.out.print("   +");
			for (int j = 0; j < 10; j++)
			{
				//create line outside of the pattern
				System.out.print("---+");
			}
			System.out.println();

			//Assign random values to matrix 1
			for (int i = 0; i < 10; i++)
			{
				//have numbers on columns
				System.out.print(" " + i + " |");
				for (int j = 0; j < 10; j++)
				{
					//see if we need to add something between a point
					if (matrix[i][j]== 0){ //battleShipsLocation
						System.out.print("   |");
					}

					else if (matrix[i][j] == 1){
						System.out.print(" x |");
					}

				}
				System.out.println();
				System.out.print("   +");
				for (int j = 0; j < 10; j++)
				{
					//create loop for rom
					System.out.print("---+");
				}
				//line break
				System.out.println();

				}
			}

		public void userinput(){
		int numOfHits = 0;
			//the  break loop when numofhits==length
			//if num==len 
			//break

			for (int start = 0; start <= 100; start ++ )
				{
				System.out.println(" ");
				Scanner input = new Scanner(System.in);
				System.out.print("Enter a coordinate to plot a point (ex: F7): ");
				String guess = input.next();
				char letter = guess.charAt(0); //takes out the letter
				char Fnumber = guess.length() > 1 ? guess.charAt(1) : ' ';

			
				//checks to see if this is outside of the boundaries
				if ((guess.length() != 2) || ((Fnumber >= 58) || (Fnumber <= 47)) || ((letter < 'A' || letter > 'A' + 9)))
				{
					System.out.print("Input is out of boundaries. Please try again");
				}

					
				 else{
					
				 	String prenumber = guess.substring(1); //takes out the number
				 	//turns string number into an integer
					int number = Integer.parseInt(prenumber);

					if (matrix[number][letter - 'A'] != 0) {
					System.out.print("This is a duplicate");
					continue;
					}


					// System.out.print(matrix[number][letter]=2);
					matrix[number][letter-65] = 1;

					for (int ii=0;ii<10;ii++){
						for (int jj=0;jj<10;jj++) {
							
						}
					}

					


						if (matrix[number][letter-65] == battleShipsLocation[number][letter-65]){ 
								numOfHits ++;
						}


					if (numOfHits == length){
						System.out.println("You won. It took you "+ start+" times to find the ship");
						return;

					}

				}

				updatedgrid();
			}
		}
				

	public void updatedgrid (){

					//print updated grid with hashtag changes
					System.out.println();
					//print extra line for formatting
					System.out.print("    ");
					for (int j = 0; j < 10; j++)
					{
						//prints out letters
						System.out.print(" " + (char)(65 + j) + "  ");
					}
					System.out.println();
					System.out.print("   +");
					for (int j = 0; j < 10; j++)
					{
						//create line outside of the pattern
						System.out.print("---+");
					}
					System.out.println();

					//Assign random values to matrix 1
					for (int i = 0; i < 10; i++)
					{
						//have numbers on columns
						System.out.print(" " + i + " |");
						for (int j = 0; j < 10; j++)
						{
							//see if we need to add something between a point
							if (matrix[i][j] == 0){
								System.out.print("   |");
							}

							else if (matrix[i][j] == battleShipsLocation[i][j]){ 
								System.out.print(" x |");
								
							}

							else{
								System.out.print(" # |"); //when ship is hit X
							}

						}
						System.out.println();
						System.out.print("   +");
						for (int j = 0; j < 10; j++)
						{
							//create loop for rom
							System.out.print("---+");
						}
						//line break
						System.out.println();

						}

					}
				}
			
