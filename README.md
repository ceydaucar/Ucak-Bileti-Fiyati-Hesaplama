# Ucak-Bileti-Fiyati-Hesaplama
Patika.dev > Java101 > Koşullu İfadeler ve Kod Blokları > Pratik7 - Uçak Bileti Fiyatı Hesaplama

## Java ile mesafeye ve şartlara göre uçak bileti fiyatı hesaplayan programı yapın. Kullanıcıdan Mesafe (KM), yaşı ve yolculuk tipi (Tek Yön, Gidiş-Dönüş) bilgilerini alın. Mesafe başına ücret 0,10 TL / km olarak alın. İlk olarak uçuşun toplam fiyatını hesaplayın ve sonrasında ki koşullara göre müşteriye aşağıdaki indirimleri uygulayın :

- Kullanıcıdan alınan değerler geçerli (mesafe ve yaş değerleri pozitif sayı, yolculuk tipi ise 1 veya 2) olmalıdır. Aksi takdirde kullanıcıya "Hatalı Veri Girdiniz !" şeklinde bir uyarı verilmelidir.
- Kişi 12 yaşından küçükse bilet fiyatı üzerinden %50 indirim uygulanır.
- Kişi 12-24 yaşları arasında ise bilet fiyatı üzerinden %10 indirim uygulanır.
- Kişi 65 yaşından büyük ise bilet fiyatı üzerinden %30 indirim uygulanır.
- Kişi "Yolculuk Tipini" gidiş dönüş seçmiş ise bilet fiyatı üzerinden %20 indirim uygulanır.


      import java.util.*;

      public class flight_cost_calculator {

        public static void main(String[] args) {

          Scanner sc= new Scanner(System.in);

          System.out.println("Enter the distance as kilometer: ");
          int km = sc.nextInt();

          System.out.println("Enter your age: ");
          int age = sc.nextInt();

          System.out.println("Enter travel type(1=> One Way, 2=> Round-Trip): ");
          int type = sc.nextInt();

          double cost;
          double discounted_cost = 0;
          double discounted_cost2;

          if(km > 0) {
            if(0 <= age && age < 12) {
              if(type == 1) {
                cost = km * 0.10;
                discounted_cost = cost - (cost * 0.50);
                System.out.println("Total cost: " + discounted_cost);
              }
              else if(type == 2) {
                cost = km * 0.10;
                discounted_cost = cost - (cost * 0.50);
                discounted_cost2 = (discounted_cost - (discounted_cost * 0.20)) *2;
                System.out.println("Total cost: "+ discounted_cost2);
              }
              else
              System.out.println("You Entered Wrong Data!");
            }
            
            else if(12 <= age && age < 24) {
              if(type == 1) {
                cost = km * 0.10;
                discounted_cost = cost - (cost * 0.10);
                System.out.println("Total cost: " + discounted_cost);
              }
              else if(type == 2) {
                cost = km * 0.10;
                discounted_cost = cost - (cost * 0.10);
                discounted_cost2 = (discounted_cost - (discounted_cost * 0.20)) * 2;
                System.out.println("Total cost: "+ discounted_cost2);
              }
              else
                System.out.println("You Entered Wrong Data!");
            }
            
            else if(age > 65) {
              if(type == 1) {
                cost = km * 0.10;
                discounted_cost = cost - (cost * 0.30);
                System.out.println("Total cost: " + discounted_cost);
              }
              else if(type == 2) {
                cost = km * 0.10;
                discounted_cost = cost - (cost * 0.30);
                discounted_cost2 = (discounted_cost - (discounted_cost * 0.20)) * 2;
                System.out.println("Total cost: "+ discounted_cost2);
              }
              else
                System.out.println("You Entered Wrong Data!");
            }
            
            else {
              cost = km * 0.10;
              System.out.println("Total cost: "+ cost);
            }

          }
          else
            System.out.println("You Entered Wrong Data!");
        }
        
      }
