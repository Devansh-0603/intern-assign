# intern-assign
//   a) Read test and label files
import python libaraies ..
import pandas as pd
import matplotlib.pyplot as plt...

test_data = pd.read_csv('test.csv')
label_data = pd.read_csv('test_label.csv')

# Task b: Draw time series plots with anomaly regions

plt.figure(figsize=(12, 6))
plt.plot(test_data['timestamp'], test_data['value'], color='blue', label='Time Series Data')
anomaly_regions = label_data[label_data['anomaly'] == 1]
for i, row in anomaly_regions.iterrows():
    plt.axvspan(row['start_time'], row['end_time'], color='red', alpha=0.3, label='Anomaly Region')
plt.xlabel('Timestamp')
plt.ylabel('Value')
plt.title('Time Series Data with Anomaly Regions')
plt.legend()
plt.show()
