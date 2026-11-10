


The order-domain module contains 2 submodules 
 - order-application-service module 
 - order-domain-core module

The order-application-service module contains the Input Port and Output Ports  .
 -  Input Port = Invoked from Primary Adapter (Rest Controller) defined in order-application module.


   // Defined in the order-application module


- The order-application module  [RestController] invokes the Input Port [OrderApplicationService] defined in order-application-service  module, so is added as dependency

    public class OrderController 
     {
      private final OrderApplicationService orderApplicationService; 
 
        <artifactId>order-application</artifactId>  
          <dependencies>
              <dependency>
                  <groupId>com.food.ordering.system</groupId>
                  <artifactId>order-application-service</artifactId> 
              </dependency>


-  Output Port  =  implemented by Secondary Adapter (order-repository).

          The order-application-service contains output port interface OrderRepository and its 
          implementation OrderRepositoryImpl in order-repository module.


## Docker changes 

1.
In Docker Desktop, go to Settings → General and untick Use containerd for pulling and storing images. 
Then Apply & restart and re-run. If the image is still pulled in a way that fails,
run docker system prune -a once first.

Use containerd for pulling and storing images

The containerd image store enables native support for multi-platform images, attestations, Wasm, and more. 