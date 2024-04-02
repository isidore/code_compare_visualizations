## Sample

```diff
# public void sendOutSeniorDiscounts(DataBase database, MailServer mailServer) {
+      Loader<List<Customer>> seniorCustomerLoader = () -> database.getSeniorCustomers();
-      List<Customer> seniorCustomers = database.getSeniorCustomers();
+      List<Customer> seniorCustomers = seniorCustomerLoader.load();
#      for (Customer customer : seniorCustomers) {
#          Discount seniorDiscount = getSeniorDiscount();
#          String message = generateDiscountMessage(customer, seniorDiscount);
#          mailServer.sendMessage(customer, message);
#      }
# }
```
