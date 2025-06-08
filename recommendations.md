# Collision Insights Recommendations

First, we are dividing these recommendations into two categories. The first category is actionable insights that we believe are well-supported by the data. The second category are more general guidance/suggestions that may not be quite as well-supported.

## Actionable Insights

### Targeted Lighting Improvements

Our analysis, initially focused on highways, found that there are some areas that are particularly dangerous at night. First, we define a "severity score" that weights higher-severity accidents exponentially, reflecting the assumption that a "Severity 4" accident likely has more than twice as much impact on traffic as a "Severity 2". The formula is:

 - Severity 1: 1
 - Severity 2: 2
 - Severity 3: 4
 - Severity 4: 8

First, we analyzed entire highways to determine which were the most 'night dangerous' overall. I-90 W is a particularly strong example, with 40% of accidents occuring at night. However, this has obvious limitations. Some interstates stretch across the width or height of the entire country, so just saying, "We need more lighting on I-90" is not particularly useful. We focused on narrowing this down to find specific "dark spots". We use the ratio of the night severity score to the total severity score to correct for areas that are simply more dangerous/higher traffic generally and identify areas that could likely benefit from additional lighting, reflective panels, and so on. We identified segments by county.

**Limitations**: The data set does not have specific information on whether the accident area was well-lit. We are assuming that an area that has a substantially higher proportion of accidents at night is likely not as well-lit, but there could be confounding variables, such as corridors with higher instances of drunk driving, which often occurs at night.

**Raw Frequency vs Proportion**: The current visualization indicates the "night severity proportion" via color and the raw frequency via size (log scaled). USDOT stakeholders will need to determine how to prioritize an area with 2 day accidents and 10 night accidents compared to an area with 20 day accidents and 20 night accidents. 

**Recommendation**: 
 1. Use the provided highway "night danger" visualization tool for regional analysis. 
 2. Physically inspect identified highway segments
    a. If they are found to be well-lit, consider drunk driving as a factor and investigate
    b. If they are not well-lit, increase visibility with standard highway lighting and reflective strips
    c. In either case, investigate maintenance plans (a currently well-lit highway may have a poor maintenance history)

Example Highway/County segments:
1. White, IL, Posey, IN, and Vanderburgh, IN stretch of I-64 (IL/IN border) - 55-65%
2. Oldham, TX on I-40 - **92%**
3. Rockdale, GA on I-20 - 80%

#### County Lighting

We have extended this "night danger" analysis to look at specific counties. This information can be relayed to local authorities to help identify areas where either poor lighting or drunk driving may be causing an increase in accidents.

### Data Quality

#### Categories to Add

The cry of the analyst is always, "More and better data, please!" There are some positives to this data - it is surprisingly standardized given the context of being collected from many different states. We recognize the difficulty and potential expense in further standardization, but if possible, it would improve future analysis efforts. If weather is considered important, ensuring all states include that information would help, as it is very difficult to derive after the fact from such a large dataset.

**Description**: this column seems very lacking in useful details. The descriptions (if present) tend to sound like radio reports, advising motorists of the delays. They contain precious little information about the details/cause of the accident. Was a truck involved? Was drunk driving suspected? Were multiple vehicles involved? Was a mechanical failure a primary cause? And so on. Ideally, including police reports (summarized, if needed) would give the most information. Even something like a police incident ID might create the potential for future enrichment with other sources. Example found when searching for instances of drunk driving: "Accident on CA-49 at Drunken Miners Rd." 

**Vehicle Types/Driver Behavior**: More details about the accident would be especially helpful. Trucks are often involved in the most severe accidents — a fact that is intuitive but difficult to substantiate with the available data. Because these are professionally driven vehicles, there should be information available such as how many hours or miles the driver had been operating, their number of years as a professional truck driver, and so on. Details like the estimated speed of the vehicles could add a lot of value. Lastly, data about the injuries and deaths would allow us to quantify the "human aspect" rather than just focusing on the "traffic aspect". Specific information about hospital outcomes could be used to identify areas where there may be additional deaths because of distance to medical services, and possibly improve access via helicopters in remote areas.

The data set can be broken down into three basic categories: weather, location, and (limited) road features. Critical details about the circumstances each accident are sorely lacking.

#### Collection Methods

