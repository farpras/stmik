---
title:  UAS - Algoritma & Pemrograman 2
updated:   2017-05-19 01:00
categories: Tugas
comments: true
---
Assalamu'alaikum wr. wb.

Berikut ini adalah program Konversi Suhu sederhana yang saya buat menggunakan JFrame Form pada NetBeans IDE.

Cara kerja atau menggunakan program ini sangat mudah, kita cukup memilih jenis suhu apa yang akan dikonversikan pada radio button, dan jenis suhu tujuan pada combo box. Lalu, masukkan nilai awal suhu dan klik "Konversi". Maka secara otomatis hasil akan muncul pada text field bawah.

Screenshot program saat dijalankan:
<img src="http://blog.farpras.xyz/uploads/sstutor9.png"/>

Lalu ini adalah fungsi exit dan Dialog Box menggunakan JOptionPane:
<img src="http://blog.farpras.xyz/uploads/joptionpane_exit.png"/>

Dan ini juga JOptionPane yang muncul ketika user belum memilih suhu tujuan konversi:
<img src="http://blog.farpras.xyz/uploads/joptionpane_error.png"/>

PseudoCode:
```
1. Program Konversi Suhu.
{
Mengkonversi nilai suhu Celsius, Fahrenheit dan Kelvin.
}
2. Deklarasi
text : String
tx : String
cel : Float
fahr : Float
kel : Float
txtHasil : String
3. Deskripsi
Read (text, tx, cel, fahr, kel)
// Cel -> Fahr
fahr = (cel*1.8)+32
txtHasil = fahr
// Cel -> Kel
kel = cel+273.15
txtHasil = kel
// Fahr -> Cel
cel = (fahr - 32) / 1.8
txtHasil = cel
// Fahr -> Kel
kel = (fahr + 459.67) * 5/9
txtHasil = kel
// Kel -> Cel
cel = kel - 273.15
txtHasil = cel
// Kel -> Fahr
fahr = kel * 9/5 - 459.67
txtHasil = fahr

Write (txtHasil)
```

