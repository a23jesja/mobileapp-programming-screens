
# Rapport

**Skriv din rapport här!**
Det som denna uppgift gick ut på var att skapa en ny activity, en knapp lades också till i den första activity "main"
som sedan kopplades till den nya activiten, inom detta skapades ett ID för knappen i activity main.xml, detta id användes för att länkas till en "onclicklistener". Denna onclicklistener utför en kodbit när själva knappen trycks på, detta blev möjligt med hjälp av "intent" på första activiten sedan på andra activiteten så tas innehållet emot i en "bundle".


```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button b = findViewById(R.id.mainknapp);

        b.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Log.d("==>","Klickat :D");
                Intent second = new Intent(MainActivity.this, SecondActivity.class);
                second.putExtra("text", "SecondActivity");
                startActivity(second);
            }
        });
    }
}

//andra aktiviteten

 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        Bundle extras = getIntent().getExtras();
        if (extras != null) {
            String name = extras.getString("text");
            Log.d("==>","Skickat :D value: " + name);
            TextView text = findViewById(R.id.textname);
            text.setText(name);
        }
    }
```



![](överblick.png)
![](andra%20aktiviteten.png) 

