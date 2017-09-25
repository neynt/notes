## autobags

autobag INTO "Loot3", "Loot2", "Loot1" where (TYPE IS "magic") OR (TYPE IS "armor") OR (TYPE IS "weapon") CALL RULE "Loot"

autobag INTO "drop item" where (name LIKE "rock") OR (name LIKE "bit of fur") OR (name LIKE "giant cloak of thieving") OR (name LIKE "chainmail") AND (NOT name LIKE "mithril chainmail") OR (name LIKE "bolt") AND (NOT name LIKE "silver bolt") OR (name LIKE "platemail") OR (name LIKE "sling") OR (name LIKE "candle") OR (name LIKE "torch") OR (name LIKE "ring mail") OR (name LIKE "splint mail") OR (name LIKE "book")  AND (NOT name LIKE "spellbook") OR (name LIKE "skull") AND (NOT name LIKE "skull key") AND (NOT name LIKE "skull shield") OR (name LIKE "bone") AND (NOT name LIKE "powdered dragon bone") AND (NOT name LIKE "bone key") CALL RULE "Trash!"
