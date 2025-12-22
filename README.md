# Highlight What You Want

Codes for ***Highlight What You Want: Weakly-Supervised Instance-Level Controllable Infrared-Visible Image Fusion***. ***(ICCV 2025)***
[Paper](https://openaccess.thecvf.com/content/ICCV2025/html/Wang_Highlight_What_You_Want_Weakly-Supervised_Instance-Level_Controllable_Infrared-Visible_Image_Fusion_ICCV_2025_paper.html)

------

![pipline](RISW-STAGE1-OS/configs/pipline.png)

------

### 1.Create Envrionment

- Create Conda Environment

```shell
conda create -n ris_fusion_env python=3.10
conda activate ris_fusion_env
```

- Install Dependencies

```shell
pip install -r requirements.yml
```

------

### 2.Pre-trained Weights
The Pre-trained weights for fusion is at [weights](https://drive.google.com/drive/folders/1Enxz_1HuLAuWGpvHjqIGOoGjNRw5SUOy?usp=drive_link). 

Please put the '`best_model.pth`' in '`RISW-STAGE2-OS/CRIS/exp/refcoco/CRIS_R50`'  and the `'model_stage2.pth'` in `'RISW-STAGE2-OS/'`

------

### 3.Testing
For generate fusion image, please run

```PYTHON
python ./RISW-STAGE2-OS/test_one_img.py
```

Result will be saved in the `'./RISW-STAGE2-OS/test_rusults/'` folder.

------

### 4.Training
Training Set for Stage II is at [Train](https://drive.google.com/file/d/1MaVBH6XuK3pqhO88BhpR1Bw3platf1uX/view?usp=drive_link).
##### RISW-STAGE1-OS

Please prepare the training data at

```python
data/ 
	IVT_train/
    	ir/
            1.png
            2.png
       		 ...
        vi/
            1.png
            2.png
            ...
        text/
            1.txt
            2.txt
            ... 	
```

Run the code

```python
python train_stage1.py
```

------

##### RISW-STAGE2-OS

Please prepare the training data at 

```PYTHON
dataset/ 
	IVT_final/
    	IVT_ir/
            1.png
            2.png
       		 ...
        IVT_vi/
            1.png
            2.png
            ...
        IVT_text/
            1.txt
            2.txt
            ... 	
```

After that, run the following command:

```python
python dataprocess.py
python train_fused.py
```
------

### 5.Fusion Results

1.Qualitative comparison of various fusion models.

![fusion](RISW-STAGE1-OS/configs/fusion.png)

------

2.Quantitative comparison of various fusion models across four test sets.

![fusion](RISW-STAGE1-OS/configs/table.png)

------
### 6.Citation
```python
@InProceedings{Wang_2025_ICCV,
    author    = {Wang, Zeyu and Zhang, Jizheng and Song, Haiyu and Ge, Mingyu and Wang, Jiayu and Duan, Haoran},
    title     = {Highlight What You Want: Weakly-Supervised Instance-Level Controllable Infrared-Visible Image Fusion},
    booktitle = {Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
    month     = {October},
    year      = {2025},
    pages     = {12637-12647}
}
```

