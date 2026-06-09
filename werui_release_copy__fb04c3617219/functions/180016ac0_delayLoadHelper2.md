# __delayLoadHelper2

- ea: `0x180016ac0`
- end: `0x180016af6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002440`
- `0x180002532`
- `0x1800026d2`
- `0x18000275d`
- `0x1800027e8`
- `0x1800028bb`
- `0x1800029c4`
- `0x180002ada`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x180016aca`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x180016aeb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x180016aeb`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(__int64 a1, __int64 a2)
{
  return ResolveDelayLoadedAPI(
           &_ImageBase,
           a1,
           _pfnDefaultDliFailureHook2,
           DelayLoadFailureHook,
           a2,
           _ResolveDelayLoadedAPIFlags);
}

```

## disassembly

```asm
0x180016ac0  sub     rsp, 38h
0x180016ac4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180016aca  mov     r9, cs:__imp_DelayLoadFailureHook
0x180016ad1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180016ad8  mov     [rsp+38h+var_10], eax
0x180016adc  mov     [rsp+38h+var_18], rdx
0x180016ae1  mov     rdx, rcx
0x180016ae4  lea     rcx, __ImageBase
0x180016aeb  call    cs:__imp_ResolveDelayLoadedAPI
0x180016af1  add     rsp, 38h
0x180016af5  retn
```
