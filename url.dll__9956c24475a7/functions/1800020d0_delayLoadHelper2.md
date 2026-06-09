# __delayLoadHelper2

- ea: `0x1800020d0`
- end: `0x18000210d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018e0`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800020fb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x1800020fb`
- `KERNEL32!DelayLoadFailureHook` at `0x1800020da`

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
0x1800020d0  sub     rsp, 38h
0x1800020d4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800020da  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800020e1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800020e8  mov     [rsp+38h+var_10], eax
0x1800020ec  mov     [rsp+38h+var_18], rdx
0x1800020f1  mov     rdx, rcx
0x1800020f4  lea     rcx, __ImageBase
0x1800020fb  call    cs:__imp_ResolveDelayLoadedAPI
0x180002102  nop     dword ptr [rax+rax+00h]
0x180002107  add     rsp, 38h
0x18000210b  retn
```
