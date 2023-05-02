Download Link: https://assignmentchef.com/product/solved-cmsc204-project-6-lication-to-maintain-a-network-of-towns-and-the-roads-connecting-them
<br>
In this project you will be creating an application to maintain a network of towns and the roads connecting them. The application will use Dijkstra’s Shortest Path algorithm to find the shortest distance between any two towns.

<strong>Academic Honesty Policy Reminder</strong> | <strong>Do your own work</strong> – each submitted project will be compared against other submissions from current and previous semesters.

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Concepts tested by this assignment</strong></td>

  </tr>

 </tbody>

</table>




Implement Graph Interface

Use Graph to maintain a network of Vertices

Implement Shortest Path Algorithm

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Classes</strong></td>

  </tr>

 </tbody>

</table>




<strong>Data Element – Town (Vertex)</strong>

Create a Town class that holds the name of the town and a list of adjacent towns, and other fields as desired, and the traditional methods (constructors, getters/setters, toString, etc.).  It will implement the Comparable interface.  This is the class header:

public class Town implements Comparable&lt;Town&gt;

Two towns will be considered the same if their name is the same.

<strong>Data Element </strong><strong>– Road (Edge)</strong>

Create a class Road that can represent the edges of a Graph of Towns.  The class must implement Comparable.  The class stores references to the two vertices(Town endpoints), the distance between vertices, and a name, and the traditional methods (constructors, getters/setters, toString, etc.), and a compareTo, which compares two Road objects. Since this is a undirected graph, an edge from A to B is equal to an edge from B to A. This is the class header:

public class Road implements Comparable&lt;Road&gt;

<strong>Data Structure </strong><strong>– TownGraph, implements GraphInterface</strong>

Create a TownGraph class that implements the GraphInterface given you.  For Graph&lt;V,E&gt;,  V is the vertex type (a Town), E is the edge type (a Road).  You will need to decide how to store the graph, use an adjacent matrix or an adjacency list.  This is the class header:

public class TownGraph implements GraphInterface&lt;Town, Road&gt;

Within the Graph interface is a method shortestPath, which finds the shortest path from a given source Town to a destination Town. Since there is a unique shortest path from every vertex to the source, there is a back-pointer to the previous vertex.  The method shortestPath calls dijkstraShortestPath which finds the shortest path from the source to every other vertex in the graph.  You will be coding the Dijkstra’s Shortest Path algorithm.  You will then be able to find the connections between two towns through the roads that connect them.

You may use the adjacency matrix approach found in the text book, or you may use a set of Towns and a set of Roads. The ShortestPath algorithm typically uses a weighted graph which means that the edges have a weight, and this is used to determine the shortest path.  For this implementation, each weight will be the distance of the road in miles.

<strong>Data Manager </strong><strong>– implements TownGraphManagerInterface</strong>

Your TownGraphManager will hold an object of your Graph. Implement the TownGraphManagerInterface. There are methods to populate the graph (reading from a text file), add a town (vertices), add a road (edge), list all towns and all roads, and list towns adjacent to a given town.

Your solution will find the shortest path from a start town to a destination town.  It will account for the possibility of a disjoint graph (i.e., not all vertices can be reached from all other vertices.)

You may add any methods as needed for your design.

<strong>Exception Classes</strong>

FileNotFoundException – created and thrown when the selected input file is not found.

IOException – created and thrown when user selects an input file that cannot be read (check out the methods of File).

These exceptions exist in the Java API.

<strong>GUI Driver </strong><strong>(provided for you)</strong>

The GUI has four sections: a Town section where you can add towns, a Road section where you add roads, a Find Connection section, and an administration section.  It has a Read File button, which allows the text files provided to be read and populate the graph.

<strong>Testing</strong>

<ol>

 <li>Your completed implementation must pass the TownGraphManagerTest.java and the GraphTest.java.</li>

 <li>The tests marked GFA (“Good Faith Attempt”) are the minimal testing that must pass in order for your implementation to meet the good faith attempt.</li>

 <li>Create a JUnit Test – TownGraphManager_STUDENT_Test. Test all the methods of the TownGraphManager with a different set of data than the TownGraphManagerTest provided for you.</li>

 <li>Create a JUnit Test – Graph_STUDENT_Test. Test all the methods of the Graph with a different set of data than the GraphTest provided for you.</li>

 <li>Create a Junit Test – Road_STUDENT_Test. Test all the methods of your Road class.</li>

 <li>Create a Junit test – Town_STUDENT_Test. Test all the methods of your Town class.</li>

</ol>

<strong> </strong>

<table width="100%">

 <tbody>

  <tr>

   <td><strong>Assignment Details</strong></td>

  </tr>

 </tbody>

</table>




<strong>Populating the Data Structure</strong>

You will be reading from a data file.  You are provided with two sample files: MD Towns.txt and US Towns.txt along with two PowerPoint slides showing these graphs.

The Towns.txt files hold the information for the individual Towns and Roads, and is in the following format:

road-name,miles;town-name; town-name




For example:

I-94,282;Chicago;Detroit

Notice that the road-name and miles are separated by a comma, while the road information and the two towns are separated by semi-colons.

After reading these files, you will have an initial set of vertices and edges in your Graph.