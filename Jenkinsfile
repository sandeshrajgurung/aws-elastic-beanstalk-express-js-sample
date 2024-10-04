version: '3.7'
services:
  dind:
    image: docker:dind
    user: root
    privileged: true
    container_name: dind
    expose:
      - 2375
    networks:
      - jenkins_dind
    environment:
      DOCKER_TLS_CERTDIR: ""

  jenkins:
    image: jenkins/jenkins:lts
    user: root
    container_name: jenkins
    depends_on:
      - dind
    ports:
      - 8080:8080
      - 50000:50000
    volumes:
      - ./jenkins:/var/jenkins_home
      - /usr/bin/docker:/usr/bin/docker
    environment:
      DOCKER_HOST: "tcp://dind:2375"
    networks:
      - jenkins_dind

networks:
  jenkins_dind:
    driver: bridge
