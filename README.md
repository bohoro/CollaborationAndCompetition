# Collaboration and Competition
Two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

##### Watch the trained agent in action.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/LeKIykhzzAM/0.jpg)](https://www.youtube.com/watch?v=LeKIykhzzAM "Click to Play")

Click the image above to play the video of a trained agent.

## Project Details

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
This yields a single score for each episode.
The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

## Getting Started

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drlnd python=3.10.12
	conda activate drlnd
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.10.12
	conda activate drlnd
	```
2. Clone the repository (if you haven't already!), and navigate to the `python/` folder.  Then, install several dependencies.
	```bash
	git clone https://github.com/bohoro/ContinuousControl.git
	cd ContinuousControl/python
	```
3. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

4. Place the file in the `CollaborationAndCompetition/` folder, and unzip (or decompress) the file. 

Within the python subdirectory, run:

```pip install -r requirements.txt```

# Instructions

##### Training the agent

```python collaborate_and_compete.py```

Output will contian

```
2018-12-02 08:16:38.490022 Training started
2018-12-02 08:16:38.551500 Episode 0	Average Score: 0.00
2018-12-02 08:16:39.600437 Episode 10	Average Score: 0.01
2018-12-02 08:16:45.561171 Episode 20	Average Score: 0.00
2018-12-02 08:16:53.509356 Episode 30	Average Score: 0.00
2018-12-02 08:17:02.587633 Episode 40	Average Score: 0.00
2018-12-02 08:17:11.890441 Episode 50	Average Score: 0.01
2018-12-02 08:17:23.658469 Episode 60	Average Score: 0.02
2018-12-02 08:17:31.750321 Episode 70	Average Score: 0.00
2018-12-02 08:17:43.407221 Episode 80	Average Score: 0.02
2018-12-02 08:17:57.458868 Episode 90	Average Score: 0.05
2018-12-02 08:18:12.455855 Episode 100	Average Score: 0.07
2018-12-02 08:18:22.771744 Episode 110	Average Score: 0.01
2018-12-02 08:18:34.303168 Episode 120	Average Score: 0.04
2018-12-02 08:18:43.420294 Episode 130	Average Score: 0.01
2018-12-02 08:18:55.906904 Episode 140	Average Score: 0.05
2018-12-02 08:19:08.383714 Episode 150	Average Score: 0.03
2018-12-02 08:19:18.640444 Episode 160	Average Score: 0.02
2018-12-02 08:19:35.693061 Episode 170	Average Score: 0.08
2018-12-02 08:19:51.599242 Episode 180	Average Score: 0.08
2018-12-02 08:20:06.437703 Episode 190	Average Score: 0.07
2018-12-02 08:20:23.614848 Episode 200	Average Score: 0.08
2018-12-02 08:20:40.661118 Episode 210	Average Score: 0.06
2018-12-02 08:20:57.786220 Episode 220	Average Score: 0.07
2018-12-02 08:21:19.488353 Episode 230	Average Score: 0.11
2018-12-02 08:21:38.756698 Episode 240	Average Score: 0.06
2018-12-02 08:21:58.062962 Episode 250	Average Score: 0.09
2018-12-02 08:22:21.982635 Episode 260	Average Score: 0.11
2018-12-02 08:22:50.632593 Episode 270	Average Score: 0.12
2018-12-02 08:23:12.342294 Episode 280	Average Score: 0.08
2018-12-02 08:23:48.888427 Episode 290	Average Score: 0.16
2018-12-02 08:24:22.027768 Episode 300	Average Score: 0.12
2018-12-02 08:24:49.430291 Episode 310	Average Score: 0.11
2018-12-02 08:25:15.681356 Episode 320	Average Score: 0.12
2018-12-02 08:25:41.943240 Episode 330	Average Score: 0.13
2018-12-02 08:26:04.785125 Episode 340	Average Score: 0.11
2018-12-02 08:26:33.346127 Episode 350	Average Score: 0.13
2018-12-02 08:26:59.700992 Episode 360	Average Score: 0.12
2018-12-02 08:27:38.636931 Episode 370	Average Score: 0.18
2018-12-02 08:28:16.595310 Episode 380	Average Score: 0.17
2018-12-02 08:28:57.935270 Episode 390	Average Score: 0.18
2018-12-02 08:29:38.082800 Episode 400	Average Score: 0.17
2018-12-02 08:30:21.931564 Episode 410	Average Score: 0.19
2018-12-02 08:31:00.065175 Episode 420	Average Score: 0.15
2018-12-02 08:31:53.077317 Episode 430	Average Score: 0.20
2018-12-02 08:32:13.807340 Episode 440	Average Score: 0.07
2018-12-02 08:32:59.704924 Episode 450	Average Score: 0.19
2018-12-02 08:34:05.224435 Episode 460	Average Score: 0.28
2018-12-02 08:34:38.544772 Episode 470	Average Score: 0.13
2018-12-02 08:35:06.242306 Episode 480	Average Score: 0.10
2018-12-02 08:35:38.454062 Episode 490	Average Score: 0.12
2018-12-02 08:36:11.823847 Episode 500	Average Score: 0.12
2018-12-02 08:36:35.945264 Episode 510	Average Score: 0.06
2018-12-02 08:37:04.649842 Episode 520	Average Score: 0.10
2018-12-02 08:37:44.990289 Episode 530	Average Score: 0.16
2018-12-02 08:38:48.361805 Episode 540	Average Score: 0.26
2018-12-02 08:39:20.705082 Episode 550	Average Score: 0.11
2018-12-02 08:39:59.769205 Episode 560	Average Score: 0.15
2018-12-02 08:41:42.085624 Episode 570	Average Score: 0.45
2018-12-02 08:42:45.606923 Episode 580	Average Score: 0.27
2018-12-02 08:43:45.654854 Episode 590	Average Score: 0.25
2018-12-02 08:44:21.395907 Episode 600	Average Score: 0.16
2018-12-02 08:45:00.685177 Episode 610	Average Score: 0.16
2018-12-02 08:46:15.483210 Episode 620	Average Score: 0.33
2018-12-02 08:47:09.571357 Episode 630	Average Score: 0.22
2018-12-02 08:47:58.128316 Episode 640	Average Score: 0.19
2018-12-02 08:48:53.415241 Episode 650	Average Score: 0.23
2018-12-02 08:50:07.463432 Episode 660	Average Score: 0.31
2018-12-02 08:51:08.654614 Episode 670	Average Score: 0.26
2018-12-02 08:52:09.864851 Episode 680	Average Score: 0.24
2018-12-02 08:53:03.648280 Episode 690	Average Score: 0.22
2018-12-02 08:54:14.239032 Episode 700	Average Score: 0.27
2018-12-02 08:55:16.752767 Episode 710	Average Score: 0.27
2018-12-02 08:55:56.156819 Episode 720	Average Score: 0.17
2018-12-02 08:56:37.857680 Episode 730	Average Score: 0.16
2018-12-02 08:57:36.843178 Episode 740	Average Score: 0.25
2018-12-02 08:59:04.879739 Episode 750	Average Score: 0.38
2018-12-02 08:59:55.963058 Episode 760	Average Score: 0.20
2018-12-02 09:00:59.977496 Episode 770	Average Score: 0.26
2018-12-02 09:01:42.815328 Episode 780	Average Score: 0.17
2018-12-02 09:02:16.575563 Episode 790	Average Score: 0.13
2018-12-02 09:03:48.613289 Episode 800	Average Score: 0.41
2018-12-02 09:04:40.876750 Episode 810	Average Score: 0.21
2018-12-02 09:05:31.778935 Episode 820	Average Score: 0.21
2018-12-02 09:06:15.506364 Episode 830	Average Score: 0.17
2018-12-02 09:07:23.705400 Episode 840	Average Score: 0.30
2018-12-02 09:08:07.576639 Episode 850	Average Score: 0.17
2018-12-02 09:08:46.883204 Episode 860	Average Score: 0.17
2018-12-02 09:09:22.624743 Episode 870	Average Score: 0.14
2018-12-02 09:10:17.014746 Episode 880	Average Score: 0.22
2018-12-02 09:11:12.548925 Episode 890	Average Score: 0.23
2018-12-02 09:11:55.343615 Episode 900	Average Score: 0.16
2018-12-02 09:13:05.661510 Episode 910	Average Score: 0.30
2018-12-02 09:13:56.569759 Episode 920	Average Score: 0.22
2018-12-02 09:15:13.949765 Episode 930	Average Score: 0.32
2018-12-02 09:16:25.624077 Episode 940	Average Score: 0.30
2018-12-02 09:17:22.249105 Episode 950	Average Score: 0.23
2018-12-02 09:17:54.637063 Episode 960	Average Score: 0.13
2018-12-02 09:19:07.479887 Episode 970	Average Score: 0.31
2018-12-02 09:20:14.852635 Episode 980	Average Score: 0.29
2018-12-02 09:20:52.067222 Episode 990	Average Score: 0.14
2018-12-02 09:21:53.527508 Episode 1000	Average Score: 0.25
2018-12-02 09:22:24.788286 Episode 1010	Average Score: 0.12
2018-12-02 09:23:11.186752 Episode 1020	Average Score: 0.19
2018-12-02 09:23:56.494084 Episode 1030	Average Score: 0.18
2018-12-02 09:24:40.738686 Episode 1040	Average Score: 0.19
2018-12-02 09:25:11.353625 Episode 1050	Average Score: 0.11
2018-12-02 09:25:40.383417 Episode 1060	Average Score: 0.09
2018-12-02 09:26:18.718054 Episode 1070	Average Score: 0.14
2018-12-02 09:27:09.690840 Episode 1080	Average Score: 0.19
2018-12-02 09:27:48.907509 Episode 1090	Average Score: 0.17
2018-12-02 09:28:36.279182 Episode 1100	Average Score: 0.20
2018-12-02 09:29:10.842540 Episode 1110	Average Score: 0.14
2018-12-02 09:30:19.192143 Episode 1120	Average Score: 0.28
2018-12-02 09:31:34.304767 Episode 1130	Average Score: 0.32
2018-12-02 09:32:31.246832 Episode 1140	Average Score: 0.24
2018-12-02 09:33:16.558354 Episode 1150	Average Score: 0.18
2018-12-02 09:34:05.274465 Episode 1160	Average Score: 0.20
2018-12-02 09:34:53.990161 Episode 1170	Average Score: 0.19
2018-12-02 09:35:22.934536 Episode 1180	Average Score: 0.10
2018-12-02 09:36:04.630050 Episode 1190	Average Score: 0.16
2018-12-02 09:37:27.031590 Episode 1200	Average Score: 0.35
2018-12-02 09:37:59.452707 Episode 1210	Average Score: 0.13
2018-12-02 09:38:35.470184 Episode 1220	Average Score: 0.15
2018-12-02 09:39:06.826145 Episode 1230	Average Score: 0.12
2018-12-02 09:39:47.473869 Episode 1240	Average Score: 0.14
2018-12-02 09:40:29.358233 Episode 1250	Average Score: 0.16
2018-12-02 09:41:04.315464 Episode 1260	Average Score: 0.12
2018-12-02 09:41:36.819258 Episode 1270	Average Score: 0.13
2018-12-02 09:41:59.981931 Episode 1280	Average Score: 0.09
2018-12-02 09:42:34.812293 Episode 1290	Average Score: 0.13
2018-12-02 09:43:21.324718 Episode 1300	Average Score: 0.19
2018-12-02 09:44:29.863253 Episode 1310	Average Score: 0.29
2018-12-02 09:45:22.263794 Episode 1320	Average Score: 0.22
2018-12-02 09:46:14.531854 Episode 1330	Average Score: 0.21
2018-12-02 09:46:58.030186 Episode 1340	Average Score: 0.15
2018-12-02 09:47:31.741265 Episode 1350	Average Score: 0.13
2018-12-02 09:48:46.997090 Episode 1360	Average Score: 0.32
2018-12-02 09:49:36.805145 Episode 1370	Average Score: 0.19
Problem solved in Episode 1375 with an Average Score: 0.50
```

##### To Watch a trained agent

```python run_trained_agent.py```



