# Collision Insights Recommendations

First, we are dividing these recommendations into two categories. The first category is actionable insights that we believe are well-supported by the data. The second category are more general guidance/suggestions that may not be quite as well-supported.

### Actionable Insights

#### Targeted Lighting Improvements

Our analysis, initially focused on highways, found that there are some areas that are particularly dangerous at night. First, we determine a "severity score" which weights higher severity accidents on an exponential scale, reflecting the assumption that a "Severity 4" accident likely has more than twice as much impact on traffic as a "Severity 2". The formula is:

 - Severity 1: 1
 - Severity 2: 2
 - Severity 3: 4
 - Severity 4: 8

Initially we just looked at the entire highway, and determined which highways are the most "night dangerous" as a whole. <example> is a particularly strong example, with <score>. However, this has obvious limitations. Some interstates stretch across the width or height of the entire country, so just saying, "We need more lighting on I-95" is not particularly useful. We focused on narrowing this down to find specific "dark spots". We use the ratio of the night severity score to the total severity score to correct for areas that are simply more dangerous/higher traffic generally and identify areas that could likely benefit from additional lighting, reflective panels, and so on.

**Limitations**: The data set does not have specific information on whether the accident area was well-lit. We are assuming that an area that has a substantially higher proportion of accidents at night is likely not as well-lit, but there could be confounding variables, such as corridors with higher instances of drunk driving, which often occurs at night.

#### Insight 2

We found something cool

#### Insight 3

And something else even cooler

### Other Recommendations

#### Roundabouts

This is a well-studied phenomenon, and there are already many sources showing Roundabouts as a safer alternative - see [this](https://www.iihs.org/topics/roundabouts) page from the Insurance Institute for Highway Safety. We found that this data set lacked sufficient "before and after" information to truly prove their effectiveness, but their very scarcity in the data (249 accidents out of 7 million) is **suggestive** though far from conclusive (they are rarer in the first place, and the data set tends to focus on more serious accidents/biases towards highways).

#### Improved Data Collection

The cry of the analyst is always, "More and better data, please!" There are a lot of positives to this data - it is in fact surprisingly standardized given the context of being collected from many different states. We recognize the difficulty and potential expense in further standardization, but if possible, it would improve future analysis efforts. If weather is perceived to be an important factor, making sure all states include that information would help - this is very difficult to derive/infer after the fact from such a large set.

In particular, the "Description" column seems very lacking in useful details. The descriptions (if present) tend to sound like radio reports, advising motorists of the delays. They contain precious little information about the details/cause of the accident. Was a truck involved? Was drunk driving suspected? Were multiple vehicles involved? Was a vehicle malfunction a primary cause? And so on. Ideally, including police reports (summarized, if needed) would give the most information. Even something like a police incident ID might create the potential for future enrichment with other sources. Example found when searching for instances of drunk driving: "Accident on CA-49 at Drunken Miners Rd." 

More details about the accident would be especially helpful. Trucks tend to be involved in some of the most serious accidents (this is known/intuitive, but hard to prove from the data). Because these are professionally driven vehicles, there should be information available such as how many hours or miles the driver had been operating, their number of years as a professional truck driver, and so on. Details like the estimated speed of the vehicles could add a lot of value. Lastly, data about the injuries and deaths would allow us to quantify the "human aspect" rather than just focusing on the "traffic aspect". Specific information about hospital outcomes could be used to identify areas where there may be additional deaths because of distance to medical services, and possibly improve access via helicopters in remote areas.

The data set can be broken down into three basic categories: weather, location, and (limited) road features. Detailed information about the circumstances of the accident itself is sorely lacking.

#### DST

The data *seems* to challenge the well-studied phenomenon of Daylight Savings Time causing an increase in accidents. We observed no consistent difference in accidents between the Monday after spring DST vs before, or the Monday-Wednesday window (some years it went up, some down). There are many possible explanations for this that don't refute the claim of the shift causing an increase. We're noting this as an "interesting/surprising" finding that might merit further investigation.

#### Collection Methods

The sampling clearly increases year over year, making any analysis over a longer period of time impossible. The data shows a ~15 fold increase in accidents from 2016 to 2023, which is obviously not the case. The best way to correct for this would be to identify "channels" that allow for constant analysis over time. For example, we could identify all the inputs available at the end of 2022 as "Channel 1". As new inputs are added to the system they would receive their own channels. Meanwhile the number of accidents reported by "Channel 1" should reflect actual trends.