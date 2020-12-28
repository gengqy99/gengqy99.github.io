---
title: CET6：整体&部分
date: 1001-12-28 11:00:00 +0800
categories: [CET6, Advanced]
tags: [cet6-phrase]     # TAG names should always be lowercase
---

## integral

<div class="word-card">
    <div class="pronunciation" style="display:flex;align-items:center;">
        /ˈɪntɪɡrəl/
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-pronunciation" preload="auto">
            <source src="/assets/audio/Whole&Part/integral-pronunciation.mp3"/>
            </audio>
        </div>
    </div>
    <div>
        adj. 必须的，必不可少的；基本的，作为组成部分的；整体的
    </div>
    <div class="sentence" style="display:flex;align-items:center;">
        Every link is integral to the strength of the chain.
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-sentence" preload="auto">
            <source src="/assets/audio/Whole&Part/integral-sentence.mp3"/>
            </audio>
        </div>
    </div>
</div>

> 结实的链子得环环相扣。

------------------------------------------------------------------------------------------------------------

## integral2

<div class="word-card">
    <div class="pronunciation" style="display:flex;align-items:center;">
        adj. 必须的，必不可少的；基本的，作为组成部分的；整体的
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-pronunciation2" preload="auto">
            <source src="/assets/audio/physical.mp3"/>
            </audio>
        </div>
    </div>
    <div>
        adj. 必须的，必不可少的；基本的，作为组成部分的；整体的
    </div>
    <div class="sentence" style="display:flex;align-items:center;">
        Every link is integral to the strength of the chain.
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-sentence2" preload="auto">
            <source src="/assets/audio/physical.mp3"/>
            </audio>
        </div>
    </div>
</div>

> 结实的链子得环环相扣。

------------------------------------------------------------------------------------------------------------

<script>
let knownAudios = [];
function audioPlay(audioId) {
    let document = this.document;
    console.log('this:', this);
    console.log('this.document:', document);
    isKnown = false;
    knownAudios.forEach((currentAudioId) => {
        isKnown = (currentAudioId === audioId) ? true : isKnown;
    });
    if(!isKnown){
        knownAudios.push(audioId);
    }
    knownAudios.forEach((currentAudioId) => {
        document.getElementById(currentAudioId).pause();
        document.getElementById(currentAudioId).currentTime = 0;
    });
    document.getElementById(audioId).play();
}
</script>
