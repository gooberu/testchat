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

   #. Command line ::

        macci:testchat cat$ cd ~/bast23/testchat
        macci:testchat cat$ cp -r ~/temp/flutter/docs .
        macci:testchat cat$ vi docs/conf.py
        macci:testchat cat$ vi docs/index.rst (and various others)
        macci:testchat cat$ cd docs
        macci:docs cat$ make html (fix errors)
        macci:docs cat$ open build/html/index.html

   #. verify docs

#. Create gooberu-testchat-readthedocs_

    #. Go to readthedocs_
    #. Sign up username: gooberu
    #. Attach github user: gooberu
    #. Import github gooberu-testchat-github_ repo
    #. Verify gooberu-testchat-readthedocs_

#. Run testchat flutter application baseline


   #. Command line ::

        macci:testchat cat$ cd ~/bast23/testchat
        macci:testchat cat$ flutter packages get
        macci:testchat cat$ flutter run

   #. Verify baseline application deploys and runs

#. Produce testchat-checkpoint-01_

   #. Command line ::

        macci:testchat cat$ cd ~/bast23/testchat/docs
        macci:docs cat$ vi source/testchat-dev-detail.rst (update doc)
        macci:docs cat$ make html 
        macci:docs cat$ open build/html/index.html (verify docs)
        macci:testchat cat$ cd ~/bast23/testchat
        macci:testchat cat$ git add *
        macci:testchat cat$ git commit -m "commit for testchat-checkpoint-01"
        macci:testchat cat$ git tag testchat-checkpoint-01
        macci:testchat cat$ git push
        macci:testchat cat$ git push origin testchat-checkpoint-01
    
   #. Verify checkpoint testchat-checkpoint-01_ Baseline

#. Use the skeleton from youtube-flutter-chat-tutorial_ source youtube-flutter-chat-github_

   #. Command line ::

        macci:testchat cat$ mv lib/main.dart lib/main.dart.flutterbaseline
        macci:testchat cat$ mv main.dart.txt lib/main.dart
        macci:testchat cat$ mv platform_adaptive.dart.txt lib/platform_adaptive.dart
        macci:testchat cat$ mv type_meme.dart.txt lib/type_meme.dart

   #. Fix errors and verify application deploys and runs ::

        macci:testchat cat$ flutter run

#. Produce testchat-checkpoint-02_ Basic Chat Screen

   #. Command line ::

        macci:testchat cat$ cd ~/bast23/testchat/docs
        macci:docs cat$ vi source/testchat-dev-detail.rst (update doc)
        macci:docs cat$ make html 
        macci:docs cat$ open build/html/index.html (verify docs)
        macci:testchat cat$ cd ~/bast23/testchat
        macci:testchat cat$ git add *
        macci:testchat cat$ git commit -m "commit for testchat-checkpoint-02"
        macci:testchat cat$ git tag testchat-checkpoint-02
        macci:testchat cat$ git push
        macci:testchat cat$ git push origin testchat-checkpoint-02
    
   #. Verify checkpoint testchat-checkpoint-02_

#. Add the testchat textfield to accept user input

    #. Code added to line 166 lib/main.dart ::

              // Begin: Add TextField
              new Flexible(
                child: new TextField(
                  controller: _textController,
                  onSubmitted: _handleSubmitted,
                  onChanged: _handleMessageChanged,
                  decoration:
                      new InputDecoration.collapsed(hintText: 'Send a message'),
                ),
              ),
              // END: Add TextField

    #. Fix any errors and verify application deploys and runs ::

        macci:testchat cat$ flutter run

#. Produce testchat-checkpoint-03_ Add Text input to testchat

   #. Command line ::

        macci:testchat cat$ cd ~/bast23/testchat
        macci:testchat cat$ git add *
        macci:testchat cat$ git commit -m "commit for testchat-checkpoint-03"
        macci:testchat cat$ git tag testchat-checkpoint-03
        macci:testchat cat$ git push
        macci:testchat cat$ git push origin testchat-checkpoint-03
    
   #. Verify checkpoint testchat-checkpoint-03_

