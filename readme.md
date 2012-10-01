ZF2 Cheat Sheet
===============
Because I always forget everything I'm told in #zftalk.2

Controller Stuff
----------------
Access querystring parameter:

    $this->params()->fromQuery('foo');

Check if querystring parameter exists:

    null !== $this->params()->fromQuery('foo', null);
    
Get a parameter from the route

    $slug = $this->params('slug');

Set a different view script:
    
    $viewModel = new ViewModel();
    $viewModel->setTemplate('module/controller/viewscript.phtml');
    
Get action from controller:

    $this->getEvent()->getRouteMatch();
    
or
    
    $this->params('action');
    
Disable layout in a ViewModel:

    $viewModel = new ViewModel();
    $viewModel->setTerminal(true);
    
Set custom headers or response code:

    /** @var \Zend\Http\PhpEnvironment\Response $response  */
    $response = $this->getResponse();
    /** 404 Not Found page return magically */
    $response->setStatusCode(404);
    /** Set custom response headder */
    $headers = $response->getHeaders();
    $headers->addHeaderLine('My-Custom-Header', 'ZF2');
    
#Module Stuff
Change controller in `Module.php`:
    $controller = $e->getTarget();
    $controller->layout('layout/alternativelayout');