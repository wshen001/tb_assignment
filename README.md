# tb_assignment
Assignment of TB Platform

## Technologies

### Backend

* [Express.js] - Fast, unopinionated framework for Node.js
* [Helmet] - Help secure Express apps with various HTTP headers
* [Mongodb] - Node.js driver for Mongodb

## Developement and Deployment

### Folder Structure

```bash
├── /server/         # Backend source code
| ├── /api.js        # Backend Api services
| ├── /config.js     # Backend configs
| ├── /db.js         # Database functional wrapper
| ├── /error.js      # Error handler
| ├── /index.js      # Backend Entrypoint
├── package.json     # npm packages info
```
## Local Development Setup

``` bash
# install package dependencies
npm install

# start the node server from localhost (debug)
npm run dev

```
## Production Deployment

Can Docker / Docker-compose to deploy the web app and its service.
In default setting, app will be deployed to :80 directly


## API Specification

All frontend activities and updates are basically driven by UI events (mouse or keyboard clicks) and actively API requesting to backend system.

The real API to transcoder and google cloud are all done in the backend. It provides restful APIs for frontside to fetch, update and delete the video.

Ａll error code are reporting as 4xx with json object { msg: 'XXXXX' }.

The following is the table of current API service provided by backend:

| Endpoint                 | Type    | Parameters            |  Return Code | Return Value                           |    Description             | 
| -------------------------|---------| ----------------------| -------------|----------------------------------------|----------------------------|
| /wishlist:pageSize-:page              | GET     |                       |              |                                        | Retrieve wishlist |
| /wishlist                   | POST    |                       |     200      | | add item to wishlist              |
| /wishlist                  | PUT    | item: { } |     200      |  { msg: 'updated' }             | update whishlist content             |
| /wishlist                    | DELETE    | item: { }         |     200      |  { msg: 'deleted' }                    | Delete item from whishlist      |
