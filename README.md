# cluster-configuration

GermanZero hat eine Weile einen Docker Swarm Cluster genutzt. Damit nichts verloren geht, habe ich hier alle notwendigen Konfigurationen gesichert.

Die [Stacks](docker-swarm) sollten sich bei Bedarf jederzeit in einem beliebigen Docker Swarm einspielen lassen. Dazu muss man jedoch Passwörter, Keys usw. an den entsprechenden Stellen ersetzen. Außerdem gehen die Stacks davon aus, dass die Knoten im Cluster Labels "germanzero-1" oder "germanzero-2" haben.

Die einzelnen Dienste werden durch ein API Gateway mit der Außenwelt verbunden, um Zugriffe steuern zu können. Als API Gateways wird Kong verwendet, mit einer Konga als Administrations-Oberfläche. In [api-gateway](api-gateway] sind die Secrets für Konga abgelegt ([Verbindung zu Kong](api-gateway/konga-kong.js] und [Administratoren](api-gateway/konga-users.js)). Auch hier muss ein Passwort angepasst werden, wenn man das wieder einspielen will.

Die [kong-config.json](api-gateway/kong-config.json) Datei enthält die im API Gateway definierten Services, Routen und Plugins. Zertifikate sind keine drin, die sollte man ggf. ohnehin neu erstellen.
