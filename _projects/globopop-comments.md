---
title: Comments for GloboPop
company: Act Digital / Globo
cover: /assets/images/comments-for-globopop/pop.png
cover_alt: Comment example
year: 2025–2026
role: Senior Product Designer
responsibilities:
- Discovery and market benchmark
- Interaction and UI design
- Motion design and interactive prototypes in Figma
- Validation and testing in the app
- Handoff to engineering, documentation, and design-to-development collaboration
- AI-supported research, ideation, prototyping, and UX copywriting
timeline: Oct 2025 – Apr 2026
summary: Designing comments end to end for a vertical video app, within the limits of an external provider.
order: 0
---
## The project

GloboPop is a curated vertical-video app by Globo. I designed its comments experience from discovery to UI, interaction rules, and post-launch validation.

Comments turn watching into participation. They give people a way to react, respond, and feel part of the conversation, without turning GloboPop into a social network.

<a href="https://globopop.globo.com/" target="_blank">Landing / Download the app</a> - <a href="https://globopop.globo.com/video/15163308/" target="_blank">Feed</a>


<i>The interface shown is in Portuguese.</i>

## Context

Globo has historically approached open comments with editorial caution, using moderation and editorial control to protect the context and safety of its content. But user sessions and App Store and Google Play reviews revealed a growing desire for participation. People wanted the ability to respond. That insight shaped the comments experience I designed.

Adding comments also raised questions beyond the interface: moderation, reporting, safety, and community guidelines. Those workstreams were handled separately, which shaped the scope of this task.

After launch, comment activity was low. We responded by making conversation activity more visible: adding a comment count and an invitation to comment. The change shipped recently, so its impact is still being measured.

## The brief

The task started on October 16, 2025, as an initial exploration: market benchmarks, a list of essential features, and a basic UX proposal for how people interact with comments.

Comments would be built with an external provider. It was not defined when the task started, and it was closed halfway through. 
I could not finalize the interaction design until the provider was selected, but I continued exploring the experience in parallel.

The ticket defined the acceptance criteria:

- Documented benchmarks, with strengths and weaknesses.
- A list of the minimum essential features.
- Wireframes or a basic prototype in Figma.
- Interaction patterns: scroll, expand and collapse, action buttons.
- Accessibility recommendations: screen readers, contrast.
- Microcopy for the empty, loading, and error states.

## Benchmark

I benchmarked YouTube, Instagram, and TikTok to understand familiar comment patterns across different audiences. Three principles stood out: replies are universal; editing and deleting should be limited to the author; and downvotes are either hidden or have little visible effect on the two largest platforms.

{% include image.html name="4.png" caption="Youtube" %}
{% include image.html name="5.png" caption="Instagram" %}
{% include image.html name="6.png" caption="Tiktok" %}


## Scope
I drafted the initial prioritization based on the benchmark and launch deadline, then aligned it with stakeholders.


The scope that shipped covers:

- **Main features:** like, comment, reply.
- **More actions menu:** edit, delete, and report. The reporting flow itself was a separate task.

The fuller version stayed as the roadmap.


{% include image.html name="list.png" caption="Priorities" %}

<div class="video-container">
{% include video.html name="prototype.mp4" caption="1st version prototype" %}
</div>



## Working within technical limits

Comments were built on Stream’s Activity Feeds. Between its documentation and conversations with the developers, I mapped what came ready and what did not:

- **Reactions:** quick reactions on comments are supported.
- **Sorting:** by date, by popularity (most liked or most replied), or by a custom score. But there was no relevance algorithm, like the ones Instagram and TikTok have, to feed any of it.
- **Deleting:** soft delete is supported, so a deleted comment can be restored.
- **GIFs:** not ready-made in comments, unlike in Stream’s chat product. They need a separate integration.


{% include image.html name="reactions.png" caption="Reactions v1" %}
{% include image.html name="sorting.png" caption="Sorting v1" %}
{% include image.html name="delete.png" caption="Delete v1" %}
{% include image.html name="gifs.png" caption="Gifs v1" %}


