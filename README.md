# Detection-of-Inefficiencies-in-Solar-Plant

## PROJECT DESIGN

In this case we will be working for a photovoltaic solar power generation company.

Anomalous behaviors have been detected in 2 of the plants and the maintenance subcontractor is unable to identify the reason.

Before deploying a team of engineers, they ask the data science team to analyze the data from the sensors and meters to see if we can detect the problem.

## OBJECTIVE

Analyze the available data to try to intuit where the problems may be and whether or not it is necessary to send a team of engineers to the plants.

## LEVERS

1. **Irradiation**: the greater the irradiation, the greater the DC generated.
2. **Condition of the panels**: they must be clean and in good working order to generate the most DC power possible.
3. **Inverter efficiency**: there is always a loss in the transformation from DC to AC, but it must be as little as possible. They must also be in proper condition and working order.
4. **Meters and sensors**: if they break down and do not measure well, we lose traceability and the possibility of detecting failures.

## KPIs

* Irradiation: measures the solar energy that arrives
* Ambient and module temperature: measured by plant sensors in degrees Celsius
* DC power: measure the kW of direct current
* AC power: measure the kW of alternating current
* Inverter efficiency (we will create it): measures the capacity of transformation from DC to AC. It is calculated as AC/DC * 100

## ENTITIES AND DATA

In our case, the entities that we have in the granularity of the data are:
    
* 15-minute windows over a 34-day period
* Plants: there are 2
* Inverters: several per plant
* Only one irradiation sensor per plant
* Only one room temperature sensor per plant
* Only one module temperature sensor per plant

This conditions what we will be able to know, for example, if an inverter in a plant has lower performance than expected, but we will not know which array, panel or module may be causing it.

## SEED QUESTIONS

Having understood the levers, KPIs and entities, we can now ask the seed questions:

About irradiation:

* Is there enough irradiation every day?
* Is it similar on both plants?
* How is your hourly distribution?
* How is it related to ambient temperature and module temperature?

About the plants:

* Does the same amount of irradiation reach them?
* Do they have a similar number of inverters?
* Do they generate similar amounts of DC?
* Do they generate a similar amount of AC?

About the DC generation:

* What is the relationship between irradiation and DC generation?
* Is it ever affected by ambient or module temperature?
* Is it similar on both plants?
* How is it distributed throughout the day?
* Is it constant throughout the days?
* Is it constant in all inverters?
* Have there been moments of failure?

About AC generation:

* What is the relationship between DC and AC generation?
* Is it similar on both plants?
* How is it distributed throughout the day?
* Is it constant throughout the days?
* Is it constant in all inverters?
* Have there been moments of failure?

About meters and sensors:

* Are the irradiation data reliable?
* Is the temperature data reliable?
* Is the DC data reliable?
* Are the CA data reliable?
* Are the data similar between the two plants?
