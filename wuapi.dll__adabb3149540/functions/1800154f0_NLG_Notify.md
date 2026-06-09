# _NLG_Notify

- ea: `0x1800154f0`
- end: `0x180015508`
- name: `_NLG_Notify`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180011c94`
- `0x180015570`
- `0x1800155c0`
- `0x1800155f0`
- `0x180015620`

## callees

- `0x180015510`

## pseudocode

```c
__int64 __fastcall NLG_Notify(__int64 a1, __int64 a2, __int64 a3)
{
  return _NLG_Dispatch2(a1, a2, a3, 429065504);
}

```

## disassembly

```asm
0x1800154f0  mov     [rsp+arg_0], rcx
0x1800154f5  mov     [rsp+arg_10], rdx
0x1800154fa  mov     [rsp+arg_8], r8d
0x1800154ff  mov     r9, 19930520h
0x180015506  jmp     short __NLG_Dispatch2
```
