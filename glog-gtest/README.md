# Dockerize glog & gtest

[GBS][1] is local build system for tizen platform developer.  
Dockerize gbs for building tizen at docker.

### HOST
1. Pull docker image from docker-hub
```sh
$ docker pull bitboom/glog-gtest
```

2. Run docker image by using volume.
```sh
$ docker run --rm -it --net=host -v ${SOURCE_CODE}:/usr/src bitboom/tizen-gbs /bin/bash
```
### Docker
3. Build glog or gtest code
```sh
$ cd /usr/src
$ g++ example.cpp -std=c++11 -lglog
```

### gtest example
```sh
$ cd /usr/src/googletest/googletest/make
$ make && ./sample1_unittest

$ cd /usr/src/googletest/samples
$ ls -al
```

### glog example
```cpp
// g++ example.cpp -std=c++11 -lglog
// g++ example.cpp -std=c++11 -lglog -DNDEBUG

#include <glog/logging.h>

int main(int argc, char* argv[]) {
	FLAGS_log_dir = "./log";
	// Initialize Google's logging library.
	google::InitGoogleLogging(argv[0]);

	int num_cookies = 30;
	LOG(INFO) << "Found " << num_cookies << " cookies";
	LOG(WARNING) << "Found " << num_cookies << " cookies";
	LOG(ERROR) << "Found " << num_cookies << " cookies";
//	LOG(FATAL) << "Found " << num_cookies << " cookies";

	LOG_IF(INFO, num_cookies > 10) << "Got lots of cookies";

	auto everyN = []() {
		LOG_EVERY_N(INFO, 10) << "Got the " << google::COUNTER << "th cookie";
	};

	for (int i = 0; i < 15; i++)
		everyN();

	// no show with -DNDEBUG
	DLOG(INFO) << "DEBUG, Found cookies";
}
```
