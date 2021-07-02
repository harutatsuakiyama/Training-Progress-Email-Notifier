<h1 align="center">
    <img width="200" height="auto" src="resources/molecule.png" />
    <br>
    Heimdall Watchtower: 
    <br>
    Training Progress Email Notifier
</h1>

<p align="center">
  <a href="#Usage">Usage</a> •
  <a href="#Exhibition">Exhibition</a> •
  <a href="#Citation">Citation</a> •
  <a href="#Credits">Credits</a> •
  <a href="#Licence">Licence</a>
</p>

<h3 align="center">
Overview
</h3>

<p align="center">
<strong align="center">
Heimdall watchtower automatically send you emails to 
notify you of the latest progress of your deep learning 
programs. In this way, you will know how the training goes 
wherever you are. You will also know as soon as your 
program has been terminated by other users :-) 
</strong>
</p>

## Usage
### Quick Start
Simply run 
```bash
python email_test.py
```

**Please note**: The test email is sent through 
a temporal gmail account. It may reach its capacity 
for sending emails through the SMTP server. In this case, 
you will receive no test email. 

### Setup Your Own Email Address
Go to the file `email_config.py` and change the 
email address as well as password there. 
You may need to open the SMTP service from your 
email service provider. 
You may register for a new gmail account. Then, 
open the SMTP service for the new gmail account 
and allow the new account for less-secure app access. 
Instructions: 
- [Open SMTP](https://support.google.com/mail/answer/7126229?hl=en)
- [Allow Less-Secure APP Access](https://support.google.com/accounts/answer/6010255?hl=en)

## Screenshots
<p align="center">
    <img width=33% height="auto" src="resources/english_progress.png" alt="wla_p5_1" />
    <img width=33% height="auto" src="resources/english_complete.png" alt="wla_p5_2" />
    <img width=33% height="auto" src="resources/english_error.png" alt="wla_p5_3" />
    <img width=33% height="auto" src="resources/chinese_progress.png" alt="wla_p5_4" />
    <img width=33% height="auto" src="resources/chinese_complete.png" alt="wla_p5_5" />
    <img width=33% height="auto" src="resources/chinese_error.png" alt="wla_p5_6" />
</p>

## Languages 
Currently we support English and Chinese. Development 
of more languages are welcome. 

Just simply run a bash script. 
You can find such a bash script in the data 
directory. 
If you see warnings or even errors, 
please just don't worry. 

If you wish to use the QM9 dataset, 
you can skip the data downloading and 
directly proceed to data preprocessing. 
```bash
bash download_dataset.sh
```
### Data Preprocessing 
Just run the python script below. 
You will need to comment different different code 
sections in the main function. 
It is too easy to figure out how to do. 
```bash
python sparse_molecular_dataset.py
```
### MolGAN
Simply run the following command to train. 
```bash
python main_gan.py
```
### MolVAE
For your convenience, 
a VAE version is also implemented. 
```bash
python main_vae.py
```
### Testing
You will need to change some arguments 
in ``args.py`` to test the saved model. 
It is too easy and I believe you can figure out 
how to do it. 
### Kind Reminder
If you witness low or even zero validity for 
generated molecules during training, that is 
normal. Please just don't worry. 

## Molecule Generation Exhibition
These results are trained with the QM9 dataset. 
### Pure RL (WGAN-Lambda = 0.0)
<p align="center">
    <img width=15% height="auto" src="resources/rl_1.png" alt="rl_1" />
    <img width=15% height="auto" src="resources/rl_2.png" alt="rl_2" />
    <img width=15% height="auto" src="resources/rl_3.png" alt="rl_3" />
    <img width=15% height="auto" src="resources/rl_4.png" alt="rl_4" />
    <img width=15% height="auto" src="resources/rl_5.png" alt="rl_5" />
    <img width=15% height="auto" src="resources/rl_6.png" alt="rl_6" />
</p>

### Mixture of RL and GAN (WGAN-Lambda = 0.5)
<p align="center">
    <img width=15% height="auto" src="resources/wla_p5_1.png" alt="wla_p5_1" />
    <img width=15% height="auto" src="resources/wla_p5_2.png" alt="wla_p5_2" />
    <img width=15% height="auto" src="resources/wla_p5_3.png" alt="wla_p5_3" />
    <img width=15% height="auto" src="resources/wla_p5_4.png" alt="wla_p5_4" />
    <img width=15% height="auto" src="resources/wla_p5_5.png" alt="wla_p5_5" />
    <img width=15% height="auto" src="resources/wla_p5_6.png" alt="wla_p5_6" />
</p>

### Pure GAN (WGAN-Lambda = 1.0)
<p align="center">
    <img width=15% height="auto" src="resources/pure_gan_1.png" alt="pure_gan_1" />
    <img width=15% height="auto" src="resources/pure_gan_2.png" alt="pure_gan_2" />
    <img width=15% height="auto" src="resources/pure_gan_3.png" alt="pure_gan_3" />
    <img width=15% height="auto" src="resources/pure_gan_4.png" alt="pure_gan_4" />
    <img width=15% height="auto" src="resources/pure_gan_5.png" alt="pure_gan_5" />
    <img width=15% height="auto" src="resources/pure_gan_6.png" alt="pure_gan_6" />
</p>

### MolVAE Reconstruction
<p align="center">
    <img width=15% height="auto" src="resources/vae_rec_1.png" alt="vae_rec_1" />
    <img width=15% height="auto" src="resources/vae_rec_2.png" alt="vae_rec_2" />
    <img width=15% height="auto" src="resources/vae_rec_3.png" alt="vae_rec_3" />
    <img width=15% height="auto" src="resources/vae_rec_4.png" alt="vae_rec_4" />
    <img width=15% height="auto" src="resources/vae_rec_5.png" alt="vae_rec_5" />
    <img width=15% height="auto" src="resources/vae_rec_6.png" alt="vae_rec_6" />
</p>

### MolVAE Sampling
<p align="center">
    <img width=15% height="auto" src="resources/sample_1.png" alt="sample_1" />
    <img width=15% height="auto" src="resources/sample_2.png" alt="sample_2" />
    <img width=15% height="auto" src="resources/sample_3.png" alt="sample_3" />
    <img width=15% height="auto" src="resources/sample_4.png" alt="sample_4" />
    <img width=15% height="auto" src="resources/sample_5.png" alt="sample_5" />
    <img width=15% height="auto" src="resources/sample_6.png" alt="sample_6" />
</p>

## Dependencies 
I use PyTorch 1.5. There is no magic for installing 
packages. You can just install all the required 
packages if you run into ``no-such-package`` issues :-) 

## Contacts
If you have any questions regarding this implementation. Please lodge Github issues. 
You can also contact Zhenyue Qin (zhenyue.qin@anu.edu.au). 
I aim to respond emails as soon as I see them :-)  

## Citation
Apart from citing the MolGAN paper, please also consider citing this Github page 
if you find this implementation assists you :-) 
```
@misc{qin2020molgan_pytorch,
  author = {Qin, Zhenyue},
  title = {MolGAN Pytorch Implementaion},
  year = {2020},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/ZhenyueQin/Implementation-MolGAN-PyTorch}}
}
```

## Credits
This repository uses the following implementations: 
- [MolGAN PyTorch by YongQyu](https://github.com/yongqyu/MolGAN-pytorch)
- [MolGAN TF](https://github.com/nicola-decao/MolGAN)
- [Freeplk](https://www.flaticon.com/free-icon/molecule_2106435?term=molecule&page=1&position=58)

## Licence
[CC-BY-4.0](https://choosealicense.com/licenses/cc-by-4.0/)
