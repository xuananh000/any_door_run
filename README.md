# fr_any_door

### Run docker image

CUDA 12.2


```bash
bash dev.sh
```

### Install Anaconda in docker container


Attach to docker container

```bash
xhost +
docker exec -it dev_64 /bin/bash
```

Install Anaconda

You must have Anaconda installer file `Anaconda3-*-*-Linux-x86_64.sh` in `your_path` and run this command

```bash
bash Anaconda3-*-Linux-x86_64.sh
```


```txt
Welcome to Anaconda3 2023.09-0

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>> 
```
Press `ENTER`

```txt
==================================================
End User License Agreement - Anaconda Distribution
==================================================

Copyright 2015-2023, Anaconda, Inc.

All rights reserved under the 3-clause BSD License:

This End User License Agreement (the "Agreement") is a legal agreement between you and Anaconda, Inc. 
("Anaconda") and governs your use of Anaconda Distribution (which was formerly known as Anaconda Indiv
idual Edition).

--More--
```
Press `q` to skip reading

```txt

Copyright 2015-2023, Anaconda, Inc.

All rights reserved under the 3-clause BSD License:

This End User License Agreement (the "Agreement") is a legal agreement between you and Anaconda, Inc. 
("Anaconda") and governs your use of Anaconda Distribution (which was formerly known as Anaconda Indiv
idual Edition).


Do you accept the license terms? [yes|no]
[no] >>> 
```
Enter `yes` to accept

```txt
Anaconda3 will now be installed into this location:
/root/anaconda3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/root/anaconda3] >>> 
```
Press `ENTER` to confirm and **wait** for installation


```txt
Do you wish to update your shell profile to automatically initialize conda?
This will activate conda on startup and change the command prompt when activated.
If you'd prefer that conda's base environment not be activated on startup,
   run the following command when conda is activated:

conda config --set auto_activate_base false

You can undo this by running `conda init --reverse $SHELL`? [yes|no]
[no] >>>
```
Enter `yes` to accept

```txt
Do you wish to update your shell profile to automatically initialize conda?
This will activate conda on startup and change the command prompt when activated.
If you'd prefer that conda's base environment not be activated on startup,
   run the following command when conda is activated:

conda config --set auto_activate_base false

You can undo this by running `conda init --reverse $SHELL`? [yes|no]
[no] >>> 

```

Enter `yes` to accept

You need to type 'bash' again to activate conda

```bash
bash
```

### Install Repo requirements

Go to repo directory


```bash
cd fr_any_door
```

Create conda environment

```bash
conda env create -f environment.yaml

```
Activate conda environment

```bash
conda activate anydoor
```

Install requirements

```bash
pip install -r requirements.txt
```

### Prepare for inference

Download pretrained model from [dino](https://dl.fbaipublicfiles.com/dinov2/dinov2_vitg14/dinov2_vitg14_pretrain.pth) and put it in `fr_any_door/srcs/AnyDoor/pretrained` directory

Download pretrained model from [huggingface.co/spaces/xichenhku/AnyDoor](https://huggingface.co/spaces/xichenhku/AnyDoor/blob/main/epoch%3D1-step%3D8687.ckpt) and put it in `fr_any_door/srcs/AnyDoor/pretrained` directory


Edit `weight`


`fr_any_door/srcs/AnyDoor/configs/anydoor.yaml`

