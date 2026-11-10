
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: PlacementPage(),
    );
  }
}

class PlacementPage extends StatefulWidget {
  @override
  State<PlacementPage> createState() => _PlacementPageState();
}

class _PlacementPageState extends State<PlacementPage> {

  bool showDetails = false;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.grey[100],

      appBar: AppBar(
        title: Text("Placement Cell Portal"),
        backgroundColor: Colors.blue,
        foregroundColor: Colors.white,
        centerTitle: true,
      ),

      body: LayoutBuilder(
        builder: (context, constraints) {

          return Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [

                Icon(
                  Icons.school,
                  size: 60,
                  color: Colors.blue,
                ),

                SizedBox(height: 15),

                Text(
                  "Welcome to College Placement Cell",
                  textAlign: TextAlign.center,
                  style: TextStyle(
                    fontSize: 24,
                    fontWeight: FontWeight.bold,
                  ),
                ),

                SizedBox(height: 25),

                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      showDetails = !showDetails;
                    });
                  },
                  child: Text("View Placement Details"),
                ),

                SizedBox(height: 20),

                if (showDetails)
                  Container(
                    padding: EdgeInsets.all(20),
                    margin: EdgeInsets.all(15),
                    color: Colors.white,
                    child: Column(
                      children: [
                        Text(
                          "Campus Recruitment 2026",
                          style: TextStyle(
                            fontSize: 20,
                            fontWeight: FontWeight.bold,
                            color: Colors.blue,
                          ),
                        ),
                        SizedBox(height: 10),
                        Text("Companies: TCS, Infosys, Wipro"),
                        Text("Job Role: Software Trainee"),
                        Text("Eligibility: Final Year Students"),
                      ],
                    ),
                  ),

                SizedBox(height: 20),

                Text(
                  constraints.maxWidth < 600
                      ? "Mobile Web Layout"
                      : "Desktop Web Layout",
                  style: TextStyle(
                    color: Colors.blue,
                    fontWeight: FontWeight.bold,
                  ),
                ),
              ],
            ),
          );
        },
      ),
    );
  }
}
