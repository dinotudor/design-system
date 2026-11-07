# UX guidelines

SkiroLiro exists to promote the exchange of knowledge and experience between people, in a useful way. These rules apply to every app in the group.

## Principles

1. **Useful first.** Every screen helps the person do or learn something. If it does not, remove it.
2. **Exchange, not just consumption.** Whenever it makes sense, give people a low-effort way to also contribute, reply, or share.
3. **Respect and warmth.** The tone is warm and direct. No guilt, no pressure, no tricks to hold attention.
4. **Multicultural by default.** No screen assumes a single language, date format, currency, or name.
5. **Easy to start.** The first useful action takes a few taps, without a long sign-up.
6. **The person is in control.** Reversible actions whenever possible, exportable data, clear privacy.

## Flows

- **First use:** show value before asking for data. Ask only for what is needed, at the moment it is needed (progressive sign-up).
- **One task per screen.** Split long flows into short steps with a progress indicator ("Step 2 of 4") and allow going back without losing input.
- **A clear main action.** One per screen, in the same place in every app.
- **Proportional confirmation.** Reversible action: do it and offer "Undo". Irreversible action: ask for confirmation and say what will be lost.
- **Automatic drafts** for anything the person writes. Never lose text.
- **Immediate response.** Every action gives feedback within 100 ms (pressed state), loads longer than 1 s show progress, and the result is confirmed in text.
- **Works on a poor connection.** Show what is saved locally, say when offline, and retry on its own when the connection returns.

## Copy and tone

- Speak like a thoughtful person: short sentences, active voice, no technical jargon, no sarcasm, no exaggeration.
- Name things by what people recognize, not by what the system does ("Your conversations", not "Manage threads").
- A button says what happens: "Publish", "Invite", "Save draft". Avoid a bare "OK" or "Submit".
- An error says what happened and how to fix it, without blaming the person: "We could not save. Check your connection and try again."
- An empty state explains what will appear and offers the first step.
- Avoid emojis as a replacement for labels. If used, they complement the text.
- Primary language of the product copy: international English, with Brazilian Portuguese as the first translation. Build all text for translation from the start (no concatenated sentences, support for plurals and different word order).

## Multicultural and inclusive

- All text lives in translation files, never hard-coded.
- Dates, times, numbers, currencies, and units follow the person's locale. Show the time zone when people are in different places.
- Names: a "what should we call you" field, without requiring a surname or a single format.
- Support longer text (German, for example) and right-to-left languages when the app reaches them.
- Images and examples with real diversity; avoid metaphors that work in only one culture.
- Neutral language and no assumptions about the person.

## Accessibility (mandatory minimum, WCAG 2.1 AA)

- Contrast: 4.5:1 for text, 3:1 for large text and controls.
- Everything works with only a keyboard (web) and with a screen reader (VoiceOver, TalkBack): logical focus order, labels on all controls, `alt` text on meaningful images.
- State never by color alone.
- Touch targets of 44 px (iOS) and 48 px (Android).
- Respects the system's enlarged text up to 200% without breaking the layout.
- Respects "reduce motion".
- Forms: visible label, error tied to its field, focus moves to the first error.
- Video and audio with captions or a transcript.

## Privacy and trust

- Say why each piece of data is requested and what happens to it.
- Privacy settings with a protective default and plain language.
- Ability to export and delete one's own data.
- No dark patterns: no hidden opt-out, no fake countdowns, no shaming people who decline.

## Collaboration and exchange (patterns for the apps)

- **Contributing is easy:** reply, comment, and suggest in one tap, with optional text.
- **Quiet recognition:** thank and highlight useful contributions, without competitive rankings or addictive scoring.
- **Shared context:** show who contributed, when, and from what (reference, source, lived experience).
- **Clear moderation:** report in two taps, visible rules, a reply to the reporter.
- **Moderate notifications:** only what the person asked for or what requires action. Digests instead of scattered alerts, with per-type control.

## Measuring whether it works

- Time to the first useful action.
- Completion of the main tasks and where people drop off.
- Errors per screen and repeated attempts.
- Spontaneous return (without depending on notifications).
- Comments and contributions per person, to check that exchange is actually happening.
- Test with real people from different backgrounds before launch: 5 people already reveal most problems.

## Checklist per screen

- [ ] What help does this screen give? Is it clear in 5 seconds?
- [ ] Is there one obvious main action?
- [ ] Empty, loading, error, and offline states defined?
- [ ] Text in translation files, short, and in active voice?
- [ ] Accessible by keyboard and screen reader?
- [ ] Can the person undo or go back without losing anything?
