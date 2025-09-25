# Car Dealership Full Stack Application
<br/><br/> 
The solution consists of multiple technologies:
<br/><br/> 
**1.** The user interacts with the "Dealerships Website", a Django website, through a web browser.

**2.** The Django application provides the following microservices for the end user:

- **get_cars/** - To get the list of cars from
- **get_dealers/** - To get the list of dealers
- **get_dealers/:state** - To get dealers by state
- **dealer/:id** - To get dealer by id
- **review/dealer/:id** - To get reviews specific to a dealer
- **add_review/** - To post review about a dealer

**3.** The Django application uses SQLite database to store the Car Make and the Car Model data.

**4.** The "Dealerships and Reviews Service" is an Express Mongo service running in a Docker container. It provides the following services::

- **/fetchDealers** - To fetch the dealers
- **/fetchDealer/:id** - To fetch the dealer by id
- **fetchReviews** - To fetch all the reviews
- **fetchReview/dealer/:id** - To fetch reviews for a dealer by id
- **/insertReview** - To insert a review

**5.** "Dealerships Website" interacts with the "Dealership and Reviews Service" through the "Django Proxy Service" contained within the Django Application.

**6.** The "Sentiment Analyzer Service" is deployed on IBM Cloud Code Engine, it provides the following service:
- **/analyze/:text** - To analyze the sentiment of the text passed. It returns positive, negative or neutral.

**7.** The "Dealerships Website" consumes the "Sentiment Analyzer Service" to analyze the sentiments of the reviews through the Django Proxy contained within the Django application.
<br/><br/> 
<br/><br/>
![Solution Architecture](./dealership-architecture.png)
