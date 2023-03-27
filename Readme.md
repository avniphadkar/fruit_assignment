# Fruits Assignment

## Used Technologies

- For the backend, I'm using Symfony 6.
- For frontend, I'm using Vue.js.
- Docker to make consistent environment for development and setup.

## Container details:

1. `FRUITS_PHP` which contains our PHP files.
2. `FRUITS_APP` for the frontend.
3. `FRUITS_DB` for Database (mysql).
4. `FRUITS_API` for nginx server.
5. `FRUITS_MAILHOG` for mailhog server.

## Local setup

```sh
# For building the containers and migrating the database
make init
```

```sh
# For Running the console command to fetch the fruits data from third-party.
make api.sync-fruits

# Or you can run this manually using the below command:
docker exec -it docker exec -it FRUITS_PHP php bin/console app:fruits-fetch
```

> Now the project should be up and running on http://localhost:8080
> NOTE: You can check the mail (mailhog) on http://localhost:8082

# API calls
Now if we talk about the API calls, I have 4 API calls:

1. `/fruit/families`: For getting the list of fruit family.
2. `/fruits`: For getting the list of fruits based on the filter query and pagination.
3. `/fruits/{uuid}/toggle-favorite`: For marking the fruit as favorite or un-favorite. 
4. `/fruits/favorites`: For getting the list of favorite fruits.

You can see the [fruits-assignment.http](./api/fruits-assignment.http) file for getting more details about the API calls.

# Glance at the UI

![Image](./images/fruit_list.png?q=1)
![Image](./images/favourite_fruit.png?q=2)
![Image](./images/mailhog.png?q=3)
