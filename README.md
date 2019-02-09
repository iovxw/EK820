# EK820
```patch
--- a/usr/share/X11/xkb/rules/evdev
+++ b/usr/share/X11/xkb/rules/evdev
@@ -1134,6 +1134,7 @@
   lv5:lwin_switch_lock_cancel     =       +level5(lwin_switch_lock_cancel)
   lv5:rwin_switch_lock_cancel     =       +level5(rwin_switch_lock_cancel)
   parens:swap_brackets   =   +parens(swap_brackets)
+  ek820_68 = +ek820_68


 ! option	=	compat
--- a/usr/share/X11/xkb/symbols/ek820_68
+++ b/usr/share/X11/xkb/symbols/ek820_68
@@ -0,0 +1,8 @@
+default hidden partial modifier_keys
+xkb_symbols "ek820_68" {
+    key <CAPS> {
+        symbols = [ Escape, Caps_Lock ],
+        actions = [ NoAction(), LockMods(modifiers=Lock) ]
+    };
+    key <ESC> { [ grave, asciitilde ] };
+};
```
`gsettings set org.gnome.desktop.input-sources xkb-options "['ek820_68']"`
