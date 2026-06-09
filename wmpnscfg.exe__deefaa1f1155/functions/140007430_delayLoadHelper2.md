# __delayLoadHelper2

- ea: `0x140007430`
- end: `0x140007466`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ec4`
- `0x140001f73`
- `0x140002010`
- `0x1400020f5`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x14000745b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x14000745b`
- `KERNEL32!DelayLoadFailureHook` at `0x14000743a`

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
0x140007430  sub     rsp, 38h
0x140007434  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000743a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140007441  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140007448  mov     [rsp+38h+var_10], eax
0x14000744c  mov     [rsp+38h+var_18], rdx
0x140007451  mov     rdx, rcx
0x140007454  lea     rcx, __ImageBase
0x14000745b  call    cs:__imp_ResolveDelayLoadedAPI
0x140007461  add     rsp, 38h
0x140007465  retn
```
