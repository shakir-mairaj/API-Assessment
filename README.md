# API-Assessment
Following are the list of APIs on the restful-booker website which I have used to write end to end tests.

Create Booking
Get Booking Id
Update Booking
Partial Update Booking
Delete Booking

For sending the Update, Partial Update and Delete Booking requests it requires an AUTH token which is generated using the CreateToken API.

Following are the detailed steps of implementation:

Create a Booking, all test data required to be sent in the body of the request will be picked from a separate pojo which will build the data for post request.
Assert the response of Create Booking request with the data posted using the Step 1.
Save the Booking Id from create booking response in a variable so it could be used in further tests.
Get Booking details using the Booking Id in Step 2 and compare with the create booking response ideally from the data posted using Step 1.
Create a token generation method so it could be reused in Put, Patch and Delete requests.
Update all the booking details using the Booking Id in Step 2 and AUTH token in Step 4. Generate a separate booking data using the booking data builder as discussed in Step 1.
Assert the response of update booking.
Update the firstnameand totalpriceusing the Patch request.
Assert the response returned from Patch request using the updated data that was supplied. Here, only firstname and totalprice will be asserted using the partial update data builder and the remaining values in the response will be asserted using the data built in Step 6.
Delete the booking and assert the status code.
Get the Booking Id which is deleted( bookingIdfrom Step 2), here it is expected to send status code 404 since the booking is already deleted. This step confirms that booking got successfully deleted from the system.
