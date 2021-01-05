---
title: CET6：整体&部分
date: 1001-12-28 11:00:00 +0800
categories: [CET6, Advanced]
tags: [cet6-compare and understand]     # TAG names should always be lowercase
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

## integrate

<div class="word-card">
    <div class="pronunciation" style="display:flex;align-items:center;">
        /ˈɪntɪɡreɪt/
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-pronunciation2" preload="auto">
            <source src="/assets/audio/Whole&Part/integrate-pronunciation.mp3"/>
            </audio>
        </div>
    </div>
    <div>
        v.（使）成为一体，（使）合并<br/>
        adj.完整的，组合的
    </div>
    <div class="sentence" style="display:flex;align-items:center;">
        Our department's four teams must integrate together to work on new projects.
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-sentence2" preload="auto">
            <source src="/assets/audio/Whole&Part/integrate-sentence.mp3"/>
            </audio>
        </div>
    </div>
</div>

> 我们部门的四个小组必须合力推进新项目。

------------------------------------------------------------------------------------------------------------

## engage

<div class="word-card">
    <div class="pronunciation" style="display:flex;align-items:center;">
        /ˈɪntɪɡreɪt/
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-pronunciation2" preload="auto">
            <source src="/assets/audio/Whole&Part/engage-pronunciation.mp3"/>
            </audio>
        </div>
    </div>
    <div>
        v.使加入，使融入；（军队）交战
    </div>
    <div class="sentence" style="display:flex;align-items:center;">
        She used to exercise alone, but now she engages in the group running.
        <div style="background-image:url(/assets/img/cet6/audio.png);height:1.5rem;width:1.5rem;margin-left:0.7rem;background-size:cover;" onclick="audioPlay(this.firstElementChild.attributes.id.nodeValue)">
            <audio id="integral-sentence2" preload="auto">
            <source src="/assets/audio/Whole&Part/engage-sentence.mp3"/>
            </audio>
        </div>
    </div>
</div>

> 她之前一般独自锻炼，但现在她加入了集体跑步的行列。

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