Talking to the developers also changed the design. One interaction I had designed in the comments bottom sheet turned out not to be possible to implement, so I changed it. My original version stayed as a future improvement.


{% include image.html name="old.png" caption="Interaction bottomsheet v1" %}
{% include image.html name="new.png" caption="Interaction bottomsheet" %}


These limits shaped most of the decisions below.

## Design decisions

Most of the value in this project came from a few decisions. For each one, here is the context, the decision, what it costs, and when to revisit it.

### No downvote

- **Context:** I noticed the dislike on YouTube and TikTok comments during the benchmark and wanted to know if it was worth adding, so I researched how each one works. A downvote only creates value if a system acts on it, for example, a ranking algorithm or a moderation workflow. GloboPop had neither at launch. In a large-audience product with a strong brand, it could also enable coordinated negativity without improving the conversation.
- **Options considered:** like and report, or multiple reactions and report.
- **Decision:** I chose a single like and a report action. This kept the interaction simple while preserving a path for moderation.
- **Trade-off:** I lose a quality signal that could help sort comments.
- **Revisit when:** there is a relevance algorithm or a moderation system that could use the signal.
- **Note:** the 👎 in the row of quick emojis above the input is not a downvote. As on Instagram, tapping an emoji only adds it to the text field.


### No comment count on the video, at first

- **Context:** I initially designed the comments icon with the number of comments below it. Stakeholders were concerned that a “0” or low count would make conversations look inactive. We also could not display the count at launch due to a technical constraint.
- **Decision:** launch without the count. A threshold-based solution still required showing a number, so it did not solve the constraint and added backend and provider complexity.
- **Trade-off:** the icon gave no indication of how active the conversation was.
- **Revisited after launch:** after launch, videos had few or no comments. We could not confirm that the missing count caused this, but it reinforced the concern that an apparently inactive conversation could feel uninviting. Once the technical dependency was resolved, we added the comment count and a tooltip inviting people to comment.


### Sorting: most recent first

- **Context:** the documentation allows sorting by date, popularity, or a custom score. In conversations with the developers it became clear that we had no algorithm to measure the relevance of comments or of likes on comments.
- **Decision:** comments show the most recent first. Replies to a comment also show the most recent first, but a thread of replies to a reply reads in chronological order, with the newest at the bottom, so that the conversation can be followed top to bottom.
- **Trade-off:** no control over the order, so a recent low-quality comment can appear on top.
- **Revisit when:** a score or priority field exists to sort by.

### Editing, with an “edited” mark

- **Context:** editing was not in my first feature list. I was not convinced it should stay out: the complexity is not high, YouTube, the main benchmark, has it, and it is better than forcing people to delete and repost.
- **Decision:** people can edit their own comments and replies. The comment gets an “edited” mark, the original timestamp does not change, there is no time limit to edit, no version history, and no notification.
- **Trade-off:** without history, a comment can change after people have reacted to it. The “edited” mark makes that visible, and I judged the risk of abuse manageable.
- **Note:** it is not critical, but highly recommended. I kept it in the design, even if it ships in a later phase.

### No avatars and no tappable @

- **Context:** without a public profile, there is nowhere for an avatar or a mention to lead. Quick emoji reactions give the interface some life instead.
- **Decision:** no avatars, and mentions without link color. The link color made them look tappable. The public profile was out of scope for this task, although necessary, and was prioritized in another task.
- **Trade-off:** the interface is drier.
- **Revisit when:** the public profile ships. I already explored a version with avatars (see Next steps).

### Replies to a reply stay in the same thread

