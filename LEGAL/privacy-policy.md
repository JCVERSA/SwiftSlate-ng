# Privacy policy

> **Version 1.0 — 20 September 2026**
> This is a translation of the authoritative French document: [politique-confidentialite.md](politique-confidentialite.md). In case of divergence, the French version prevails.
> This document supplements, without replacing, the [legal notice](legal-notice.md).

---

## 1. In one page

| Question | Answer |
|:--|:--|
| Does the app create an account? | **No.** No account, no sign-up, no user identifier. |
| Does the publisher collect your data? | **No.** There is no publisher-operated server, database or dashboard. The publisher has no way of knowing who uses the app or what is typed. |
| Cookies, trackers, analytics? | **None.** No analytics, no advertising pixel, no automatic crash reporting. |
| What happens to the text you rewrite? | It is sent **to the AI provider you configured yourself**, using your own API key. This is the only substantial processing described here. |
| Where does my data go? | To the provider you choose: the United States for most of them, **China for DeepSeek**. Section 6. |
| What stays on my phone? | Your API keys (encrypted), your preferences and, if you enable it, a local history. Section 5. |
| For how long? | The publisher keeps nothing. The retention periods below concern your device and the providers. Section 7. |
| How do I exercise my rights? | By email to **jcversa16@gmail.com**. Section 9. |

---

## 2. Who is the controller?

**Controller**: the publisher of the SwiftSlate service, a natural person acting on a non-professional basis, reachable at **jcversa16@gmail.com**.

Under Article 6-III-2 of the French LCEN, the publisher does not make their identity and personal details public; those details have been communicated to the hosting provider (GitHub B.V.). The same email address serves as the functional contact point for any data protection question and for exercising the rights set out in section 9.

**No Data Protection Officer**: none of the cases requiring one (Art. 37 GDPR) applies. The contact above serves that purpose.

### 2.1 A point of vocabulary that matters

The publisher's role differs depending on the processing:

| Processing | Who decides the purpose and the means? |
|:--|:--|
| Sending text to the AI provider | **The publisher**, who designs and documents what the app does. The publisher is the controller for that transmission, as described in section 5.1. |
| Choosing the provider, the command and the text | **You.** The app sends nothing unless you explicitly trigger it. |
| Data stored on your device (keys, history, preferences, statistics) | **You.** The publisher has **no access**: this data never leaves the phone. |
| The AI provider receiving the data | **The provider**, as a separate controller or processor under its own terms. Its privacy policy applies from the moment it receives the text. |

---

## 3. Design principle

The app is built so that the publisher **needs no data at all** in order to work:

- no account, no application server, no database on the publisher's side;
- no analytics, advertising or crash-reporting library is included in the software (verifiable in the project dependencies);
- automatic Android cloud backups are **disabled** for sensitive preferences;
- privacy mode, switchable in Settings, **blocks all transmission**: only local text-replacement commands keep working.

Real processing nonetheless remains, described one by one below. It is limited, but it exists, and this document exists to make it readable.

---

## 4. Who this document applies to

| | |
|:--|:--|
| **Territorial basis** | Regulation (EU) 2016/679 (GDPR) applies because the publisher is established in France (Art. 3(1)) **and** because the service is offered to people in the Union (Art. 3(2)), including where you reside outside Europe. |
| **Complementary French law** | The French Data Protection Act (Law No. 78-17, as amended), including its provisions on children's consent. |
| **Intended audience** | Individual users. The app is not intended for children (see section 11). |

---

## 5. The processing activities, one by one

### 5.1 Sending text to an AI provider

This is the app's core processing: without it, the rewriting assistant does nothing.

