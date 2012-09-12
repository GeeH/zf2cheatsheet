ZF2 Cheat Sheet
===============
Because I always forget everything I'm told in #zftalk.2

Controller Stuff
----------------
Access querystring parameter:

    $this->getRequest()->getQuery()->foo;

Check if querystring parameter exists:

    $this->getRequest()->getQuery()->offsetExists('foo');
    
Get a parameter from the route

    $slug = $this->getEvent()->getRouteMatch()->getParam('slug');

Set a different view script:
    
    $viewModel = new ViewModel();
    $viewModel->setTemplate('module/controller/viewscript.phtml');
    
Get action from controller:

    $this->getEvent()->getRouteMatch();
    
or
    
    $this->params()->fromRoute('action');
    
Disable layout in a ViewModel:

    $viewModel = new ViewModel();
    $viewModel->setTerminal(true);
    
Set custom headers or response code:

    /** @var \Zend\Http\PhpEnvironment\Response $response  */
    $response = $this->getResponse();
    /** 404 Not Found page return magically */
    $response->setStatusCode(404);
    /** Set custom response headder */
    $headers = new \Zend\Http\Headers();
    $headers->addHeaderLine('My-Custom-Header', 'ZF2');
    $response->setHeaders($headers);