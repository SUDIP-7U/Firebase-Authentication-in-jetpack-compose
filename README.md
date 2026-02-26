class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        //Use this line for firebase access
        FirebaseApp.initializeApp(this)
        setContent {
            AuthScreen()
        }
    }


Just ADD this dependencies 

dependencies {

    implementation(platform(libs.firebase.bom.v3351))

}

-dont use auth dependencies beacuse it will handle everything..
