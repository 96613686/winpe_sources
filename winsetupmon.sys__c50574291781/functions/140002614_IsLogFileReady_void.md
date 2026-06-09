# IsLogFileReady(void)

- ea: `0x140002614`
- end: `0x140002620`
- name: `?IsLogFileReady@@YAEXZ`
- size: `12`
- prototype: `unsigned __int8(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14001f6c0`
- `0x14001fe30`
- `0x14001ffd0`

## pseudocode

```c
bool IsLogFileReady(void)
{
  return FileHandle != 0;
}

```

## disassembly

```asm
0x140002614  cmp     cs:FileHandle, 0
0x14000261c  setnz   al
0x14000261f  retn
```
