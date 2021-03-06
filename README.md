![Python 2.7](https://img.shields.io/badge/python-2.7-green.svg)
![Python 3.6](https://img.shields.io/badge/python-3.6-green.svg)
## Dancing to Music
PyTorch implementation for music-to-dance generation.   


### License
Copyright (C) 2020 NVIDIA Corporation. All rights reserved. 

This work is made available under the Nvidia Source Code License (1-Way
 Commercial). To view a copy of this license, visit https://nvlabs.github.io/Dancing2Music/LICENSE.txt


### Paper 
[Hsin-Ying Lee](http://vllab.ucmerced.edu/hylee/), [Xiaodong Yang](https://xiaodongyang.org/), [Ming-Yu Liu](http://mingyuliu.net/), [Ting-Chun Wang](https://tcwang0509.github.io/), [Yu-Ding Lu](https://jonlu0602.github.io/), [Ming-Hsuan Yang](https://faculty.ucmerced.edu/mhyang/), and [Jan Kautz](http://jankautz.com/)  
[Dancing to Music](https://arxiv.org/abs/1911.02001)  
In Neural Information Processing Systems (**NeurIPS**) 2019


### Example Videos
For videos with audio, please visit our [youtube video](https://youtu.be/-e9USqfwZ4A)
- Generated Dance Sequences
second row: music beats; third row: kinematic beats
<p align='center'>
  <img src='imgs/example.gif' width='400'/>
</p>

- Multimodality
Generation given same music and same initial poses
<p align='center'>
  <img src='imgs/multimodal.gif' width='400'/>
</p>

- Long Sequence
<p align='center'>
  <kbd>
   <img src='imgs/long.gif' width='400'/>
  </kbd>
</p>

- Photo Realisitc Video
<p align='center'>
  <img src='imgs/v2v.gif' width='400'/>
</p>


## Train Decomposition Stage
- Run the script
  ```
  python train_decomp.py --name Decomp
  ```

## Train Composition Stage
- Run the script
  ```
  python train_comp.py --name Decomp --decomp_snapshot DECOMP_SNAPSHOT
  ```

## Demo
- Run the script
  ```
  python demo.py --decomp_snapshot DECOMP_SNAPSHOT --comp_snapshot
   COMP_SNAPSHOT --aud_path AUD_PATH --out_file OUT_FILE --out_dir OUT_DIR
   --thr THR
  ```
- Flags
  - `aud_path`: input .wav file
  - `out_file`: location of output .mp4 file
  - `out_dir`: directory for output frames
  - `thr`: threshold based on motion magnitude
  - `modulate`: whether to do beat warping

- For example
  ```
  python demo.py -decomp_snapshot snapshot/Stage1.ckpt --comp_snapshot
   snapshot/Stage2.ckpt --aud_path demo/demo.wav --out_file demo/out.mp4 
   --out_dir demo/out_frame
  ```

  

### Citation

If you find this code useful for your research, please cite our paper:

```
@inproceedings{lee2019dancing2music,
  title={Dancing to Music},
  author={Lee, Hsin-Ying and Yang, Xiaodong and Liu, Ming-Yu and Wang, Ting
-Chun and Lu, Yu-Ding and Yang, Ming-Hsuan and Kautz, Jan},
  booktitle={NeurIPS},
  year={2019}
}
```


