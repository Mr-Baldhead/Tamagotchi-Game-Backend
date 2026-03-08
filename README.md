# Tamagotchi Game - Project Description

I've built a Tamagotchi game that works on the web! It's like the old Tamagotchi toys from the 90s, but on your computer. You can create your own digital pet, feed it, play with it, and make sure it stays healthy and happy.

## Backend (The Server)

I programmed a server in Java that:
- Stores all Tamagotchis in memory
- Handles all actions (feed, play, sleep, etc.)
- Checks that you don't do wrong things (like feeding when it's asleep)
- Sends back nice error messages if something goes wrong

## How it works

Start server: `mvn wildfly:run`  
Stop server: `ctrl + c`

### Endpoints

| Action | Method | URL |
|--------|--------|-----|
| Hatch Tamagotchi | POST | http://localhost:8080/api/tamagotchis |
| Get All Tamagotchis | GET | http://localhost:8080/api/tamagotchis |
| Get by ID | GET | http://localhost:8080/api/tamagotchis/{id} |
| Feed | PUT | http://localhost:8080/api/tamagotchis/{id}/feed |
| Play | PUT | http://localhost:8080/api/tamagotchis/{id}/play |
| Sleep | PUT | http://localhost:8080/api/tamagotchis/{id}/sleep |
| Wake | PUT | http://localhost:8080/api/tamagotchis/{id}/wake |
| Clean | PUT | http://localhost:8080/api/tamagotchis/{id}/clean |
| Medicine | PUT | http://localhost:8080/api/tamagotchis/{id}/medicine |
| Release | DELETE | http://localhost:8080/api/tamagotchis/{id} |

### Query parameters

- **Pagination** (default limit=10, offset=0): `GET /api/tamagotchis?offset=0&limit=10`
- **Filtering**: `GET /api/tamagotchis?character=Mametchi`
- **Sorting** (sortBy, default order=asc): energy, happiness, health, hunger, name, needsCleaning, status  
  `GET /api/tamagotchis?sortBy=happiness&order=desc`

## Technology I used

- **Jakarta EE 10** - Modern Java for web applications
- **JAX-RS** - For creating the REST API
- **CDI** - Makes different parts of the code work together automatically
- **Bean Validation** - Checks that input data is correct
- **WildFly** - The server that runs everything
- **Maven** - Tool that builds and packages the application
