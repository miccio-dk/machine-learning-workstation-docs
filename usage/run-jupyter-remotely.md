# Run Jupyter remotely

This page provides support on how to interact with a jupyter notebook that's running remotely on the workstation. This is particularly useful, for instance, when training a deep learning model from a jupyter notebook.

Before proceeding, you need to make sure to have a conda environment, and activate it.

Install jupyter in your environment:

```bash
conda install jupyter
```

Create a jupyter configuration file:

```bash
jupyter notebook --generate-config
```

Set up authentication for jupyter:

```bash
jupyter notebook password
```

Start the notebook \(use a custom `<PORT_NUMBER>`\):

```bash
jupyter notebook --no-browser --port=<PORT_NUMBER>
```

From your local machine, set up port forwarding:

```bash
ssh -N -f -L localhost:<LOCAL_PORT>:localhost:<PORT_NUMBER> ml_workstation
```

That's it. To access jupyter, just point your browser to `http://localhost:<LOCAL_PORT>`

