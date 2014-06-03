arquivo
=======
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
import java.util.ArrayList;

public class Arquivo {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		ArrayList<Carro> c = new ArrayList<Carro>();
		Carro car;

		ObjectOutputStream out;

		try {

			out = new ObjectOutputStream(new FileOutputStream("carro.txt"));
			car = new Carro("Gol Bola", "XXT-6969", 23000);

			c.add(car);
			out.writeObject(c);
			out.close();

		} catch (IOException e) {

			System.out.println("Ta errado " + e);
		}

	}

}


import java.io.*;


public class ArquivosTeste {

	public static void main(String[] args) {

		BufferedReader i;
		String linha;
		int cont = 0;

		try {
			
			i = new BufferedReader(new FileReader("aluno.txt"));
			
			linha = i.readLine();

			while (i.read() >= 0 ) {
				
				for(int k = 0; k < linha.length() ; k++ ){
				
					if (linha.charAt(k) == '1') {
						cont += 1;
					}
					
				}
				
				linha = i.readLine();
				
			}

			
			System.out.println(cont);
			i.close();

		} catch (IOException e) {

			System.out.println("Arquivo não encontrado " + e);
		}

	}

}



import java.util.*;
import javax.sql.rowset.serial.SerialException;




public class Carro extends SerialException{

	private String modelo;
	private String placa;
	private float preço;

	public Carro(String modelo, String placa, float preço) {

		this.modelo = modelo;
		this.placa = placa;
		this.preço = preço;
	}

	public String getModelo() {
		return modelo;
	}

	public void setModelo(String modelo) {
		this.modelo = modelo;
	}

	public String getPlaca() {
		return placa;
	}

	public void setPlaca(String placa) {
		this.placa = placa;
	}

	public float getPreço() {
		return preço;
	}

	public void setPreço(float preço) {
		this.preço = preço;
	}

}
