---
layout: post
title: "spring-data-jpa-repository explained"
date: "2019-05-30 23:22:25"
author: brunojensen
header-img: img/post-bg-02.jpg
---
<p>On a recent experience working on a self-contained spring-boot based application I faced some “problems”. What happened was that even with so many different ways to write a repository with spring-data-jpa, in some cases it was not enough and as a quick solution the development team introduced a concrete implementation of respositories with EntityManager injection. Does it works? Yeah, of course, but is there any other way to do it? </p>
<h3>spring-data-jpa</h3>
<p>First, let’s explore more about how to use spring-data-jpa.</p>
<p>There are  three main solutions to write a query on a spring repository: method query, @Query annotation and JpaSpecificationExecutor.</p>
<ul>
  <li>Method query is translated at atartup time into a JPQL query.</li>
  <li>Query annotation allow JPQL and native query with named or positional parameters.</li>
  <li>JpaSpecificationExecutor contains various methods to run JPA Criteria Builder queries.</li>
</ul>
<p>Well, it’s looks good, why would I need more?</p>
<p>Method queries is very cool but can looks ugly if you need to filter and sort by various fields; Query annotation is nice but when your queries starts to be more complex it doesn’t look so good, specially to maintain in the same repository and if you have a same query with different parameters, usually you need to write it twice or concatenate strings; Criteria Builder solve all the previous problems but how does likes it? And, just like JPQL, there’s a few limitations on the query sintax and you might need a native query instead of.</p>
<h3>Spring data extension</h3>
<p>Okay, what’s the chances of this happen in a project? Well, it shouldn’t happen, but sometimes it does. And everybody knows about the JPA limitations regarding querying in case you need performance, sometimes there’s no option besides writing a native query.</p> 
<p>And based on those problems I decided to write a spring-data-jpa extension which is based on the specification pattern similar to JpaSpecificationExecutor but allowing the developer to write Specifications classes with more flexibility on the filtering and with better maintainability of the query, whether is JPQL or native.</p>
<p>Am I using this extension in that project? No, I’m not, the damage on that project is already done. I’m trying to avoid the same in future projects and help anyone how might facing the same situation.</p>
<p>So, let’s contribute. I have some issues and improvements waiting for you on github :)</p>
[https://github.com/brunojensen/spring-data-repository-demo](https://github.com/brunojensen/spring-data-repository-demo)
