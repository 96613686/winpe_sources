# __RTDynamicCast_0

- ea: `0x180015c6d`
- end: `0x180015c73`
- name: `__RTDynamicCast_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ec90`
- `0x18000ee00`
- `0x18000f8e0`
- `0x18000f9d0`
- `0x180011150`

## import_xrefs

- `msvcrt!__RTDynamicCast` at `0x180015c6d`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _RTDynamicCast_0(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  return __RTDynamicCast(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180015c6d  jmp     cs:__imp___RTDynamicCast
```
