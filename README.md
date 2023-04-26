# Experiment 5
<pre>
import 'package:flutter/material.dart';  
void main() {  
runApp(const MyApp());  
}  
class MyApp extends StatelessWidget {  
const MyApp({super.key});  
// This widget is the root of your application.  
@override  
Widget build(BuildContext context) {  
return MaterialApp(  
title: 'Flutter Demo',  
theme: ThemeData(  
primarySwatch: Colors.amber,  
),  
home: const MyHomePage(title: 'Login Page'),  
);  
}  
}  
class MyHomePage extends StatefulWidget {  
const MyHomePage({super.key, required this.title});  
final String title;  
@override  
State<MyHomePage> createState() => _MyHomePageState();  
}  
class _MyHomePageState extends State<MyHomePage> {  
String name = " ";  
String pass = " ";  
bool changebutton = false;  
final _formkey = GlobalKey<FormState>();
animate(BuildContext context) async {
if (_formkey.currentState!.validate()) {
setState(() {
changebutton = true;
});
await Future.delayed(Duration(seconds: 1));
setState(() {
changebutton = false;
});
}
}
@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
title: Text(widget.title),
),
body: SingleChildScrollView(
child: Form(
key: _formkey,
child: Column(
// ignore: prefer_const_literals_to_create_immutables
children: [
Image.asset(
"assets/img/profile(1).png",
height: 200,
width: 275,
),
SizedBox(height: 20),
Text(
"Welcome $name",
style: TextStyle(
fontSize: 20,
color: Colors.black,
fontWeight: FontWeight.normal),
),
SizedBox(height: 20),
Padding(
padding: const EdgeInsets.all(16.0),
child: Column(
children: [
TextFormField(
decoration: InputDecoration(
hintText: "Enter UserName",
labelText: "UserName "),
validator: (value) {
if (value!.isEmpty) {
return "Username cannot be empty";
}
return null;
},
onChanged: (value) {
name = value;
setState(() {});
},
),
TextFormField(
obscureText: true,
decoration: InputDecoration(
hintText: "Enter Password",
labelText: "Password "),
validator: (value) {
if (value!.isEmpty) {
return "Password cannot be empty";
} else if (value.length < 8) {
return " Password length should be atleast 8";
}
return null;
},
onChanged: (value) {
pass = value;
setState(() {});
},
),
SizedBox(
height: 20,
),
InkWell(
onTap: () => {animate(context), print(name), print(pass)},
child: AnimatedContainer(
duration: Duration(seconds: 1),
width: changebutton ? 50 : 150,
height: 50,
alignment: Alignment.center,
child: changebutton
? Icon(Icons.done, color: Colors.white)
: Text(
"Login",
style: TextStyle(
color: Colors.white,
fontWeight: FontWeight.bold),
),
decoration: BoxDecoration(
color: Colors.amber,
borderRadius: BorderRadius.circular(
changebutton ? 50 : 8),
)),
)
],
),
)
]),
),
),
);
}
}
</pre>


# Experiment 1
<pre>
import 'package:flutter/material.dart';
void main() { runApp(const
MyApp());
}
class MyApp extends StatelessWidget {
const MyApp({super.key});
// This widget is the root of your application. @override
Widget build(BuildContext context) {
return MaterialApp(
title: 'Flutter Exp1 ',
theme: ThemeData(
primarySwatch: Colors.blue,
),
home: const MyHomePage(title: 'Flutter Exp1'),
);
}
}
class MyHomePage extends StatefulWidget {
const MyHomePage({super.key, required this.title});
final String title;
@override
State<MyHomePage> createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> {
@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
// Here we take the value from the MyHomePage object that was created by
// the App.build method, and use it to set our appbar title.title:
Text(widget.title),
),
body: Column(
children: [
Text('Hello World !! Welcome Vishaaall')
],
Output :
Conclusion : Therefore we have successfully installed Android studio andflutter
and created first hello world app.
),
// This trailing comma makes auto-formatting nicer for build methods.
);
}
}
}
</pre>

