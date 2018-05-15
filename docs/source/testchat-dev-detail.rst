testchat dev detail
===================

Steps
-----

#. Create new Flutter Application

   #. Fire up Andriod Studio
   #. Start a new Flutter project
   #. Flutter Application
   #. Project name: testchat
   #. Project location: /Users/cat/bast23
   #. Description: GooberU testchat flutter application
   #. Comany domain: bast23.me
   #. Package name: me.bast23.testchat

#. Pull in docs structure

   #. cd ~/bast23/testchat
   #. cp -r ~/temp/flutter/docs .
   #. vi docs/conf.py
   #. vi docs/index.rst (and various others)
   #. cd docs
   #. make html (fix errors)
   #. open build/html/index.html
   #. verify docs

#. Create gooberu-testchat-readthedocs_

    #. Go to readthedocs_
    #. Sign up username: gooberu
    #. Attach github user: gooberu
    #. Import github gooberu-testchat-github_ repo
    #. Verify gooberu-testchat-readthedocs_

#. Run testchat flutter application baseline

   #. cd ~/bast23/testchat
   #. flutter packages get
   #. flutter run
   #. Verify baseline application deploys and runs

#. testchat-checkpoint-01_

   #. cd ~/bast23/testchat/docs
   #. vi source/testchat-dev-detail.rst (update doc)
   #. make html 
   #. open build/html/index.html (verify docs)
   #. git add *
   #. git commit -m "commit for testchat-checkpoint-01"
   #. git tag testchat-checkpoint-01

#. tbd

Resources
---------

.. _readthedocs: https://readthedocs.org/
.. _gooberu-testchat-readthedocs: https://gooberu-testchat.readthedocs-hosted.com/en/latest/index.html
.. _gooberu-testchat-github: https://github.com/gooberu/testchat
.. _testchat-checkpoint-01: https://github.com/gooberu/testchat