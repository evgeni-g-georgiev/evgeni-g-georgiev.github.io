---
title: "How much AI makes a photo an AI photo?"
date: 2026-08-08
standfirst: The EU's new transparency rules turn on a threshold nobody has defined.
tags: [AI policy, EU AI Act]
pdf: /assets/files/how-much-ai-makes-a-photo-an-ai-photo.pdf
---

## A real video and a confident (mis)detection

During the 2026 Iran war, false claims circulated online that the Israeli Prime
Minister, Benjamin Netanyahu, had been killed in an Iranian missile strike. He
responded by posting a video of himself sitting in a café. Shortly after, users on
social media platforms started circulating a result from the AI detection tool Hive,
reporting that the clip was likely to be AI-generated, with a supposed probability of
96.9 percent. Understandably, this caused a big stir online as accounts sympathetic to
Iran presented the detector output as evidence that he was in fact dead [<a href="#ref-5">5</a>].

Eventually, comparisons with independent footage recorded at the same location
confirmed that the video was real. NewsGuard, which documented the episode, reported
that a slight edit had been applied to the clip, slightly blurring its background,
which caused the misclassification [<a href="#ref-5">5</a>]. A genuine recording with a
slight cosmetic edit led to a confident tool falsely concluding that a head of state
was no longer alive.

## What the law now asks

From 2 August 2026, transparency rules in the EU AI Act became applicable, imposing
duties on companies that build generative tooling and on the people who use and publish
the results of such tools [<a href="#ref-1">1</a>]. Two provisions of Article 50 are
particularly relevant, and they highlight the split of responsibility between the two
parties. Under Article 50(2), a company whose system produces synthetic audio, images,
video or text has to make sure the output carries a marker from the moment it is
produced, one that software can later read and that identifies the content as
machine-made. The Act requires that marker to be "effective, interoperable, robust and
reliable as far as this is technically feasible", without saying how effective or how
reliable. Then, under Article 50(4), someone who publishes a deepfake has to say so, and
this time the disclosure is aimed at readers rather than machines [<a href="#ref-1">1</a>].
Article 3(60) helps to define what this means: AI-generated or manipulated material that
depicts real people, places, or events convincingly enough to be confused for the real
thing.

The Act explicitly extends to manipulated material; in other words, it is designed to
reach content that has been altered, not only content generated from nothing. However,
it is also stated that marking duty does not apply, to quote the source material
directly, "to the extent the AI systems perform an assistive function for standard
editing or do not substantially alter the input data provided by the deployer or the
semantics thereof" [<a href="#ref-1">1</a>]. In plainer words, what matters is not
whether a system used AI, but whether any alterations made are substantial. Pinpointing
what substantial means exactly is difficult but the Commission has issued Guidelines on
Transparency of AI-Generated Content [<a href="#ref-3">3</a>]. A Code of Practice
followed on 10 June 2026, which the Commission and the AI Board have confirmed is an
adequate voluntary tool for demonstrating compliance, and which around 190 organisations
had signed by the end of July [<a href="#ref-4">4</a>]. Non-compliance can attract fines
of up to 15 million euros or 3 percent of worldwide annual turnover [<a href="#ref-2">2</a>].

Despite all this legislation, a provider is still faced with a fundamentally difficult
question: given a particular tool and a particular output, how would you tell whether
the line has been crossed? The problem is not careless drafting. Law fixes thresholds on
continuous quantities all the time, for example in speed limits, blood alcohol limits
and the age of majority. Those work because the quantity being measured is settled, and
only the number is argued over. With image manipulation the argument has not reached
that stage. There is no general consensus about what to measure.

## Photographs have never been unaltered

To demonstrate the challenges faced by providers, it is useful to review the work of
Meding and Sorge who explore exactly what constitutes a deep fake [<a href="#ref-6">6</a>].
They make the point by walking through the life of an ordinary digital photograph.
Before anyone sees an image, a camera has typically interpolated colour, because sensors
usually record only one colour per pixel. It has corrected faulty pixels, suppressed
sensor noise, corrected lens vignetting and distortion, adjusted for the colour of the
ambient light so the result matches how a person would have perceived the scene,
compressed the tonal range to suit a screen, and sharpened edges. Every one of these
steps changes what a viewer sees, and all are considered entirely legitimate [<a href="#ref-6">6</a>].

Newer features sit less comfortably. Meding and Sorge discuss Samsung's Scene Optimizer,
shown to add moon texture to photographs in which the moon was recognised, and Google's
Best Take, which replaces a face in a group photograph with the same person's face from
another frame in the burst, producing what they describe as a depiction of a situation
that never occurred [<a href="#ref-6">6</a>].

