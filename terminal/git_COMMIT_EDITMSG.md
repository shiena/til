WindowsからSambaなどでLinuxのGitリポジトリにコミットしたときに以下のエラーになった場合の対処方法

```
fatal: could not open '.git/COMMIT_EDITMSG': Permission denied
```

1. ownerの見直し
1. パーミッションの見直し
644の場合は664に変更すると解消した644の場合は664に変更すると解消した644の場合は664に変更すると解消した644の場合は664に変更すると解消した644の場合は664に変更すると解消した644の場合は664
に変更すると解消した
