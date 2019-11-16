MaTris
======

This fork is modified to be usable in laboratory experiments with human subjects.

**Modifications:**
- The game runs in fullscreen mode (centered, with black bars on all four sides)
- The game starts right away. On game over, a new game starts immediately. The menu is not shown anymore.
- Sounds removed (commented out)
- Ingame events will be logged to a text file (by default `matris.log`) with time stamps
- Added command line arguments `cancelable`, `timelimit`,  `log_fpath`

   If the `--cancelable` argument is passed, <kbd>Esc</kbd> can be used to quit the game. This was default behavior in the original and has been moved to an optional command line argument in this fork to prevent subjects from accidentially aborting the experiment.
   
   If a number is passed through the `--timelimit` argument, the game will automatically terminate after that amount of seconds. If `timelimit` is not set, the game will be `cancelable` by pressing <kbd>Esc</kbd> (otherwise there would be no way to quit the game)
      
   `--log_fpath` can be used to pass a path to a log file that should be used instead of the default `matris.log`. Python will attempt to open this in `a+` mode.
   
## Example Usage

For example, to run this fork with a timelimit of 5 minutes, use:

```bash
$ pipenv run python matris.py --timelimit 300
```