Their sharpest contribution is a demonstration. They take one photograph of a man and
produce two edited versions. In the first, a stylised pistol is placed over his hand. In
the second, the intensity around the hand is nudged, with no visible effect. Measured as
the root mean squared difference across the colour channels, both differ from the
original by exactly the same amount, 1.83 pixel values. The meanings could hardly be
further apart [<a href="#ref-6">6</a>]. Their conclusion is that measuring how much an
image has changed tells you nothing about whether the change mattered. They recommend
removing this half of the exemption altogether, on the grounds that the other half,
which asks whether the meaning has shifted, is the only one doing useful
work [<a href="#ref-6">6</a>].

## Detectors do not see what people see

Unsurprisingly, there exists a chain of research that aims to develop technology that
can tell generated images from real ones. Most simply, a diffusion model can be run
backwards. Given a finished image, the sampling process can be inverted to estimate the
noise pattern that would have produced it, and the image can then be rebuilt from that
estimate. How closely the rebuilt version matches the original carries information about
where the image came from. Wang et al. found that images a diffusion model made can be
reconstructed this way fairly accurately, while real photographs cannot, and turned the
residual between an image and its reconstruction into the input for a trained
classifier [<a href="#ref-7">7</a>]. Cazenavette et al. took a related route, handing a
classifier the original image alongside the recovered noise pattern and the
reconstruction, rather than working from the residual alone [<a href="#ref-8">8</a>].
Both, however, answer a yes-or-no question about a whole image. Neither estimates how
much of a picture a model is responsible for, or how far its meaning has moved.

Work on that second question has moved quickly, and a large assessment of it arrived in
May 2026. Nichols and colleagues built AUDITS, a collection of just over half a million
images in which regions have been replaced, removed or inserted using eleven different
diffusion editing tools, Adobe Firefly among them [<a href="#ref-9">9</a>]. Roughly three
fifths of it comes from press photographs published by the Guardian, the BBC, USA Today
and the Washington Post. Edited regions run from a small fraction of the frame to the
whole of it, and the authors use this to ask questions that had not previously been
separable.

The finding worth pausing on concerns people. Nearly two thousand respondents were shown
edited images together with an overlay marking the altered region, and asked whether the
object there looked realistic. Their answers sort the edits into ones that struck
viewers as convincing and ones that did not. Detector performance barely moves between
the two groups: the gap is usually under two percentage points and often under half a
point [<a href="#ref-9">9</a>].

Some care is needed in reading that across to the law. Respondents were told where to
look, which is not the position of somebody scrolling past an image, and when the same
study asked outright whether an image had been manipulated, around four in five said
yes [<a href="#ref-9">9</a>]. So this is not evidence about who gets deceived in the
wild. What it does show is that a detector's confidence and a person's sense that
something looks wrong are close to unrelated. That should trouble anyone applying
Article 3(60), which turns on whether content would falsely appear to a person to be
authentic [<a href="#ref-1">1</a>]. The statute asks about an impression formed by a
human being, and the available instruments are responding to something else.

A second finding matters for the exemption specifically. Spotting that an image has been
altered somewhere is a different job from marking out how much of it was altered, and
the exemption depends on the second. These systems produce a map of where they think
editing occurred, and they are cautious about it, reluctant to mark a region unless
fairly confident. On a small edit that caution costs little. When most of a frame has
been changed, it shows up plainly: the maps identify only part of what was
altered [<a href="#ref-9">9</a>]. An instrument that consistently understates the extent
of a change is an awkward foundation for a rule that turns on whether the change was
substantial.

The third finding most resembles the problem this essay is about. Diffusion editing does
not stay inside the region it was asked to change. These tools blend new content into
its surroundings, and the blending reaches past the boundary. The authors therefore
could not simply label pixels edited or not, and introduced a middle category for pixels
outside the intended region that nonetheless differ from the original. Deciding which
pixels qualified required a cut-off on pixel difference, which they set at 0.0025 and
describe as chosen empirically [<a href="#ref-9">9</a>]. There is nothing wrong with the
choice. The point is that it had to be made at all, by researchers, with nothing in the
field telling them where it belonged.

None of this is a criticism of the work, which is careful and reports its performance
honestly, in a field where that has not always been true. It is a description of the
gap. The instruments produce graded estimates whose accuracy depends on the tool used to
make the edit, the source of the photograph and the size of the change, and which track
human judgements of realism hardly at all. The law needs a decision, about whether a
viewer would be misled, with a fifteen million euro consequence attached.

## Thresholds are being set in private

