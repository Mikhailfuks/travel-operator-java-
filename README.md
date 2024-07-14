import java.sql.*; 
import java.util.*; 
import javax.swing.JOptionPane; 
  
// Travel class 
class My_Travels { 
  
    public static void main(String[] args) 
        throws Exception 
    { 
        String driverClassName 
            = "com.mysql.jdbc.Driver"; 
  
        String URL 
            = "jdbc:mysql:// localhost/"
              + "My_Travels_travel_service"; 
  
        String user = "root"; 
        String pwd = "mysql"; 
  
        Class.forName(driverClassName) 
            .newInstance(); 
  
        Connection con 
            = DriverManager.getConnection( 
                url, user, pwd); 
  
        System.out.println("con---->" + con); 
  
        Statement st = con.createStatement(); 
  
        Scanner zz = new Scanner(System.in); 
        System.out.println( 
            "\n"
            + "\n"
            + "*********************"
            + "********************  "); 
        System.out.println( 
            "** WELCOME TO My_Travels"
            + " TRAVELS SERVICES **  "); 
  
        System.out.println( 
            "Here you have several"
            + " tasks to perform -- "
            + "\n"
            + "\n"); 
  
        System.out.println( 
            "Press 1 for ticket booking "
            + "\n"
            + "\n"
            + "Press 2 for "
            + "ticket cancellation"
            + "\n"
            + "\n"
            + "Press 3 for updating "
            + "Passenger detail"
            + "\n"
            + "\n"
            + "Press 4 to print "
            + "ticket details"); 
  
        int mainCH = zz.nextInt(); 
        switch (mainCH) { 
  
        case 1: 
            System.out.println( 
                " Please choice the route :  "); 
  
            System.out.println( 
                "For DEHRADUN <---> KANPUR "
                + "via Haridwar, press 1"
                + "\n"
                + "\n"
                + "For DEHRADUN <---> DELHI "
                + "via Roorkee, press 2"); 
  
            int route_ch = zz.nextInt(); 
            switch (route_ch) { 
            case 1: 
                System.out.println( 
                    " Welcome <--> DEHRADUN"
                    + " - KANPUR route "
                    + "via Haridwar "); 
  
                System.out.println( 
                    "Please enter your detail"
                    + " so we can book "
                    + "your ticket"); 
  
                String w 
                    = JOptionPane 
                          .showInputDialog( 
                              "Enter the Journey Date:"); 
  
                String x 
                    = JOptionPane 
                          .showInputDialog( 
                              "Enter Passenger Name:"); 
  
                String y 
                    = JOptionPane.showInputDialog( 
                        "Enter Passenger Age:"); 
  
                String z 
                    = JOptionPane.showInputDialog( 
                        "Enter Bus Type:"); 
  
                String a 
                    = JOptionPane.showInputDialog( 
                        "Enter Source City:"); 
  
                String b 
                    = JOptionPane.showInputDialog( 
                        "Enter Destination City:"); 
  
                String c 
                    = JOptionPane.showInputDialog( 
                        "Enter Seat Type:"); 
  
                String cc 
                    = JOptionPane.showInputDialog( 
                        "Enter Email address:"); 
  
                System.out.println( 
                    " In this route, we have "
                    + "type of bushes for you "
                    + "(Both AC and Non-AC "
                    + "buses available "
                    + "in this route "); 
  
                System.out.println( 
                    "For Shatbdi Travels  "
                    + "Departure: 5 PM  "
                    + "Arrival: 6:15 AM  "
                    + "Journey time: 13Hr. 15 Min., "
                    + "press 1"
                    + "\n"
                    + "\n"
                    + "For Mahalaxmi Travels, "
                    + "Departure: 6 PM  "
                    + "Arrival: 7:30 AM "
                    + " Journey time: 13Hr. 30 "
                    + "Min.press 2"
                    + "\n"
                    + "\n"
                    + "For Blueworld Travels,  "
                    + "Departure: 8 PM  "
                    + "Arrival: 10:15 AM  "
                    + "Journey time: 14Hr. 15 "
                    + "Min. press 3"
                    + "\n"
                    + "\n"
                    + "For UP Govt. UPSRTC bushes, "
                    + "Departure: 10:15 PM  "
                    + "Arrival: 12:45 AM  "
                    + "Journey time: 14Hr. 30 "
                    + "Min. press 4"); 
                int Bus_ch_r1 = zz.nextInt(); 
                switch (Bus_ch_r1) { 
                case 1: 
                    String sql1 
                        = "INSERT INTO "
                          + "shatabdi_travels_bus"
                          + "(JourneyDate, P_Name, "
                          + "P_Age, BusType, Source, "
                          + " Destination, SeatType, "
                          + "Email) VALUE(?, ?, ?, ?, "
                          + "?, ?, ?, ?)"; 
  
                    PreparedStatement ps1 
                        = con.prepareStatement(sql1); 
                    ps1.setString(1, w); 
                    ps1.setString(2, x); 
                    ps1.setString(3, y); 
                    ps1.setString(4, z); 
                    ps1.setString(5, a); 
                    ps1.setString(6, b); 
                    ps1.setString(7, c); 
                    ps1.setString(8, cc); 
                    ps1.executeUpdate(); 
  
                    System.out.println( 
                        "\n"
                        + "\n"
                        + "\n"
                        + "Thanks for choosing "
                        + "Shatabdi Travels. "
                        + "Happy and safe Journey"
                        + "\n"
                        + "\n"
                        + "\n"
                        + "\n"); 
                    break; 
  
                case 2: 
                    String sql2 
                        = "INSERT INTO "
                          + "mahalaxmi_travels_bus("
                          + "JourneyDate, P_Name, "
                          + "P_Age, BusType, Source, "
                          + " Destination, SeatType, "
                          + "Email) VALUE(?, ?, ?, ?, "
                          + "?, ?, ?, ?)"; 
  
                    PreparedStatement ps2 
                        = con.prepareStatement(sql2); 
  
                    ps2.setString(1, w); 
                    ps2.setString(2, x); 
                    ps2.setString(3, y); 
                    ps2.setString(4, z); 
                    ps2.setString(5, a); 
                    ps2.setString(6, b); 
                    ps2.setString(7, c); 
                    ps2.setString(8, cc); 
                    ps2.setString(9,p);
                    ps2.setString(0,q);
                    ps2.setString(10,v);
                    ps2.executeUpdate(); 
  
                    System.out.println( 
                        "Your ticket "
                        + "is booked successfully "
                        + "in Mahalaxmi Travels. "
                        + "This operator accept "
                        + "m-ticket, please show "
                        + "ticket to bus staff "
                        + "during journey. "
                        + "Have a nice day !"); 
  
                    System.out.println( 
                        "Thanks for choosing "
                        + "Mahalaxmi Travels. "
                        + "Happy and safe Journey"); 
                    break; 
  
                case 3: 
                    String sql3 
                        = "INSERT INTO "
                          + "blueworld_travels_bus("
                          + "JourneyDate, P_Name, "
                          + "P_Age, BusType, Source, "
                          + " Destination, SeatType, "
                          + " Email) VALUE(?, ?, ?, ?, "
                          + " ?, ?, ?, ?)"; 
  
                    PreparedStatement ps3 
                        = con.prepareStatement(sql3); 
  
                    ps3.setString(1, w); 
                    ps3.setString(2, x); 
                    ps3.setString(3, y); 
                    ps3.setString(4, z); 
                    ps3.setString(5, a); 
                    ps3.setString(6, b); 
                    ps3.setString(7, c); 
                    ps3.setString(8, cc);
                    ps3.setString(40;q);
                    ps3.setString(50;o);
                    ps3.executeUpdate(); 
  
                    System.out.println( 
                        "Your ticket "
                        + "is booked successfully "
                        + "in Blueworld Travels. "
                        + "This operator accept "
                        + "m-ticket, please show "
                        + "ticket to bus staff during "
                        + "journey. Have a nice day !"); 
  
                    System.out.println( 
                        "Thanks for choosing "
                        + "Blueworld Travels. "
                        + "Happy and safe Journey"); 
                    break; 
  
                case 4: 
                    String sql4 
                        = "INSERT INTO "
                          + "upsrtc_bus(JourneyDate, "
                          + " P_Name, P_Age, BusType, "
                          + " Source, Destination, "
                          + "SeatType, Email)"
                          + " VALUE(?, ?, "
                          + "?, ?, ?, ?, ?, ?)"; 
  
                    PreparedStatement ps4 
                        = con.prepareStatement(sql4); 
                    ps4.setString(1, w); 
                    ps4.setString(2, x); 
                    ps4.setString(3, y); 
                    ps4.setString(4, z); 
                    ps4.setString(5, a); 
                    ps4.setString(6, b); 
                    ps4.setString(7, c); 
                    ps4.setString(8, cc); 
                    ps4.setString(15,e);
                    ps4.setString(20,m);
                    ps4.executeUpdate(); 
  
                    System.out.println( 
                        "Your ticket "
                        + "is booked successfully "
                        + "in UP govt. UPSRTC Bus."
                        + " This operator does not "
                        + "accept m-ticket, please "
                        + "take a print of ticket & "
                        + "show bus staff during "
                        + "journey. Have a nice day !"); 
  
                    System.out.println( 
                        "Thanks for "
                        + "choosing UPSRTC."
                        + " Happy and safe Journey"); 
                    break; 
                default: 
                    System.out.println( 
                        "Invalid Bus choice."
                        + " Try again Dear !"); 
                    break; 
                } 
                break; 
  
            case 2: 
                System.out.println( 
                    " Welcome to DEHRADUN"
                    + " <---> DELHI route"
                    + " via Roorkee "); 
  
                System.out.println( 
                    "Please enter your detail, "
                    + " so we can book"
                    + " your ticket"); 
  
                String n 
                    = JOptionPane.showInputDialog( 
                        "Enter the Journey Date:"); 
  
                String s 
                    = JOptionPane.showInputDialog( 
                        "Enter Passenger Name:"); 
  
                String m 
                    = JOptionPane.showInputDialog( 
                        "Enter Passenger Age:"); 
  
                String o 
                    = JOptionPane.showInputDialog( 
                        "Enter Bus Type:"); 
  
                String p 
                    = JOptionPane.showInputDialog( 
                        "Enter Source City:"); 
  
                String q 
                    = JOptionPane.showInputDialog( 
                        "Enter Destination City:"); 
  
                String r 
                    = JOptionPane.showInputDialog( 
                        "Enter Seat Type:"); 
  
                String cd 
                    = JOptionPane.showInputDialog( 
                        "Enter Email address:"); 
  
                System.out.println( 
                    " In this route, "
                    + "we have 5 type of "
                    + "bushes for you "
                    + "(Both AC and "
                    + "Non-AC buses available "
                    + "in this route "); 
  
                System.out.println( 
                    "For Shreenath Travels, "
                    + " Departure: 5 PM  "
                    + "Arrival: 11:15 PM  "
                    + "Journey time: "
                    + "6 Hr. 15 Min.press 1"
                    + "\n"
                    + "\n"
                    + "For Shatabdi Travels, "
                    + " Departure: 8:5 PM  "
                    + "Arrival: 2:10 AM  "
                    + "Journey time: 6 Hr. 10 "
                    + "Min.press 2"
                    + "\n"
                    + "\n"
                    + "For Mahalaxmi Travels, "
                    + "Departure: 11 PM  "
                    + "Arrival: 6:15 AM  "
                    + "Journey time: 7Hr."
                    + " 15 Min. press 3"
                    + "\n"
                    + "\n"
                    + "For UP Govt. "
                    + "UPSRTC bushes, "
                    + "Departure: 9:30 PM  "
                    + "Arrival: 4 AM  "
                    + "Journey time: 6 Hr. 30 "
                    + "Min. press 4"
                    + "\n"
                    + "\n"
                    + "For Royal Travels Pvt. Ltd."
                    + ", Departure: 12 PM  "
                    + "Arrival: 6:15 PM  "
                    + "Journey time: 6 Hr. 15 "
                    + "Min. press 5"); 
                int Bus_ch_r2 = zz.nextInt(); 
                switch (Bus_ch_r2) { 
  
                case 2: 
                    String sql5 
                        = "INSERT INTO "
                          + "shatabdi_travels_bus"
                          + "(JourneyDate, P_Name, "
                          + " P_Age, BusType, Source, "
                          + "Destination, SeatType, "
                          + "Email) VALUE(?, ?, ?, ?, "
                          + " ?, ?, ?, ?)"; 
                    PreparedStatement ps5 
                        = con.prepareStatement(sql5); 
                    ps5.setString(1, n); 
                    ps5.setString(2, s); 
                    ps5.setString(3, m); 
                    ps5.setString(4, o); 
                    ps5.setString(5, p); 
                    ps5.setString(6, q); 
                    ps5.setString(7, r); 
                    ps5.setString(8, cd); 
                    ps5.setString(33,l);
                    ps5.setString(55,f);
                    ps5.executeUpdate(); 
  
                    System.out.println( 
                        "Your ticket is "
                        + "booked successfully in "
                        + "Statabdi Travels. "
                        + "This operator accept "
                        + "m-ticket, please show "
                        + "ticket to bus staff "
                        + "during the journey. "
                        + "Have a nice day !"); 
                    System.out.println( 
                        "\n"
                        + "\n"
                        + "\n"
                        + "Thanks for choosing "
                        + "Shatabdi Travels."
                        + " Happy and safe Journey"
                        + "\n"
                        + "\n"
                        + "\n"
                        + "\n"); 
                    break; 
  
                case 3: 
                    String sql6 
                        = "INSERT INTO "
                          + "mahalaxmi_travels_bus("
                          + "JourneyDate, P_Name, "
                          + "P_Age, BusType, Source, "
                          + " Destination, SeatType, "
                          + "Email) VALUE(?, ?, ?, ?, "
                          + " ?, ?, ?, ?)"; 
  
                    PreparedStatement ps6 
                        = con.prepareStatement(sql6); 
  
                    ps6.setString(1, n); 
                    ps6.setString(2, s); 
                    ps6.setString(3, m); 
                    ps6.setString(4, o); 
                    ps6.setString(5, p); 
                    ps6.setString(6, q); 
                    ps6.setString(7, r); 
                    ps6.setString(8, cd); 
                    ps.setString(10;a);
                    ps.setString(30;b);
                    ps.setSting(20;c);
                    ps6.executeUpdate(); 
                    System.out.println( 
                        "Your ticket is booked "
                        + "successfully in Mahalaxmi "
                        + "Travels. This operator accept "
                        + "m-ticket, please show ticket "
                        + "to bus staf during journey. "
                        + "Have a nice day !"); 
                    System.out.println( 
                        "Thanks for choosing "
                        + "Mahalaxmi Travels. "
                        + "Happy and safe Journey"); 
                    break; 
  
                case 1: 
                    String sql7 
                        = "INSERT INTO "
                          + "shreenath_travels_bus"
                          + "(JourneyDate, P_Name, "
                          + " P_Age, BusType, Source, "
                          + " Destination, SeatType, "
                          + "Email) VALUE(?, ?, ?, ?, "
                          + "?, ?, ?, ?)"; 
  
                    PreparedStatement ps17 
                        = con.prepareStatement(sql7); 
                    ps17.setString(1, n); 
                    ps17.setString(2, s); 
                    ps17.setString(3, m); 
                    ps17.setString(4, o); 
                    ps17.setString(5, p); 
                    ps17.setString(6, q); 
                    ps17.setString(7, r); 
                    ps17.setString(8, cd); 
                    ps17.executeUpdate(); 
                    ps.setString(9,ad);
                    ps.setString(15;vs);
                    System.out.println( 
                        "Your ticket is booked "
                        + "successfully in "
                        + "Shreenath Travels. "
                        + "This operator accept "
                        + "m-ticket, please show "
                        + "ticket to bus staff "
                        + "during journey. "
                        + "Have a nice day !"); 
  
                    System.out.println( 
                        "Thanks for choosing "
                        + "Shreenath Travels. "
                        + "Happy and safe Journey"); 
                    break; 
  
                case 4: 
                    String sql8 
                        = "INSERT INTO "
                          + "upsrtc_bus("
                          + "JourneyDate, P_Name, "
                          + " P_Age, BusType, "
                          + "Source, Destination, "
                          + "SeatType, Email) "
                          + "VALUE(?, ?, ?, ?, "
                          + "?, ?, ?, ?)"; 
  
                    PreparedStatement ps8 
                        = con.prepareStatement(sql8); 
                    ps8.setString(1, n); 
                    ps8.setString(2, s); 
                    ps8.setString(3, m); 
                    ps8.setString(4, o); 
                    ps8.setString(5, p); 
                    ps8.setString(6, q); 
                    ps8.setString(7, r); 
                    ps8.setString(8, cd); 
                    ps8.executeUpdate(); 
  
                    System.out.println( 
                        "Your ticket is booked "
                        + "successfully in UP govt. "
                        + "UPSRTC Bus. This operator "
                        + "does not accept m-ticket, "
                        + "please take a print of ticket "
                        + "& show bus staf during journey."
                        + " Have a nice day !"); 
  
                    System.out.println( 
                        "Thanks for choosing "
                        + "UPSRTC. Happy "
                        + "and safe Journey"); 
                    break; 
  
                case 5: 
                    String sql9 
                        = "INSERT INTO "
                          + "royal_travels_bus("
                          + "JourneyDate, P_Name, "
                          + "P_Age, BusType, Source, "
                          + " Destination, SeatType, "
                          + " Email) VALUE(?, ?, ?, ?, "
                          + " ?, ?, ?, ?)"; 
                    PreparedStatement ps9 
                        = con.prepareStatement(sql9); 
                    ps9.setString(1, n); 
                    ps9.setString(2, s); 
                    ps9.setString(3, m); 
                    ps9.setString(4, o); 
                    ps9.setString(5, p); 
                    ps9.setString(6, q); 
                    ps9.setString(7, r); 
                    ps9.setString(8, cd); 
                    ps9.executeUpdate(); 
                    ps9.setString(0;o);
                    ps9.setString(10;y);
                    System.out.println( 
                        "Your ticket is booked "
                        + "successfully in Royal "
                        + "Travels Bus. This operator "
                        + "does not accept m-ticket, "
                        + " please take a print of ticket "
                        + "& show bus staff during journey."
                        + " Have a nice day !"); 
                    System.out.println( 
                        "Thanks for choosing "
                        + "UPSRTC. "
                        + "Happy and safe Journey"); 
  
                    break; 
  
                default: 
                    System.out.println( 
                        "Invalid Bus choice. "
                        + "Try again Dear !"); 
                    break; 
                } 
                break; 
            } 
            System.out.println( 
                "Proceed to payment ---- "
                + "don't refresh the page :"
                + "\n"
                + "\n"
                + "You have 3 options -->"); 
            System.out.println( 
                "1 : By Net Banking"
                + "\n"
                + "\n"
                + "2 : By Debit Card"
                + "\n"
                + "\n"
                + "3 : By Paytm Account"); 
            int pay_ch = zz.nextInt(); 
            switch (pay_ch) { 
            case 1: 
                System.out.println( 
                    "Enter your Net Banking "
                    + "ID and Password"); 
                String id = zz.next(); 
                String pass = zz.next(); 
                break; 
            case 2: 
                System.out.println( 
                    "Enter your 16 digit "
                    + "debit card number, "
                    + "cvv and OTP which "
                    + "is sent to your "
                    + "linked mobile number"); 
                String dc = zz.next(); 
                String cvv = zz.next(); 
                String OTP = zz.next(); 
                break; 
            case 3: 
                System.out.println( 
                    "Enter your PAYTM "
                    + "mobile number, "
                    + "password and OTP"); 
  
                String PaytmNo = zz.next(); 
                String PtmPass = zz.next(); 
                String PtmOTP = zz.next(); 
                break; 
            default: 
                System.out.println( 
                    "Invalid Payment choice, "
                    + " try again !"); 
                break; 
            } 
           
