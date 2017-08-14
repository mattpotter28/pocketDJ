# pocketDJ
 
 **To Run**
 
 Make sure Node.js is installed, open a command window in the pocketDJ folder, and run `npm install --save express@4.15.2` and `npm install --save socket.io`.
 
 Once both are installed, you can run `node index` which should open the webpage at http://localhost:3000/
 
 **Outline**

- Landing page has two options
  - Create a room
  - Join a room - text box for a url
- Inside each room
  - Prompts user for nickname
  - Welcome's user to the room
  - Indicates number of users in current room
  - Shows a queue of the songs currently in line
  - Text box that only accepts youtube urls
  - Invite button that copies the url to clipboard

**To Do**

- Create/Join rooms
  - As of now it's just a giant room for the server. Socket.IO has support for [rooms](https://socket.io/docs/rooms-and-namespaces/) but I haven't messed around with it yet. Ideally, creating a room would generate a url somewhat like "pocketDJ.com/QDhEwS"

- Filter youtube urls
  - Automatically check sent messages and filter out the ones that are not youtube urls.
  - I think this would be done as a fucntion in main.js that's called from the socket new message function in index.js but I couldn't get it working perfectly when I tried messing with it

- Download youtube audio
  - There's a module on npm called [youtube-dl](https://www.npmjs.com/package/youtube-dl) that uses Node to download youtube audio to a file , but I'd like to do more research. If it's not too complicated I'd prefer not using a module.

- Streaming audio
  - This is a little less complicated than it seemed at first glance because it really only has to stream the audio for the room creator, it shouldn't have to interact with Socket.IO. Everything I've seen is talking about streaming audio from client to client but I'm sure there's a simple solution somewhere.

**Optional**

- Commands, such as vote to kick someone from the room or vote to skip the current song

- Use more than just youtube
  - the youtube-dl module has support for a [huge list of sites](http://rg3.github.io/youtube-dl/supportedsites.html)
