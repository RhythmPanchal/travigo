# TraviGo

A travel-planning website for exploring destinations, building day-by-day itineraries and browsing places to stay, eat and visit.

![HTML5](https://img.shields.io/badge/HTML5-E34F26)
![CSS3](https://img.shields.io/badge/CSS3-1572B6)
![JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E)
![PHP](https://img.shields.io/badge/PHP-backend-777BB4)
![MySQL](https://img.shields.io/badge/MySQL-database-4479A1)

## What it does

TraviGo is a multi-page web app with a plain HTML/CSS/JavaScript front end and a small PHP + MySQL back end.

## Pages and features

- **Home** (`index.html`): landing page linking to the main features
- **Login / sign up** (`login.html`): account creation and login against the PHP backend
- **Explore** (`explore.html`): search a city and see nearby points of interest, fetched from the OpenTripMap API
- **Itineraries** (`itinerary.html`) and **Trip planning** (`tripplanning.html`): build trips as days with timed activities and save them per user
- **Bookings** (`booking.html`): browse accommodations, food and activities by city, loaded from the database
- **Feedback**, **FAQ**, **Contact us** and **About us** pages

City imagery for Barcelona, Dubai, New York, Paris, Rome and Tokyo is bundled in `images/`.

## Tech stack

- HTML, CSS, vanilla JavaScript (no build step)
- PHP (mysqli / PDO) endpoints in `backend/`
- MySQL; schema and sample data in `Database/`
- OpenTripMap API for the Explore page (requires your own API key, set in `JS/explore.js`)

## Getting started

Needs a local PHP + MySQL stack (for example XAMPP).

1. Put the project folder in your web server's document root.
2. Create a MySQL database named `travigo` and run the scripts in `Database/` (`user.sql`, `itineraries.sql`, `booking.sql`). The feedback endpoint also expects a `feedbacks` table, which has no script in the repo.
3. The PHP files in `backend/` connect to MySQL on `localhost` as `root` with an empty password, and some use port 3307. Adjust the connection settings in those files to match your setup.
4. Add an OpenTripMap API key in `JS/explore.js`.
5. Open `index.html` through the web server (not as a `file://` URL), so the `fetch` calls to `backend/*.php` work.

## Project layout

```
*.html        pages
CSS/, JS/     per-page styles and scripts
Temp/         shared header/footer snippet
backend/      PHP endpoints (authenticate, register, bookings, trips, feedback)
Database/     SQL schema and seed data
images/       site images
```

## Status

A student project. The code is a work in progress: some backend files contain unfinished or inconsistent pieces (for example password handling in the login and register endpoints, and SQL built by string concatenation in the trip-saving endpoint), so it should not be deployed as is.
