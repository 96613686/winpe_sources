# SIPolicyStateToReadOnlyMutableState

- ea: `0x18001d064`
- end: `0x18001d068`
- name: `SIPolicyStateToReadOnlyMutableState`
- size: `4`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800492f8`

## pseudocode

```c
__int64 __fastcall SIPolicyStateToReadOnlyMutableState(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x18001d064  mov     rax, [rcx]
0x18001d067  retn
```
