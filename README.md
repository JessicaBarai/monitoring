# monitoring

A readme is included for both Jaeger and Prometheus libraries.

After downloading code make sure to change:

1. CMakeLists.txt: "add_subdirectory()"
add the right path to Jaeger-client-cpp-master directory

2. Make sure to change configuration of Prometheus. 
In main function: "Exposer exposer{"172.17.0.2:8080"};".
Tell the Exposer class where to expose the data and configure prometheus to scrape from that endpoint.

3. If needed also configuration of Jaeger agent port can be changed in config.yml.

When dowloaded run:

./configure.sh

./build.sh

./run.sh


