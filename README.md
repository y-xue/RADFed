[Mobilenet V2 checkpoint](https://storage.googleapis.com/mobilenet_v2/checkpoints/mobilenet_v2_1.0_224.tgz) from its [official github repo](https://github.com/tensorflow/models/tree/master/research/slim/nets/mobilenet)

Datasets: [COVFEAT](https://www.dropbox.com/s/dfy32fuc8cuqcm4/100_client_data_dirichlet_noniid_cat_features_classes_random_qp_alpha1_lambda0.1_theta0.1_5folds_seed1122.tar.gz?dl=1), [COVCLS](https://www.dropbox.com/s/1kmznrszez0psx0/100_client_data_dirichlet_noniid_classes_random_qp_alpha1_beta0.1_0.1-0.2opt_loss_piter5e5_biter5e5_5folds_seed1020.tar.gz?dl=1), [Cifar10](https://www.dropbox.com/s/rzuvemautwlx8pj/100_client_data_dirichlet_noniid_classes_random_qp_alpha1_beta0.1_0.1-0.2opt_loss_piter5e5_biter5e5_seed2366.tar.gz?dl=1), [Shakespeare](https://www.dropbox.com/s/4m8ihsl18kopfad/143_client_data_seed245.tar.gz?dl=1), [MNIST lambda1](https://www.dropbox.com/s/0k327mg7ssrycqi/100_client_data_dirichlet_noniid_classes_random_qp_alpha1_beta0.1_0.1-0.2opt_loss_search0.002_piter5e5_biter5e5_5folds_seed233.tar.gz?dl=1), [MNIST lambda0.1](https://www.dropbox.com/s/hc4rmxdohppaitz/100_client_data_dirichlet_noniid_classes_random_qp_alpha1_beta1_0.1-0.2opt_loss_search0.002_qiter5e5_biter5e5_seed10.tar.gz?dl=1)

Train RADFed

`python radfed.py --modelname=lstm --score=acc --num_round=1500 --num_clients=143 --num_shuffle_round=15 --client_data_path=data/shakespeare/143_client_data_seed245 --out_path=out/test_run --num_classes=80 --save_file --num_tr_workers=2 --num_gpus=1 --gpu_ids=0 --learning_rate=0.5 --batch_size=256 --num_local_epochs=1 --C=0.1 --optimizer=sgd --window_size=100 --threshold=0.001 --converge_window=100`