# theatrical_supertitler
Script for producing powerpoint for theatrical supertitles .

# Warnings

This is based largely on python-pptx. It unfortunately suffers from the limitations imposed on it by that library.

1. It cannot change the background at a slide level, so it creates a white slide with white text which has to be globally transformed to black in order for the writing to show up.

2. It has no real understanding of what is or is not text that is relevant. There are ways to force it to skip certain lines, but that's only based on what the line starts with.

# How it works.

1. Create your script in the form of a text file. Usually this is of the following form:

```
ROMEO:
But soft, what light through yonder window breaks,
Ah, but it is a cyborg with heat vision!
```

Where usually there is a line break between different characters talking.

The script breaks slides on every blank line. It also breaks slides when a character has talked for more than LINES_PER_SLIDE, so it splits things into small, easily digestible sections.

It also ignores lines that start with an open parentheses.

2. Set anything you need to set.

This could include SKIP_STARTS, which skips lines that start with SKIP_STARTS.

3. Set up your virtualenv.

Use the requirements.txt, it should have what you need.

4. Run the script.

```python supertitler.py [INFILE] [OUTFILE]```

The INFILE is the script that you're putting in. The OUTFILE is the final powerpoint destination.
