# Zaalima-Project-2
git add # Initialize inspector
inspector = PCBQualityInspector(image_size=(256, 256))

# Option 1: Train on new data
# train_dir = 'path/to/train_data'
# val_dir = 'path/to/val_data'
# history = inspector.train_on_data(train_dir, val_dir, epochs=30, batch_size=32)
# inspector.save_model('pcb_model_trained.h5')

# Option 2: Load pre-trained model
# inspector.load_model('pcb_model_trained.h5')

# Option 3: Real-time inspection from camera
print("\nStarting Real-Time Inspection from Camera...")
inspector.real_time_inspection_from_camera(
    camera_id=0,
    output_file='inspection_results.json',
    threshold=0.5
)

# Print performance metrics
metrics = inspector.get_performance_metrics()
if metrics:
    print("\nPerformance Metrics:")
    for key, value in metrics.items():
        print(f"  {key}: {value}")
