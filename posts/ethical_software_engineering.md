# Finding Ethics in Data Security

_(For the purpose of this blog post, the term engineer is defined as software engineers, devops engineers, and all of those that have a responsibility for maintaining the infrastructure and software for computer systems)_

We live in a world increasingly intertwined with software; the Internet of Things allows companies to collect data relating to not only what we type, but on where we are, who we are with, how we drive our vehicles, and more intimate details like our sleeping patterns and heart rates. In the near future it will be trivial to sequence an individual's genomic information and make predictions about their personality traits and health.

Modern computers have the space and power to analyze this data incredibly efficiently, and if Moore’s Law continues to hold up, we will start to see real time analysis of an individual's genetic constitution. The implications of this are far reaching; individuals could be discriminated against on a level far deeper than gender or ethnicity, and it has the potential to impact everything from loans, job prospects, insurance and even our interpersonal relationships - imagine a dating app based on genetic viability.

Although 'genetic fortune telling’ may seem a way off, the way we handle privacy and data security now will build the foundations for the future, and engineers often play the role of gatekeeper to the systems which contain this sensitive information. To whom is their moral obligation? The client, the user, or perhaps the Government?

## The Home Office's stance

The terrorist attack on Westminster in March 2017 brought the issue to the fore when a WhatsApp message was sent a few minutes before the attack, which the government were unable to decipher due to the end to end encryption in place. Should the engineers responsible for this encryption allow the government access, or decrypt the messages for them? To the Home Secretary, Amber Rudd, the answer is clear;  WhatsApp have a moral obligation to allow the government ‘backdoor access’ to its messaging services. The rationale for this is that terrorists should not have a place to hide online, that encryption enables terrorists to communicate freely and that society would be a safer place if encryption were banned. Although it’s likely a difficult task to ban a branch of mathematics, it would be an even more difficult task to enable worldwide banking and e-commerce without encryption. The does not seem, to me, to be a viable solution.

Perhaps had the government had access to WhatsApp’s data they could have intervened sooner, however it seems unlikely given the two minute time frame. More likely, they would have been able to analyze this information after the incident to glean a better insight into the cause, however this is not without its own risks. A backdoor for one individual means an exposed point for groups with less than ethical ideals. A ‘secure backdoor’ is not secure - people can and will access it and their intentions most likely won’t be good. Would every holder of personal data (almost every company operating on the web) be expected to have a backdoor? This would present incredibly difficult to solve problems for keeping personal data secure, and largely useless too; no organisation has the computing power to analyze all of this data fast enough to make use of it. Perhaps some time in the future, but not now.

## Practices for Ethical Engineering

There is a solution, I believe, which is more balanced. It is the system currently in place; the government requests access to encrypted organisational data, and the organisation makes a choice to either release the data or refuse access. Ethically, I believe they have an obligation to support the government in investigations, but the government also have an ethical obligation not to put society's personal data at risk of exposure.

So where does this leave the ethical obligations of the engineer? Should they make a stand and refuse to allow access to data if it is requested, if it conflicts with their moral principles? This is a far more difficult question to answer. It is so subjective that it cannot, I believe, be generalised broadly. There are however a few practices which can be applied broadly, and that would in my mind, mark both a professional and ethical engineer from a security perspective:

* An engineer should always stay on top of security developments and potential vulnerabilities in their chosen tools.

* They should understand the advantages of other technologies, and when using them offers their customers better security.

* They should have a good knowledge of cryptographic methods. Perhaps not at the implementation level, but at least a high level understanding of the advantages and disadvantages of each.

* They should have a good understanding of data backup methods to mitigate the risk of data loss, but to also ensure the data isn’t easily accessed by those who shouldn’t be able to.

* They should ensure that physical access to infrastructure is secure if it is kept on site. Failing that, a reliable infrastructure provider should be used.

* The geographic location of third party hardware should be considered carefully. Different countries have different data protection laws.

## Looking to the future

Data plays an integral role in our day to day lives, and it is likely to play a more important role in the future. The data being collected is becoming more personal, more invasive and as a result, our responsibility to keep it secure has never been greater. Whatever the ethical implications of the particular situation, as long as an engineer does all they can to ensure the security and integrity of their customer's data, at a professional level I believe they have fulfilled their moral obligations.