# Experiment 3
import 'package:flutter/material.dart';
void main() {
runApp(const MyApp());
}
class MyApp extends StatelessWidget {
const MyApp({super.key});
// This widget is the root of your application.
@override
Widget build(BuildContext context) {
return MaterialApp(
title: 'Flutter Demo',
theme: ThemeData(
// This is the theme of your application.
//
// Try running your application with "flutter run". You'll see the
// application has a blue toolbar. Then, without quitting the app, try
// changing the primarySwatch below to Colors.green and then invoke
// "hot reload" (press "r" in the console where you ran "flutter run",
// or simply save your changes to "hot reload" in a Flutter IDE).
// Notice that the counter didn't reset back to zero; the application
// is not restarted.
primarySwatch: Colors.blue,
),
home: const MyHomePage(title: 'Flutter Demo Home Page'),
);
}
}
class MyHomePage extends StatefulWidget {
const MyHomePage({super.key, required this.title});
// This widget is the home page of your application. It is stateful, meaning
// that it has a State object (defined below) that contains fields that
affect
// how it looks.
// This class is the configuration for the state. It holds the values (in
this
// case the title) provided by the parent (in this case the App widget) and
// used by the build method of the State. Fields in a Widget subclass are
// always marked "final".
final String title;
@override
State<MyHomePage> createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> {
int _counter = 0;
void _incrementCounter() {
setState(() {
// This call to setState tells the Flutter framework that something has
// changed in this State, which causes it to rerun the build method below
// so that the display can reflect the updated values. If we changed
// _counter without calling setState(), then the build method would not
be
// called again, and so nothing would appear to happen.
_counter++;
});
}
@override
Widget build(BuildContext context) {
// This method is rerun every time setState is called, for instance as done
// by the _incrementCounter method above.
//
// The Flutter framework has been optimized to make rerunning build methods
// fast, so that you can just rebuild anything that needs updating rather
// than having to individually change instances of widgets.
return Scaffold(
appBar: AppBar(
title: Text('Flutter Button'),
),
body: Column(
children: [
Row(
children: [
SizedBox(width: 30),
ElevatedButton(
onPressed:() {
showDialog(
context: context,
builder: (ctx)=> AlertDialog(
title: const Text('You clicked on the Phone Button')
));
},
child: Text('Phone')
),
SizedBox( width:20),
ElevatedButton.icon(
onPressed: (){
showDialog(
context: context,
builder: (ctx)=> AlertDialog(
title: const Text('You clicked on the Phone Button')
));
},
icon: Icon(
Icons.phone
),
label: Text('Phone'))
],
),
Row(
children: [
SizedBox(width: 30),
TextButton(
onPressed:() {
showDialog(
context: context,
builder: (ctx)=> AlertDialog(
title: const Text('You clicked on the Mail Button')
));
},
child: Text('Mail')
),
SizedBox( width:20),
TextButton.icon(
onPressed: (){
showDialog(
context: context,
builder: (ctx)=> AlertDialog(
title: const Text('You clicked on the Mail Button')
));
},
icon: Icon(
Icons.mail
),
label: Text('Mail'))
],
),
Row(
children: [
SizedBox(width: 30),
OutlinedButton(
onPressed:() {
showDialog(
context: context,
builder: (ctx)=> AlertDialog(
title: const Text('You clicked on the Download
Button')
));
},
child: Text('Download')
),
SizedBox( width:20),
OutlinedButton.icon(
onPressed: (){
showDialog(
context: context,
builder: (ctx)=> AlertDialog(
title: const Text('You clicked on the Download
Button')
));
},
icon: Icon(
Icons.download
),
label: Text('Download'))
],
)
],
)
, // This trailing comma makes auto-formatting nicer for build methods.
);
}
}

# Experiment 
class MyHomePage extends StatefulWidget {
const MyHomePage({super.key, required this.title});
final String title;
@override
State<MyHomePage> createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> {
@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
title: Text(widget.title),
),
body: Column(
children: [
Container(
padding: EdgeInsets.all(20),
margin: EdgeInsets.fromLTRB(10, 10, 10, 10),
width: 500,
decoration: BoxDecoration(
border: Border.all(color: Colors.purple),
borderRadius: BorderRadius.circular(20),
),
alignment: Alignment.center,
child: Text("Rahul Sarvaiya",style: TextStyle(fontWeight: FontWeight.bold,fontSize: 30,fontStyle:
FontStyle.italic),),
),
Container(
padding: EdgeInsets.all(20),
margin: EdgeInsets.fromLTRB(10, 10, 10, 10),
width: 500,
decoration: BoxDecoration(
border: Border.all(color: Colors.purple),
borderRadius: BorderRadius.circular(20),
color: Colors.purple,
boxShadow: [
new BoxShadow(color: Colors.pinkAccent, offset: new Offset(3.0, 3.0),),
],
),
alignment: Alignment.center,
child: Image.asset('assets/img/img.png',width: 300),
),
Container(
padding: EdgeInsets.all(10),
margin: EdgeInsets.fromLTRB(10, 0, 10, 10),
width: 500,
child: Text("A college is an educational institution or a constituent part of one. A college may be a
degree-awarding tertiary educational institution, a part of a collegiate or federal university, an institution
offering vocational education, or a secondary school.",style: TextStyle(fontWeight: FontWeight.bold,fontSize:
15,),),
)
],
),
// This trailing comma makes auto-formatting nicer for build methods.
);
}
}

