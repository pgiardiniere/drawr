Preprequisite: Make an account on huggingface.co. 

Then create a user access token so you can use model weights. read permission is enough, we are only using the model at test-time (i.e. for evaluation). *Write permission would be useful only if we were training models and/or otherwise uploading to huggingface.co.* You also need to link that token to your shell session, but you can't do this until after you've created the environment, so just leave the page with your token open for now.

Finally, accept the terms & conditions on the Stable Diffusion v1.4 'model card' page found here https://huggingface.co/CompVis/stable-diffusion-v1-4

That is also the location of the sample code I finally got to run.

This is basically the tutorial from the same model card page except that it actually works because we installed torch to the environment (seriously guys...)


```
conda create --prefix ./.env python=3.8

conda activate ./.env

pip install --upgrade diffusers transformers scipy flask torch

huggingface-cli login
<& input your access token>

python ./sample.py

```

If it works you'll get an astronaut_rides_horse.png file.
