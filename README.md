### How to find this bug?
I want to be the same as usual. Developed on Windows. Deployed to Docker. But it can’t be packaged because of the log problem...

I want to record logs in the /home directory of docker. Usually, it can be packaged successfully. But now because I don’t have this directory under windows, I can’t package it..

### explain:
1. pom `<version></version>` tag
2. When you set the version to 2.7.6, the log storage path will be created automatically. But the version 3.0.1 will not be created and an exception will be thrown
3. When you set the version to 2.7.6, the automatically created directory is in the root directory of your Windows disk, assuming that the directory of your project is in H:\project\.....\(your project folder). The automatically created log The folder will be in H:\home\log\2023-01-17
4. You can use Maven to package...and then errors will occur. So this may be a Spring Boot3 problem, not a Native packaging problem