#. Add the user input _handleSubmitted function

    #. Code added to line 84 lib/main.dart ::

              // Begin: Add _handleSubmitted function
                void _handleSubmitted(String text) {
                    _textController.clear();
                    _addMessage(name: _name, text: text);
                }
              // END: Add _handleSubmitted function

    #. Fix any errors and verify application deploys and runs ::

        macci:testchat cat$ flutter run

    #. NOTE: While the text input is now hanled by _handleSubmitted it is not displayed

#. Display text on text input _handleSubmitted

    #. Code uncommented to update message display state line 110 lib/main.dart ::

        // Begin: Insert message
        setState(() {
          _messages.insert(0, message);
        }); //End: Insert message

    #. Fix any errors and verify application deploys and runs ::

        macci:testchat cat$ flutter run

#. Add Theme

    #. Code uncommented to update message display state line 110 lib/main.dart ::

        // Begin: Insert message
        setState(() {
          _messages.insert(0, message);
        }); //End: Insert message

    #. Fix any errors and verify application deploys and runs ::

        macci:testchat cat$ flutter run

#. Add Aniamation and call from build widget

    #. Code uncommented animationController line 99 lib/main.dart ::

        //    var animationController;
        // Begin: initialize animationController
        var animationController = new AnimationController(
        duration: new Duration(milliseconds: 700),
        vsync: this,
        ); // End: initialize animationController

    #. Code uncommented animationController line 229 lib/main.dart ::

        Widget build(BuildContext context) {
        //    return new Container(
            // Begin: Add SizeTransition
            return new SizeTransition(
                sizeFactor: new CurvedAnimation(
                    parent: message.animationController, curve: Curves.easeOut),
                axisAlignment: 0.0,
                child: new Container( // End: Add SizeTransition
        ...
                    ),
                ) // EndClose: Add SizeTransition
            );
        }
        }

    #. Fix any errors and verify application deploys and runs ::

        macci:testchat cat$ flutter run

#. Produce testchat-checkpoint-04_ Added Theme and Aniamation Look and Feel stuff

   #. Command line ::

        macci:testchat cat$ cd ~/bast23/testchat
        macci:testchat cat$ git add *
        macci:testchat cat$ git commit -m "commit for testchat-checkpoint-04"
        macci:testchat cat$ git tag testchat-checkpoint-04
        macci:testchat cat$ git push
        macci:testchat cat$ git push origin testchat-checkpoint-04
    
   #. Verify checkpoint testchat-checkpoint-04_


Resources
---------

#. Github Project Repo: gooberu-testchat-github_
#. Read the Docs: gooberu-testchat-readthedocs_
#. Tutorial via GoogleIO-17 "Single Codebase, Two Apps with Flutter and Firebase" see youtube-flutter-chat-tutorial_
#. Github source for tutorial youtube-flutter-chat-github_ 
#. Firebase console for firebase-chat2cld_ project database
#. Github source for memechat-skeleton_


.. _readthedocs: https://readthedocs.org/
.. _gooberu-testchat-readthedocs: https://gooberu-testchat.readthedocs-hosted.com/en/latest/index.html
.. _gooberu-testchat-github: https://github.com/gooberu/testchat
.. _testchat-checkpoint-01: https://github.com/gooberu/testchat/tree/testchat-checkpoint-01
.. _testchat-checkpoint-02: https://github.com/gooberu/testchat/tree/testchat-checkpoint-02
.. _testchat-checkpoint-03: https://github.com/gooberu/testchat/tree/testchat-checkpoint-03
.. _testchat-checkpoint-04: https://github.com/gooberu/testchat/tree/testchat-checkpoint-04

.. _youtube-flutter-chat-tutorial: https://youtu.be/w2TcYP8qiRI?list=PLlpxjI4sVd-zZ1jpJHJMSHGiWInsvwwf_
.. _youtube-flutter-chat-github: https://github.com/efortuna/memechat
.. _firebase-chat2cld: https://console.firebase.google.com/project/chat2cld/overview
.. _memechat-skeleton: https://github.com/efortuna/memechat/blob/skeleton/lib/main.dart