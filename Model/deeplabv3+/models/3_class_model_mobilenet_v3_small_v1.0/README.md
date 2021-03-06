## deeplabv3+ (mobilenet v3 small segmentation model)

Trained using following command:

python deeplab/train_adam.py     --logtostderr     --training_number_of_steps=20000     --train_split="combined"     --model_variant="mobilenet_v3_small_seg"     --tf_initial_checkpoint=deeplab/pretrained_models/deeplab_mnv3_small_cityscapes_trainfine/model.ckpt     --dataset_dir=deeplab/datasets/grassclover/tfrecord     --num_clones=3 --base_learning_rate=0.00001     --initialize_last_layer=False     --last_layers_contain_logits_only=False         --train_crop_size="768,768"     --train_batch_size=21     --dataset="combined3c"     --save_interval_secs=300     --save_summaries_secs=300     --save_summaries_images=True     --train_logdir=deeplab/logs/combined3c/mobilenetv3_small

Exported to .pb-file using following commands for either 2049x2049 or 256x256 input image size:

python deeplab/export_model.py   --logtostderr   --checkpoint_path=deeplab/logs/combined3c/mobilenetv3_small/model.ckpt-20000   --add_flipped_images=False --export_path="3_class_model_mobilenet_v3_small_v1.0.pb"   --model_variant="mobilenet_v3_small_seg"   --num_classes=3   --vis_crop_size=2049   --vis_crop_size=2049 --crop_size=2049 --crop_size=2049 --inference_scales=1.0 --dataset="combined3c"

python deeplab/export_model.py   --logtostderr   --checkpoint_path=deeplab/logs/combined3c/mobilenetv3_small/model.ckpt-20000   --add_flipped_images=False --export_path="3_class_model_mobilenet_v3_small_v1.0_256x256.pb"   --model_variant="mobilenet_v3_small_seg"   --num_classes=3   --vis_crop_size=256   --vis_crop_size=256 --crop_size=256 --crop_size=256 --inference_scales=1.0 --dataset="combined3c"
