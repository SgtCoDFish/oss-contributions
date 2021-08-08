# coddingtonbear/python-myfitnesspal

Fixing the library after the upstream changed; I remember this being a really positive experience.

Looking back, it looks like I messed up some whitespace 😅

[Link](https://github.com/coddingtonbear/python-myfitnesspal/commit/d0b85921ff54a55e867294b99d4be1707e73414d)

## Commit Diff

```diff
commit d0b85921ff54a55e867294b99d4be1707e73414d
Author: Ashley Davis <ashley_davis10419@hotmail.com>
Date:   Sat Jul 9 18:25:58 2016 +0100

    Handle new "macro-value" span element in entries
    
    Regular diary entries, and the goals entries, had a span element added
    to support toggling views of %age based macro goals and raw nutrition values.
    
    Adds support for getting the actual values from the table of a diary page.
    Ignores the %age values but these could be implemented in future.
    
    Also adds some span elements to the test page to ensure the changes work as
    expected.

diff --git a/myfitnesspal/client.py b/myfitnesspal/client.py
index b2c6268..0fff12d 100644
--- a/myfitnesspal/client.py
+++ b/myfitnesspal/client.py
@@ -241,7 +241,7 @@ class Client(MFPBase):
             except IndexError:
                 # This is the 'delete' button
                 continue
-            value = self._get_numeric(column.text)
+            value = self._extract_value(column)
             nutrition[nutr_name] = self._get_measurement(nutr_name, value)
 
         return nutrition
@@ -282,7 +282,9 @@ class Client(MFPBase):
                     except IndexError:
                         # This is the 'delete' button
                         continue
-                    value = self._get_numeric(column.text)
+                    
+                    value = self._extract_value(column)
+                    
                     nutrition[nutr_name] = self._get_measurement(
                         nutr_name,
                         value
@@ -304,6 +306,14 @@ class Client(MFPBase):
 
         return meals
 
+    def _extract_value(self, element):
+        if len(element.getchildren()) == 0:
+            value = self._get_numeric(element.text)
+        else:
+            value = self._get_numeric(element.xpath("span[@class='macro-value']")[0].text)
+        
+        return value
+
     def get_date(self, *args, **kwargs):
         if len(args) == 3:
             date = datetime.date(
diff --git a/tests/html/diary.html b/tests/html/diary.html
index 3d36935..e0cd9a1 100644
--- a/tests/html/diary.html
+++ b/tests/html/diary.html
@@ -209,7 +209,10 @@
                 <td>240</td>
                 
                 
-                <td>44</td>
+                <td>
+                    <span class="macro-value">44</span>
+                    <span class="macro-percentage">20</span>
+                </td>
                 
                 
                 <td>6</td>
```
