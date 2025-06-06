# Collision Insights

This is a project for a data science course. We're analyzing the US Traffic Accidents data set, which can be found [here](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents)

Per the source's request, these two papers are cited:
 * Moosavi, Sobhan, Mohammad Hossein Samavatian, Srinivasan Parthasarathy, and Rajiv Ramnath. “A Countrywide Traffic Accident Dataset.”, 2019.

 * Moosavi, Sobhan, Mohammad Hossein Samavatian, Srinivasan Parthasarathy, Radu Teodorescu, and Rajiv Ramnath. "Accident Risk Prediction based on Heterogeneous Sparse Data: New Dataset and Insights." In proceedings of the 27th ACM SIGSPATIAL International Conference on Advances in Geographic Information Systems, ACM, 2019.

 ### Project Structure

  * `col_insights.ipynb` - contains the working Jupyter notebook code that includes EDA and supports the final analysis
  * `museum.ipynb` - storage for ideas that didn't quite work out (read IFF you are curious what didn't work)
  * `recommendations.md` - the final recommendations for the project; USDOT stakeholders are the intended theoretical audience.
  * `project_discussion.md` - early discussion document
  * `created_data/` - directory for derived data (created is a slight misnomer). Intended for use in tableau or other general use. Data lacks documentation; see col_insights notebook.
  * `<tableau file> - tableau structure without data
  * `weather_mapping.json` - File to contain weather condition consolidation schema

### Project Tools

 * Tech stack: Python, including Pandas/NumPy, PySpark, 