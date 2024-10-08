# Лабораторная работа №1. Создание activity и передача параметров между ними
Код приложения написан на языке Java и использует Android SDK.

## Инструкция по использованию приложения
1. Запустите приложение.
2. На первом экране нажмите на кнопку `btn1`.
3. При переходе на второй экран будет отображен переданный параметр в виде текста.
<p align="center">
<img src="https://github.com/user-attachments/assets/92b11613-753c-4403-be3c-d601d635fb03" width="250" height="500"> <img src="https://github.com/user-attachments/assets/7d600af7-6b87-428a-8ebe-3019893b74e3" width="250" height="500">
</p>

## Передача параметра
Передача параметра между двумя `Activity` реализована с помощью `Intent` и метода `PutExtra`. На `MainActivity` создается `Intent` с параметром, который передается в `MainActivity2`.
```java
// MainActivity
public void onClick(View v) {
     Intent intent = new Intent(MainActivity.this, MainActivity2.class);
     intent.putExtra("surname", "Новикова");
     startActivity(intent);
}

// MainActivity2
protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        String surname = getIntent().getStringExtra("surname");
        TextView textView = findViewById(R.id.textView);
        textView.setText(surname);
    }