- **Context:** in a reply to a reply, the @ of the person being answered does two jobs. It shows who is answering whom, and it notifies that person. If the @ is removed, the person is not notified, and it is no longer obvious who the reply is for.
- **Options considered:** nested replies, replies one below the other (as on Instagram), or a “Caique > Thami” label, closer to TikTok.
- **Decision:** replies to a reply stay in the same thread, one below the other, to improve reading order. The @ comes pre-filled in the input.
- **Trade-off:** a long thread can get hard to follow without visual nesting.

### Delete with Undo instead of a confirmation dialog

- **Context:** with soft delete, a deleted comment disappears from the feed but stays in the database, and the documentation sets no time limit to restore it. I considered an immediate Undo, or a place to manage deleted items (for example, Settings > Deleted items), which would take more work.
- **Decision:** deleting removes the comment immediately and shows a snackbar, “Comment deleted”, with an Undo button for 10 seconds. After that, the person can no longer undo it.
- **Trade-off:** it depends on the backend using soft delete. Deleting a comment also deletes its replies, which makes the immediate Undo more important.
- **Revisit when:** comment history and controls exist in Settings. They do not yet, and they were prioritized as a future need.

## Final solution

The comments experience lives in a bottom sheet over the video. People can open comments without leaving the video, comment, reply, and navigate threads. The sheet expands when the keyboard opens, and the video pauses to keep attention on the conversation.

- **Entry point and states:** the comments button on the video. At launch it had no count; after launch we added the count and a tooltip inviting people to comment. While loading, a skeleton in a color variant (the default skeleton has the same color as the sheet). The empty state reads “No comments yet” and invites the first comment.
- **Commenting:** tapping the input opens the keyboard and expands the sheet. The video pauses while the sheet is expanded. A row of quick emojis sits above the input: tapping one adds it to the text field, as on Instagram.
- **Replying:** tapping Reply expands the sheet. Replies are grouped under the original comment. At first it shows 5 replies, with “See 3 more replies” and “Hide replies”.
- **Replying to a reply:** a “Replying to” bar shows above the input, with the @ already filled in.
- **More actions:** edit and delete only on your own content, report on anyone’s comment.
- **Layers:** the More actions sheet opens over the comments sheet, so I proposed a blur behind it and a lighter surface to separate the levels, and reusing the destructive red already used in Globoplay.

Comments, likes, and replies generate notifications. That work is part of the notifications center, which will be its own case.


{% include image.html name="entrypoint.png" caption="Entry point" %}
{% include image.html name="states.png" caption="Empty - Loading - Error states" %}


## Handoff and validation

The presentation doubled as the handoff. Each screen is annotated with the behavior: tapping the input opens the keyboard, the sheet expands and the video pauses, the @ comes pre-filled in replies, and edited comments keep the original timestamp. After implementation, I validated and tested the feature in the app.


{% include image.html name="specs.png" caption="Handoff - Specs" %}
{% include image.html name="flows.png" caption="Handoff - Navigation Flows " %}

## Future steps

- **Public profile:** an interface with avatars and a link to the profile. It is necessary and was prioritized in another task.
- **GIFs and stickers:** in Stream’s feeds this is not a ready component, so it needs a GIPHY integration, storing the GIF in the comment, and checking whether specific GIFs can be excluded.
- **Contextual emoji row:** we agreed with the developers that the row of quick emojis could change according to the theme or subject of the video.
- **Comment history and controls in Settings.**
- **The original sheet interaction** I had designed before talking to the developers.

<!--
  ![GIF and sticker exploration](/assets/img/globopop/next-gifs.png)
  *Exploration: replying with GIFs and stickers*

  ![Exploration with avatars](/assets/img/globopop/next-avatars.png)
  *Exploration: interface with public profile elements*
-->

## What I’d do differently

- Validate the comment-count hypothesis before launch, even with a lightweight prototype or A/B test.
- Involve moderation and trust-and-safety stakeholders earlier, since comments affect more than the interface.
- Define success metrics at the start - for example, comment participation rate, reply rate, and share of videos with at least one comment.

Even without mature metrics, these would have made the post-launch decision faster and more measurable.

