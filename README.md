# OptimizelyStudy  
## Objectives
This study is to understand Optimizely as a technical context.  
Lean the technology used in the world famous startup and leverage the knowledge.  

## Use case
Optimizely is a SaaS for AB Testing. The basic use case will be below.
  
![test](https://lh3.googleusercontent.com/qPq70-B0GDdmfa1AIoM7UQKM45-QU2shAygKBzyBsuKNdv-Nsa7z8JOs2Z1Q2FFgJqbIbgN43wjtFmA=w2560-h1576-rw)

## Platform
Optimizely seems to be using Google App Engine. The access log from Optimizely would be below.  
You will notice it has a **AppEngine-Google** identifier(*1).
  
>107.178.200.189 - - [04/Jun/2015:14:47:00 +0000] "GET /test.html HTTP/1.1" 200 5 "https://app.optimizely.com/edit?experiment_id=2979440879" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2272.104 Safari/537.36 AppEngine-Google; (+http://code.google.com/appengine; appid: s~optimizelyedit-hrd)"
  
*1 No wonder they suggest using the App Engine. The CTO, Pete Koomen, is a former App Engine product manager.  
<https://www.linkedin.com/profile/view?id=50948717&authType=NAME_SEARCH&authToken=Wal6&locale=en_US&trk=tyah&trkInfo=clickedVertical%3Amynetwork%2Cidx%3A1-1-1%2CtarId%3A1433452703012%2Ctas%3Apete%20koo>

## Programming Language / Frameworks
On the server side, which only the developers knows, should be using ether Python、Java、PHP or Go since they're using the App Engine. It's conciderable to bet on Python by looking at their blogs.
<https://blog.optimizely.com/2012/09/12/optimizely-open-sources-python-scripts-for-amazon-ec2/>  
  
On the client side, which will be the browsers, there is no doubt they are a HTML/Js/Css specialists. It is obvious Optimizely seems to have favor in JQuery(I'd say when providing a quick fix patch for executing A/B Tests, you will need a simple DOM operating codes. JQuery meets the conditions.)

## Concerns
* ~~I've tried to do an sample experiment on <http://52.69.49.50/test.html> which is a sample html deployed on EC2. I was not able to edit the page.~~ --> Looks like all the submit transactions work async. It was just the matter of time.
* Security. While editing the variation, Optimizely needs an public accessable page. The page is publicaly accessable from the first place so there is no need for concern. On the other hand, providing access logs to Optmizely might have some concerns. 


