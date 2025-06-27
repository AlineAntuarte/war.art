## Version 1.9.5.5 (29-Mar-2025)

### Changes

* Robocode cannot run with Java 24, which
  implemented [JEP 486: Permanently Disable the Security Manager](https://openjdk.org/jeps/486).
    * Robocode has its own security manager built on top of Java's Security Manager, which has now been removed with
      Java 24.
    * Robocode will not start up when running Robocode on Java 24 and newer. Instead, an error message is written out
      that Robocode does not support Java 24.
    * Fixing this issue requires a big rewrite of large parts of the security mechanisms in Robocode to prevent robots
      from doing harm on the system and from cheating against other competitor robots in battles.
    * Use Java 23 or an older version of Java instead, or head over to the new platform for Robocode:
      [Robocode Tank Royale](https://github.com/robocode-dev/tank-royale).