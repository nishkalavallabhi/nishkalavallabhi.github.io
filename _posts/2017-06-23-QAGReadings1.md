---
layout: post
title: Reading Notes - Question Answering and Question Generation as Dual Tasks
categories: Readings
tags: [QG/QA/RC]
---
I have been reading about automatic question generation on and off for about an year now. There has been an increase in stuff that is coming up since last year, thanks to work on machine comprehension. My idea is to read regularly and write my summaries here from now on.

This post is my quick summary of what I understood an article I read, by a team from Microsoft Research, China.

Question Answering and Question Generation as Dual Tasks

Duyu Tang, Nan Duan, Tao Qin and Ming Zhou

It can be read on [ArXiv](https://arxiv.org/pdf/1706.02027.pdf)

Summary about the paper: Question generation and question answering are treated as two separate tasks generally speaking. This paper proposes a frame work to treat them both as a "dual" task considering the fact that they are both intrinsically related. For learning these tasks, they used bidirectional GRU (Gated Recurrent Unit) based RNN (Recurrent Neural Network) architecture. They then evaluate their method using two standard datasets used in Question Answering research - MS MARCO ([Microsoft Machine Reading and Comprehension](http://www.msmarco.org/about.aspx)) and SQuAD ([The Stanford Question Answering Dataset](https://rajpurkar.github.io/SQuAD-explorer/)) and conclude that they improve the state of the art for both QA and QG tasks.

My summary: In the beginning, I thought the paper was well written. The algorithm part was reasonably clear, and I was eager to look at the experiment section, although I was also skeptical considering my earlier disappointments about these claims of "improving state of the art" which usually boils down to something like 0.05% improvement in precision or some other measure on some standard dataset. I was not wrong.

First about QA evaluation: I did not understand the explanation for not using the standard test set of SQuAD and MARCO datasets. 

>  "It is worth to note that a common characteristic of these two datasets is that the ground truth of the test is invisible to the
public. Therefore, we randomly split the original validation set into the dev set and the test set."

Both MARCO and SQuAD have leaderboards where one can see the comparision numbers for the test data that they provide. So, an ideal comparison would not have been impossible to do in this case. While that will not actually tell us a whole lot about the system and the task (my reason: because all results could be just overfitting towards that test set), it will atleast let one do a fair comparison on the same test data with existing solutions. 

Next to QG evaluation: I wondered what is the point of evaluating a QG system with BLEU type metric and stopping there. Shouldn't there be some way to evaluate the grammaticality/fluency of the question, correctness etc? What is the point of a question generation system otherwise?  

Overall, I was not convinced that there is a lot of improvement over the state of the art because of their architectural choices. My perception may change as I continue to read more. One good thing about reading this though is: I knew most of the pre-2016, non-DL related work mentioned over there, but I did not know many datasets referred there.

So, my homework:
> "We are aware of other question answering datasets like WebQuestions (Berant et al., 2013), WikiQA (Yang et al., 2015) and  SimpleQuestions (Bordes et al., 2015)."

-next step is to start going through these first!

Phew, tough job. It will take a while to get used to Jekyll markdown and posting with it!
