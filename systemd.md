# systemd/systemd

A single drive-by commit when I noticed a docs issue, I believe when I was playing around with [bedrock-bootstrap](https://github.com/sgtCoDFish/bedrock-bootstrap).

[Link](https://github.com/systemd/systemd/commit/8bc943b47256fd6aeb4c2aa7a8fb81d59b01e7f4)

## Commit Diff

```diff
commit 8bc943b47256fd6aeb4c2aa7a8fb81d59b01e7f4
Author: Ashley Davis <...>
Date:   Tue Jan 28 15:47:25 2020 +0000

    fix erroneous "`" in boot loader spec

diff --git a/docs/BOOT_LOADER_SPECIFICATION.md b/docs/BOOT_LOADER_SPECIFICATION.md
index 6df522c9e7..13ceaa8482 100644
--- a/docs/BOOT_LOADER_SPECIFICATION.md
+++ b/docs/BOOT_LOADER_SPECIFICATION.md
@@ -60,7 +60,7 @@ Everything described below is located on a placeholder file system `$BOOT`. The
   * Otherwise, if the OS is installed on a disk with MBR disk label, a new partition with MBR type id of 0xEA shall be created, of a suitable size (let's say 500MB), and it should be used as `$BOOT`.
 * On disks with GPT disk labels
   * If the OS is installed on a disk with GPT disk label, and a partition with the GPT type GUID of `bc13c2ff-59e6-4262-a352-b275fd6f7172` already exists, it should be used as `$BOOT`.
-  * Otherwise, if the OS is installed on a disk with GPT disk label, and an ESP partition (i.e. with the GPT type UID of `c12a7328-f81f-11d2-ba4b-00a0c93ec93b`) already exists and is large enough (let's say 250MB`) and otherwise qualifies, it should be used as `$BOOT`.
+  * Otherwise, if the OS is installed on a disk with GPT disk label, and an ESP partition (i.e. with the GPT type UID of `c12a7328-f81f-11d2-ba4b-00a0c93ec93b`) already exists and is large enough (let's say 250MB) and otherwise qualifies, it should be used as `$BOOT`.
   * Otherwise, if the OS is installed on a disk with GPT disk label, and if the ESP partition already exists but is too small, a new suitably sized (let's say 500MB) partition with GPT type GUID of `bc13c2ff-59e6-4262-a352-b275fd6f7172` shall be created and it should be used as `$BOOT`.
   * Otherwise, if the OS is installed on a disk with GPT disk label, and no ESP partition exists yet, a new suitably sized (let's say 500MB) ESP should be created and should be used as `$BOOT`.
```
