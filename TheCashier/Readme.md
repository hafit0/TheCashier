# The Cashier

<n>

## Purpose
Aplikasi The Cashier berguna untuk menjumlahkan harga sehingga mendapatkan total dari harga yang harus dibayarkan 

## Features
* User dapat melakukan input nama ,harga , dan banyaknya barang/jasa 
* user mendapatkan output subtotal
* user mendapatkan output total harga

## How Does it Work?
Pada `Item.cs` terdapat kodingan sebagai berikut:

``` 
public double getSubTotal()
{
    subtotal = price * quantity;
    return subtotal;
}   
```
Kodingan diatas berrfungsi untuk mengandle subtotal atau total harga dari setiap barang

Sedangkan pada `Calculator.cs` terdapat kodingan yang berfungsi untuk menjumlahkan dari setiap subtotal  yang telah di inputkan yaitu terdapat pada

```
public void addItem(Item item)
        {
            this.listItem.Add(item);
            this.total += item.getSubTotal();
        }
```

Kemudian pada `MainWindow.xaml.cs` terdapat koding sebagai berikut :
```
 <TextBlock Grid.Column="0" Text="{Binding title}" TextAlignment="Left" />
 <TextBlock Grid.Column="1" Text="{Binding quantity}"  TextAlignment="Right"  />
 <TextBlock Grid.Column="2" Text="{Binding price}"  TextAlignment="Right" />
 <TextBlock Grid.Column="3" Text="{Binding subtotal}" TextAlignment="Right" />
```

Koding tersebut berfungsi untuk mengambil value yang diinput kan pada aplikasi tersebut. 


Prinsip penggunaan Single Reponsibility terdapat pada `class Calculator.cs` . Pada class ini digunakan untuk menambahkan item yang dimasukkan oleh user kedalam sebuah list dan menghitung total harganya

```
public void addItem(Item item)
        {
            this.listItem.Add(item);
            this.total += item.getSubTotal();
        }
```
