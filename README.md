# Dive Hub — Android Application (Legacy)

A native Android application originally developed in **2014** for **Dive Hub Scuba Diving Center**.

Built with **Java, XML layouts and SQLite**, the application combines dive center information, local dive site guides, training course descriptions, a bundled photo gallery and contact tools.

The repository also contains an offline dive logbook prototype.

## Project Context

Developed by **Hakan Berat Demircan**, a scuba diving instructor and former Dive Hub co-owner.

The application reflects an early effort to bring the center's services, diving locations and customer information into a mobile interface.

This repository preserves the original implementation as part of my software development portfolio.

## Features

| Area | Implementation |
|---|---|
| Center Information | About pages, team information and service descriptions |
| Dive Sites | Local dive site descriptions and images |
| Courses | Expandable course information for PADI, CMAS and DAN |
| Diving Services | Information about try dives, shore dives, boat dives and night dives |
| Gallery | Bundled photos displayed with thumbnails and image transitions |
| Contact | Contact information, website links and phone-call actions |
| Contact Form | Form and legacy email-sending implementation |
| Logbook Prototype | SQLite-backed entry, listing and deletion code |

## Dive Site Guide

The application includes content for sites such as:

- Dive Hub Shore
- Amphora Beach
- Amphora Wall
- Boğaz Shipwreck
- Alp
- Bedri
- Pitos
- Noah's Ark
- Ray Cave
- Abdulselam

Dive site content and photographs are packaged with the application rather than retrieved from a content management backend.

## Training and Services

Course information is organized through expandable lists and dedicated screens.

The application includes descriptions of training programs and diving services. These are historical informational pages, not an online booking or certification system.

## Photo Gallery

The gallery uses Android's original `Gallery` widget and an `ImageSwitcher` with fade transitions.

Images are bundled as drawable resources. The application does not upload photos or synchronize a remote gallery.

## Offline Logbook Prototype

The source includes a local SQLite database and screens for adding, listing and deleting dive entries.

Supported fields include:

| Category | Fields |
|---|---|
| Identification | Dive number, date and dive site |
| Dive Profile | Depth and dive duration |
| Equipment | Starting/ending tank pressure, exposure protection and weight |
| People | Dive leader and buddy |
| Additional Information | Notes |

The database is named `db1`, with records stored in a `logbook` table.

**Current navigation limitation:** the main menu's Logbook action displays a “LogBook will be ready soon!” dialog. The logbook Activities and database code exist, but the normal menu does not open them.

This module is documented as a prototype rather than a completed user-facing feature.

## Technology Stack

| Area | Technology |
|---|---|
| Language | Java |
| Platform | Android SDK |
| Interface | XML layouts and Android Activities |
| Navigation | Android Intents |
| Lists | ListView, ExpandableListView and custom adapters |
| Gallery | Gallery and ImageSwitcher |
| Local Persistence | SQLiteOpenHelper |
| Email Implementation | Bundled JavaMail-related libraries |
| Original Project Format | Eclipse ADT |

The project declares:

- Minimum SDK: **API 7**
- Target SDK: **API 18**
- Build target: **android-18**
- Application package: `com.hbd.divehub`

These values describe the original configuration, not verified compatibility with current devices.

## Application Structure

The application is organized primarily around individual Activities.

Static information is stored in Android resources and Java collections. The logbook uses a dedicated SQLite helper.

| Path | Contents |
|---|---|
| `src/com/hbd/divehub/` | Java Activities, adapters, database helper and email code |
| `res/layout/` | Default screen layouts |
| `res/layout-land/` | Landscape layout overrides |
| `res/layout-large/` | Large-screen layouts |
| `res/layout-xlarge/` | Extra-large-screen layouts |
| `res/values/` | Strings, lists, styles and dimensions |
| `res/drawable*` | Bundled images and interface assets |
| `libs/` | Android support and email libraries |
| `AndroidManifest.xml` | Activities, permissions and application configuration |
| `project.properties` | Legacy Android build target |

### Key Source Files

| File | Responsibility |
|---|---|
| `Splash.java` | Application launch screen |
| `MainActivity.java` | Welcome screen |
| `Menupage.java` | Main navigation |
| `Divesites.java` | Dive site selection |
| `Padicourses.java` | Expandable PADI course information |
| `Galleryy.java` | Bundled photo gallery |
| `Contact.java` | Contact links and phone actions |
| `Contactform.java` | Contact form input |
| `DiveDatabase.java` | SQLite logbook operations |
| `Logbooknew.java` | Dive entry form |
| `Logbooklist.java` | Dive listing and deletion |

## Inspecting the Project

Clone the repository:

```bash
git clone https://github.com/hakanberat/DiveHub-Android-Legacy.git
cd DiveHub-Android-Legacy
```

The source can be inspected directly.

This is an Eclipse ADT project. It does not include a Gradle wrapper or a modern Android Studio build configuration.

Running it requires restoring a compatible legacy environment or migrating the project and its dependencies to a supported Android build system.

No verified one-command setup for current Android tooling is provided.

## Legacy Limitations

The repository retains unfinished behavior and implementation issues from the original project:

- The main menu does not open the logbook prototype.
- The logbook listing code skips the first database record.
- Logbook insertion result handling and database upgrade SQL require correction.
- The contact form contains a legacy direct-SMTP approach with placeholder credentials; email delivery is not configured.
- Phone actions and older Android widgets require compatibility review.
- No automated test suite is included.

The project should be treated as historical source code requiring restoration and modernization before reuse.

## Experience Demonstrated

This project documents early experience with:

- Native Android development in Java
- XML-based mobile interfaces
- Activity navigation
- Expandable lists and custom adapters
- Bundled multimedia resources
- SQLite persistence
- Translating dive center information into a mobile application

## Author

**Hakan Berat Demircan**

Software developer, PADI IDC Staff Instructor and former Dive Hub co-owner.

[GitHub Profile](https://github.com/hakanberat)
