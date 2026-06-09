# _NLG_Notify

- ea: `0x1800154a0`
- end: `0x1800154b8`
- name: `_NLG_Notify`
- size: `24`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180011c44`
- `0x180015520`
- `0x180015570`
- `0x1800155a0`
- `0x1800155d0`

## callees

- `0x1800154c0`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x1800154a0  mov     [rsp+arg_0], rcx
0x1800154a5  mov     [rsp+arg_10], rdx
0x1800154aa  mov     [rsp+arg_8], r8d
0x1800154af  mov     r9, 19930520h
0x1800154b6  jmp     short __NLG_Dispatch2
```
