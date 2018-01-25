# portainer-php-api

Portainer API client

## Install

    composer req mangati/portainer-php-api

## Usage

Managing endpoints:

```
$portainer = new \Mangati\Portainer\Client('http://127.0.0.1:9000');
$portainer->auth('admin', '123456789');

$endpointsApi = $portainer->endpoints();
$endpoints    = $endpointsApi->getAll();

print_r($endpoints);
```

Managing stacks:

```
$stacksApi = $portainer->stacks($endpoints[0]['Id']);
$stacks    = $stacksApi->getAll();

print_r($stacks);

if (count($stacks)) {
    $stacksApi->delete($stacks[0]['Id']);
}
```
