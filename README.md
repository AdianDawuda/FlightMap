# Live Flight Tracker Austria

![Screenshot](git_assets/screenshot.png)

### Implementation 
This live flight-tracking application is developed using HTML, CSS, and JavaScript along with the OpenLayers library. The aircraft information is sourced from the OpenSky Network REST API. Additional data sources are Stadia Maps (basemaps), and Statistik Austria (state borders WFS). The application parses and makes use of sourced data with JavaScript functions, providing input for the OpenLayers map. The code contains extensive inline documentation explaining all key parts.
### Functionalities 
#### *Popups*
The pop-ups serve as one of the fundamental features of the application. By clicking on an aircraft, they allow users to access information about the specific flight, including the aircraft callsign, country of origin, velocity, and altitude. These pop-ups automatically close when the map is moved or when users click elsewhere.
#### *Basemaps* 
A layer switcher has been added to the code, allowing the user to switch between a dark and a light basemap, thereby altering the appearance of our application. This enables users to customize the design according to their preferences.
#### *Automated data update*
As our web application tracks flights in real time, an automated data update interval of five seconds was chosen to provide the user with the latest aircraft position and information. 	
#### *Scalebar and zoom buttons*
The scalebar allows for an easy understanding of the map’s scale. Zoom buttons in addition to scroll wheel zooming allow users to interactively change the scale of the map in an intuitive way.  
#### *Spatial filtering*
The WFS (Web Feature Service) of Austrian states is used to filter the aircraft geometries contained in the OpenSky API response (already filtered to Austria bounding box) to the exact borders of the Country.

### Design  
#### *Colors*
The colors of this application were selected to complement each other and match the overall dark theme.
#### *Panel* 
The panel provides users with additional information about the web application, the data sources as well as the authors. It has been selected with a dark background and is scrollable in case the user's screen size is too small to display it entirely.
#### *Basemap* 
Two basemaps were chosen. One dark-themed basemap is used as the default, and one light-themed map which users can switch to using the layer switcher.
#### *WFS*
The WFS has been rendered in a lighter grey tone and set with a transparency of 20% to ensure the underlying basemap remains legible. Representing data on the federal-state level allows users to quickly grasp the position of the aircraft. This layer may also be removed from the map using the layer switcher.
#### *Aircraft symbols* 
The aircraft symbols have been kept in simple white to provide a good contrast against the dark default basemap. Upon changing to the light basemap the aircraft icons change to dark icons the next time they are drawn to keep the contrast to the underlying layers.
### Additional notes
During the implementation phase, some minor changes were made to the original conceptual design of the application. The initially planned search bar was not implemented due to the limited meaningfulness of searching for specific aircraft callsign codes located in Austrian airspace. Instead, greater emphasis was placed on the visual appearance of the application, with the addition of a layer switcher, side panel, and changing aircraft colors based on the basemap. These features were not initially envisioned in the original concept.

Due to technical issues of the OpenSky Network infrastructure, account registration is not possible. Therefore, the application interacts with the API as an anonymous user (no authentication) and is limited to a certain number of API requests (400 credits). This limit is no problem to display the working concept of the application. However, if the application were to be made operational this issue would need to be resolved.