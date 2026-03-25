# Drone

Drone Challenge
Drone Airport Navigation

Task
Introduction
In this task, the drone must autonomously navigate through the
environment by following the yellow guiding line, which includes
both straight and curved segments, in order to reach the
required airport landing pads.
Each airport is represented using an AprilTag marker, and the
drone must read the tag to determine airport information.
The drone will be given up to two target country codes, and it
must travel through the airport network and land at at least one
airport belonging to each requested country.
Important guarantee:
If a country code appears in the array, there will always be at
least one airport in that country with a valid landing status
(Airport status = 1).

AIRPORT REPRESENTATION
Airports in the simulation are represented using a
landing_pad_stand, which appears as a grey box
with an AprilTag placed on its top surface.
Each landing pad stand corresponds to one airport in
the system.

APRILTAG ENCODING FORMAT
All tags used in the task belong to the AprilTag family:
36h11
Each AprilTag encodes a three-digit number. The
digits represent the following information:
Digit 1 → Country Code
Digit 2 → Airport Status
Digit 3 → Number of other airports reachable from this
airport

Country Code
The first digit identifies the country to which the
airport belongs.

Status
The second digit represents whether the airport
is available for landing.
Example interpretation:
1 → Landing safe
0 → Landing unsafe

Reachable Airports
The third digit indicates how many other
airports can be reached directly from that
airport.

GRAPH NAVIGATION REQUIREMENTS
The airports form a graph of connected nodes.
Your drone must search through this graph to find a
valid airport that belongs to the required country code.
The solution must not rely on hardcoded airport
locations or tag IDs.
During evaluation:
AprilTags on the landing pads will be swapped
Target country codes will also be changed
Therefore, your algorithm must dynamically:
1.Read the AprilTag
2.Interpret its encoded information
3.Determine whether the airport belongs to the
required country
4.Navigate through connected airports until a valid
one is found

REQUIRED INPUT VARIABLE IN CODE
Each team must include a clearly identifiable variable in
the code that stores the requested target countries.
This variable must be named exactly:
Airports = []
The array must contain two values. Format:
Airports = [country1, country2]
If only one country needs to be visited, the second
value will be: 0
this is to indicate that there is no second destination.

Examples:
Landing in two countries:
Airports = [1, 2]
Landing in one country:
Airports = [1, 0]
This variable is already included in the project code.
You can find it in:
Task Folder → flight.py
Evaluators will modify this variable when testing your
solution.

DEMONSTRATION INPUT FOR VIDEO
SUBMISSION
For the video submission, teams should
demonstrate the system using values:
Airports = [1, 2]
The drone should:
1.Land at an airport belonging to country 1
2.Take off again
3.Land at an airport belonging to country 2

Task CTD.
LANDING BEHAVIOR REQUIREMENTS
When the drone reaches a target airport:
It must land on the landing pad.
After landing on the first required airport:
the drone does not need to disarm.
however, it must remain grounded on the
landing pad for at least 4 seconds
After the waiting period, the drone must take off
again and continue toward the next required airport
if one exists.

NAVIGATION REQUIREMENT
The drone must use the yellow line as the navigation
guide.
This includes:
straight yellow line segments
curved yellow line segments
The drone must correctly follow this path to reach the
target airports.
During takeoff and flying the drone must not exceed
a height of more than 3 meters from the initial
landing pad

how to complete this task with proper method




when showing a node with two or tree lines in different angels how decide where should go. it should have a method that what is the came line and where should go without confusing.

wannina-ec22031@stu.kln.ac.lk

then
as a example when give a variable Airports = [1, 2], how to find shortest path to visit these countries

Without making hall task at once,
divide this complete task to subtasks for easy implementation and troubleshooting.
