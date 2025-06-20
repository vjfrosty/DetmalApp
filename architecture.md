%% Single Docker container, all-in-one stack
graph TD
    Dentist --> Browser
    Browser --> WebApp["Web App (React + Flask)"]
    WebApp --> Auth["JWT + MFA Auth"]
    WebApp --> ModelAPI["ML Prediction (U-Net / YOLO)"]
    WebApp --> LocalDB["Postgres DB"]
    WebApp --> FileStore["Local / MinIO Storage"]
    WebApp --> Logs["Audit Logs"]
    WebApp --> ModelManager["Model Hotloader + Retrainer"]
