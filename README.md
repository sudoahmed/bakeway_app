# bakeway_app
import 'package:bakeway_app/screens/order_summary_screen/cart_screen.dart';
import 'package:bakeway_app/screens/shipping_address_screen/shipping_address_screen.dart';
import 'package:bakeway_app/screens/splash_screen/splash_screen.dart';
import 'package:flutter/material.dart';

import 'routes/Routes.dart';

void main() {
  runApp(MyApp());
  ErrorWidget.builder = (FlutterErrorDetails details) => Material(
        color: Colors.blue.shade200,
        child: Center(
          child: Text(
            details.exception.toString(),
            style: TextStyle(
                color: Colors.white, fontWeight: FontWeight.bold, fontSize: 20),
          ),
        ),
      );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        fontFamily: 'Poppins',
      ),
      debugShowCheckedModeBanner: false,
      onGenerateRoute: Routes.onGenerateRoute,
      routes: {
        "/": (context) => SplashScreen(),
        "/order-summary": (context) => CartScreen(),
        "/shipping-screen": (context) => ShippingAddressScreen(),
      },
    );
  }
}
