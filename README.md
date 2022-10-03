

# NestJS-Rest-API-basic1 #
**A basic, not data-persistence repository that aims to serve as a starting point for further development of nestjs-based REST API projects**

-------
![NestJS-Rest-API-basic1](https://user-images.githubusercontent.com/41330248/193578093-ef32071e-be04-4b4d-99c7-05deb10f6a43.png)

-------
<!-- <p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo_text.svg" width="175" alt="Nest Logo" /></a>
</p> -->

Use this repo as your starting point for your next NestJS REST API project. For example you can use it and add database persistence by connecting and using your favorite Database  e.g. [MongoDB](https://www.mongodb.com/), [MySQL](https://www.mysql.com/)/[MariaDB](https://mariadb.org/), [PostgreSQL](https://www.postgresql.org/), [MS SQL Server](https://www.microsoft.com/en-us/sql-server/), [Oracle](https://www.oracle.com/database/technologies/), etc.

-------

## Key-points

The repo’s key points are summarized as follows:

![VSCodeRepoImage](https://user-images.githubusercontent.com/41330248/193578736-30fd16e3-d69e-4a0d-a96d-f8463e47f643.png)


* The repo (as in the [NestJS Documentation](https://docs.nestjs.com/security/authentication#implementing-passport-strategies))  already includes both the **AuthModule** and the **UsersModule** respectively, as well as their Controller and Service classes.

* Instead of using the UsersService for the basic CRUD operations, the repo uses a separate solo @injectable class, the DbRepo. It serves both the AuthService and the UsersService. [You can read how to use a solo @injectable class as a singleton Provider at my post [here](https://blog.devgenius.io/nestjs-use-a-solo-injectable-class-as-a-singleton-provider-884911eff279) and/or [here](https://www.devxperiences.com/pzwp1/2022/03/18/nestjs-use-a-solo-injectable-class-as-a-singleton-provider/)]

* The DbRepo provides the necessary methods for the CRUD operations. It gets the users’ data from the UsersDB. UsersDB is not persisted. It just contains a couple of users in an array who have been pre-set in the UsersDB class.

* [class-validator](https://www.npmjs.com/package/class-validator) and [class-transformer](https://www.npmjs.com/package/class-transformer) packages are installed. DTOs and entities are defined in the src/dataObjects folder, and they are decorated accordingly. [See more [here](https://medium.com/@zzpzaf.se/nestjs-rest-api-class-validator-class-transformer-bf7a0e6b311a) and/or [here](https://www.devxperiences.com/pzwp1/2022/03/14/nestjs-rest-api-class-validator-class-transformer/)]

* The repo uses externally defined variables, so the [@nestjs/config](https://www.npmjs.com/package/@nestjs/config) package is already installed, and it is declared globally in AppModule. The external variables are defined in the src/config/.env.dev file.  [See more [here](https://betterprogramming.pub/step-ahead-fast-with-nestjs-environment-configuration-406701b3379f) and/or [here](https://www.devxperiences.com/pzwp1/2022/01/26/step-ahead-fast-with-nestjs-environment-configuration/)]

* Also, the repo uses the  [Joi](https://joi.dev/) schema validation tool (which is also is being used in  [NestJS Documentation](https://docs.nestjs.com/pipes#object-schema-validation) for object schema validation). Moreover, a JSON object schema validator has been defined and decorated (using the appropriate Joi property decorators) in the src/config/config.schema.ts file. It is being used for the externally defined variables in the src/config/.env.dev file.

* The repo has defined and uses (via AuthController and UsersController) the following endpoints:

    + /auth/signup
    + /auth/signin
    + /users/
    + /users?
    + /users/:id/

* Also, note that the **/tickets** Global Prefix is being used, so for accessing users, you have to use: http://localhost:3000/tickets/users

* Finally, it uses the [Passport](https://www.passportjs.org/) package, uses [JSON Web Tokens – JWT](https://jwt.io/), and implements the Passport’s [JWT strategy](https://www.passportjs.org/packages/passport-jwt/) (as it is described in the **post** mentioned before)

## Clone this Repo

You can clone this repo by: 

`git clone https://github.com/zzpzaf/NestJS-Rest-API-basic1.git`

## License
[MIT](https://choosealicense.com/licenses/mit/)
