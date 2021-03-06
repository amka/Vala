# Классы не наследующие Object

Классы не наследующие от GLib.Object являются специальными. Они получаются напрямую из системы типов GLib, поэтому они намного легковеснее. Последние версии Vala позволяют реализовывать интерфейсы, сигналы и свойства на этих классах.

Одно очевидное применение данного вида классов состоит в создании биндингов к GLib, т.к. GLib более низкоуровневый чем GObject, большинство биндингов используют именно данный тип классов. Так же, из-за легковесности такие классы можно использовать во многих ситуациях на практике \(напр. в самом компиляторе Vala\). Однако детальное описание таких классов выходит за рамки данного руководства. Нужно знать, что эти классы основательно отличаются от структур.

