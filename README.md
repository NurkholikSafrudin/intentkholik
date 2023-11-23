# intentkholik
Nama : nurkholik safrudin

NIM : 312210507

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Mobile 1

Tugas : Buatkanlah :

Launcher Splash logo masing-masing Individu

Buatkanlah untuk menampilkan semua project sebelum UTS dengan metode Ekplisit Intent dan

Implisit Intent:

a. Project Hallo

b. Project Count

c. Project Sianida

d. Project TwoActivity

e. Project Set Alarm

Untuk tampilan Layout Bebas, terima kasih. Launcher Splash Logo Pertama, yaitu membuat Launcher Splash Logo atau menampilkan logo / icon saat kita pertama kali membuka aplikasi. Caranya adalah : Persiapkan gambar terlebih dahulu Selanjutnya kita klik app, lalu klik res dan setelahnya kita pilih dan klik mipmap Setelah itu klik kanan pada bagian mipmap , lalu pilih new Lalu pilih dan klik Image Asset Lalu ketika sudah terbuka, kita klik bagian Icon Type lalu pilih yang Launcher Icons (Adaptive and Legacy) Lalu pada bagian Path kita klik logo file lalu kita pilih dan klik file gambar yang telah disiapkan sebelumnya dan klik OK Lalu untuk ukuran logo / ikon bisa kita atur pada bagian Resize, Jika sudah kita klik Next Setelah itu kita klik Finish, Maka logo / ikon aplikasi kita akan berubah sesuai gambar yang kita inginkan Untuk menambahkan file gambar seperti untuk SplashScreen, Background di setiap project kita bisa klik bagian Resource Manager lalu kita klik tanda +. Setelah itu kita pilih dan klik Import Drawables, setelah itu kita pilih dan klik file gambar yang sudah kita siapkan lalu klik OK. Maka gambar akan tersedia di res pada drawable.

Lalu buka backgroundlauncher.xml dan masukkan code ini :

Untuk Warna bisa kita sesuaikan dengan Logo yang telah kita tambahkan tadi Lalu, buka themes.xml yang letaknya ada di res/values/themes, dan tambahkan code ini didalam resourcesnya : <style name="SplashScreen" parent="Theme.MaterialComponents.DayNight.NoActionBar"> @drawable/bg2 ?attr/colorOnPrimary </style> Selanjutnya kita buat java class nya agar SplashScreen bisa berjalan, lalu pada SplashScreen.java kita masukkan code dibawah ini : package com.tgs9;

import android.content.Intent; import android.os.Bundle; import android.os.Handler;

import androidx.appcompat.app.AppCompatActivity;

public class SplashScreen extends AppCompatActivity { @Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState);

new Handler().postDelayed(new Runnable() {
    @Override
    public void run() {
        startActivity(new Intent(SplashScreen.this, MainActivity.class));
        finish();
    }
}, 2500);
} } Code di atas digukankan untuk menampilkan SplashScreen, ketika SplashScreen selesai dalam 2.5 detik maka akan langsung berpindah pada tampilan MainActivity.java.

Buka AndroidManifest.xml, dan tambahkan code berikut didalam application : Selesai sudah kita membuat perintah Launcher Splash Logo, Selanjutnya kita akan ke tahap berikutnya yaitu membuat menu untuk menampilkan semua project yang sudah dibuat pada pertemuan sebelumnya.

Menu Utama Yang kedua, disini kita akan membuat menu utamanya yang akan berjalan setelah SplashScreen Logo. Caranya adalah: Jika awal pembuatan project kita memilih template Empty Views Activity, maka pada layout otomatis terbuat file activity_main.xml dan pada java akan ada MainActivity.java. Maka langsung saja kita buka activity_main.xml, dan buat code seperti berikut ini:

Maka tampilannya akan seperti ini : WhatsApp Image 2023-11-19 at 19 11 46_b9d46af7 Setelah itu kita buka MainActivity.java untuk menambahkan code intent untuk masing-masing tombol : package com.tgs9;
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent; import android.os.Bundle; import android.view.View;

public class MainActivity extends AppCompatActivity {

@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main);

findViewById(R.id.btnSetAlarm).setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // Panggil metode untuk mengatur alarm
        setAlarm();
    }
});
} private void setAlarm() { Intent alarm = new Intent(android.provider.AlarmClock.ACTION_SET_ALARM); startActivity(alarm); }

public void btnHelloWorld(View view) { Intent helloworld = new Intent(MainActivity.this, HelloActivity.class); startActivity(helloworld); }

