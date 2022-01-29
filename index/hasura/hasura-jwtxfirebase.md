---
title: hasura-jwt x firebase
date: 2022-01-18
categories: [hasura, firebase]
tags: []
author: eastasian
---
# Authentication in hasura x firebase

1. create hasura and firebase project.
	1. create firebase project.
	2. create hasura project.
2. configure Authentication in hasura and firebase.
	1. configure permissions of db in hasura project.
	2. enable firebase authentication.
3. configure custom claim in firebase authentication.
	1. implement cloud function that set custom claim on user creation. ( [sample](https://github.com/reactboy/kabchi/blob/develop/functions/src/index.ts))
	2. in sample updating firestore when completed so that client side will listen to changes and check authenticated user has custom claims.
4. configure environment variables for hasura project.
	1. generata jwt config for `HASURA_GRAPHQL_JWT_SECRET` at [hasura.io](https://hasura.io/jwt-config/).
	2. if necessary configure `HASURA_GRAPHQL_UNAUTHORIZED_ROLE` to the unauthorized role you configure in 2-1.
5. implement firebase authentication logics in to client side. ([sample](https://github.com/reactboy/kabchi/blob/develop/src/utils/hooks/useAuth.ts))
	-  It may take few seconds to set custom claims.
	-  make sure you have custom claims before execute api calls need auth.
	-  in sample update firestore when custom claims are set and client side are listening to that changes by firestores snapshot listener. (ref: 3-2)