ZF2 Cheat Sheet
===============
Because I always forget everything I'm told in #zftalk.2

Controller Stuff
----------------
Access querystring parameter:
    $this->getRequest()->getQuery()->foo;

Check if querystring parameter exists:
    $this->getRequest()->getQuery()->offsetExists('foo');

Set a different view script:
    
