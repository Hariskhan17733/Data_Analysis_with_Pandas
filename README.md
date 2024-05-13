# Pandas Project

# The Data

This data set contains booking information for a city hotel and a resort hotel, and includes information such as when the booking was made, length of stay, the number of adults, children, and/or babies, and the number of available parking spaces, among other things.

All personally identifying information has been removed from the data.

Acknowledgements
The data is originally from the article Hotel Booking Demand Datasets, written by Nuno Antonio, Ana Almeida, and Luis Nunes for Data in Brief, Volume 22, February 2019.


----------------------------

#### NOTE: Names, Emails, Phone Numbers, and Credit Card numbers in the data are synthetic and not real information from people. The hotel data is real from the publication listed above.

## <div style="text-align: center">Data Column Reference</div>

<table><thead><tr class="rowsep-1"><th scope="col"><strong>Variable</strong></th><th scope="col"><strong>Type</strong></th><th scope="col"><strong>Description</strong></th><th scope="col"><strong>Source/Engineering</strong></th></tr></thead><tbody><tr><th scope="row"><em>ADR</em></th><td>Numeric</td><td>Average Daily Rate as defined by <a name="bbib5" href="#bib5" class="workspace-trigger">[5]</a></td><td>BO, BL and TR / Calculated by dividing the sum of all lodging transactions by the total number of staying nights</td></tr><tr><th scope="row"><em>Adults</em></th><td>Integer</td><td>Number of adults</td><td>BO and BL</td></tr><tr><th scope="row"><em>Agent</em></th><td>Categorical</td><td>ID of the travel agency that made the booking<a name="btbl1fna" href="#tbl1fna" class="workspace-trigger"><sup>a</sup></a></td><td>BO and BL</td></tr><tr><th scope="row"><em>ArrivalDateDayOfMonth</em></th><td>Integer</td><td>Day of the month of the arrival date</td><td>BO and BL</td></tr><tr><th scope="row"><em>ArrivalDateMonth</em></th><td>Categorical</td><td>Month of arrival date with 12 categories: “January” to “December”</td><td>BO and BL</td></tr><tr><th scope="row"><em>ArrivalDateWeekNumber</em></th><td>Integer</td><td>Week number of the arrival date</td><td>BO and BL</td></tr><tr><th scope="row"><em>ArrivalDateYear</em></th><td>Integer</td><td>Year of arrival date</td><td>BO and BL</td></tr><tr><th scope="row"><em>AssignedRoomType</em></th><td>Categorical</td><td>Code for the type of room assigned to the booking. Sometimes the assigned room type differs from the reserved room type due to hotel operation reasons (e.g. overbooking) or by customer request. Code is presented instead of designation for anonymity reasons</td><td>BO and BL</td></tr><tr><th scope="row"><em>Babies</em></th><td>Integer</td><td>Number of babies</td><td>BO and BL</td></tr><tr><th scope="row"><em>BookingChanges</em></th><td>Integer</td><td>Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation</td><td>BO and BL/Calculated by adding the number of unique iterations that change some of the booking attributes, namely: persons, arrival date, nights, reserved room type or meal</td></tr><tr><th scope="row"><em>Children</em></th><td>Integer</td><td>Number of children</td><td>BO and BL/Sum of both payable and non-payable children</td></tr><tr><th scope="row"><em>Company</em></th><td>Categorical</td><td>ID of the company/entity that made the booking or responsible for paying the booking. ID is presented instead of designation for anonymity reasons</td><td>BO and BL.</td></tr><tr><th scope="row"><em>Country</em></th><td>Categorical</td><td>Country of origin. Categories are represented in the ISO 3155–3:2013 format <a name="bbib6" href="#bib6" class="workspace-trigger">[6]</a></td><td>BO, BL and NT</td></tr><tr><th scope="row"><br></th><td><br></td><td><br></td><td><br></td></tr><tr><th scope="row" rowspan="5"><em>CustomerType</em></th><td rowspan="5">Categorical</td><td>Type of booking, assuming one of four categories:</td><td rowspan="5">BO and BL</td></tr><tr><td>Contract - when the booking has an allotment or other type of contract associated to it;</td></tr><tr><td>Group – when the booking is associated to a group;</td></tr><tr><td>Transient – when the booking is not part of a group or contract, and is not associated to other transient booking;</td></tr><tr><td>Transient-party – when the booking is transient, but is associated to at least other transient booking</td></tr><tr><th scope="row"><em>DaysInWaitingList</em></th><td>Integer</td><td>Number of days the booking was in the waiting list before it was confirmed to the customer</td><td>BO/Calculated by subtracting the date the booking was confirmed to the customer from the date the booking entered on the PMS</td></tr><tr><th scope="row"><br></th><td><br></td><td><br></td><td><br></td></tr><tr><th scope="row" rowspan="7"><em>DepositType</em></th><td rowspan="7">Categorical</td><td>Indication on if the customer made a deposit to guarantee the booking. This variable can assume three categories:</td><td rowspan="2">BO and TR/Value calculated based on the payments identified for the booking in the transaction (TR) table before the booking׳s arrival or cancellation date.</td></tr><tr><td rowspan="3">No Deposit – no deposit was made;</td></tr><tr><td>In case no payments were found the value is “No Deposit”.</td></tr><tr><td rowspan="2">If the payment was equal or exceeded the total cost of stay, the value is set as “Non Refund”.</td></tr><tr><td rowspan="2">Non Refund – a deposit was made in the value of the total stay cost;</td></tr><tr><td rowspan="2">Otherwise the value is set as “Refundable”</td></tr><tr><td>Refundable – a deposit was made with a value under the total cost of stay.</td></tr><tr><th scope="row"><em>DistributionChannel</em></th><td>Categorical</td><td>Booking distribution channel. The term “TA” means “Travel Agents” and “TO” means “Tour Operators”</td><td>BO, BL and DC</td></tr><tr><th scope="row"><em>IsCanceled</em></th><td>Categorical</td><td>Value indicating if the booking was canceled (1) or not (0)</td><td>BO</td></tr><tr><th scope="row"><em>IsRepeatedGuest</em></th><td>Categorical</td><td>Value indicating if the booking name was from a repeated guest (1) or not (0)</td><td>BO, BL and C/ Variable created by verifying if a profile was associated with the booking customer. If so, and if the customer profile creation date was prior to the creation date for the booking on the PMS database it was assumed the booking was from a repeated guest</td></tr><tr><th scope="row"><em>LeadTime</em></th><td>Integer</td><td>Number of days that elapsed between the entering date of the booking into the PMS and the arrival date</td><td>BO and BL/ Subtraction of the entering date from the arrival date</td></tr><tr><th scope="row"><em>MarketSegment</em></th><td>Categorical</td><td>Market segment designation. In categories, the term “TA” means “Travel Agents” and “TO” means “Tour Operators”</td><td>BO, BL and MS</td></tr><tr><th scope="row"><br></th><td><br></td><td><br></td><td><br></td></tr><tr><th scope="row" rowspan="5"><em>Meal</em></th><td rowspan="5">Categorical</td><td>Type of meal booked. Categories are presented in standard hospitality meal packages:</td><td rowspan="5">BO, BL and ML</td></tr><tr><td>Undefined/SC – no meal package;</td></tr><tr><td>BB – Bed &amp; Breakfast;</td></tr><tr><td>HB – Half board (breakfast and one other meal – usually dinner);</td></tr><tr><td>FB – Full board (breakfast, lunch and dinner)</td></tr><tr><th scope="row"><em>PreviousBookingsNotCanceled</em></th><td>Integer</td><td>Number of previous bookings not cancelled by the customer prior to the current booking</td><td>BO and BL / In case there was no customer profile associated with the booking, the value is set to 0. Otherwise, the value is the number of bookings with the same customer profile created before the current booking and not canceled.</td></tr><tr><th scope="row"><em>PreviousCancellations</em></th><td>Integer</td><td>Number of previous bookings that were cancelled by the customer prior to the current booking</td><td>BO and BL/ In case there was no customer profile associated with the booking, the value is set to 0. Otherwise, the value is the number of bookings with the same customer profile created before the current booking and canceled.</td></tr><tr><th scope="row"><em>RequiredCardParkingSpaces</em></th><td>Integer</td><td>Number of car parking spaces required by the customer</td><td>BO and BL</td></tr><tr><th scope="row"><br></th><td><br></td><td><br></td><td><br></td></tr><tr><th scope="row" rowspan="4"><em>ReservationStatus</em></th><td rowspan="4">Categorical</td><td>Reservation last status, assuming one of three categories:</td><td rowspan="4">BO</td></tr><tr><td>Canceled – booking was canceled by the customer;</td></tr><tr><td>Check-Out – customer has checked in but already departed;</td></tr><tr><td>No-Show – customer did not check-in and did inform the hotel of the reason why</td></tr><tr><th scope="row"><em>ReservationStatusDate</em></th><td>Date</td><td>Date at which the last status was set. This variable can be used in conjunction with the <em>ReservationStatus</em> to understand when was the booking canceled or when did the customer checked-out of the hotel</td><td>BO</td></tr><tr><th scope="row"><em>ReservedRoomType</em></th><td>Categorical</td><td>Code of room type reserved. Code is presented instead of designation for anonymity reasons</td><td>BO and BL</td></tr><tr><th scope="row"><em>StaysInWeekendNights</em></th><td>Integer</td><td>Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel</td><td>BO and BL/ Calculated by counting the number of weekend nights from the total number of nights</td></tr><tr><th scope="row"><em>StaysInWeekNights</em></th><td>Integer</td><td>Number of week nights (Monday to Friday) the guest stayed or booked to stay at the hotel</td><td>BO and BL/Calculated by counting the number of week nights from the total number of nights</td></tr><tr><th scope="row"><em>TotalOfSpecialRequests</em></th><td>Integer</td><td>Number of special requests made by the customer (e.g. twin bed or high floor)</td><td>BO and BL/Sum of all special requests</td></tr></tbody></table>