#  To connect flutter UI with firebase database.

## Main dart

<pre>

// @dart=2.9
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';
import 'welcome_screen.dart';
import 'home_screen.dart';
import 'signup_screen.dart';
import 'login_screen.dart';
void main() async {
WidgetsFlutterBinding.ensureInitialized();
await Firebase.initializeApp();
runApp(MyApp());
}
class MyApp extends StatelessWidget {
// This widget is the root of your application.
@override
Widget build(BuildContext context) {
return MaterialApp(
initialRoute: 'welcome_screen',
routes: {
'welcome_screen': (context) => WelcomeScreen(),
'registration_screen': (context) => RegistrationScreen(),
'login_screen': (context) => LoginScreen(),
'home_screen': (context) => HomeScreen()
},
);
}
}
Welcome_screen.dart
import 'package:flutter/material.dart';
class WelcomeScreen extends StatefulWidget {
@override
_WelcomeScreenState createState() => _WelcomeScreenState();
}
class _WelcomeScreenState extends State<WelcomeScreen> {
@override
Widget build(BuildContext context) {
return Scaffold(
backgroundColor: Colors.white,
body: Padding(
padding: EdgeInsets.symmetric(horizontal: 24.0),
child: Column(
mainAxisAlignment: MainAxisAlignment.center,
crossAxisAlignment: CrossAxisAlignment.stretch,
children: <Widget>[
ElevatedButton(
//colour: Colors.lightBlueAccent,
child: Text('Log In'),
onPressed: () {
Navigator.pushNamed(context, 'login_screen');
},
),
ElevatedButton(
//colour: Colors.blueAccent,
child: Text('Register'),
onPressed: () {
Navigator.pushNamed(context, 'registration_screen');
}),
]),
));
}
}
login_screen.dart
import 'package:firebase_auth/firebase_auth.dart';
import 'package:modal_progress_hud/modal_progress_hud.dart';
import 'package:flutter/material.dart';
//code for designing the UI of our text field where the user writes his
email id or password
const kTextFieldDecoration = InputDecoration(
hintText: 'Enter a value',
hintStyle: TextStyle(color: Colors.grey),
contentPadding: EdgeInsets.symmetric(vertical: 10.0, horizontal: 20.0),
border: OutlineInputBorder(
borderRadius: BorderRadius.all(Radius.circular(32.0)),
),
enabledBorder: OutlineInputBorder(
borderSide: BorderSide(color: Colors.lightBlueAccent, width: 1.0),
borderRadius: BorderRadius.all(Radius.circular(32.0)),
),
focusedBorder: OutlineInputBorder(
borderSide: BorderSide(color: Colors.lightBlueAccent, width: 2.0),
borderRadius: BorderRadius.all(Radius.circular(32.0)),
));
class LoginScreen extends StatefulWidget {
@override
_LoginScreenState createState() => _LoginScreenState();
}
final _auth = FirebaseAuth.instance;
class _LoginScreenState extends State<LoginScreen> {
late String email;
late String password;
bool showSpinner = false;
@override
Widget build(BuildContext context) {
return Scaffold(
backgroundColor: Colors.white,
body: ModalProgressHUD(
inAsyncCall: showSpinner,
child: Padding(
padding: EdgeInsets.symmetric(horizontal: 24.0),
child: Column(
mainAxisAlignment: MainAxisAlignment.center,
crossAxisAlignment: CrossAxisAlignment.stretch,
children: <Widget>[
TextField(
keyboardType: TextInputType.emailAddress,
textAlign: TextAlign.center,
onChanged: (value) {
email = value;
//Do something with the user input.
},
decoration: kTextFieldDecoration.copyWith(
hintText: 'Enter your email',
)),
SizedBox(
height: 8.0,
),
TextField(
obscureText: true,
textAlign: TextAlign.center,
onChanged: (value) {
password = value;
//Do something with the user input.
},
decoration: kTextFieldDecoration.copyWith(
hintText: 'Enter your password.')),
SizedBox(
height: 24.0,
),
ElevatedButton(
//colour: Colors.lightBlueAccent,
child:Text('Log In'),
onPressed: () async {
setState(() {
showSpinner = true;
});
try {
final user = await _auth.signInWithEmailAndPassword(
email: email, password: password);
if (user != null) {
Navigator.pushNamed(context, 'home_screen');
}
} catch (e) {
print(e);
}
setState(() {
showSpinner = false;
});
}),
],
),
),
),
);
}
}
</pre>

## sign up screen

<pre>

