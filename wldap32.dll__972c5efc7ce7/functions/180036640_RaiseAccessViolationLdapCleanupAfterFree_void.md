# RaiseAccessViolationLdapCleanupAfterFree(void)

- ea: `0x180036640`
- end: `0x180036647`
- name: `?RaiseAccessViolationLdapCleanupAfterFree@@YAXXZ`
- size: `7`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180024a60`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180036640`

## pseudocode

```c
// attributes: thunk
void __stdcall RaiseAccessViolationLdapCleanupAfterFree()
{
  DebugBreak();
}

```

## disassembly

```asm
0x180036640  jmp     cs:__imp_DebugBreak
```
