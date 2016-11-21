# CircleCI
Just another repository
Case 1: PRODSUP-001:
Hi. I am trying to get my test cases to show up on CircleCI but it is not working. I have a fork of this project in my github account https://github.com/mtedone/podam. I added the project to CircleCI and got a green build but the Test Results tab is empty

---
Harry


I've checked an issue and the below is the solution for that issue.
1)	CircleCI is case-sensitive , so you need to rename your Circle.yml to  circle.yml
------------------------------------------------------------------------------------------------------------------------------------

2)case 2: PRODSUP-002:
Hi. I added my project to CircleCI but I can’t get the build complete. I’m not sure what I’m doing wrong. Can you help? My project is https://github.com/nym2015/commons-csv. 
---
Jolene

We need to enable Maven Surefire Plugin in pov.xml file in root dir
just remove below code at line 279:
<configuration>
   <skip>true</skip>
</configuration>

Once it is removed. The project code is working fine without any issue.
----------------------------------------------------------------------------------------------------------------------------------------
3)Case 3: PRODSUP-003:
Dear customer support,
I need to explain how CircleCI works to my boss. I’ve read the docs but I still don’t get it. Can you please explain to me, in your own words, how CircleCI works? Also, it seems like you don’t support .NET builds. Why is that?
--
Adam

I need to clear you circle.yml file and add below lines:

test:
  post:
    - mkdir -p $CIRCLE_TEST_REPORTS/junit/
    - find . -type f -regex ".*/target/surefire-reports/.*xml" -exec cp {} $CIRCLE_TEST_REPORTS/junit/ \;

More information is available here:
https://circleci.com/docs/test-metadata#metadata-collection-in-custom-test-steps
https://github.com/DeviJayaprakasan/2.-CircleCI
