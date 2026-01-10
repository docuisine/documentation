# Development

Before writing code, it is important to understand the overall architecture of Docuisine, so that developers know what are they building, and who is it for. As well as direct developers to tasks they are most proficient with.

Docuisine is aimed to be an app that can run anywhere. As such, we designed it with microservices in mind. Docuisine should be able to run in a single machine or scale to a large number of users using cloud services.

## Tech Stack

Docuisine has 4 main components.

1. The Backend server
2. The Frontend server
3. A Database
4. An S3 bucket

The backend server is a Python [FastAPI](https://fastapi.tiangolo.com/) app. The frontend server is a JavaScript [ReactJS](https://react.dev/) app. Both apps are independently developed and are further discussed in their relevant documentation respectively: (1) [Backend](./backend.md); (2) [Frontend](./frontend.md).

The backend aims to abstract all processes for the frontend to work with. The backend communicates directly with the database where we store app data and an S3 bucket to store BLOB objects, particularly images.

### Single Machine

To run Docuisine in a single machine, we only need to use [Docker](https://www.docker.com/) and a single `docker compose` file to run the four microservices. This approach is aimed to users who want to self-host Docuisine on their own machine or inside a [VPS](https://en.wikipedia.org/wiki/Virtual_private_server).

We use Postgres `postgres:18.1` for the database and MinIO `minio/minio:RELEASE.2025-09-07T16-13-09Z-cpuv1` for the S3 bucket.

### Cloud

Docuisine be deployed to cloud for free using Vercel, Cloudflare, and Supabase. This approach is recommended for users who want to scale up to a larger userbase or simply to take advantage of free-tier offerings to reduce costs to zero instead of self-hosting on their own machines, which incurs hardware and electricity expenses, only of course if you are willing to give up the custody of your data and privacy.

Both the [frontend](https://github.com/docuisine/docuisine-react) and [backend](https://github.com/docuisine/docuisine) can be deployed by forking their repositories on GitHub. These repos can then be connected to [Vercel](https://vercel.com/) and be deployed automatically. [Cloudflare R2](https://www.cloudflare.com/developer-platform/products/r2/) as the S3 storage, and [Supabase](https://supabase.com/) for the Postgres database. See the [relevant documentation](../../user-guide/installation.md#cloud-services) for more details on how to run Docuisine on the cloud.

## What should you work on?

You should work on the backend if you're proficient with Python, or the frontend if otherwise with JavaScript. You can also work on both if you can.

### Contributing changes

The first step is to set up a copy of the Git repository of the project you want to contribute to. Docuisine follows a "fork, feature-branch, and PR" model for contributions.

1. On GitHub, "Fork" the Docuisine repository you wish to contribute to, to your own user account using the "Fork" button in the relevant repository.

2. Clone your fork to your local machine and enter the directory:

```bash
git clone git@github.com:yourusername/projectname.git
cd projectname/
```
3. Add the "upstream" remote, which allows you to pull down changes from the main project easily:

```bash
git remote add upstream git@github.com:Docuisine/projectname.git
```
4. When contributing code, ensure that you have read the [guidelines](/documentation/contributing/artifacts/style-guides/#contributing-code) of doing so, so then you can start making commits and changes to the code. See the relevant documentation to on how to run a development server on both [frontend](frontend.md) and [backend](./backend.md) projects.
