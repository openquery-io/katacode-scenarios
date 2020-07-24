# Running Synth

Downloading Synth is super easy - simply pull the image from our container registry to get started:

'''bash
docker pull gcr.io/getsynth/synth
'''

Next, start the container:

'''bash
docker run -it \
           --entrypoint /bin/bash \
           -v $PWD/synth:/root/.config/synth:rw \
           gcr.io/getsynth/synth
'''


That's it - your done!
