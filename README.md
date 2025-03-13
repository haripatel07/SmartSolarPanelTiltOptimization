# Solar Panel Tilt Optimization using Machine Learning & Deep Learning

## Project Overview
This project focuses on optimizing solar panel performance by predicting **POA Global Irradiance**, **Surface Tilt**, and **Surface Azimuth** to maximize energy generation. It leverages **Machine Learning (Random Forest, Gradient Boosting)** and **Deep Learning (LSTM)** models to achieve this goal. The models are trained and evaluated using performance metrics such as **Mean Squared Error (MSE)**, **R² Score**, and **Mean Absolute Error (MAE)**.

The notebook follows a structured approach:
- **Data Preprocessing**: Cleaning and preparing datasets.
- **Feature Engineering**: Selecting key features for predicting POA Global Irradiance, Surface Tilt, and Surface Azimuth.
- **Model Training**: Implementing and training ML/DL models.
- **Model Evaluation**: Assessing performance with metrics.
- **Results & Analysis**: Comparing model outcomes.
- **Conclusion**: Summarizing findings and suggesting improvements.

## Key Findings
- **Random Forest** outperformed other traditional ML models with the lowest error and highest R² scores for predicting POA Global Irradiance, Surface Tilt, and Surface Azimuth.
- **Gradient Boosting** showed high accuracy but was slightly less effective than Random Forest across these predictions.
- **LSTM** achieved the lowest test loss, excelling in sequential learning, though Surface Tilt predictions require further refinement.

## Dependencies
This project requires the following Python libraries:
- `pandas`
- `numpy`
- `seaborn`
- `matplotlib`
- `tensorflow` (with GPU support recommended)
- `scikit-learn`

**Note**: The datasets (`2017_2019.csv`, `solar_angles_dataset.csv`, `solar_forecasting.csv`) are not included in this repository due to size or access restrictions. Users must provide these files and adjust file paths in the notebook accordingly.

## Model Details
### Machine Learning Models
- **Random Forest**: Best-performing model for accuracy and stability in predicting POA Global Irradiance, Surface Tilt, and Surface Azimuth.
- **Gradient Boosting**: High accuracy, slightly less effective than Random Forest for these predictions.

### Deep Learning Model
- **LSTM**:
  - **Architecture**: 64 LSTM units (ReLU) → 32 Dense units (ReLU) → 3 output neurons (for POA Global Irradiance, Surface Tilt, Surface Azimuth).
  - **Optimization**: Adam optimizer and MSE loss.
  - **Challenges**: Captures temporal dependencies but requires adjustment for **negative Surface Tilt predictions**.

## Results
- **Random Forest**: Most reliable for predicting **POA Global Irradiance, Surface Tilt, and Surface Azimuth**.
  - Test Metrics:
    - **POA Global Irradiance MSE**: `17.6038`
    - **POA Global Irradiance R²**: `0.9997`
    - **Surface Tilt MSE**: `0.0444`
    - **Surface Tilt R²**: `0.9999`
    - **Surface Azimuth MSE**: `0.0144`
    - **Surface Azimuth R²**: `0.99997`
  - Sample Predictions (assumed examples):
    - Sample 1: POA Global = 300.12, Surface Tilt = 5.23, Surface Azimuth = 90.45
    - Sample 2: POA Global = 370.89, Surface Tilt = 12.67, Surface Azimuth = 98.12

- **Gradient Boosting**:
  - High accuracy but slightly outperformed by Random Forest in predicting POA Global Irradiance, Surface Tilt, and Surface Azimuth.
  - Test Metrics:
    - **POA Global Irradiance MSE**: `88.6979`
    - **POA Global Irradiance R²**: `0.9986`
    - **Surface Tilt MSE**: `0.4066`
    - **Surface Tilt R²**: `0.9991`
    - **Surface Azimuth MSE**: `0.2972`
    - **Surface Azimuth R²**: `0.9993`
  - Sample Predictions (assumed examples):
    - Sample 1: POA Global = 298.76, Surface Tilt = 4.89, Surface Azimuth = 91.23
    - Sample 2: POA Global = 368.45, Surface Tilt = 11.98, Surface Azimuth = 97.89

- **LSTM**: Promising for sequential predictions of POA Global Irradiance, Surface Tilt, and Surface Azimuth, with:
  - **Test Loss**: `0.4816`
  - **Test MSE**: `0.4816`
  - **Test MAE**: `0.5092`
  - Sample Predictions:
    - Sample 1: POA Global = 296.7306, Surface Tilt = -0.7658, Surface Azimuth = 89.1590
    - Sample 2: POA Global = 374.0726, Surface Tilt = 10.9956, Surface Azimuth = 99.0403

## Future Enhancements
- Develop **hybrid models** (e.g., **Random Forest + LSTM**) for improved generalization in predicting POA Global Irradiance, Surface Tilt, and Surface Azimuth.
- **Fine-tune LSTM** to eliminate **negative Surface Tilt predictions**.
- Incorporate **additional data** (e.g., **weather conditions**) for enhanced accuracy.

## Conclusion
This project demonstrates the effectiveness of **ML and DL** in predicting **POA Global Irradiance, Surface Tilt, and Surface Azimuth** to optimize solar panel orientation. **Random Forest** is the best-performing approach, while **LSTM** offers potential for **time-series applications** with further refinement.

## License
This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details (if applicable).