| | |
|:--|:--|
| **Data** | The contents of the text field to which you apply a command (the visible text, truncated to the limits set by the app); your API key, sent as an authentication header; technical data inherent to any network request (IP address, timestamp), processed by the provider. |
| **Data subjects** | You, and — if the text you rewrite mentions them — third parties the text is about. See the warning below. |
| **Purpose** | To run the rewrite command you triggered; to return the transformed text into the input field. No other purpose: no profiling, no advertising, no database built by the publisher. |
| **Legal basis** | **Consent** (Art. 6(1)(a) GDPR). You only trigger a transmission by deliberately typing a trigger command, after configuring a provider and a key yourself. |
| **Withdrawing consent** | Stop using AI commands; enable **privacy mode** (no transmission at all, local replacement still works); delete the provider key; or uninstall the app. |
| **Recipients** | The provider you selected, and only that provider. The publisher receives no copy and no log. |
| **Retention** | **Nothing is retained by the publisher.** The text is not kept after the response, unless you enabled local history (section 5.4). At the provider, retention is as described in section 6. |
| **Transfer outside the EU** | Yes, in most configurations. See section 6. |
| **Security measures** | HTTPS required, HTTP redirects disabled (a key cannot be redirected to another host or to an unencrypted connection), keys encrypted at rest, keys stripped from error messages before display. |

> ⚠️ **Warning — do not send just any text.** Transmitted text is processed by a third-party provider, on infrastructure the publisher does not control. Do not include special-category data within the meaning of Article 9 GDPR (health, political or religious opinions, sexual orientation, trade union membership, biometric or genetic data), passwords, bank card numbers, or data about third parties who do not expect such processing. The provider may retain requests for the period stated in section 6, and **no human review** of those requests can be ruled out by the publisher.

### 5.2 Daily update check

| | |
|:--|:--|
| **Data** | IP address, installed app version, request timestamp. |
| **Purpose** | To find out whether a newer version exists and notify you. No data is extracted from your text. |
| **Legal basis** | **Legitimate interest** (Art. 6(1)(f) GDPR): informing you of an update, in particular a security fix. The privacy impact is minimal and the publisher keeps nothing. |
| **Frequency** | At most once a day, in the background. |
| **Recipient** | GitHub, Inc. / GitHub B.V. (a call to `api.github.com`). |
| **Retention** | The publisher stores only the last version you were already notified about, **on your device**. GitHub applies its own log policy. |
| **Transfer outside the EU** | Yes, to GitHub (see section 6). |
| **How to avoid it** | Disable the app's notifications, or restrict its network access at system level. |

### 5.3 Provider API keys

| | |
|:--|:--|
| **Data** | Your API keys for the AI providers, plus any access settings for a custom endpoint. |
| **Purpose** | To authenticate your requests to the provider you configured. Without a key, the app cannot work. |
| **Legal basis** | **Consent** (Art. 6(1)(a) GDPR), given by voluntarily entering the key. |
| **Storage** | **On your device only**, encrypted with AES-256-GCM using a non-exportable key held by Android Keystore. If encryption fails, the app refuses to write rather than degrade protection. |
| **What is never done** | Keys are never sent to the publisher; never included in automatic Android backups (disabled); never included in the manual settings backup. An encrypted, passphrase-protected export exists, at your exclusive initiative. |
| **Retention** | Until you delete the key, or until you uninstall the app. |
| **Transfer outside the EU** | The key is sent only to the relevant provider, as an authentication header of your own requests. No other recipient. |

### 5.4 Local command history — disabled by default

| | |
|:--|:--|
| **Data** | Input text, output text, command name, associated provider, date. |
| **Purpose** | To let you find and, if needed, revisit your recent rewrites. |
| **Legal basis** | **Consent** (Art. 6(1)(a) GDPR). History is **off by default**: until you enable it, no entry is written. |
| **Storage** | On your device only, in the app's private storage. Never transmitted, never synced, excluded from backups. |
| **Retention** | Whichever period you choose: **30 days by default**, up to 365 days maximum. The number of entries is capped (100). You can clear history in one action, at any time, from Settings. |
| **Withdrawing consent** | Disable history or clear it. Deletion is immediate and permanent. |

