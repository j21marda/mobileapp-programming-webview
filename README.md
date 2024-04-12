
# Rapport

```
Jag har ändrat appens namn till "MinApp" genom att ändrade på stringen kallad app_name

```
<resources>
    <string name="app_name">MinApp</string>
    <string name="action_external_web">External Web Page</string>
    <string name="action_internal_web">Internal Web Page</string>
</resources>
```

Jag har också möjligjort internetåtkomst för appen inuti AndroidManifest.xml
```
   <uses-permission android:name="android.permission.INTERNET" />
```
Jag skapade ett webview element samt gav den ett id inuti activity_main.xml genom att ersätta ett Textview element
```
    <WebView
        android:id="@+id/my_webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
```
Inuti MainActivity.Java gjordes variabeln myWebView som inuti OnCreate används för att webbsidor ska kunna visas i appen med en webbklient. 
En referens görs till elementet som gjordes tidigare med ett ID. Java inställningar sätts till true.
```
       myWebView = findViewById(R.id.my_webview);
        WebSettings webSettings = myWebView.getSettings();
        webSettings.setJavaScriptEnabled(true);
        myWebView.setWebViewClient(new WebViewClient()); // Do not open in Chrome!
```

Internal och external webbsida implementeras med en url, sedan kallas funktionerna inuti onOptionsSelected
```
    public void showExternalWebPage(){
        // TODO: Add your code for showing external web page here
        myWebView.loadUrl("https://his.se");
    }

    public void showInternalWebPage(){
        // TODO: Add your code for showing internal web page here
        myWebView.loadUrl("https://his.se");
    }
    
    //inuti onOptionsSelected
    if (id == R.id.action_external_web) {
            Log.d("==>","Will display external web page");
            showExternalWebPage();
            return true;
        }
    
```

en html-fil lades in i projektet genom att skapa en asset folder och lägga till en ny fil inuti den.


![img_1.png](img_1.png ext)
![img_2.png](img_2.png int)

