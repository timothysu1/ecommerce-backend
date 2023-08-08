# E-Commerce Backend

## Description
This application allows the user to interact with a database that contains information on different merchanise that the user desires. It allows the user to log information on the product, what category the product pertains to, and any descriptive tags that describe the product.

[Walkthrough Video](https://drive.google.com/file/d/1Q08AfcmADfKOCShs6q9qdN51rBIx7Fuf/view?usp=sharing)

## Built With
* [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* [Git](https://git-scm.com/)
* [Node.js](https://nodejs.org/en/about)
* [MySQL](https://www.mysql.com/)
* [MySQL 2](https://www.npmjs.com/package/mysql2)
* [Sequelize](https://sequelize.org/)
* [Express](https://expressjs.com/)
* [dotenv](https://www.npmjs.com/package/dotenv)

## Installation

To install necessary dependancies, run the following command: 

```
npm i
```
## Usage
First the user will need to download the repository from GitHub and also create the ecommerce_db in their MySQL shell or workbench. The user will then have to install the dependancies and seed information into the database if they wish. Once all of that has been set up, the user can run ```npm start``` and open the application in Insomnia. The user will then be able to make requests to interact with the information on products, categories, and tags.

## Learning Points
* Using dotenv to store environment variables
* Using Sequelize to make working with MySQL easier
* Defining relationships between models

## Important Code
```js
router.get('/', async (req, res) => {
  try {
    const productData = await Product.findAll({
      include: [{ model: Category }, { model: Tag }],
    });
    res.status(200).json(productData);
  } catch (err) {
    res.status(500).json(err);
  }
});
```
This code sends infromation on a product in the JSON format when a get request is made.

## Author Info

### Timothy Su

* [LinkedIn](https://www.linkedin.com/in/timothysu1/)
* [Github](https://github.com/timothysu1)

## License

Please refer to license in the repo. 

## Contributions
Sequelize Associations Guide: https://sequelize.org/docs/v6/advanced-association-concepts/advanced-many-to-many/ 