The research literature has the luxury of saying where it drew its lines. Commercial
detection tools do not, and they are the ones being consulted when someone wants to know
whether a photograph on their screen is real. To return a verdict at all, such a tool
must decide how much alteration is enough to count, and it makes that decision thousands
of times a day without publishing where the line falls. That line can still be inferred,
by handing several tools the same images and watching where they disagree.

In late April and early May 2026, NewsGuard assembled fifteen authentic photographs
relating to the Iran war, drawn from Reuters, the Associated Press, The New York Times,
The Guardian and Google Earth. Each was edited twice, once lightly by asking an AI tool
to improve the lighting and blur the background, and once heavily by asking it to change
the image's meaning. The forty-five resulting images went to five commercial detectors,
Hive, AI or Not, ZeroGPT, Sightengine and ScamAI, with anything scored at 50 percent or
above counted as a positive [<a href="#ref-5">5</a>]. NewsGuard sells
information-reliability ratings and so is not a disinterested party, and fifteen images
is a small sample, but this is the only public comparison of several detectors on
lightly and heavily edited versions of the same photographs.

On the untouched originals, the tools collectively called authentic images AI-generated
13.33 percent of the time. ScamAI flagged six of the fifteen, ZeroGPT three, AI or Not
one. Hive and Sightengine flagged none [<a href="#ref-5">5</a>]. The revealing result is
the middle category, which is precisely the population the standard-editing exemption is
meant to describe. On the lightly touched-up images, ScamAI returned an AI-generated
verdict for 93 percent, AI or Not for 87 percent and ZeroGPT for 80 percent. Hive and
Sightengine returned it for 27 percent [<a href="#ref-5">5</a>]. The same images, and a
spread running from roughly a quarter of them to almost all of them. On the images
edited to change their meaning, detection rates ranged from 33 percent for Sightengine
to 100 percent for AI or Not, and across the whole set at least one tool disagreed with
the others on 35 of the 45 images [<a href="#ref-5">5</a>]. At the extremes a familiar
trade-off appears. Sightengine never misjudged an authentic image, and missed two thirds
of the meaning-changing edits. ScamAI misjudged the most authentic images, and caught 80
percent of the meaning-changing ones.

NewsGuard's own conclusion is the one worth carrying forward. There is no industry
consensus on what counts as AI-generated content, and the tools do not state what level
of manipulation will produce a positive verdict [<a href="#ref-5">5</a>]. The sensitivity
of such systems to ordinary processing is documented in the research literature.
Grommelt et al. found that a detector trained on part of the GenImage dataset classified
uncompressed natural images correctly only about 80 percent of the time, and that its
accuracy on those same images rose steadily as they were compressed, reaching 100
percent at a JPEG quality factor of 60 [<a href="#ref-10">10</a>]. The detector had
partly learned that compression means authenticity. Whether a real photograph is judged
real depends, in part, on how it was saved.

## A perspective from industry

Announcing Content Credentials on the Pixel 10, Google linked directly to Article 50 and
observed that the traditional approach of sorting content into "AI" and "not AI" has
been the basis of many legislative efforts, and that this approach has drawbacks. The
reason they gave is the implied truth effect, if only synthetic content is labelled,
people come to believe that unlabelled content is authentic [<a href="#ref-11">11</a>].

Google's stated alternative is provenance: a signed record travelling with a file,
saying where it came from and what has been done to it. The sorting question changes as
a result. Rather than asking whether an image is synthetic, you ask whether it can
account for itself. Pixel Camera attaches Content Credentials at the moment of capture,
and Google Photos adds them when an image is edited with AI tools [<a href="#ref-11">11</a>].
The limits are real. A credential only survives as long as the file does, so a
screenshot or a re-encoding strips it. And signing at the moment of capture is confined
to a small number of recent devices, so the overwhelming majority of cameras in use
produce nothing of this kind. A credential tells you something when it is present; it
tells you almost nothing when it is absent. The risk is that people read a missing
credential as a warning, which is the mistake Google itself identifies, arriving from
the opposite direction.

## Looking to the future: what a usable threshold would need

The conclusion is not that the marking duty should be abandoned. It is that a threshold
written into law has to be specified as a decision rule, and at present it is not
specified at all. Three things are missing.

**It needs a stated quantity.** Not raw pixel distance, which Meding and Sorge have
shown to be meaningless here [<a href="#ref-6">6</a>], but something closer to a
calibrated estimate of how much of an image a model is responsible for, kept separate
from a measure of how much the meaning has changed. The Act distinguishes between
altering the input data and altering its semantics [<a href="#ref-1">1</a>], without
specifying how either should be measured.

**It needs a stated operating point.** Any classifier can be tuned to be cautious or
aggressive, and the choice determines who bears the cost of its mistakes. Vendors have
already made that choice, differently from one another, without publishing
it [<a href="#ref-5">5</a>].