### 5.5 Local usage statistics

| | |
|:--|:--|
| **Data** | Aggregated counters: number of commands run, breakdown by command, by day and by month. |
| **Purpose** | To show your own activity on the app's dashboard. |
| **Legal basis** | This processing is **purely local** and is never transmitted to the publisher, who has no access to it. It does not identify you. |
| **Retention** | Until uninstallation, or until you reset it from the app. |
| **Transfer** | None. |

### 5.6 Email correspondence

| | |
|:--|:--|
| **Data** | Your email address, the content of your message and any attachments (screenshots, log excerpts, device information). |
| **Purpose** | To answer your request; to handle vulnerability or abuse reports; to follow up on incidents. |
| **Data subjects** | You, and anyone you mention in your message. |
| **Legal basis** | **Legitimate interest** (Art. 6(1)(f) GDPR): answering a request and keeping the service secure. Where your message seeks to exercise a right (section 9), processing is based on the **legal obligation** in Art. 6(1)(c). |
| **Recipient** | The publisher, on their email mailbox (mail hosting provider: **Google — Gmail**). |
| **Retention** | Kept while the request is handled, then **12 months** after the last reply, then permanently deleted. |
| **Transfer outside the EU** | Yes, the mailbox being hosted by Google. See section 6. |
| **Warning** | Do not send passwords, API keys or special-category data in a message; if a report contains any, they may be redacted in the exchange. |

### 5.7 Android permissions and the accessibility service

The app requests the following permissions. None is used for any purpose other than those described here.

| Permission | Why | What is not done |
|:--|:--|:--|
| **Accessibility service** | To detect a trigger command at the end of text in the foreground app, then replace the text with the result. | Text is **not** read continuously: only text changes are inspected for a command. Password fields are skipped. No text is transmitted until a command is recognised. Nothing is retained by the publisher. |
| **Internet** | To reach the configured AI provider and check for updates. | No call to any publisher server: none exists. |
| **Notifications** | To show the update-available notification. | No advertising or promotional notifications. |
| **Vibration** | Haptic feedback on actions. | — |
| **Boot completed** | To restore its state after a phone restart. | No data transmitted. |

If you deny or revoke the accessibility permission, the app stops working inside other apps; its other features remain available.

---

## 6. Transfers outside the European Union

The publisher **transfers no personal data**, because it holds none. The transfers described here are those triggered by **your own configuration**, towards the providers you choose.

### 6.1 The AI provider you select

| Provider | Destination | Safeguards known as of 20 September 2026 |
|:--|:--|:--|
| **Google — Gemini API** | United States (caching possible in any country where Google operates) | Google LLC is certified under the **EU–US Data Privacy Framework**. Processing falls under the Google Cloud Data Processing Addendum, which incorporates the Commission's **standard contractual clauses**. For users in the EEA, the UK and Switzerland, "paid services" terms apply even to the free tier: **text is not used to train models**. Technical logs are kept for about **55 days** for abuse prevention. |
| **Groq** | United States (Google Cloud buckets) | Groq's services agreement **contractually prohibits** training on your inputs and outputs. By default Groq **does not retain** inference data; limited logging may remain for up to **30 days** for troubleshooting or abuse investigations. A **zero data retention** option can be enabled by you in the console. The DPA incorporates the EU standard contractual clauses and the UK addendum. |
| **NVIDIA NIM** | United States | **[TO BE VERIFIED]** Refer to NVIDIA's DPA and privacy policy before sending personal data. This document will be completed once verified. |
| **OpenRouter** | United States (routing service to third-party providers) | **[TO BE VERIFIED]** OpenRouter routes to providers with differing policies. An account setting lets you refuse training on requests: **turn it off if you have not already**. |
| **DeepSeek** | 🇨🇳 **China** | ⚠️ **No adequacy decision, no published standard contractual clauses.** The transfer to China has no documented safeguard under Chapter V GDPR, and European supervisory authorities have opened investigations into this service. **Do not use this provider for text containing personal data**, yours or third parties'. |
| **Custom endpoint** | Wherever **you** host it: often a server on your own local network (Ollama, LM Studio, vLLM) | No transfer: data stays on your network. Over plain HTTP on a local network, traffic is unencrypted — the app warns you. |

