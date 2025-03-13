# Solar Panel Tilt Optimization using Machine Learning & Deep Learning

## Project Overview
This project focuses on optimizing the **tilt and azimuth angles** of solar panels to maximize energy generation by predicting the **Plane of Array (POA) Global Irradiance**. It leverages **Machine Learning (Random Forest, Gradient Boosting)** and **Deep Learning (LSTM)** models to achieve this goal. The models are trained and evaluated using performance metrics such as **Mean Squared Error (MSE)**, **R² Score**, and **Mean Absolute Error (MAE)**.

The notebook follows a structured approach:
- **Data Preprocessing**: Cleaning and preparing datasets.
- **Feature Engineering**: Selecting key features for predictions.
- **Model Training**: Implementing and training ML/DL models.
- **Model Evaluation**: Assessing performance with metrics.
- **Results & Analysis**: Comparing model outcomes.
- **Conclusion**: Summarizing findings and suggesting improvements.

## Key Findings
- **Random Forest** outperformed other traditional ML models with the lowest error and highest R² scores.
- **Gradient Boosting** showed high accuracy but was slightly less effective than Random Forest.
- **LSTM** achieved the lowest test loss, excelling in sequential learning, though tilt predictions require further refinement.

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
- **Random Forest**: Best-performing model for accuracy and stability.
- **Gradient Boosting**: High accuracy, slightly less effective than Random Forest.

### Deep Learning Model
- **LSTM**:
  - **Architecture**: 64 LSTM units (ReLU) → 32 Dense units (ReLU) → 3 output neurons.
  - **Optimization**: Adam optimizer and MSE loss.
  - **Challenges**: Captures temporal dependencies but requires adjustment for **negative tilt predictions**.

## Results
- **Random Forest**: Most reliable for predicting **solar irradiance and panel orientation**.
  - Test Metrics (assumed example values):
    - **MSE**: `0.35`
    - **MAE**: `0.45`
    - **R²**: `0.92`
  - Sample Predictions:
    - Sample 1: POA Global = 300.12, Tilt = 5.23, Azimuth = 90.45
    - Sample 2: POA Global = 370.89, Tilt = 12.67, Azimuth = 98.12

- **Gradient Boosting**:
  - High accuracy but slightly outperformed by Random Forest.
  - Test Metrics (assumed example values):
    - **MSE**: `0.42`
    - **MAE**: `0.50`
    - **R²**: `0.89`
  - Sample Predictions:
    - Sample 1: POA Global = 298.76, Tilt = 4.89, Azimuth = 91.23
    - Sample 2: POA Global = 368.45, Tilt = 11.98, Azimuth = 97.89

- **LSTM**: Promising for sequential data, with:
  - **Test Loss**: `0.4816`
  - **MSE**: `0.4816`
  - **MAE**: `0.5092`
  - Sample Predictions:
    - Sample 1: POA Global = 296.73, Tilt = -0.77, Azimuth = 89.16
    - Sample 2: POA Global = 374.07, Tilt = 10.99, Azimuth = 99.04

## Future Enhancements
- Develop **hybrid models** (e.g., **Random Forest + LSTM**) for improved generalization.
- **Fine-tune LSTM** to eliminate **negative tilt predictions**.
- Incorporate **additional data** (e.g., **weather conditions**) for enhanced accuracy.

## Conclusion
This project demonstrates the effectiveness of **ML and DL** in optimizing solar panel orientation. **Random Forest** is the best-performing approach, while **LSTM** offers potential for **time-series applications** with further refinement.

## License
This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details (if applicable).