**Source Code:**
```
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package tempconverter;

/**
 *
 * @author Farpras
 */
public class TempConverterGUI extends javax.swing.JFrame {

    /**
     * Creates new form TempConverterGUI
     */
    public TempConverterGUI() {
        initComponents();
        buttonGroup1.add(rbtnCelsius);
        buttonGroup1.add(rbtnFahr);
        buttonGroup1.add(rbtnKelvin);
        rbtnCelsius.setSelected(true);
    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        buttonGroup1 = new javax.swing.ButtonGroup();
        jPanel1 = new javax.swing.JPanel();
        lblDari = new javax.swing.JLabel();
        rbtnCelsius = new javax.swing.JRadioButton();
        rbtnFahr = new javax.swing.JRadioButton();
        rbtnKelvin = new javax.swing.JRadioButton();
        cboxSuhu = new javax.swing.JComboBox<>();
        lblKe = new javax.swing.JLabel();
        jPanel3 = new javax.swing.JPanel();
        txtNilai = new javax.swing.JTextField();
        jLabel1 = new javax.swing.JLabel();
        btnKonversi = new javax.swing.JButton();
        txtHasil = new javax.swing.JTextField();
        jLabel2 = new javax.swing.JLabel();
        menuBar = new javax.swing.JMenuBar();
        menuFile = new javax.swing.JMenu();
        menuExit = new javax.swing.JMenuItem();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);
        setTitle("Temperatur Converter");

        lblDari.setText("Dari:");

        rbtnCelsius.setText("Celsius");

        rbtnFahr.setText("Fahrenheit");

        rbtnKelvin.setText("Kelvin");

        cboxSuhu.setModel(new javax.swing.DefaultComboBoxModel<>(new String[] { "Pilih", "Celsius", "Fahrenheit", "Kelvin" }));
        cboxSuhu.setName(""); // NOI18N
        cboxSuhu.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                cboxSuhuActionPerformed(evt);
            }
        });

        lblKe.setText("Ke:");

        javax.swing.GroupLayout jPanel1Layout = new javax.swing.GroupLayout(jPanel1);
        jPanel1.setLayout(jPanel1Layout);
        jPanel1Layout.setHorizontalGroup(
            jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addContainerGap()
                        .addComponent(lblDari, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addGap(20, 20, 20)
                        .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                            .addComponent(rbtnCelsius, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                            .addComponent(rbtnFahr, javax.swing.GroupLayout.DEFAULT_SIZE, 118, Short.MAX_VALUE)
                            .addComponent(rbtnKelvin, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                        .addGap(0, 32, Short.MAX_VALUE))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addContainerGap()
                        .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(jPanel1Layout.createSequentialGroup()
                                .addComponent(lblKe)
                                .addGap(0, 0, Short.MAX_VALUE))
                            .addComponent(cboxSuhu, javax.swing.GroupLayout.Alignment.TRAILING, 0, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))))
                .addContainerGap())
        );
        jPanel1Layout.setVerticalGroup(
            jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(lblDari, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(rbtnCelsius)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(rbtnFahr)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(rbtnKelvin)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(lblKe)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(cboxSuhu, javax.swing.GroupLayout.PREFERRED_SIZE, 32, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
        );

        txtNilai.setHorizontalAlignment(javax.swing.JTextField.CENTER);
        txtNilai.setText("0");
        txtNilai.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                txtNilaiActionPerformed(evt);
            }
        });

        jLabel1.setText("Masukan Suhu Awal:");

        btnKonversi.setText("Konversi");
        btnKonversi.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnKonversiActionPerformed(evt);
            }
        });

        txtHasil.setHorizontalAlignment(javax.swing.JTextField.CENTER);
        txtHasil.setText("0");

        jLabel2.setText("Hasil:");

        javax.swing.GroupLayout jPanel3Layout = new javax.swing.GroupLayout(jPanel3);
        jPanel3.setLayout(jPanel3Layout);
        jPanel3Layout.setHorizontalGroup(
            jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel3Layout.createSequentialGroup()
                .addContainerGap()
                .addGroup(jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)
                    .addComponent(jLabel2, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                    .addComponent(txtNilai, javax.swing.GroupLayout.Alignment.LEADING)
                    .addComponent(jLabel1, javax.swing.GroupLayout.Alignment.LEADING, javax.swing.GroupLayout.DEFAULT_SIZE, 160, Short.MAX_VALUE)
                    .addComponent(btnKonversi, javax.swing.GroupLayout.Alignment.LEADING, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                    .addComponent(txtHasil))
                .addContainerGap())
        );
        jPanel3Layout.setVerticalGroup(
            jPanel3Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel3Layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(txtNilai, javax.swing.GroupLayout.PREFERRED_SIZE, 32, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(18, 18, 18)
                .addComponent(btnKonversi, javax.swing.GroupLayout.PREFERRED_SIZE, 31, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(jLabel2, javax.swing.GroupLayout.PREFERRED_SIZE, 21, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(txtHasil, javax.swing.GroupLayout.DEFAULT_SIZE, 33, Short.MAX_VALUE)
                .addContainerGap())
        );

        menuFile.setText("File");

        menuExit.setAccelerator(javax.swing.KeyStroke.getKeyStroke(java.awt.event.KeyEvent.VK_F4, java.awt.event.InputEvent.ALT_MASK));
        menuExit.setText("Exit");
        menuExit.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                menuExitActionPerformed(evt);
            }
        });
        menuFile.add(menuExit);

        menuBar.add(menuFile);

        setJMenuBar(menuBar);

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addComponent(jPanel1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(jPanel3, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(jPanel1, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
            .addComponent(jPanel3, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
        );

        pack();
    }// </editor-fold>                        

    private void menuExitActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
        System.exit(0);
    }                                        

    private void cboxSuhuActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
    }                                        

    private void btnKonversiActionPerformed(java.awt.event.ActionEvent evt) {                                            
        
        String tx = (String)cboxSuhu.getSelectedItem();
        
        // Celsius
        if(rbtnCelsius.isSelected() && tx.equals("Fahrenheit")){
            String text = txtNilai.getText();
            float cel = Float.parseFloat(text);
            float fahr = (float) ((cel*1.8)+32);
            txtHasil.setText(""+fahr);
        }
        
        if(rbtnCelsius.isSelected() && tx.equals("Kelvin")){
            String text = txtNilai.getText();
            float cel = Float.parseFloat(text);
            float kel = (float) (cel+273.15);
            txtHasil.setText(""+kel);
        }
        
        if(rbtnCelsius.isSelected() && tx.equals("Celsius")){
            String text = txtNilai.getText();
            float cel = Float.parseFloat(text);
            txtHasil.setText(""+cel);
        }
        
        if(rbtnCelsius.isSelected() && tx.equals("Pilih")){
            String text = txtNilai.getText();
            float cel = Float.parseFloat(text);
            txtHasil.setText("ERROR: Celsius ke ?");
        }
        
        // Fahrenheit
        if(rbtnFahr.isSelected() && tx.equals("Celsius")){
            String text = txtNilai.getText();
            float fahr = Float.parseFloat(text);
            float cel = (float) ((fahr - 32) / 1.8);
            txtHasil.setText(""+cel);
        }
        
        if(rbtnFahr.isSelected() && tx.equals("Kelvin")){
            String text = txtNilai.getText();
            float fahr = Float.parseFloat(text);
            float kel = (float) ((fahr + 459.67) * 5/9);
            txtHasil.setText(""+kel);
        }
        
        if(rbtnFahr.isSelected() && tx.equals("Fahrenheit")){
            String text = txtNilai.getText();
            float fahr = Float.parseFloat(text);
            txtHasil.setText(""+fahr);
        }
        
        if(rbtnFahr.isSelected() && tx.equals("Pilih")){
            String text = txtNilai.getText();
            float fahr = Float.parseFloat(text);
            txtHasil.setText("ERROR: Fahrenheit ke ?");
        }
        
        // Kelvin
        if(rbtnKelvin.isSelected() && tx.equals("Celsius")){
            String text = txtNilai.getText();
            float kel = Float.parseFloat(text);
            float cel = (float) (kel - 273.15);
            txtHasil.setText(""+cel);
        }
        
        if(rbtnKelvin.isSelected() && tx.equals("Fahrenheit")){
            String text = txtNilai.getText();
            float kel = Float.parseFloat(text);
            float fahr = (float) (kel * 9/5 - 459.67);
            txtHasil.setText(""+fahr);
        }
        
        if(rbtnKelvin.isSelected() && tx.equals("Kelvin")){
            String text = txtNilai.getText();
            float kel = Float.parseFloat(text);
            txtHasil.setText(""+kel);
        }
        
        if(rbtnKelvin.isSelected() && tx.equals("Pilih")){
            String text = txtNilai.getText();
            float kel = Float.parseFloat(text);
            txtHasil.setText("ERROR: Kelvin ke ?");
        }
        
    }                                           

    private void txtNilaiActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
    }                                        

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException ex) {
            java.util.logging.Logger.getLogger(TempConverterGUI.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (InstantiationException ex) {
            java.util.logging.Logger.getLogger(TempConverterGUI.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (IllegalAccessException ex) {
            java.util.logging.Logger.getLogger(TempConverterGUI.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (javax.swing.UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(TempConverterGUI.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new TempConverterGUI().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JButton btnKonversi;
    private javax.swing.ButtonGroup buttonGroup1;
    private javax.swing.JComboBox<String> cboxSuhu;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JPanel jPanel1;
    private javax.swing.JPanel jPanel3;
    private javax.swing.JLabel lblDari;
    private javax.swing.JLabel lblKe;
    private javax.swing.JMenuBar menuBar;
    private javax.swing.JMenuItem menuExit;
    private javax.swing.JMenu menuFile;
    private javax.swing.JRadioButton rbtnCelsius;
    private javax.swing.JRadioButton rbtnFahr;
    private javax.swing.JRadioButton rbtnKelvin;
    private javax.swing.JTextField txtHasil;
    private javax.swing.JTextField txtNilai;
    // End of variables declaration                   
}

```

Source code NetBeans Project bisa didownload disini: <a href="https://drive.google.com/file/d/0B3guqsE8r2uENERqdGdsc3dHc1E/view?usp=sharing">https://drive.google.com/file/d/0B3guqsE8r2uENERqdGdsc3dHc1E/view?usp=sharing</a>

Terima kasih.