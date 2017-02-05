# Meetup RSVP Memorizer

This is a quick little script for helping Meetup.com event organizers
remember the names and faces of attendees, taken from their public profiles.

![Screenshot of Anki Desktop and AnkiDroid](https://imgur.com/h471IJt.png)

**Meetup.com** is an online platform for finding and organizing
in-person communities of practice.

**Anki** is a popular flashcard tool that helps people memorize things.
It is available on desktop and mobile.

Use this script to generate an Anki flashcard deck for memorizing the
names and faces of your Meetup attendees.

## Requirements

* `make`
* Python

## Usage

To run the script and generate a new APKG file for
[importing](https://ankidroid.org/docs/manual.html#importing):

```
# Get your MEETUP_API_KEY here:
# https://secure.meetup.com/meetup_api/key/
export MEETUP_API_KEY=xxxxxxxxx

# Find the <meetup-event-id> in the event URL
make apkg <meetup-event-id>
```
