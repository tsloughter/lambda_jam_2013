!SLIDE
# Let it Crash #
## Tristan Sloughter ##
### @t_sloughter ###
### tristan@heroku.com ###
### github.com/tsloughter ###

!SLIDE bullets
# Credits Already?? #

* This OTP Life (http://thisotplife.tumblr.com/)
* Learn You Some Erlang (http://learnyousomeerlang.com/)

!SLIDE bullets
# Handles! #

* Github: tsloughter
* Twitter: @t_sloughter
* Email: tristan@heroku.com

![octocat](../images/adventure-cat2.png)

!SLIDE bullets
# Who Am I? #

* Heroku routing infastructure engineer
* Routing
* Logging (github.com/heroku/logplex)


!SLIDE bullets
# Outline #

* Erlang
* Fault Tolerance
* It's OK to Crash?
* Unique Erlang Characteristics
* OTP

!SLIDE center
# Real World? #


!SLIDE bullets
# History #

* Ericsson looking for best language for telecom systems
* Concurrency and error recovery at top of the list
* Lisp, Prolog, Parlog considered, but ruled out
* Joe creates Erlang in 1986, language with concurrency and error recovery built in
* Joe's thesis mentions 9 9's for AXD301

!SLIDE center
# Erlang's Focused on Features #

* Concurrency
* Distribution
* Actors
* Green Threads

!SLIDE center
# Without Error Recovery #

![hill of beans](../images/hill-of-beans.jpg)


!SLIDE center
# Fault Tolerance Compared#

Erlang ![erlang](../images/erlang_ft.gif)
Copycats ![other](../images/other_ft.gif)

!SLIDE bullets
# Fault Tolerance in Routing #

* Many components can go wrong (bad request, bad response, missing dyno, missing records, overloaded, ...)
* Degradation better than no response

!SLIDE bullets
# Fault Tolerance in Logging #

* Similar to routing issues
* Better delayed than lost
* Better some than none
* And better to inform of missing logs then them simply not be there

!SLIDE bullets
# Who Are You? #

* Engineers
* Novice or no Erlang experience


!SLIDE center
# What is Fault Tolerance? #

Ability to keep working to a level of satisfaction in the presence of failure


!SLIDE bullets
# Isolation #

![isolation](../images/isolation4.png)

!SLIDE bullets
# Graceful Degradation #

![isolation](../images/degraded.gif)

!SLIDE bullets
# What is Let It Crash? #

![let it crash](../images/let_it_crash.gif)

!SLIDE bullets
# Why it Matters #

* You'll never test every scenario (though QuickCheck/PropEr help)
* You don't want your system to go down!
* Defensive coding sucks
* Prepares you for the quick recovery from the unexpected
* And most important...

!SLIDE center
# It Will Catch on Fire! #

![catch on fire](../images/homer_fire.gif)

!SLIDE bullets
# What's a Crash? #

* A process crash
* No longer exists, all state lost

!SLIDE center
# Erlang's Best Unknown Feature #

* Language comparisons to Erlang leave it out (except Akka)
* Can't be duplicated on existing VMs
* But why?

!SLIDE bullets
# Erlang Isolation #

* Immutable
* Cheap process spawning
* Message passing
* Process monitoring and linking

!SLIDE bullets
# Immutable #

![variables](../images/un-bound.png)

!SLIDE bullets
# Ada Lovelace #

![ada](../images/ada.jpg)

!SLIDE bullets
# Message Passing #

* No Shared State

!SLIDE bullets
# Lightweight Processes #

* Key to isolation, message passing and supervising

!SLIDE bullets
# Monitor #

* Unidirectional

!SLIDE bullets
# Link #

* Bidirectional

!SLIDE center
#Link #
![link](../images/link-exit.png)

!SLIDE bullets
# Erlang Graceful Degradation #

* Cheap process spawning
* Preemptive scheduling
* Concurrent garbage collection


!SLIDE bullets
# Garbage Collection #

* Concurrent
!SLIDE bullets
# Erlang Middleware #

* OTP: gen_server, supervisors, etc.

!SLIDE bullets
# OTP: The J2EE of Erlang?

![duck](../images/bush-ducking.gif)

!SLIDE bullets
# Server Common Pattern #

![server](../images/common-pattern.png)


!SLIDE bullets
# Supervisors #

![supervisor error](../images/supervisor_error.gif)

!SLIDE center
# One for All #
![one for all](../images/restart-one-for-all.png)

!SLIDE center
# One for One #
![one for one](../images/restart-one-for-one.png)

!SLIDE center
# Rest for One #
![rest for one](../images/restart-rest-for-one.png)

!SLIDE bullets
# Init State #

* All process state is lost on crash
* Safe state to restart from
* Able to start accepting messages again from a error-free state

!SLIDE bullets
# Pull it All Together #

*

!SLIDE bullets
# Back to Industry #

*

!SLIDE bullets
# References #

* LYSE : http://learnyousomeerlang.com/
* OTP in Action: http://www.manning.com/logan/
* Erlang Central : http://erlangcentral.org/
