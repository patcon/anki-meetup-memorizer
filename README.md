# Meetup RSVP Memorizer

This is a command line tool for helping Meetup.com event organizers
remember the names and faces of attendees, taken from their public profiles.

![Screenshot of Anki Desktop and AnkiDroid](https://imgur.com/h471IJt.png)

**Meetup.com** is an online platform for finding and organizing
in-person communities of practice.

**Anki** is a popular flashcard tool that helps people memorize things.
It is available on desktop and mobile.

Use this tool to generate an Anki flashcard deck for memorizing the
names and faces of your Meetup attendees.

## Technologies Used

- **Python.** A programming language common in scripting.
- [**Click.**][click] A Python library for writing simple command-line
  tools.

## Requirements

* Python 3.6+
* [`pipenv`](https://pipenv.readthedocs.io/en/latest/#install-pipenv-today) (optional)

## Usage

```
$ cd path/to/project
$ pip install git+https://github.com/civictechto/anki-meetup-memorizer#egg=anki-meetup-memorizer

# For usage instructions
$ anki-meetup-memorizer --help
Usage: anki-meetup-memorizer [OPTIONS] MEETUP_EVENT_URL

Options:
  --meetup-api-key <string>  API key for any unprivileged site user
                             [required]
  -y, --yes                  Skip confirmation prompts
  -v, --verbose              Show output for each action
  -d, --debug                Show full debug output
  --noop                     Skip API calls that change/destroy data
  -h, --help                 Show this message and exit.

```

You may also choose to use `pipenv`, if you have it installed. It
allows for better isolation of Python projects.

```
# To use `pipenv` and an isolated project environment via `pipenv run`:
$ pipenv install git+https://github.com/civictechto/anki-meetup-memorizer#egg=anki-meetup-memorizer
$ pipenv run anki-meetup-memorizer --help

# You can set config via a dot-env file
$ cp sample.env .env

# To generate an APKG import file
$ pipenv run anki-meetup-memorizer <meetup-event-url>
```

Your generated APKG file will now be in the `outputs/` directory.

## Development

To run the script and generate a new APKG file for
[importing](https://ankidroid.org/docs/manual.html#importing):

```
cd path/to/anki-meetup-memorizer

# Install dependencies
git submodule update --init
pipenv install
```

## Notes

* Each meetup event gets it's own card deck.
* We include attendees who RSVP'd both Yes and No, as both forms of
  action are indicative of an active community member.
* Members without photos are obviously not included in the deck.

<!-- Links -->
   [click]: http://click.pocoo.org/5/
