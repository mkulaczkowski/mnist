# MNIST on ClusterOne
<p align="center">
<img src="c1_logo.png" alt="ClusterOne" width="200">
<br>
<br>
<a href="https://slackin-altdyjrdgq.now.sh"><img src="https://slackin-altdyjrdgq.now.sh/badge.svg" alt="join us on slack"></a>
</p>

This is a demo to show you how to run a handwritten digit recognition model on [ClusterOne](https://clusterone.com). The demo uses [TensorFlow](https://tensorflow.org) and the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset.



Follow the instructions below to run the model on ClusterOne using the `just` command line tool. This project is part of ClusterOne's [Getting Started guide](https://docs.clusterone.com/docs/get-started). There is also an [in-depth tutorial](https://docs.clusterone.com/v1.0/docs/mnist-with-clusterone) based on this repository.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [More Info](#more-info)
- [License](#license)

## Install

To run this project on the ClusterOne platform, you need:

- [Python](https://python.org/) 3.5
- [Git](https://git-scm.com/)
- The ClusterOne Python library. Install it with `pip install clusterone==2.0.0a02`
- A ClusterOne account. [Sign up](https://clusterone.com/) for free if you don't have an account yet.

### Setting Up

Start out by cloning this repository onto your local machine. 

```shell
$ git clone https://github.com/clusterone/mnist
```

Now you're all set to run MNIST on ClusterOne!

## Usage

These instructions use the `just` command line tool. It comes with the ClusterOne Python library and is installed automatically with the library.

cd into the folder you just downloaded with `cd mnist`  and log into your ClusterOne account using `just login`.

First, create a new project on ClusterOne:

```shell
$ just init project mnist
```

Then, upload the code to the new project:

```shell
$ git push clusterone master
```

Finally, create a job. Make sure to replace `YOUR_USERNAME` with your username.

```shell
$ just create job distributed --project YOUR_USERNAME/mnist --module mnist --name first-job \
--description first-job --python-version 3 --framework-version 1.0.0 --time-limit 1h
```

Now all that's left to do is starting the job:

```shell
$ just start job -p mnist/first-job
```

That's it! You can monitor its progress on the command line using `just pulse`. More elaborate monitoring is available on the [Matrix](https://clusterone.com/matrix), ClusterOne's graphical web interface.

## More Info

For further information on this example, take a look at the tutorial based on this repository in the [ClusterOne Documentation](https://docs.clusterone.com/v1.0/docs/mnist-with-clusterone).

For further info on the MNIST dataset, check out [Yann LeCun's page](http://yann.lecun.com/exdb/mnist/) about it. To learn more about TensorFlow and Deep Learning in general, take a look at the [TensorFlow](https://tensorflow.org) website.

## License

[MIT](LICENSE) © ClusterOne Inc.

The [MNIST](http://yann.lecun.com/exdb/mnist/) dataset has been created and curated by Corinna Cortes, Christopher J.C. Burges, and Yann LeCun.