import 'package:flutter/material.dart';
import 'package:firebase_auth/firebase_auth.dart';
import 'package:modal_progress_hud/modal_progress_hud.dart';
//code for designing the UI of our text field where the user writes his
email id or password
const kTextFieldDecoration = InputDecoration(
hintText: 'Enter a value',
hintStyle: TextStyle(color: Colors.grey),
contentPadding: EdgeInsets.symmetric(vertical: 10.0, horizontal: 20.0),
border: OutlineInputBorder(
borderRadius: BorderRadius.all(Radius.circular(32.0)),
),
enabledBorder: OutlineInputBorder(
borderSide: BorderSide(color: Colors.lightBlueAccent, width: 1.0),
borderRadius: BorderRadius.all(Radius.circular(32.0)),
),
focusedBorder: OutlineInputBorder(
borderSide: BorderSide(color: Colors.lightBlueAccent, width: 2.0),
borderRadius: BorderRadius.all(Radius.circular(32.0)),
),
);
class RegistrationScreen extends StatefulWidget {
@override
_RegistrationScreenState createState() => _RegistrationScreenState();
}
class _RegistrationScreenState extends State<RegistrationScreen> {
final _auth = FirebaseAuth.instance;
late String email;
late String password;
bool showSpinner = false;
@override
Widget build(BuildContext context) {
return Scaffold(
backgroundColor: Colors.white,
body: ModalProgressHUD(
inAsyncCall: showSpinner,
child: Padding(
padding: EdgeInsets.symmetric(horizontal: 24.0),
child: Column(
mainAxisAlignment: MainAxisAlignment.center,
crossAxisAlignment: CrossAxisAlignment.stretch,
children: <Widget>[
TextField(
keyboardType: TextInputType.emailAddress,
textAlign: TextAlign.center,
onChanged: (value) {
email = value;
},
decoration: kTextFieldDecoration.copyWith(
hintText: 'Enter your email')),
SizedBox(
height: 8.0,
),
TextField(
obscureText: true,
textAlign: TextAlign.center,
onChanged: (value) {
password = value;
},
decoration: kTextFieldDecoration.copyWith(
hintText: 'Enter your Password')),
SizedBox(
height: 24.0,
),
ElevatedButton(
//colour: Colors.blueAccent,
child: Text('Register'),
onPressed: () async {
setState(() {
showSpinner = true;
});
try {
final newUser = await
_auth.createUserWithEmailAndPassword(
email: email, password: password);
if (newUser != null) {
Navigator.pushNamed(context, 'home_screen');
}
} catch (e) {
print(e);
}
setState(() {
showSpinner = false;
});
},
)
],
),
),
),
);
}
}
</pre>

## Home screen
<pre>
import 'package:flutter/material.dart';
import 'package:firebase_auth/firebase_auth.dart';
User loggedinUser= loggedinUser;
class HomeScreen extends StatefulWidget {
@override
_HomeScreenState createState() => _HomeScreenState();
}
class _HomeScreenState extends State<HomeScreen> {
final _auth = FirebaseAuth.instance;
void initState() {
super.initState();
getCurrentUser();
}
//using this function you can use the credentials of the user
void getCurrentUser() async {
try {
final user = await _auth.currentUser;
if (user != null) {
loggedinUser = user;
}
} catch (e) {
print(e);
}
}
@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
leading: null,
actions: <Widget>[
IconButton(
icon: Icon(Icons.close),
onPressed: () {
_auth.signOut();
Navigator.pop(context);
//Implement logout functionality
}),
],
title: Text('Home Page'),
backgroundColor: Colors.lightBlueAccent,
),
body: Center(
child: Text(
"Welcome User",
style: TextStyle(fontSize: 20.0, fontWeight: FontWeight.bold),
),
),
);
}
}
</pre>

# To test and deploy production ready Flutter App on Android platform.
<pre>

