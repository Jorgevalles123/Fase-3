Fase 3
Desarrollo de botones

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