public void btnCount(View view) { Intent count = new Intent(MainActivity.this, CountActivity.class); startActivity(count); }

public void btnSianida(View view) { Intent sianida = new Intent(MainActivity.this, SianidaActivity.class); startActivity(sianida); }

public void btnTwoActivity(View view) { Intent twoact = new Intent(MainActivity.this, TwoActivity.class); startActivity(twoact); } } Button HelloWorld, Count, Sianida dan TwoActivity menggunakan Explicit Intent, dan project SetAlarm menggunakan Implicit Intent.

Menu halaman utama dan tombol-tombol aplikasi sudah berhasil dibuat. Maka selanjutnya yang kita lakukan adalah menambahkan coding pada AndroidManifest.xml agar aplikasi dapat berjalan.

AndroidManifest.xml Didalam AndroidManifest.xml kita tambahkan semua java class dari semua project kita sebelumnya. Berikut nama java class dari berbagai project yang telah saya buat: a. Project Hello World = HelloActivity.java b. Project Count = CountActivity.java c. Project Scroll Movie = SianidaActivity.java d. Project TwoActivity = TwoActivity.java dan Two2Activity.java e. Project Set Alarm = MainActivity.java (karena merupakan Implicit Intent, jadi code untuk set alarm langsung dibuat disini)

<activity
    android:name=".MainActivity"
    android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.SET_ALARM" />
        <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>
</activity>

<activity
    android:name=".HelloActivity"
    android:exported="true" />

<activity
    android:name=".TwoActivity"
    android:exported="true" />

<activity
    android:name=".Two2Activity"
    android:exported="true" />

<activity
    android:name=".CountActivity"
    android:exported="true" />

<activity
    android:name=".SianidaActivity"
    android:exported="true" />

<activity
    android:name=".SplashScreen"
    android:exported="true"
    android:theme="@style/SplashScreen">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
4. Code All Projects (Strings, Colors dan Dimens) Strings.xml TGS9INTENT Hello World!! Send Enter Your Message Here Message Received Reply Enter Your Reply Here Reply Received
Toast Count 1 Hello Toast! Restart Masukkan Angka Limit

Kasus Sianida ICE COLD!

Film dokumenter Ice Cold: Murder, Coffee and Jessica Wongso memaparkan pertanyaan tak terjawab tentang persidangan yang dilalui Jessica Wongso. Dengan menyajikan perspektif baru, film ini hadir bertahun-tahun setelah kematian sahabat Jessica, Wayan Mirna Salihin. Film ini menggambarkan bagaimana Jessica yang mengajak teman-temannya, termasuk Mirna, untuk bertemu setelah sekian lama tak berjumpa. Pertemuan di salah satu kafe di mal ibu kota tersebut pun berlangsung lancar, sebelum akhirnya Mirna pingsan sesaat setelah meminum kopi yang sebelumnya dipesan Jessica.Dokumenter ini turut menyajikan rekaman CCTV pada waktu kejadian, berbagai footage berita saat persidangan berlangsung, hingga wawancara eksklusif dengan beberapa sumber, termasuk Jessica Wongso.

Persidangan atas dugaan pembunuhan Mirna Salihin digelar lima bulan setelah kematiannya. Sidang tersebut melalui 32 kali persidangan dengan menghadirkan puluhan saksi di pengadilan. Hasilnya, Jessica Wongso divonis bersalah atas kematian Mirna dan dijatuhi hukuman 20 tahun penjara. Kasus yang berjalan cukup lama tersebut menyita banyak perhatian dari masyarakat Indonesia. Musababnya, banyak misteri tak terjawab selama rangkaian persidangan yang panjang tersebut. Salah satunya adalah mengenai akses untuk mendapatkan bubuk sianida yang tidak bisa didapatkan oleh orang sembarangan. Selain itu, motif Jessica di balik pembunuhan tersebut pun belum menemukan jawabannya.

Film dokumenter buatan Netflix ini menyoroti rangkaian persidangan yang saat itu menjadi sidang pertama yang disiarkan secara langsung di berbagai stasiun televisi Indonesia. Selain itu, kasus ini juga diliput secara intens oleh media massa, baik nasional maupun internasional.Tak hanya itu, pihak rumah produksi Beach House Pictures juga berhasil mendapatkan akses untuk mewawancarai Jessica Wongso secara langsung dari balik tahanan. Dalam video trailer yang diluncurkannya, ditampilkan juga sejumlah wawancara eksklusif yang dilakukan dengan beberapa narasumber. Mulai dari ayah dan saudara kembar Mirna Salihin, pengacara Jessica Wongso, jurnalis yang mendalami kasus tersebut, hingga bagaimana saat itu kasus ini begitu ramai diberitakan oleh media massa Indonesia dan internasional.

