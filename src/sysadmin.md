
# Systems Overview

Systems interview was added as another part of the competition. This was a late add, so it will be judged warmly.

Topics discussed will be the design, infrastructure, management, and other details that have gone into building and maintainging your system. Additionally, talking about the problems encountered along the way can be very telling of the effort behind the cluster. 

Interviews will be around 10-15 minutes.


## Log Submission
Compress the paths where logs are often stored, usually just `/var`, from the head/login/main compute nodes. If your team believes that the logs after a certain number of nodes is too similar, exclude them. This means if you feel that node 1, node 2, node 3 have the most distinct logs, but the following nodes 4---12 nodes are just a repetition of the first 3 logs, just exclude them. We will ask for these files to be submitted at the end of the competition.

Create a folder called `Logs/` in your google drive and place them there.

Make sure to send a picture of your team with the cluster to the committee as well. This can be a possible location to put it.

The log submission does not receive points, but is *is required* to have some record of the clusters.
