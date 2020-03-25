---
layout: post
title:  "[Web] Redis Client"
date:   2020-03-18 08:00
categories: redis
permalink: /archivers/20200318-Redis-Client
summary: Redis Client 성능 이슈\nJedis와 Lettuce를 공부해보자!
tag: redis web cache session jedis lettuce
---

## 개요 
이번 포스팅은...  
최근 발생했던 생생한 프로젝트 이슈에 관한 내용을 담고자 한다.  

시스템 오픈 후, 내가 맡은 파트에서 다양한 이슈가 발생했다.  
대부분의 이슈는 하루 이틀 안에 해결되었지만,  
약 열흘간 손도 못 대던 이슈가 있었다.

그것은 바로 오늘 포스팅에서 다룰 **Redis Client**이다.

이슈의 내용은 다음과 같았다.  
**사용자의 세션 정보가 간헐적으로 사라져버린다는 것**  
(정말 전화 지옥이 따로 없었다...ㅠ)  

우리 시스템에서는 운영 WAS만 Redis를 이용해  
사용자 세션 정보를 저장하고 있는데,  
이때 사용되는 **Jedis**가 문제가 되었던 모양이다.  

구글링을 해보니 Java에서 사용되는 Redis Client는  
크게 두 종류가 있고 각각 **Jedis**와 **Lettuce**라고 한다.  

성능 상 이슈 때문에 많은 사람들이 Lettuce를 추천하는 듯 하다.  

나도 두 라이브러리는 모두 처음 들어본 터라,  
이번 포스팅에서 간단하게 정리를 해보고자 한다.

## Jedis
- 특징
- 장단점

## Lettuce
- 특징
- 장단점



