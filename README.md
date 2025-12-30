# Integrating LocationIQ with AIMMS

This AIMMS project illustrates the use of the LocationIQ AIMMS Library:

1. It provides an alternative to the AIMMS function GeoFindCoordinates. The argument names are the same, and the return value is the same.
    1. Copy the library to your own application.
    2. Get an access token from [LocationIQ](https://locationiq.com/)
    3. Replace calls to [GeoFindCoordinates](https://documentation.aimms.com/functionreference/system-interaction/environment-functions/geofindcoordinates.html) by calls to `liq::pr_GeoFindCoordinates`.
2. It illustrates using [the AIMMS DEX client library](https://documentation.aimms.com/dataexchange/rest-client.html)
   including its error handling.

## Functions

### liq::pr_setAccessToken

Arguments: 

- sp_newAccessToken: Input, String. The new access token to be used by `liq::pr_GeoFindCoordinates`

### liq::pr_GeoFindCoordinates

Convert a physical address into geographic coordinates using LocationIQ.
Returns 1 if the coordinates were successfully found, 0 if an error occurred.

Arguments:

- address: Input, String. A string representing the address for which the latitude and longitude coordinates have to be found.
- Latitude: Output, Numeric. A scalar numerical parameter that will contain the latitude coordinate of the specified address upon success.
- Longitude: Output, Numeric. A scalar numerical parameter that will contain the longitude coordinate of the specified address upon success.
- e-mail: Optional, String. Argument ignored, just provided for compatibility.
- url: Optional, String. Argument ignored, just provided for compatibility.

