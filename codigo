/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package main;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileWriter;
import java.io.PrintWriter;
import java.io.FileReader;
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.IOException;
import java.util.Scanner;
import java.util.LinkedList;

/**
 *
 * @author USER
 */
class PilhaIngenua2 {
	protected int capacity;
        public static final int CAPACITY = 8;
	protected Integer[] pilha;
        protected int size;

	PilhaIngenua2() { capacity = CAPACITY; pilha = new Integer[capacity]; size = 0; }

	void add(int newElement){
            if(size == capacity){
                capacity += CAPACITY;
                Integer[] tmp = new Integer[capacity];
                for (int j = 0; j < size; j++) 
                    tmp[j] = pilha[j];
                pilha = tmp;
            }
            
            pilha[size] = newElement;
            size++;
        }

	int remove(){
            int tmp = pilha[size-1];
            size--;
            return tmp;
        }
}

class Estrutura{
    protected int value;
    protected Estrutura next;
    
    Estrutura(int v) {value = v;}
}

class Pilha{
    protected Estrutura inicio;
    

void add(int a){
    Estrutura tmp = new Estrutura(a);
    Estrutura aux = inicio;
    
    if(aux==null){
        inicio = tmp;
        return;
    }
    
    inicio = tmp;
    tmp.next = aux;
          
    //System.out.println(inicio.value);
}

int remove(){
    Estrutura aux = inicio;
    int ret;
    
    if(aux == null)
        return -1;
    
    
    //System.out.println(aux.value);
    
    ret = aux.value;
    inicio = aux.next;   

    return ret;   
}
    
}



 class PilhaArranjo {
    protected int size;
    protected int topo;
    protected Integer[] pilha;
    
    PilhaArranjo() {size = 8; pilha = new Integer[size]; topo = 0; }
    
    void add(int a){
        //System.out.println(topo);
        if(topo == size){
            size *= 2;
            Integer[] tmp = new Integer[size];
            for (int i = 0; i < topo; i++) 
                tmp[i] = pilha[i];
            pilha = tmp;
        }
        
        pilha[topo] = a;
        topo++;
    }
    
    int remove(){
        int tmp = pilha[topo-1];
        topo--;
        return tmp;
    }
}


public class AED {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        int count;
        LinkedList<Long> timestamps = new LinkedList<>();
        LinkedList<Integer> sizes = new LinkedList<>();
        int iterator = 1000;
        PilhaArranjo x = new PilhaArranjo();
        Pilha y = new Pilha();
        
        
        while(iterator<=99000){
            LinkedList<Integer> ordem = new LinkedList<>();
            count = 0;
            long timeStart = System.currentTimeMillis();
        try {
            PrintWriter out = new PrintWriter("output"+iterator+".txt");
            FileReader Reader = new FileReader("tarefas"+iterator+".txt");
            //FileReader Reader = new FileReader("./main/tarefas"+iterator+".txt");
            BufferedReader Input = new BufferedReader(Reader);
            
            
            String linha = Input.readLine();
            
            while(linha!=null){               
                if(linha.isEmpty()){
                    //ordem.add(x.remove());                  
                    ordem.add(y.remove());                   
                }
                else{             
                //x.add(Integer.parseInt(linha));               
                y.add(Integer.parseInt(linha));
                }
                linha = Input.readLine();
                count++;
                                              
            }
            
            while(!ordem.isEmpty()){
                out.println(ordem.getFirst());
                //System.out.println(ordem.getFirst());
                ordem.removeFirst();
            }
            
            out.flush();
            out.close();
            Reader.close();
            System.out.println("Arquivo output"+iterator+".txt criado");
            timestamps.add(System.currentTimeMillis()-timeStart);
            sizes.add(count);
            
            
            
            //ordem.print(Output);
            
            iterator += 1000;
            
            
        }
        
        
        catch(IOException a){
            System.out.println("Arquivo não encontrado");
            return;
        }
        
        }
        
        
        try{
            PrintWriter out = new PrintWriter("timestamps.txt");
            PrintWriter size = new PrintWriter("sizes.txt");
            while(!timestamps.isEmpty()){
                
                out.println(timestamps.getFirst());
                size.println(sizes.getFirst());
                timestamps.removeFirst();
                sizes.removeFirst();                
                    
            }
            out.flush();
            size.flush();
            out.close();
            size.close();
        }
        catch(IOException a){
        }
        
        
    }
    
   
    
}
