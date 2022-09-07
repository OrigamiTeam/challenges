# Fullstack-challenge

Welcome to this fullstack Flutter + Elixir programming challenge.

We kindly ask you to read all steps below with atention in order to maximize the chances of success.

The task consists of developing an interaction with music playlists, respecting some rules accordingly to the plan payed by the user. The implementation is comprised of two applications:

1) Mobile app in Flutter
2) Elixir Phoenix backend

## Summary

- [Task](#task)
- [Assessment Criteria](#assessment-criteria)
- [Business Rules](#business-rules)
- [Requirements](#requirements)

## Task

The time available is 7 days to deliver the best software as possible guided by the importance of requirements described in the next section, respecting the 3Cs aspects of a software: consistency, completeness and correctness. Your challenge answser might be delivered through your personal repository account of your choice (GitHub, Gitlab, BitBucket, etc). Please send us the link when you finish.

## Assessment Criteria

The analysis of the code will consider the following facets in decrescent order of importance:

- Lack of bugs
- Responsiveness
- Flutter coding principles (suggested reading: [Flutter: Best Practices and Tips]([https://reactjs.org/docs/thinking-in-react.html](https://medium.com/flutter-community/flutter-best-practices-and-tips-7c2782c9ebb5)))
- Objectivity (good semantics, readability)
- Decoupling
- Extensibility
- Manutenability
- Nice formatting
- Backend Deployment

### Optionals

The following points are optionals, but we would appreaciate to see some of it:

- Automated tests
- Comments
- Exception handling
- Use of tooling (like lint and CI/CD)

## Business Rules

Our system is aimed to allow business clients (B2B) to reproduce music in comercial spots like groceries, restaurants, etc. As such, the user is associated with a determined **plan** that provides a specific set of **musics** that might me added to a **playlist**. Each **plan** has a specific limit for the amount of musics that might be added to the playlist.

Consider that in the first version of the system, it has these two **plans** available:

| Plan   | Playlist size |
|--------|---------------|
| Basic  | 3             |
| Gold   | 5             |

Consider also the musics available are:

| Music    | Plan  |
|----------|-------|
| Orient   | Basic |
| Chiptune | Gold  |
| EDM      | Basic | 
| Chillout | Gold  |
| Dubstep  | Gold  |
| Winter   | Basic |
| Summer   | Basic |
| Ocarina  | Gold  |

All musics of `Basic` plan are also available for the `Gold` but the converse statement is not true.
We know that the system is going to grow and new plans might be added in future.

## Requirements

### Admin Frontend 

A backoffice is required for the `admin` to add new musics to the existing plans and to register new clients.

- For the music CRUD, it might be possible to set the name of the music and the associated plan.
- For the clients CRUD, the attributes are email, password and the plan choosen.

### Clients Frontend

The main frontend is for the clients, where they can sign-in, see all musics available in the system and define which musics belongs to his/her playlist. Remember to respect the limits of the plan and to make this restriction clear in the user experience.

- The app must run on android and/or iOS platform

### Cloud Environment

You are free to utilize any service available at AWS (like storaging, data bases, compute node instances, etc.) but at least one of them must be used and must be explained the reason of the choice in the backend README file.

### UI

There is no specific requirements regarding UI. The main point is to think on the consequences of usability decisions. Some thoughts:

- a list might be shown with available musics
- the playlist might be updated with drag and drop

### Backend

There are some choices regarding the stack to be used on backend:

- Postgres as relational database will be a must
- The API might be REST or GraphQL
