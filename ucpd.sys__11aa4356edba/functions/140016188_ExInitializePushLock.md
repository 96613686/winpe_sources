# ExInitializePushLock

- ea: `0x140016188`
- end: `0x14001618f`
- name: `ExInitializePushLock`
- size: `7`
- prototype: `void __stdcall(PULONG_PTR PushLock)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001a5c`
- `0x14000265c`
- `0x14000fcb4`
- `0x1400124c8`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140016188`

## pseudocode

```c
// attributes: thunk
void __stdcall ExInitializePushLock(PULONG_PTR PushLock)
{
  __imp_ExInitializePushLock(PushLock);
}

```

## disassembly

```asm
0x140016188  jmp     cs:__imp_ExInitializePushLock
```
