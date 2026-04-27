<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: BARANIKUMAR S</h3>
<h3>Register Number: 212224060038</h3>


<h3>AIM:</h3>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>
<h3>PROGRAM:</h3>

```
import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.performance = 0
        self.rooms = ["Room 1", "Room 2"]
        self.current_room = "Room 1" 
        self.environment = {}

    def sense_environment(self):
        # generate random temperature (97–102°F)
        temp = round(random.uniform(97, 102), 1)
        self.environment[self.current_room] = temp
        return temp

    def prescribe_medicine(self, temperature):
        if temperature > 98.5:
            print(f"Treatment given in {self.current_room}.")
            self.performance += 10
        else:
            print(f"No treatment needed in {self.current_room}.")

    def move_to_other_room(self):
        next_room = "Room 2" if self.current_room == "Room 1" else "Room 1"
        print(f"\nMoving from {self.current_room} to {next_room}...")
        self.current_room = next_room
        self.performance -= 1

    def run(self):
        print("Medicine Prescribing Agent Simulation Started\n")
        # Room 1
        temp = self.sense_environment()
        print(f"Checking {self.current_room}... Patient temperature: {temp}°F")
        self.prescribe_medicine(temp)
        # Move to Room 2
        self.move_to_other_room()
        # Room 2
        temp = self.sense_environment()
        print(f"Checking {self.current_room}... Patient temperature: {temp}°F")
        self.prescribe_medicine(temp)
        print("\nSimulation Complete!")
        print(f"Final Performance Score: {self.performance}")
        print(f"Environment State: {self.environment}")

agent = MedicinePrescribingAgent()
agent.run()
```
OUTPUT:
<img width="849" height="482" alt="image" src="https://github.com/user-attachments/assets/b4aaf6b5-bcce-409a-8ebd-d7e4d3809a8b" />

RESULT:
Thus the AI agent is developed successfully
