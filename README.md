<p align="center"><img src="Fibit Resources\Fitbit_logo.png" alt="Fitbit_logo" style="height:50px"/></p>

<p align="center">
 <a href="#overview">Overview</a> •
 <a href="#Rationale and definition (SDG9c)">Rationale and Definition</a> •
 <a href="#Data Source">Data Source</a> •
 <a href="#Solution Architecture">Solution Architecture</a> •
 <a href="#networking">Networking</a> •
 <a href="#license">License</a>
</p>



## Overview

On the 17 May 2022 ITU marks [World Telecommunication and Information Society Day](https://www.un.org/en/observances/telecommunication-day), this year's theme is **Digital technologies for older persons and healthy ageing**:

> The ageing of the global population will be the defining demographic trend of the 21st century—yet our societies struggle to see the opportunities that this trend can unfold. Telecommunications and information communication technologies (ICTs) have a role to play in achieving healthier ageing, but also in helping people build smarter cities, combat age-based discrimination at the workplace, ensure financial inclusion of older persons, and support millions of caregivers across the world.
>
> This year's theme raises awareness of the important role of telecommunications/ICTs in supporting people to stay healthy, connected and independent - physically, emotionally and financially. Supporting a life of healthy ageing is also critical for the sustainability of economic and health systems. The [International Telecommunication Union](https://www.itu.int/en) (ITU) hopes to foster initiatives to accelerate digital technologies for older persons and healthy ageing that will contribute towards the [UN Decade of Healthy Ageing](https://www.decadeofhealthyageing.org/).



## Rationale and definition

The theme described in the overview inspired me to do an analysis of my personal health and fitness and evaluate the progress 🤞😂 that I have made. The data is tracked from the **15 March 2022** (when I got my [Fitbit Charge 5](https://www.fitbit.com/global/uk/products/trackers/charge5?gclid=CjwKCAjwj42UBhAAEiwACIhADmoVq37g5FDdnkQb_A3GpXnVwAxkAp7_sVM9_h_jyt-eVn1rEH9C0RoC__gQAvD_BwE&gclsrc=aw.ds)) to the **14 May 2022**.



## Data Source

The data comes from two primary sources: my Charge 5 and  [Rephno Smart Body Fat Scale](https://uk.renpho.com/products/smart-body-fat-scale-basic?variant=38203353891015)

1. **Fitbit Data**: Daily Distance from Activities

   <p align="center"><img src="Fibit Resources\charge5-black-device-3qtr.png" alt="charge5-black-device-3qtr" style="height:350px" /></p>

2. **Rephno Data**: Daily Weight Measurement (Incl. BMI)

   <p align="center"><img src="https://m.media-amazon.com/images/I/61JlA-7e7aL._AC_SL1500_.jpg" alt="RENPHO Body Fat Scale Bluetooth, Digital Body Weight Bathroom Scales  Weighing Scale Smart BMI Scales, Body Composition Monitors with Smartphone  App, Black : Amazon.co.uk: Health & Personal Care" style="height:350px" /></p>

## Solution Architecture

1. Link the Rephno scale to the Fitbit app, every measurement recorded in the app gets auto send to Fitbit

   <p align="center"><img src="Fibit Resources\rephno-fitbit.jpeg" alt="rephno-fitbit" style="height:350px" /></p>

2. The data is collected/tracked in the Fitbit app

   <p align="center"><img src="Fibit Resources\fitbit_weight.jpeg" alt="fitbit_weight" style="height:350px" /></p>

3. Export the data from the Fitbit web-based dashboard as a CSV (**NB: **Data can only be exported in batches of 31 days, this is a bit inconvenient but PowerBI handles merging multiple files with relative ease)

   <p align="center"><img src="Fibit Resources\image-20220517121903674.png" alt="image-20220517121903674" style="height:350px" /></p>

4. Export the CSV files into a single working directory which will be used as a `folder data source` in PowerBI

  <p align="center"><img src="Fibit Resources\image-20220517122106574.png" alt="image-20220517122106574" style="height:350px" /></p>

5. The Fitbit data comes in well formatted and easily usable, only a few transformation steps were performed on the data
   - Filter to `Activity` data only i.e. exclude information on `body, foods and sleep` as highlighted in step 3 **NB**: the data can be filtered at export (Step 3)
   - Conversion to explicit data types (Decimal for numerical values)
   - Created a date column to conform to the set system date format `mm-dd-yyyy`



6. Create Report to represent the tracker metrics under focus
<p align="center"><img src="Fibit Resources\image-20220517122804588.png" alt="image-20220517122106574" style="zoom:25%" /></p>


## Networking

Connecting and building networks is always part of our priorities, please reach out if you have any ideas on collaborative efforts or any suggestions on ways we could improve our work, here's a funny picture to tag along with the analysis, so it looks like there's positive progress in my Fitness journey, getting my jawline back 😂😂:



<p align="center"><img src="Fibit Resources\before_after.png" alt="before_after" style="height:350px" /></p>



> Lehlohonolo Makoti, Data Management and Analytics Specialist
>
> LinkedIn - https://www.linkedin.com/in/lehlohonolomakoti/



## License

This license lets others distribute, remix, adapt, and build upon your work, even commercially, as long as they credit you for the original creation. This is the most accommodating of licenses offered. Recommended for maximum dissemination and use of licensed materials. (https://creativecommons.org/licenses/)
