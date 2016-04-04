# FluentManager
Tiny wrapper that lets you create and show snackbars in a fluent manner. Contains queue feature.

### All you need to know

```java
public class MainActivity extends AppCompatActivity {

    private FluentSnackbar mFluentSnackbar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mFluentSnackbar = new FluentSnackbar(this);

        mFluentSnackbar.create("Text")
                .maxLines(2) // default is 1 line
                .backgroundColorRes(R.color.purple_500) // default is #323232
                .textColorRes(R.color.blue_grey_500) // default is Color.WHITE
                .duration(Snackbar.LENGTH_SHORT) // default is Snackbar.LENGTH_LONG
                .actionTextColorRes(R.color.colorAccent)
                .important()
                .action(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        Toast.makeText(MainActivity.this, "Action clicked", Toast.LENGTH_SHORT).show();
                    }
                })
                .show();
    }
}

```

If you want to show several messages following one by one you can use `important()` method. Such snackbars cannot be dismissed by another snackbars and will be shown throughout their duration. 