### 6.2 Hosting and email

| Recipient | Destination | Safeguards known as of 20 September 2026 |
|:--|:--|:--|
| **GitHub** (service hosting, releases, update check) | United States and the Netherlands — GitHub B.V. is the contracting entity for the European Union | GitHub states that it adheres to the **EU–US Data Privacy Framework** and its UK extension, and relies on standard contractual clauses for other transfers. |
| **Google — Gmail** (contact mailbox) | United States | Google LLC is certified under the EU–US Data Privacy Framework. |

---

## 7. Retention periods at a glance

| Data | Where | Retention | Who deletes it |
|:--|:--|:--|:--|
| Text sent to a provider | At the provider | Never retained by the publisher; at the provider, per section 6.1 | The provider, under its policy |
| Input and output text (local history) | On your device | **Off by default.** 30 days by default when enabled, 365 days maximum, at most 100 entries | You, in one action |
| API keys | On your device, encrypted | Until you delete them or uninstall | You |
| Preferences, custom commands, model choice | On your device | Same as above | You |
| Usage statistics | On your device | Until reset or uninstall | You |
| Last notified version (update) | On your device | Until the next notification | You, by uninstalling |
| Contact emails | On the publisher's mailbox | **12 months** after the last reply | The publisher |

---

## 8. Recipients and processors

The publisher uses **no processor** to handle your data: it handles none. The only recipients are those determined by your configuration:

| Recipient | Role | Data received |
|:--|:--|:--|
| Selected AI provider (Google, Groq, NVIDIA, OpenRouter, DeepSeek or your endpoint) | Delivering the model's answer | The text you submit, your API key, the request's technical data |
| GitHub (hosting, releases) | Distributing the app, hosting the code and issues | Platform login data when you browse it; IP address and app version during the update check |
| Google (Gmail) | Receiving contact emails | Your address, the content of your message |
| GitHub Sponsors | Processing voluntary donations, if you make one | The data **you** provide to GitHub for that purpose — the publisher only sees your public username and the amount, never bank details |

**No data is sold, rented, shared for advertising purposes, or used to train a model by the publisher.** It has neither the means nor the intention: it receives nothing.

---

## 9. Your rights and how to exercise them

### 9.1 The rights

| Right | What it means here |
|:--|:--|
| **Access** (Art. 15) | To know whether data about you is processed and obtain a copy. Here: the publisher holds none, apart from our email exchange. |
| **Rectification** (Art. 16) | To correct inaccurate data. |
| **Erasure** (Art. 17) | To have your data deleted. For local data, erasure is **immediate and yours to perform**: Settings, or uninstall. |
| **Objection** (Art. 21) | To object to processing based on legitimate interest — concretely: disable notifications, or stop using AI commands. |
| **Restriction** (Art. 18) | To freeze use of your data while a disagreement is resolved. |
| **Portability** (Art. 20) | To receive your data in a readable format. The app's local data can be exported with the built-in backup feature (without API keys, which are never exported in the clear). |
| **Withdrawal of consent** (Art. 7(3)) | To withdraw consent at any time, without affecting the lawfulness of prior processing. |
| **Complaint** (Art. 77) | To lodge a complaint with a supervisory authority. Section 15. |

**No solely automated decision-making** producing legal or similarly significant effects is carried out (Art. 22): there is no profiling, scoring or automated sorting. See section 12.

### 9.2 How to exercise them

Write to **jcversa16@gmail.com**, stating what your request concerns. Requests are handled within **one month** (extendable by two months for complex requests, in which case you will be informed).

