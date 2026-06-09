# _RNvMs0_NtCsgM4vqlL801R_6gre_os2osNtB5_13CPushLockLite16ReleaseExclusive

- ea: `0x140017480`
- end: `0x140017485`
- name: `_RNvMs0_NtCsgM4vqlL801R_6gre_os2osNtB5_13CPushLockLite16ReleaseExclusive`
- size: `5`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140013890`
- `0x1400139c0`
- `0x140013c70`

## callees

- `0x140017720`

## pseudocode

```c
// attributes: thunk
__int64 RNvMs0_NtCsgM4vqlL801R_6gre_os2osNtB5_13CPushLockLite16ReleaseExclusive()
{
  return cxxbridge1_W32ReleasePushLockExclusive();
}

```

## disassembly

```asm
0x140017480  jmp     cxxbridge1$W32ReleasePushLockExclusive
```
