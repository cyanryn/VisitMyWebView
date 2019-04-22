# VisitMyWebView
访问自定义浏览器

```
package com.example.myapplication;

import android.content.Intent;
import android.net.Uri;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity implements View.OnClickListener{
    private EditText editText;
    private Button button;
    private String et_header = "http://";
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText_url);
        button = findViewById(R.id.button_view_browser);
        button.setOnClickListener(this);
    }

    @Override
    public void onClick(View v) {
        switch (v.getId()) {
            case R.id.button_view_browser:
                Intent intent = new Intent();
                intent.setAction("android.intent.action.VIEW");
                intent.setData(Uri.parse(et_header + editText.getText().toString()));
                Intent choose = Intent.createChooser(intent,"选择一个浏览器");
                startActivity(choose);
                break;
        }
    }
}

```

### 截图：
![](https://i.loli.net/2019/04/22/5cbdcd897f4d0.jpg)
![](https://i.loli.net/2019/04/22/5cbdcd89bb571.jpg)
