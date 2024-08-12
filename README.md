# ECommerceMicroservices
Microservices E-Commerce Backend SpringBoot Application.  

#### Repository Links to individual microservices-
Product Service   -   [Product Service Github Repo](https://github.com/neeraj06152k/ProductService.git)  
Order Service     -   [Order Service Github Repo](https://github.com/neeraj06152k/OrderService.git)  
Payment Service   -   [Payment Service Github Repo](https://github.com/neeraj06152k/PaymentService.git)  
Cart Service      -   [Cart Service Github Repo](https://github.com/neeraj06152k/CartService.git)  

## TL;DR
This repo is a collection of backend RESTful APIs required for E-Commerce applications. These are built using Java and SpringBoot.  
- Product Service will provide the products and it's cost and other details to the client.
- Order Service will create an order for a user's product cart and will calculate the total amount.
- Payment Service will create a payment link for the client to pay for their order.
- After successful payment the order status will updated and the user's cart will be cleared.


## Process Flow
The process flow from browsing the products to the order payment is as follows.  
- First the client will get the list of products from product service.
- Then the client will send post requests to the cart service to add the desired products to the cart.
- Then a post request will be sent to the order service with the list of products in the request body.
- Then the order service will create an order entity for the products with status as 'PENDINGPAYMENT'.
- The order service will the send a request to cart service to clear the cart and respond to the client with an orderId.
- The client will then initiate the payment process by sending a post request to the payment service with the orderId in the request body.
- The payment service will get the payment details like the amount by sending a request to the order service with the orderId in the request body.
- After receiving the details from order service, the payment service will send the client a payment link.
- After successful payment by the client, the payment service will send a request to the order service to update the order's order status.
- The order service then updates the status of the order to "PAYMENTCOMPLETED".


## Microservices Diagram  
![ECommerce_backend drawio](https://github.com/user-attachments/assets/fb1b4700-75e5-40d9-a416-e5cdb36fe32b)


## Payment Flow Diagram
![Payment Flow Diagram drawio](https://github.com/user-attachments/assets/076ceede-4096-4d44-bfe8-8a807606c115)






