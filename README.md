# polaris-deployment
Different deployment setups for polaris using docker-compose

* *docker-composeversion: '3'

services:
  polaris-backend:
    image: p2olab/polaris-backend:1.9.0
    ports:
      - 3000:3000

  polaris-frontend:
    image: p2olab/polaris-frontend:1.9.0
    ports:
      - 80:80
    depends_on:
      - polaris-backend
      - mtp-converter

  mtp-converter:
    image: p2olab/mtp-converter:1.4.3
    ports:
      - 3031:3031

  test-pea:
    image: p2olab/test-pea:1.9.0
    ports:
      - 4334:4334.yml* should provide the latest stable release of Polaris
* *docker-compose-devlop.yml* should provide the latest development version. Do only use when you what you are doing.