One important clarification, in the interest of honesty: for data sent to an AI provider, **the publisher holds no copy** and therefore cannot consult or delete it. A request about that data must be addressed **directly to the provider concerned**, which receives it and applies its own policy. On request, the publisher will tell you where to send it.

---

## 10. Security

Technical measures actually in place (verifiable in the source code, released under the MIT Licence):

| Measure | Detail |
|:--|:--|
| Key encryption | AES-256-GCM, with a non-exportable key held by Android Keystore. An encryption failure causes a write refusal, never a plaintext fallback. |
| Transport | HTTPS required for every remote provider. Automatic HTTP redirects are disabled, so a key cannot be redirected to another host or to an unencrypted connection. |
| Local network | HTTP tolerated only towards private local-network addresses, with an explicit warning that traffic is unencrypted. |
| Secret leakage | Keys are masked in error messages before any display. |
| Backups | Automatic Android backups (cloud and device transfer) are disabled for sensitive preferences. Manual backup excludes keys and history. |
| Telemetry | None. No analytics, no automatic crash reporting. |

**Data breach**: if a breach likely to result in a high risk to your rights came to the publisher's knowledge, it would be notified to the CNIL within 72 hours (Art. 33) and, where necessary, to the data subjects (Art. 34), through the available channels — the app not being connected to any publisher server, information would have to go through the public repository and release notes.

---

## 11. Children

The service **is not intended for children**. It is not designed for them, addresses no communication to them, and collects no data about them — the publisher collects no data at all, regardless of age.

In France, the consent of the holder of parental authority is required for a child under **15** to sign up for an information society service (Art. 45 of Law No. 78-17). As no sign-up is offered, this situation does not arise.

If you are a parent and find that your child uses the app, you can uninstall it: no data is held by the publisher, so no remote deletion is needed.

---

## 12. Cookies, trackers and automated decisions

- **Cookies**: the app uses none. It embeds no browser, no ad network, no third-party script.
- **Trackers and identification**: no advertising identifier and no device identifier is collected or transmitted.
- **Local storage**: the app writes data into its private storage (encrypted keys, preferences, history if enabled). This storage is **strictly necessary for the service you request** and therefore requires no prior consent under Article 82 of the French Data Protection Act.
- **Automated decision-making and profiling**: none (Art. 22 GDPR). No decision about you is taken by an algorithm.

---

## 13. No telemetry, no advertising, no resale

- **No analytics.** The publisher does not know how many people use the app, or how.
- **No automatic crash reporting.** A malfunction is only known if you report it.
- **No advertising**, no data sharing for advertising purposes.
- **No sale or rental of data.**
- Download and star counts visible on GitHub are **aggregate figures provided by the platform** to the publisher; they contain no personal data about you.

---

## 14. Changes to this policy

Any change is published in the project repository, with a version and date increment at the top of this document and an entry in the history below.

A **substantial** change (new provider, new processing, change of legal basis, transfer to an additional country) will be flagged in the app's release notes, so that you can see it before updating.

If you disagree with a revised version, you can uninstall the app: as no data is held by the publisher, there is nothing to delete remotely.

---

## 15. Complaints

If you believe your data is processed in breach of the GDPR, you may complain to the publisher (**jcversa16@gmail.com**) and then, without waiting, to the competent supervisory authority.

**In France:**

> Commission nationale de l'informatique et des libertés (CNIL)
> 3 place de Fontenoy, TSA 80715, 75334 Paris Cedex 07, France
> Online complaint portal: `cnil.fr`
> Telephone: +33 1 53 73 22 22

If you live in another EU Member State, you may lodge a complaint with the supervisory authority of your habitual residence or place of work.

---

## 16. Version history

| Version | Date | Change |
|:--|:--|:--|
| 1.0 | 20 September 2026 | Document created. Seven processing activities described (sending text to the AI provider, update check, API keys, optional local history, local statistics, email correspondence, permissions), legal bases, retention, recipients, transfers outside the EU, rights and security. |