import ...
Future<void> main() async {
WidgetsFlutterBinding.ensureInitialized();
Paint.enableDithering = true;
if (Platform.isWindows || Platform.isLinux || Platform.isMacOS) {
await Hive.initFlutter('BlackHole');
} else {
await Hive.initFlutter();
}
await openHiveBox('settings');
await openHiveBox('downloads');
await openHiveBox('stats');
await openHiveBox('Favorite Songs');
await openHiveBox('cache', limit: true);
await openHiveBox('ytlinkcache', limit: true);
if (Platform.isAndroid) {
setOptimalDisplayMode();
}
await startService();
runApp(MyApp());
}
Future<void> setOptimalDisplayMode() async {
await FlutterDisplayMode.setHighRefreshRate();
}
Future<void> startService() async {
await initializeLogging();
final AudioPlayerHandler audioHandler = await AudioService.init(
builder: () => AudioPlayerHandlerImpl(),
config: AudioServiceConfig(
androidNotificationChannelId: 'com.shadow.blackhole.channel.audio',
androidNotificationChannelName: 'BlackHole',
androidNotificationIcon: 'drawable/ic_stat_music_note',
androidShowNotificationBadge: true,
androidStopForegroundOnPause: false,
// Hive.box('settings').get('stopServiceOnPause', defaultValue: true)
as bool,
notificationColor: Colors.grey[900],
),
);
GetIt.I.registerSingleton<AudioPlayerHandler>(audioHandler);
GetIt.I.registerSingleton<MyTheme>(MyTheme());
}
Future<void> openHiveBox(String boxName, {bool limit = false}) async {
final box = await Hive.openBox(boxName).onError((error, stackTrace) async
{
Logger.root.severe('Failed to open $boxName Box', error, stackTrace);
final Directory dir = await getApplicationDocumentsDirectory();
final String dirPath = dir.path;
File dbFile = File('$dirPath/$boxName.hive');
File lockFile = File('$dirPath/$boxName.lock');
if (Platform.isWindows || Platform.isLinux || Platform.isMacOS) {
dbFile = File('$dirPath/BlackHole/$boxName.hive');
lockFile = File('$dirPath/BlackHole/$boxName.lock');
}
await dbFile.delete();
await lockFile.delete();
await Hive.openBox(boxName);
throw 'Failed to open $boxName Box\nError: $error';
});
// clear box if it grows large
if (limit && box.length > 500) {
box.clear();
}
}
class MyApp extends StatefulWidget {
@override
_MyAppState createState() => _MyAppState();
static _MyAppState of(BuildContext context) =>
context.findAncestorStateOfType<_MyAppState>()!;
}
class _MyAppState extends State<MyApp> {
Locale _locale = const Locale('en', '');
late StreamSubscription _intentTextStreamSubscription;
late StreamSubscription _intentDataStreamSubscription;
final GlobalKey<NavigatorState> navigatorKey =
GlobalKey<NavigatorState>();
@override
void dispose() {
_intentTextStreamSubscription.cancel();
_intentDataStreamSubscription.cancel();
super.dispose();
}
@override
void initState() {
super.initState();
final String systemLangCode = Platform.localeName.substring(0, 2);
if (ConstantCodes.languageCodes.values.contains(systemLangCode)) {
_locale = Locale(systemLangCode);
} else {
final String lang =
Hive.box('settings').get('lang', defaultValue: 'English') as
String;
_locale = Locale(ConstantCodes.languageCodes[lang] ?? 'en');
}
AppTheme.currentTheme.addListener(() {
setState(() {});
});
// For sharing or opening urls/text coming from outside the app while
the app is in the memory
_intentTextStreamSubscription =
ReceiveSharingIntent.getTextStream().listen(
(String value) {
Logger.root.info('Received intent on stream: $value');
handleSharedText(value, navigatorKey);
},
onError: (err) {
Logger.root.severe('ERROR in getTextStream', err);
},
);
// For sharing files coming from outside the app while the app is in the
memory
_intentDataStreamSubscription =
ReceiveSharingIntent.getMediaStream().listen(
(List<SharedMediaFile> value) {
if (value.isNotEmpty) {
for (final file in value) {
if (file.path.endsWith('.json')) {
final List playlistNames = Hive.box('settings')
.get('playlistNames')
?.toList() as List? ??
['Favorite Songs'];
importFilePlaylist(
null,
playlistNames,
path: file.path,
pickFile: false,
).then(
(value) =>
navigatorKey.currentState?.pushNamed('/playlists'),
);
}
}
}
},
onError: (err) {
Logger.root.severe('ERROR in getDataStream', err);
},
);
void setLocale(Locale value) {
setState(() {
_locale = value;
});
}
Widget initialFuntion() {
return Hive.box('settings').get('userId') != null
? HomePage()
: AuthScreen();
}
@override
Widget build(BuildContext context) {
SystemChrome.setSystemUIOverlayStyle(
SystemUiOverlayStyle(
statusBarColor: Colors.transparent,
systemNavigationBarColor: AppTheme.themeMode == ThemeMode.dark
? Colors.black38
: Colors.white,
statusBarIconBrightness: AppTheme.themeMode == ThemeMode.dark
? Brightness.light
: Brightness.dark,
systemNavigationBarIconBrightness: AppTheme.themeMode ==
ThemeMode.dark
? Brightness.light
: Brightness.dark,
),
);
SystemChrome.setPreferredOrientations([
DeviceOrientation.portraitUp,
DeviceOrientation.portraitDown,
DeviceOrientation.landscapeLeft,
DeviceOrientation.landscapeRight,
]);
return MaterialApp(
title: 'BlackHole',
restorationScopeId: 'blackhole',
debugShowCheckedModeBanner: false,
themeMode: AppTheme.themeMode,
theme: AppTheme.lightTheme(
context: context,
),
darkTheme: AppTheme.darkTheme(
context: context,
),
locale: _locale,
localizationsDelegates: const [
AppLocalizations.delegate,
GlobalMaterialLocalizations.delegate,
GlobalWidgetsLocalizations.delegate,
GlobalCupertinoLocalizations.delegate,
],
supportedLocales: ConstantCodes.languageCodes.entries
.map((languageCode) => Locale(languageCode.value, ''))
.toList(),
routes: {
'/': (context) => initialFuntion(),
'/pref': (context) => const PrefScreen(),
'/setting': (context) => const SettingPage(),
'/about': (context) => AboutScreen(),
'/playlists': (context) => PlaylistScreen(),
'/nowplaying': (context) => NowPlaying(),
'/recent': (context) => RecentlyPlayed(),
'/downloads': (context) => const Downloads(),
'/stats': (context) => const Stats(),
},
navigatorKey: navigatorKey,
onGenerateRoute: (RouteSettings settings) {
if (settings.name == '/player') {
return PageRouteBuilder(
opaque: false,
pageBuilder: (_, __, ___) => const PlayScreen(),
);
}
return HandleRoute.handleRoute(settings.name);
},
);
}
}
</pre>


# To create a responsive User Interface for Ecommerce applications.
<pre>

import 'package:day16_shopping/Pages/home_page.dart';
import 'package:day16_shopping/Pages/not_found.dart';
import 'package:day16_shopping/Pages/welcome.dart';
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'app_state.dart';
class App extends StatefulWidget {
@override
_AppState createState() => _AppState();
}
class _AppState extends State<App> {
Map<String, WidgetBuilder> _routes;
AppState _state;
@override
void initState() {
super.initState();
_state = AppState();
_routes = {
WelcomePage.routeName: (_) => WelcomePage(),
HomePage.routeName: (_) => HomePage(),
};
}
@override
void dispose() {
super.dispose();
}
@override
Widget build(BuildContext context) {
return MultiProvider(
child: MaterialApp(
debugShowCheckedModeBanner: false,
theme: ThemeData(fontFamily: 'Gotham'),
title: 'Shop',
onGenerateRoute: (settings) {
if (_routes.containsKey(settings.name)) {
final builder = _routes[settings.name];
return inPageRoute(
builder(context), RouteSettings(name: settings.name));
}
return inPageRoute(NotFound());
},
// Mirgration to Navigator 2.0
// merge request: https://github.com/flutter/flutter/pull/51435
// migration guide: https://flutter.dev/docs/release/breaking-
changes/route-navigator-refactoring
onGenerateInitialRoutes: (initialRoute) {
return <Route>[
inPageRoute(
WelcomePage(), RouteSettings(name: WelcomePage.routeName))
];
}
// supportedLocales: [//TODO DEFINE SUPOORTED LANGSSSSS],
),
providers: [
inProvider<AppState>(_state),
],
);
}
}
bool neverNotify(_, __) => false;
Provider<T> inProvider<T>(T value) =>
Provider<T>.value(value: value, updateShouldNotify: neverNotify);
MaterialPageRoute inPageRoute(Widget child, [RouteSettings settings]) =>
MaterialPageRoute(builder: (context) => child, settings: settings);
</pre>


# To study and implement deployment of your app to GitHub Pages.
<pre>

import ...
Future<void> main() async {
WidgetsFlutterBinding.ensureInitialized();
Paint.enableDithering = true;
if (Platform.isWindows || Platform.isLinux || Platform.isMacOS) {
await Hive.initFlutter('BlackHole');
} else {
await Hive.initFlutter();
}
await openHiveBox('settings');
await openHiveBox('downloads');
await openHiveBox('stats');
await openHiveBox('Favorite Songs');
await openHiveBox('cache', limit: true);
await openHiveBox('ytlinkcache', limit: true);
if (Platform.isAndroid) {
setOptimalDisplayMode();
}
await startService();
runApp(MyApp());
}
Future<void> setOptimalDisplayMode() async {
await FlutterDisplayMode.setHighRefreshRate();
}
Future<void> startService() async {
await initializeLogging();
final AudioPlayerHandler audioHandler = await AudioService.init(
builder: () => AudioPlayerHandlerImpl(),
config: AudioServiceConfig(
androidNotificationChannelId: 'com.shadow.blackhole.channel.audio',
androidNotificationChannelName: 'BlackHole',
androidNotificationIcon: 'drawable/ic_stat_music_note',
androidShowNotificationBadge: true,
androidStopForegroundOnPause: false,
// Hive.box('settings').get('stopServiceOnPause', defaultValue: true)
as bool,
notificationColor: Colors.grey[900],
),
);
GetIt.I.registerSingleton<AudioPlayerHandler>(audioHandler);
GetIt.I.registerSingleton<MyTheme>(MyTheme());
}
Future<void> openHiveBox(String boxName, {bool limit = false}) async {
final box = await Hive.openBox(boxName).onError((error, stackTrace) async
{
Logger.root.severe('Failed to open $boxName Box', error, stackTrace);
final Directory dir = await getApplicationDocumentsDirectory();
final String dirPath = dir.path;
File dbFile = File('$dirPath/$boxName.hive');
File lockFile = File('$dirPath/$boxName.lock');
if (Platform.isWindows || Platform.isLinux || Platform.isMacOS) {
dbFile = File('$dirPath/BlackHole/$boxName.hive');
lockFile = File('$dirPath/BlackHole/$boxName.lock');
}
await dbFile.delete();
await lockFile.delete();
await Hive.openBox(boxName);
throw 'Failed to open $boxName Box\nError: $error';
});
// clear box if it grows large
if (limit && box.length > 500) {
box.clear();
}
}
class MyApp extends StatefulWidget {
@override
_MyAppState createState() => _MyAppState();
static _MyAppState of(BuildContext context) =>
context.findAncestorStateOfType<_MyAppState>()!;
}
class _MyAppState extends State<MyApp> {
Locale _locale = const Locale('en', '');
late StreamSubscription _intentTextStreamSubscription;
late StreamSubscription _intentDataStreamSubscription;
final GlobalKey<NavigatorState> navigatorKey =
GlobalKey<NavigatorState>();
@override
void dispose() {
_intentTextStreamSubscription.cancel();
_intentDataStreamSubscription.cancel();
super.dispose();
}
@override
void initState() {
super.initState();
final String systemLangCode = Platform.localeName.substring(0, 2);
if (ConstantCodes.languageCodes.values.contains(systemLangCode)) {
_locale = Locale(systemLangCode);
} else {
final String lang =
Hive.box('settings').get('lang', defaultValue: 'English') as
String;
_locale = Locale(ConstantCodes.languageCodes[lang] ?? 'en');
}
AppTheme.currentTheme.addListener(() {
setState(() {});
});
// For sharing or opening urls/text coming from outside the app while
the app is in the memory
_intentTextStreamSubscription =
ReceiveSharingIntent.getTextStream().listen(
(String value) {
Logger.root.info('Received intent on stream: $value');
handleSharedText(value, navigatorKey);
},
onError: (err) {
Logger.root.severe('ERROR in getTextStream', err);
},
);
// For sharing files coming from outside the app while the app is in the
memory
_intentDataStreamSubscription =
ReceiveSharingIntent.getMediaStream().listen(
(List<SharedMediaFile> value) {
if (value.isNotEmpty) {
for (final file in value) {
if (file.path.endsWith('.json')) {
final List playlistNames = Hive.box('settings')
.get('playlistNames')
?.toList() as List? ??
['Favorite Songs'];
importFilePlaylist(
null,
playlistNames,
path: file.path,
pickFile: false,
).then(
(value) =>
navigatorKey.currentState?.pushNamed('/playlists'),
);
}
}
}
},
onError: (err) {
Logger.root.severe('ERROR in getDataStream', err);
},
);
void setLocale(Locale value) {
setState(() {
_locale = value;
});
}
Widget initialFuntion() {
return Hive.box('settings').get('userId') != null
? HomePage()
: AuthScreen();
}
@override
Widget build(BuildContext context) {
SystemChrome.setSystemUIOverlayStyle(
SystemUiOverlayStyle(
statusBarColor: Colors.transparent,
systemNavigationBarColor: AppTheme.themeMode == ThemeMode.dark
? Colors.black38
: Colors.white,
statusBarIconBrightness: AppTheme.themeMode == ThemeMode.dark
? Brightness.light
: Brightness.dark,
systemNavigationBarIconBrightness: AppTheme.themeMode ==
ThemeMode.dark
? Brightness.light
: Brightness.dark,
),
);
SystemChrome.setPreferredOrientations([
DeviceOrientation.portraitUp,
DeviceOrientation.portraitDown,
DeviceOrientation.landscapeLeft,
DeviceOrientation.landscapeRight,
]);
return MaterialApp(
title: 'BlackHole',
restorationScopeId: 'blackhole',
debugShowCheckedModeBanner: false,
themeMode: AppTheme.themeMode,
theme: AppTheme.lightTheme(
context: context,
),
darkTheme: AppTheme.darkTheme(
context: context,
),
locale: _locale,
localizationsDelegates: const [
AppLocalizations.delegate,
GlobalMaterialLocalizations.delegate,
GlobalWidgetsLocalizations.delegate,
GlobalCupertinoLocalizations.delegate,
],
supportedLocales: ConstantCodes.languageCodes.entries
.map((languageCode) => Locale(languageCode.value, ''))
.toList(),
routes: {
'/': (context) => initialFuntion(),
'/pref': (context) => const PrefScreen(),
'/setting': (context) => const SettingPage(),
'/about': (context) => AboutScreen(),
'/playlists': (context) => PlaylistScreen(),
'/nowplaying': (context) => NowPlaying(),
'/recent': (context) => RecentlyPlayed(),
'/downloads': (context) => const Downloads(),
'/stats': (context) => const Stats(),
},
navigatorKey: navigatorKey,
onGenerateRoute: (RouteSettings settings) {
if (settings.name == '/player') {
return PageRouteBuilder(
opaque: false,
pageBuilder: (_, __, ___) => const PlayScreen(),
);
}
return HandleRoute.handleRoute(settings.name);
},
);
}
}
</pre>


# To include bar charts in Flutter application
<pre>

import 'package:flutter/material.dart';
import 'package:charts_flutter/flutter.dart' as charts;
// @dart=2.9
void main() {
runApp(const MyApp());
}
class MyApp extends StatelessWidget {
const MyApp({super.key});
// This widget is the root of your application.
@override
Widget build(BuildContext context) {
return MaterialApp(
title: 'Flutter Demo',
theme: ThemeData(
primarySwatch: Colors.blue,
),
home: const MyHomePage(title: 'Flutter Demo Home Page'),
);
}
}
class MyHomePage extends StatefulWidget {
const MyHomePage({super.key, required this.title});
final String title;
@override
State<MyHomePage> createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> {
late List<charts.Series<dynamic, String>> seriesList;
static List<charts.Series<Sales, String>> _createRandomData()
{
final desktopSalesData = [
Sales( '2017',19000),
Sales( '2018',38000),
Sales( '2019',35000),
Sales( '2020',37000),
Sales( '2021',45000),
];return[
charts.Series<Sales, String>(
id: 'Sales',
domainFn: (Sales sales,_) =>sales.year,
measureFn: (Sales sales,_) =>sales.sales,
data: desktopSalesData,
fillColorFn: (Sales sales, _)
{return (sales.year == '2023')
?charts.MaterialPalette.green.shadeDefault
:charts.MaterialPalette.green.shadeDefault;},)];}
barChart() {return charts.BarChart(
seriesList = _createRandomData()
);
}
@override
Widget build(BuildContext context) => Scaffold(
appBar: AppBar(
title: Text(widget.title),
),
body: Container(
padding: EdgeInsets.all(20.0),
child:barChart(),
),
);
}
class Sales{
final String year;
final int sales;
Sales(this.year,this.sales);
}
</pre>


# To apply navigation, routing and gestures in Flutter Application.
<pre>
import 'package:flutter/material.dart';
import 'package:untitled5/SecondScreen.dart';
void main() {
runApp(const MyApp());
}
class MyApp extends StatelessWidget {
const MyApp({super.key});
@override
Widget build(BuildContext context) {
return MaterialApp(
title: 'Flutter Demo',
theme: ThemeData(
primarySwatch: Colors.blue,
),
home: const MyHomePage(title: 'Flutter Demo Home Page'),
);
}
}
class MyHomePage extends StatefulWidget {
const MyHomePage({super.key, required this.title});
final String title;
@override
State<MyHomePage> createState() => _MyHomePageState();
}
class _MyHomePageState extends State<MyHomePage> {
void initState() {
super.initState();
// _navigation();
}
// _navigation()async{
// await Future.delayed(Duration(milliseconds: 3000),(){});
// Navigator.pushReplacement(this.context, MaterialPageRoute(builder:
(context)=>SecondScreen()));
// }
@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
title: Text(widget.title),
),
body: Center(
child: Column(
mainAxisAlignment: MainAxisAlignment.center,
children: <Widget>[
Text("Hello, World"),
SizedBox(
height: 20,
),
ElevatedButton(onPressed:(){
Navigator.push(this.context, MaterialPageRoute(builder:
(context)=>SecondScreen()));
}, child:
Text("Next"))
],
),
),
);
}
}
import 'package:flutter/material.dart';
import 'main.dart';
class SecondScreen extends StatelessWidget {
const SecondScreen({Key? key}) : super(key: key);
@override
Widget build(BuildContext context) {
return Scaffold(
appBar: AppBar(
title: Text("Navigation"),
),
body: Center(
child: Column(
mainAxisAlignment: MainAxisAlignment.center,
children: [
Text("Bye Guys"),
SizedBox(
height: 20,
),
ElevatedButton(onPressed:(){
Navigator.pop(context);
}, child:
Text("Back")),
],
),
),
);
}
}
</pre>