Colors.xml #FF000000 #FFFFFFFF #3700B3 #FFC0CB #3F5185 #303F9F #FF4081 #ABCBFA #E3A2ED #92A676 #8FC2EA #C2E69C #E6C18A Dimens.xml 10dp 5sp A. Code Project Hello World activity_hello.xml <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".HelloActivity">

</androidx.constraintlayout.widget.ConstraintLayout> HelloActivity.java

package com.tgs9;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class HelloActivity extends AppCompatActivity{ @Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_hello); } } B. Code Project Count activity_count.xml

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:ignore="ExtraText" tools:context=".CountActivity">

</androidx.constraintlayout.widget.ConstraintLayout> CountActivity.java

package com.tgs9;

import android.app.AlertDialog; import android.content.DialogInterface; import android.graphics.Color; import android.os.Bundle; import android.view.View; import android.widget.EditText; import android.widget.TextView; import androidx.appcompat.app.AppCompatActivity;

public class CountActivity extends AppCompatActivity { private TextView show_count; private int count = 1; private long fibNMinus1 = 1; private long fibNMinus2 = 1; private int limit = -1; // Inisialisasi limit dengan nilai default

@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_count);

show_count = findViewById(R.id.show_count);
}

public void countUp(View view) { if (count == 0) { show_count.setText("0"); } else if (count == 1) { show_count.setText("1"); } else { if (limit != -1 && count > limit) { // Jika count melebihi limit, atur ulang perhitungan count = 0; fibNMinus1 = 1; fibNMinus2 = 0; show_count.setText(getString(R.string.count_initial_value)); } else { long fibCurrent = fibNMinus1 + fibNMinus2; fibNMinus2 = fibNMinus1; fibNMinus1 = fibCurrent;

        //Mengatur warna teks berdasarkan angka Fibonacci
        int colorResId = R.color.colorAccent; // Warna Default
        switch (count % 11) {
            case 1:
                colorResId = R.color.colorAccent; // Warna Pink Tua
                break;
            case 2:
                colorResId = R.color.hijaumuda; // Warna Hijau Muda
                break;
            case 3:
                colorResId = R.color.purple; // Warna Ungu
                break;
            case 4:
                colorResId = R.color.salem; // Warna Salem
                break;
            case 5:
                colorResId = R.color.birumuda; // Warna Biru Muda
                break;
            case 6 :
                colorResId = R.color.kuning; // Warna Kuning
                break;
            case 7:
                colorResId = R.color.hijau; // Warna Hijau
                break;
            case 8:
                colorResId = R.color.cream; // Warna Cream
                break;
            case 9:
                colorResId = R.color.pink; // Warna Pink
                break;
            case 10:
                colorResId = R.color.biru; // Warna Biru
                break;
            case 11:
                colorResId = R.color.orange; // Warna Orange
                break;
        }
        show_count.setTextColor(getResources().getColor(colorResId));
        show_count.setText(String.valueOf(fibCurrent));
    }
}

count++;
}

public void back1(View view) { count = 1; fibNMinus1 = 1; fibNMinus2 = 0; show_count.setText(getString(R.string.count_initial_value)); }

public void setLimit(View view) { // Create and display a dialog to set the limit AlertDialog.Builder builder = new AlertDialog.Builder(this); builder.setTitle("Set Limit");

final EditText input = new EditText(this);
input.setInputType(android.text.InputType.TYPE_CLASS_NUMBER);
builder.setView(input);

builder.setPositiveButton("OK", new DialogInterface.OnClickListener() {
    @Override
    public void onClick(DialogInterface dialog, int which) {
        // Get the limit from the input and set it for calculations
        String limitStr = input.getText().toString();
        limit = Integer.parseInt(limitStr);
    }
});

builder.setNegativeButton("Cancel", new DialogInterface.OnClickListener() {
    @Override
    public void onClick(DialogInterface dialog, int which) {
        dialog.cancel();
    }
});

builder.show();
} } C. Code Project Scroll Movie activity_scrollmovie.xml

<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical">

    <TextView
        android:id="@+id/article_subheading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="@dimen/padding_regular"
        android:text="@string/article_subtitle"
        android:textAlignment="center"
        android:textAppearance="@android:style/TextAppearance.DeviceDefault"
        android:textColor="#1AA0C1" />

    <TextView
        android:id="@+id/article"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:autoLink="web"
        android:lineSpacingExtra="@dimen/line_spacing"
        android:padding="@dimen/padding_regular"
        android:text="@string/article_text"
        tools:ignore="VisualLintLongText" />