**And it needs stated test conditions.** A detector's accuracy is not a fixed property
of the detector. Grommelt et al. showed that the same photographs were judged very
differently depending only on whether they had been saved as compressed files, because
the detector had partly learned that compression is a sign of
authenticity [<a href="#ref-10">10</a>]. Since a picture that has passed through a
messaging app has been re-encoded and shrunk, and one sent straight from a camera has
not, the same image can receive different verdicts depending on how it reached you.

Underneath all three is a single question nobody has answered where it counts: how much
alteration is enough. It is being answered constantly, just not in public. Providers
decide, without explaining themselves, whether their own editing tools cross the line.
Detection vendors answer a version of it from the outside, and the NewsGuard results
show how far apart their answers fall. Researchers who build these systems have to
answer it too, and at least they say so, though the thresholds they choose are chosen
for want of anything better. Nobody has been asked to justify a line, and the law has
not offered one. The Code of Practice has a formal adequacy assessment and roughly 190
signatories. What it does not have is a clear way to tell a substantial alteration from
a trivial one.

## References

<ol class="refs">
<li id="ref-1">Regulation (EU) 2024/1689 of the European Parliament and of the Council of 13 June 2024 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act), OJ L, 2024/1689, 12.7.2024. <a href="http://data.europa.eu/eli/reg/2024/1689/oj">ELI</a>.</li>
<li id="ref-2">European Commission, <a href="https://digital-strategy.ec.europa.eu/en/faqs/transparency-obligations-under-article-50-ai-act">Transparency obligations under Article 50 of the AI Act</a> (frequently asked questions). Last updated 24 July 2026.</li>
<li id="ref-3">European Commission, <a href="https://digital-strategy.ec.europa.eu/en/policies/guidelines-transparency-ai-generated-content">Guidelines on Transparency of AI-Generated Content</a>. Page last updated 20 July 2026.</li>
<li id="ref-4">European Commission, <a href="https://digital-strategy.ec.europa.eu/en/policies/code-practice-ai-generated-content">Code of Practice on Transparency of AI-generated Content</a>. Published 10 June 2026; page last updated 31 July 2026.</li>
<li id="ref-5">I. Blachez, S. Rubinson and I. Chomnalez, <a href="https://www.newsguardtech.com/special-reports/leading-ai-image-detection-tools-mislead-online-users-often-declaring-authentic-content-fake/">Leading AI Image Detection Tools Mislead Online Users, Often Declaring Authentic Content Fake</a>. NewsGuard, 8 May 2026.</li>
<li id="ref-6">K. Meding and C. Sorge, What constitutes a Deep Fake? The blurry line between legitimate processing and manipulation under the EU AI Act. Symposium on Computer Science and Law (CSLAW '25), Munich, March 2025, pp. 152–159. DOI: <a href="https://doi.org/10.1145/3709025.3712218">10.1145/3709025.3712218</a>. Preprint: <a href="https://arxiv.org/abs/2412.09961">arXiv:2412.09961</a>.</li>
<li id="ref-7">Z. Wang, J. Bao, W. Zhou, W. Wang, H. Hu, H. Chen and H. Li, DIRE for Diffusion-Generated Image Detection. Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV), 2023, pp. 22445–22455. Preprint: <a href="https://arxiv.org/abs/2303.09295">arXiv:2303.09295</a>.</li>
<li id="ref-8">G. Cazenavette, A. Sud, T. Leung and B. Usman, FakeInversion: Learning to Detect Images from Unseen Text-to-Image Models by Inverting Stable Diffusion. Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR), 2024. Preprint: <a href="https://arxiv.org/abs/2406.08603">arXiv:2406.08603</a>.</li>
<li id="ref-9">K. Nichols, D. Appapogu, G. Biamby, D. Bashkirova, A. Rohrbach and B. A. Plummer, Multi-axis Analysis of Image Manipulation Localization. Preprint, May 2026. arXiv:2605.20174. <a href="https://huggingface.co/datasets/DivyaApp/AUDITS">Dataset</a>.</li>
<li id="ref-10">P. Grommelt, L. Weiss, F.-J. Pfreundt and J. Keuper, Fake or JPEG? Revealing Common Biases in Generated Image Detection Datasets. ECCV Workshops, 2024. Preprint: <a href="https://arxiv.org/abs/2403.17608">arXiv:2403.17608</a>.</li>
<li id="ref-11">E. Lynch and S. Hanna, <a href="https://blog.google/security/pixel-android-trusted-images-c2pa-content-credentials/">How Pixel and Android are bringing a new level of trust to your images with C2PA Content Credentials</a>. Google Security Blog, 10 September 2025.</li>
</ol>
