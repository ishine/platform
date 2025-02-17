### Maintenance release 1.45.1 is scheduled for 11/9/2021 between 6:00pm and 10pm CST

This release fixes the following issues:
* #rcj-386: multiple callback requests are sent for a given request
* #rcj-385: occasionally responses from recognition take extra long (incompleteTimeout) - incompleteTimeout was not behaving as per spec
* #rcj-384: Realtime session takes 1-2s to start - requests to billing were not being cached efficiently
* #rcj-383: Audio from AIVR transcription shows in the Portal under normal Transcribe 

### Minor release 1.45.0 is scheduled for 11/5/2021 between 6:00pm and 10pm CST

This release has these main changes:
* Introduces a uniform way to handle kubeconfg in Edge deployments. This makes it easy to deploy Voicegain Edge to various Cloud Platforms.
* For Edge: moved to a different GPU runtime framework which uses GPU resource more efficiently. Allows to run more recognition sessions on same hardware.
* Optimized offline task queue - significantly higher throughput is now possible (more hours of audio transcribed in the same period of time). 
* The latency of the callback response in real-time transcription has been reduced to better support voicebot scenarios.
* Polling now goes via load-balancer URL instead of directly to individual services in order to better support rolling deployments. 
* Microphone capture in web browser applications moved away from deprecated methods

This release fixes the following issues:
* #rcj-368: callback from recognition not working (introduced when adding redis:// callback method)
* #rcj-365: Transcripts of Telephony Bot Session cannot be viewed in Web Console
* #rcj-359: Reduce delay between end of recognition and call-back response 

Known issue that is not fixed in this release:
* #rcj-380: polling requests fail to return transcript after poll.afterlife -- the workaround is to make sure that content.full includes both ["transcript", "words"]
* #rcj-377: if content.full is only ["transcript"] then the callback will not have the transcript -- it is necessary to specify ["transcript", "words"] to get any transcript in the callback 

It also provides these enhancements:
* #vgp-822: naming changes in Edge management ACP pages - uses less ambiguous names in Web Console

Additional announcements:
* We now offer advanced monitoring for Edge deployments (for a slight per-port price premium).

### Maintenance release 1.44.1 is scheduled for 10/25/2021 between 6:00pm and 10pm CST

This release provides:
* Further improved accuracy of the real-time/command model.

### Minor release 1.44.0 is scheduled for 10/21/2021 between 6:00pm and 11pm CST

This release provides:
* New versions of the models used for real-time and offline transcription. They provide improved accuracy. This improvement in accuracy is particularly noticeable for short real-time transcripts, like e.g. encountered in voice-bots.
* The hints feature provides new misspellings capability. 
For more info about hints see [this Knowledge Base article](https://support.voicegain.ai/hc/en-us/articles/4407993206548-Using-Hints)

This release fixes the following issues:
* #rcj-358: web-api returns "missing websocket name" by mistake
* #rcj-355: ContentType.word-tree was serialized as WordTree by mistake


































 













































