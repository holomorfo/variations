# Variations
Music composition framework based on monads for theme and variations symbolic content.


Variations framework

Given a series of themes, collections of notes and durations, generate methods for variating content, creating sections and theme development toghether with form and structure.

## Sample API expectations

Given a set of themes

$$t1, t2... tn$$

Where each $t_i$ is an array containing a set of pitch clasess and a set of durations:

Tupple representation
$$[(C, 4), (D,8),...]$$

Separate arrays representation
$$[[C, D], [4,8], ...]$$

Each tupple representation is associated to a Scale, meaning they are degrees, this can be the chromatic scale, in which case all the notes are present.

```
t1.durations
t1.pitches
t1.harmony

t1.develop(n)
t1.permutation
```

All methods of theme should be reversible, we should have some kind of algebraic structure to give it consistance.

### Instruments

Each theme/motif will be associated with a voice or instrument, that is the instance that is running through the notes on a given time.

```
i = Instrument("viola")
i.theme(t1)

t1.permute()
// Then the instrument will respond


```

Each instrument can have a range according to its limits. In this case, even if the theme is in another octave, then the instrument will adapt the notes to a range that are accessible to its constraints

There can be many instruments associated to the same theme. There should be an option so that different instruments have different ways of playing the same theme if needed. Maybe they can share the harmony, but each instrument will have instructions on what to do or how to play.