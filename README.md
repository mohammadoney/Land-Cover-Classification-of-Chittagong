# Land-Cover-Classification-of-Chittagong
1. Objective

The primary objective was to create a precise and reliable land cover map for the Chittagong District in Bangladesh. 
The project aimed to classify the landscape into four distinct categories—Urban, Bare Soil, Water, and Vegetation—using satellite imagery and machine learning. 
A key focus was on achieving high accuracy through rigorous validation, hyperparameter tuning, and post-processing techniques to ensure the map was robust and usable for environmental monitoring.
2. Data Acquisition

The project leveraged multiple geospatial data sources:

    Sentinel-2 Satellite Imagery: Used for its high spatial resolution and spectral bands, providing the base data for analysis.

    Google Cloud Score+: Used to perform cloud masking, ensuring a clear, high-quality composite image by removing pixels obscured by clouds and haze.

    JAXA ALOS Digital Elevation Model: Provided elevation and slope data, which are crucial topographical features for improving classification accuracy.

    Training Data: Manually collected point data (Ground Control Points) for the four land cover classes, which served as the "ground truth" for training and validating the model.

3. Data Processing

A multi-step pipeline was implemented to prepare the data for analysis:

    Cloud Masking: The Sentinel-2 imagery was filtered using the Cloud Score+ dataset to create a clean, cloud-free median composite.

    Spectral Index Calculation: Critical indices were computed from the satellite bands to enhance feature separation:

        NDVI (Normalized Difference Vegetation Index): To identify vegetation.

        NDBI (Normalized Difference Built-up Index): To identify urban areas.

        MNDWI (Modified Normalized Difference Water Index): To identify water bodies.

        BSI (Bare Soil Index): To identify bare land.

    Feature Integration: Elevation and slope data were added to the composite image to provide the model with topographical context.

4. Data Analysis

The core of the project involved supervised classification and rigorous accuracy assessment:

    Machine Learning Classification: A Random Forest classifier was trained on the prepared satellite data and the manually collected ground truth points.

    Robust Accuracy Assessment: A 10-fold cross-validation was performed to ensure the model's performance was not dependent on a single train-test split, providing a more reliable estimate of its real-world accuracy.

    Hyperparameter Tuning: The model's performance was systematically optimized by testing different combinations of parameters (like the number of trees and bag fraction) to find the most accurate configuration.

    Post-Processing: Two techniques were applied to the raw classification to reduce noise:

        Smoothing with Clusters: Isolated pixels were grouped into coherent segments.

        Majority Filtering: Small, isolated patches were replaced with the value of their surrounding pixels.

5. Potential Usage

The resulting high-resolution land cover map has direct applications in:

    Urban Planning: Monitoring urban sprawl and infrastructure development.

    Natural Resource Management: Tracking deforestation, water body changes, and soil erosion.

    Disaster Risk Assessment: Informing flood models and landslide risk by understanding land cover types.

    Agricultural Monitoring: Identifying and mapping agricultural land versus natural vegetation.

    Climate Change Studies: Serving as a baseline for monitoring land-use/land-cover change over time.

6. Impact

This project demonstrates a complete, production-grade workflow for generating accurate land cover data. 
By integrating multiple data sources, employing advanced machine learning, and implementing rigorous validation and optimization, it moves beyond a simple classification to create a reliable geospatial product. 
This methodology can be replicated for any region, providing valuable, data-driven insights for sustainable development and environmental conservation.
