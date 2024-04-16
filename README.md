# Fase-3
Fase 3 productividad basada en herramientas tecnologicas

package com.mycompany.refacciones;

import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.Font;
import java.awt.GridLayout;
import java.awt.event.ActionListener;
import java.util.ArrayList;
import java.util.List;
import javax.swing.BorderFactory;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;
import javax.swing.JTextField;

/**
 *
 * @author Jorge VV
 */
public class almacen extends JFrame implements ActionListener  {
    
    private JTextField txtNombre;
    private JTextField txtserie;
    private JTextArea txtAreaResultado;
    private List<Refaccion> refacciones;
    
    public almacen (){
        super("Almacen");
        
        refacciones = new ArrayList<>();

setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
setSize(600,400);
setLayout(new BorderLayout());
setResizable(false);
setLocationRelativeTo(null);



//Panel de formulario para agregar refacciones

JPanel panelFormulario =new JPanel (new GridLayout(2, 2, 10, 10));
panelFormulario.setBorder(BorderFactory.createEmptyBorder(20,20,10,20));

JLabel lblNombre = new JLabel ("Nombre");
lblNombre.setFont(new Font("Arial", Font.BOLD, 16));
txtNombre = new JTextField();
txtNombre.setFont(new Font("arial", Font.PLAIN, 16 ));

JLabel lblserie = new JLabel ("Serie");
lblNombre.setFont(new Font("Arial", Font.BOLD, 16));
txtserie = new JTextField();
txtserie.setFont(new Font("arial", Font.PLAIN, 16 ));

panelFormulario.add(lblNombre);
panelFormulario.add(txtNombre);
panelFormulario.add(lblserie);
panelFormulario.add(txtserie);


//Boton añadir refaccion
 JButton btnAgregar= new JButton("Agregar");
 btnAgregar.addActionListener(this);
 btnAgregar.setFont(new Font("Arial", Font.BOLD, 16));
btnAgregar.setBackground(new Color(0, 153, 51));
btnAgregar.setForeground(Color.BLUE);
btnAgregar.setPreferredSize(new Dimension(200, 40));

//Boton eliminar refaccion
 JButton btnEliminar= new JButton("Eliminar");
 btnEliminar.addActionListener(this);
 btnEliminar.setFont(new Font("Arial", Font.BOLD, 16));
btnEliminar.setBackground(new Color(204, 0, 0));
btnEliminar.setForeground(Color.BLUE);
btnEliminar.setPreferredSize(new Dimension(200, 40));

//Boton buscar refaccion
 JButton btnBuscar= new JButton("Buscar");
 btnBuscar.addActionListener(this);
 btnBuscar.setFont(new Font("Arial", Font.BOLD, 16));
btnBuscar.setBackground(new Color(0, 102, 204));
btnBuscar.setForeground(Color.BLUE);
btnBuscar.setPreferredSize(new Dimension(200, 40));

//Boton para consultar inventario
 JButton btnInventario= new JButton("Inventario");
 btnInventario.addActionListener(this);
 btnInventario.setFont(new Font("Arial", Font.BOLD, 16));
btnInventario.setBackground(new Color(255, 153, 0));
btnInventario.setForeground(Color.BLUE);
btnInventario.setPreferredSize(new Dimension(200, 40));

panelFormulario.add(btnAgregar);
panelFormulario.add(btnEliminar);
panelFormulario.add(btnBuscar);
panelFormulario.add(btnInventario);

//Area de resultados

txtAreaResultado = new JTextArea();
txtAreaResultado.setEditable(false);
txtAreaResultado.setFont(new Font("Arial", Font.PLAIN, 16));
txtAreaResultado.setLineWrap(true);
txtAreaResultado.setWrapStyleWord(true);
 txtAreaResultado.setBackground(new Color(240, 240, 240));
 txtAreaResultado.setBorder(BorderFactory.createLineBorder(Color.GREEN)) ;
 JScrollPane scrollPane = new JScrollPane (txtAreaResultado);
 scrollPane.setPreferredSize(new Dimension(560, 200));
    
    //Panel principal
    
    JPanel panelPrincipal = new JPanel(new BorderLayout());
    panelPrincipal.add(panelFormulario, BorderLayout.NORTH);
    panelPrincipal.add(scrollPane, BorderLayout.SOUTH);
    panelPrincipal.setBorder(BorderFactory.createEmptyBorder(20, 20, 20, 20));
    
    add(panelPrincipal);
    setVisible(true);
    
    }
    
    @Override
  public void actionPerformed(ActionEvent e){
      if(e.getActionCommand().equals("Agregar")){
      String nombre= txtNombre.getText();
      String serie= txtserie.getText();
      if(!nombre.isEmpty()&&!serie.isEmpty());
      agregarRefaccion (nombre, serie);
      txtNombre.setText("");
      txtserie.setText("");
      txtAreaResultado.setText("La refaccion se ha añadido correctamente al almacen");
      }else{
      txtAreaResultado.setText("Porfavor introduce la refaccion y el numero de serie");
      }
      } else if (e.getActionCommand().equals("Eliminar")) {
              String nombre = txtNombre.getText();
              eliminarRefaccion(nombre);
              txtNombre.setText("");
              txtserie.setText("");
              txtAreaResultado.setText("la refaccion se ha eliminado correctamente");
  } else if (e.getActionCommand() .equals ("Buscar")){
      String terminoBusqueda= txtNombre.getText();
      String tipoBusqueda = "Nombre"; // Por defecto el programa buscara por el nombre de lsa refaccion
      if(!terminoBusqueda.isEmpty()){
          List<string> resultados= buscarRefaccion(terminoBusqueda, tipoBusqueda);
          txtAreaResultado.setText("No se encuntran refacciones con ese nombre"+ terminoBusqueda+".");
          
  }else {
          for(String resultado : resultados){
              txtAreaResultado.append(resultado + "n");
          }
      }
              
}  else{