The sampling clearly increases year over year, making any analysis over a longer period of time impossible. The data shows a ~15-fold increase in reported accidents from 2016 to 2023, but this appears to reflect an increase in reporting rather than a true rise in incidents. The best way to correct for this would be to identify "channels" that allow for constant analysis over time. For example, we could identify all the inputs available at the end of 2022 as "Channel 1". As new inputs are added to the system they would receive their own channels. Meanwhile the number of accidents reported by "Channel 1" should reflect actual trends. There seems to be some attempt at this with the "Source" field, but even broken down by source, there is a clear reporting increase.

#### Conclusion

We discussed ways to add to this data, but an equally valid approach would be to simplify the data set, focusing on only a few essential fields like Severity, Time, Latitude, and Longitude. The data could then be used to measure the effectiveness of various interventions.

**Recommendations**:
 1. "Go Big on Data"
    a. Identify and lock down input channels, enabling analysis over time
    b. Add core accident information: basic vehicle type (sedan, van, truck); important driver behavior factors like intoxication; outcome information (fatalities, injuries, estimated vehicle damage)
    c. This will allow **deep analysis** to uncover causal patterns
 2. "Go Small on Data"
    a. Defined input channels as above
    b. Pare down future collection to just essential fields
    c. Use this data to measure impacts of **specific interventions**

### Rare Winter Weather Events

We looked at the impact of winter weather events, particularly focused on a contrast between an identified set of "summer states" (AZ, GA, LA, SC, and TX) and "winter states" (MI, MN, NY, OR, and PA). The winter states, with consistently higher snowfall, have a substantially higher rate of accidents during winter weather (3-11%, compared to <1% for summer states). While there is always room for improvement, the winter states are likely already taking almost all measures to mitigate the frequent impacts.

Summer states, seeing these events much less frequently, are not as prepared. There is a statistically and practically significant increase in the severity of accidents during winter weather. Because Severity 3 and Severity 4 accidents are assumed to be much more disruptive, even a slight change in those rates would be helpful.

We created a visualization showing the relative frequency of winter accidents, looking at one state at a time to determine specifically where more resources should be allocated. Warmer states face the following challenges in dealing with winter weather events:

 1. Lack of equipment/infrastructure - fewer snow plows and salting trucks, less availability/distribution of sand/ice
 2. Driver inexperience - many drivers have little to no experience driving in winter weather conditions
 3. Emergency management inexperience - because of their rarity, emergency management teams lack the practical knowledge that comes with repeated experience
 4. Understandable hesitation to allocate resources preparing for rare events

**Recommendations**:
 1. Use the provided visualization tool to find particular areas that could benefit from dedicated resources (i.e. salt)
 2. Identify or create a pool of experts within USDOT who understand these challenges and also have experience with winter weather management. Make these experts available for both ongoing training and in advance of likely winter events
 3. Invest in modular vehicles and be ready to repurpose existing vehicles for winter events. This ensures resources are not idle, while also preparing for snow.
 4. Provide guidance on cross-training staff and ways to increase local collaboration

Example Counties: White, GA (ironically); Marion, AL; Ouachita, LA

## Other Recommendations

#### Roundabouts

This is a well-studied phenomenon, and there are already many sources showing Roundabouts as a safer alternative - see [this](https://www.iihs.org/topics/roundabouts) page from the Insurance Institute for Highway Safety. We found that this data set lacked sufficient "before and after" information to truly prove their effectiveness, but their very scarcity in the data (249 accidents out of 7 million) is **suggestive** though far from conclusive (they are rarer in the first place, and the data set tends to focus on more serious accidents/biases towards highways). For context, traffic signals (admittedly much more common) account for over **1 million** of the reported accidents.

#### Work From Home

There are substantially fewer accidents reported on the weekends. Weekday commutes ("rush hour" in particular) are a major source of accidents, and when accidents occur during these periods, they are more severe. The data should show a substantial drop in accidents during the COVID-19 lockdown, but we were unable to confirm this because of inconsistent reporting. Even a modest shift - such as 10-20% of employers offering one remote work day per week - could significantly reduce rush hour congestion and related accidents. It's easy to say "get more people to work from home" but challenging to put in place. USDOT could explore pilot programs that offer incentives to employers.

#### Daylight Savings Time

Our analysis does not show the expected consistent increase in accidents immediately following the spring DST shift. We observed no consistent difference in accidents between the Monday after spring DST vs before, or the Monday-Wednesday window (some years it went up, some down). There are many possible explanations for this that don't refute the claim of the shift causing an increase. We're noting this as an "interesting/surprising" finding that might merit further investigation.