## [Main Video Demo](https://youtu.be/yk2MgBBbZYU)

## Game Links (Mentioned in Video)
- [Video 1 - Table Tennis] (https://youtu.be/cblvrjWiBj4)
- [Video 2 - 8-Ball Pool] (https://youtu.be/zka610WsfZo)
- [Video 3- Hockey]  (https://youtu.be/l3W90ylTd9Y)

## Inspiration
Have you ever felt alone or bored because of all the isolation nowadays? Whether you're a freshman or about to graduate, it's clear that a large part of the excitement and fun of school life has been taken away through COVID-19. Without online chat platforms like Discord and Zoom, my friends and I agree that this pandemic would have caused many mental issues relating to depression through forceful isolation. Hence, we created ChatSpace VR to fix this issue and allow students to connect and interact with each other through the use of Multiplayer Virtual Reality.

## What it does
Chatspace VR is a virtual hangout app that brings students together into a UWindsor Welcome Center filled with recreational activities including Air Hockey, Table Tennis, and 8-Ball Pool. It uses Unity to create a truly interactive space where users are free to interact with any recreational activities making it as realistic as possible. They can walk around, interact with each other's characters, use the proximity voice chat, and play tabletop games. 
 
## How we built it
We built ChatSpace VR using Unity and Windows Mixed Reality Headsets. Using Mirror Networking, we were able to set up a server-client relationship to allow us to use both high-level and low-level networking objects, giving us a flexible yet efficient framework for multiplayer. High-level objects were used to network player movement and replicate transform objects across clients with low latency, while low-level objects were used for more specialized features relating to interactions such as the pick-up tool feature specific to each recreational game. This required the use of synchronizing variables to hooks and setting up multiple server-sided and client-sided commands. Blender was used to create a realistic UWindsor Welcome Center that is used to house a majority of the games.
We started the VR aspect by using the template Mixed Reality VR Unity build, but we quickly had to change the prefabs and set up listeners for important events. This included delving into the XR extension and using custom XR events to set up hooks for game events (ex. picking up the billiard stick).

## Challenges we ran into
Along the way, we ran into many challenges. The biggest of these challenges include:
1. Switching Headsets from Oculus -> Windows Mixed Reality:
    - At the start of our hack, we had an Oculus Rift S and an Oculus Quest. However, due to functionality and compatibility issues between the two along with the installation glitch that wasted some of our hacking time, we switch to using Windows Mixed Reality, a system we were more familiar with. 
2. Proximity VoiceChat with Mirror + Dissonance API
    - We used different libraries on Unity to set up Event Broadcast and Event Receipt Triggers for listening to voice chats against the network. During this period, we had a large issue with proximity as a single broadcast and receipt trigger would make all clients hear broadcasts from every other client even if they are not in range. This problem was fixed by creating a Playback Prefab which connected to a script on each broadcaster that processed output speech into a "Playback" object played on each other client. This "Playback" object had a variable of distance which gave us not only proximity chat but also more flexible sound features.
3. Debugging multiplayer in VR
  - Setting up the networking and the VR aspects alone had been difficult, but putting them together proved a big obstacle. It was hard to test changes as it often required multiple PCs, and debugging which client or server was causing a problem proved troublesome. This resulted in difficult troubleshooting scenarios, where nothing would happen and we'd have to debug between devices. This was often the case when trying to replicate vr changes between clients.

4. Replicating changes
 - For player objects, we were able to restrict the movement of each player to their own client. However, in the instance of the game objects like the table hockey, it had to synchronize with multiple clients adjusting it. This required us to create a complicated system for the server to preemptively determine the best client to control any given object at a given time.

5. Demo
None of us have worked with video editing software in the past, so creating a demo was very difficult. This is especially because you cannot capture the vr experience in video, but we are proud that we put a video together.

## Accomplishments that we're proud of
We are pretty proud of our networking that allows for voice chat and data interactions between clients and the server. Furthermore, using Dissonance to pull a networked proximity voice is another aspect of this hack that we are pretty proud of. Finally, seeing the fun interactions and chat between topics makes us truly proud as our creation actually is a good prototype for what it was meant to truly be. An app to help students connect with after-class activities.  


## What we learned
We learned that it's best to be very flexible. For example, we had to switch away from Oculus after nearly 7 hours of work into it. Now in hindsight, we recognize that it was for the best. However, at the moment, it was extremely difficult to make this decision.

## What's next for ChatSpace VR
While the program makes a great virtual reality simulator for the campus, we would like to expand to other devices, allowing for more interactions between students. Furthermore, we want to add more features later on, such as linking your student account to your vr experience. 


