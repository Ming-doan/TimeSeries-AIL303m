# Time Series

---

- Create virtual environment

```
$ virtualenv env
```

- Activate environment

```
$ env/Scripts/activate
```

- Install requirement

```
$ pip install -r requirements.txt
```

- Configs setting in cell `2` and `3`.

```python
# CONFIG VARIABLES
DATASET = 'PhuLien' # 'NiveauMer', 'PhuLien'
N_MISSING_SPACE = 2
MISSING_PERCENTAGE = 3
REMOVED_MODE = 'Random' # 'Linear', 'Random'
RANDOM_SEED = 42
KARMAN_FILTER = False

# MODEL CONFIGS
WINDOW_SIZE = 10
BATCH_SIZE = 1
EPOCHS = 10
SCALER = MinMaxScaler()
LOSS = keras_loss.MeanSquaredError()
OPTIMIZER = keras_optimizer.Adam()

# LAYERS CONFIGS
MODEL_LAYERS = [
    keras_layers.LSTM(128, activation='relu', return_sequences=True),
    keras_layers.Dropout(0.2),
    keras_layers.LSTM(2**5, activation='relu'),
    keras_layers.Dropout(0.2),
    keras_layers.Dense(1)
]

# Nếu True, model sẽ train trên tập data được chia làm đôi, mỗi tập được loại bỏ missing và nối lại
# Nếu False, model sẽ train trên 2 data không missing ngay cạnh khu vực missing
IS_CONCAT_PIPELINE = True

# Nếu True, mỗi khu vực missing sẽ được train trên 1 model riêng
# Nếu False, tất cả khu vực missing sẽ được train trên 1 model
IS_DISCRETE_MODEL = False

# Nếu True, mỗi chiều sẽ được train trên 1 model riêng
# Nếu False, tất cả chiều sẽ được train trên 1 model
IS_2_SIDE_MODEL = True
```

- Press Run All on `TIMESERIES_1.ipynb` file.