</LinearLayout>
SianidaActivity.java package com.tgs9;
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

public class SianidaActivity extends AppCompatActivity { @Override protected void onCreate(Bundle savedInstanceState){ super.onCreate(savedInstanceState); setContentView(R.layout.activity_scrollmovie); } } D. Code Project Two Activity activity_twoactivity.xml

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" android:layout_width="match_parent" android:layout_height="match_parent" xmlns:tools="http://schemas.android.com/tools" xmlns:app="http://schemas.android.com/apk/res-auto" tools:context=".TwoActivity">

</androidx.constraintlayout.widget.ConstraintLayout> activity_twoact2.xml

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" android:layout_width="match_parent" android:layout_height="match_parent" xmlns:tools="http://schemas.android.com/tools" xmlns:app="http://schemas.android.com/apk/res-auto" tools:context=".Two2Activity">

</androidx.constraintlayout.widget.ConstraintLayout> TwoActivity.java

package com.tgs9;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent; import android.os.Bundle; import android.util.Log; import android.view.View; import android.widget.EditText; import android.widget.TextView;

public class TwoActivity extends AppCompatActivity {

private static final String LOG_TAG = TwoActivity.class.getSimpleName();

public static final String EXTRA_MESSAGE = "com.example.android.Two2Activity.extra.MESSAGE";

public static final int TEXT_REQUEST = 1;

private EditText mMessageEditText;

private TextView mReplyHeadTextView;

private TextView mReplyTextView;

@Override protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_twoactivity);

mMessageEditText = findViewById(R.id.editText_main);
mReplyHeadTextView = findViewById(R.id.text_header_reply);
mReplyTextView = findViewById(R.id.text_message_reply);
}

public void LaunchSecondActivity(View view) { Log.d(LOG_TAG, "Button clicked!"); Intent intent = new Intent(this, Two2Activity.class); String message = mMessageEditText.getText().toString(); intent.putExtra(EXTRA_MESSAGE, message); startActivityForResult(intent, TEXT_REQUEST); }

@Override public void onActivityResult(int requestCode, int resultCode, Intent data) { super.onActivityResult(requestCode, resultCode, data);

if (requestCode == TEXT_REQUEST) {
    if (resultCode == RESULT_OK) {
        String reply = data.getStringExtra(Two2Activity.EXTRA_REPLY);

        mReplyHeadTextView.setVisibility(View.VISIBLE);
        mReplyTextView.setText(reply);
        mReplyTextView.setVisibility(View.VISIBLE);
    }
}
} } Two2Activity.java

package com.tgs9;

import android.content.Intent; import android.os.Bundle; import android.view.View; import android.widget.EditText; import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class Two2Activity extends AppCompatActivity {

public static final String EXTRA_REPLY ="com.example.android.Two2Activity.extra.REPLY"; public static final String EXTRA_MESSAGE ="com.example.android.Two2Activity.extra.MESSAGE"; private EditText mReply;

@Override protected void onCreate(Bundle savedInstanceState){ super.onCreate(savedInstanceState); setContentView(R.layout.activity_twoact2);

mReply = findViewById(R.id.editText_second);

Intent intent = getIntent();
String message = intent.getStringExtra(Two2Activity.EXTRA_MESSAGE);

TextView textView = findViewById(R.id.text_message);
textView.setText(message);
} public void returnReply(View view){ String reply = mReply.getText().toString(); Intent replyIntent = new Intent(); setResult(RESULT_OK, replyIntent); finish(); } } E. Code Project Set Alarm Pertama, buatlah button terlebih dahulu pada activity_main.xml, bersama dengan button aplikasi lainnya :

Lalu tambahkan code Implicit Intent pada MainActivity,java :

findViewById(R.id.btnSetAlarm).setOnClickListener(new View.OnClickListener() { @Override public void onClick(View v) { // Panggil metode untuk mengatur alarm setAlarm(); } }); } private void setAlarm() { Intent alarm = new Intent(android.provider.AlarmClock.ACTION_SET_ALARM); startActivity(alarm); } Selanjutnya buka AndroidManifest.xml dan tambahkan code untuk izin membuka Alarm : Tambahkan code berikut pada bagian application agar set alarm dapat berjalan : Hasil Run Berikut adalah hasil running dari aplikasi yang telah saya buat :


https://github.com/NurkholikSafrudin/intentkholik/assets/149698766/296fe8b6-0110-481b-b03f-84a332d2df47



sekian terima kasih.
