# Fibonacci# DeretBilanganFibonacci

Nama : Mohammad Azmi Abdussyukur

NIM : 312210109

Kelas : TI.22.A1

Mata Kuliah : Pemrograman Mobile 1

Tugas : Buatlah Method Program java Toast Number, dengan menghasilkan Bilangan Fibonacci

## Code pada menu program java class `(MainActivity.java)` :
```
package com.fibonacci;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    private int count = 1;
    private TextView showcount;
    private Button mbtnToast,mbtnCount, mbtnRestart;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_fibonacci);

        showcount = findViewById(R.id.show_count);
        mbtnToast = findViewById(R.id.button_toast);
        mbtnCount = findViewById(R.id.button_count);
        mbtnRestart = findViewById(R.id.button_kembali);

        mbtnToast.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                showToast();
            }
        });

        mbtnCount.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                countTop();
            }
        });
        mbtnRestart.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                count = 1;
                showcount.setText("1");
            }
        });
    }

    public void showToast() {
        Toast toast = Toast.makeText(this, "Bilangan Fibonacci", Toast.LENGTH_SHORT);
        toast.show();
    }
    public void countTop() {
        if (count < 0) {
            count = 0;
        }
        int result = generateFibonacci(count);
        showcount.setText(Integer.toString(result));
        count++;
    }

    private int generateFibonacci(int n) {
        if (n <= 0) {
            return 0;
        }
        else if (n == 1) {
            return 1;
        }

        int first = 1;
        int second = 1;

        for (int i = 2; i <= n; i++) {
            int next = first + second;
            first = second;
            second = next;
        }

        return second;
    }
}
```

## Code pada menu layout (activity_fibonacci.xml) :
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:background="@color/colorPrimary"
        android:onClick="showToast"
        android:textColor="@android:color/white"
        android:text="@string/button_label_toast"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="UsingOnClickInXml,VisualLintButtonSize"/>


    <Button
        android:id="@+id/button_count"
        android:layout_width="186dp"
        android:layout_height="51dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="4dp"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.061"
        app:layout_constraintStart_toStartOf="parent"
        tools:ignore="UsingOnClickInXml,VisualLintButtonSize" />

    <Button
        android:id="@+id/button_kembali"
        android:layout_width="179dp"
        android:layout_height="53dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="4dp"
        android:background="@color/colorPrimary"
        android:onClick="Restart"
        android:text="@string/button_label_kembali"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.97"
        app:layout_constraintStart_toStartOf="parent"
        tools:ignore="UsingOnClickInXml,VisualLintButtonSize" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="#FFFF00"
        android:gravity="center_vertical"
        android:text="@string/count_initial_values"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@id/button_count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/button_toast"
        tools:ignore="RtlCompat" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## Code pada menu values (strings.xml) :
```
<resources>
    <string name="app_name">Fibonacci</string>
    <string name="button_label_toast">Toast</string>
    <string name="button_label_count">Count</string>
    <string name="button_label_kembali">Restart</string>
    <string name="count_initial_values">1</string>
    <string name="toast_message">Bilangan Fibonacci</string>
</resources>
```

## Code pada menu values (colors.xml) :
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="blue">#3700B3</color>
    <color name="pink">#FFC0CB</color>
    <color name="colorPrimary">#3F5185</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
</resources>
```


## Hasil run program bilangan Fibonacci :



https://github.com/MohAzmii04/Fibonacci/assets/115864496/b07573d7-286a-4416-a414-83625cbb0b17



## Finish, Terima Kasih



