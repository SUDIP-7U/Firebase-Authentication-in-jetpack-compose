
<img width="280" height="620" alt="Screenshot_20260228_175534" src="https://github.com/user-attachments/assets/beee2a51-b58f-465d-8f7e-42d7938e2c2f" />

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        //Use this line for firebase access
        
        FirebaseApp.initializeApp(this)
        setContent {
            AuthScreen()
        }
    }
    
FirebaseApp.initializeApp(this) লাইনটা ব্যবহার করা হয় Firebase SDK কে তোমার Android app এর সাথে initialize করার জন্য।

কেন দরকার?
Firebase Console থেকে তুমি যখন project বানাও আর google-services.json ফাইল app এ রাখো, তখন Firebase SDK সেই configuration ফাইল পড়ে।

কিন্তু SDK কে জানাতে হয় যে "এই app এখন Firebase এর সাথে connect হবে" — সেটাই করে FirebaseApp.initializeApp(this)।

একবার initialize হয়ে গেলে তুমি FirebaseAuth.getInstance(), FirebaseFirestore.getInstance() ইত্যাদি Firebase services ব্যবহার করতে পারো।

নোট:

অনেক সময় google-services plugin + Gradle setup থাকলে Firebase নিজে থেকেই initialize হয়ে যায়।

কিন্তু কিছু ক্ষেত্রে (বিশেষ করে custom setup বা multi-module project এ) manual initialization দরকার হয়।

👉 তাই এই লাইনটা basically Firebase কে তোমার app এ চালু করার জন্য দরকার।

Just ADD this dependencies 

dependencies {

    implementation(platform(libs.firebase.bom.v3351))

}

-dont use auth dependencies beacuse it will handle everything..
