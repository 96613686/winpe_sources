# __delayLoadHelper2

- ea: `0x180002eb0`
- end: `0x180002ee6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c30`
- `0x180003d4b`
- `0x180003e30`
- `0x180003f27`
- `0x180003fa0`
- `0x18000403d`
- `0x180004134`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x180002eba`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x180002edb`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x180002edb`

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
0x180002eb0  sub     rsp, 38h
0x180002eb4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180002eba  mov     r9, cs:__imp_DelayLoadFailureHook
0x180002ec1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180002ec8  mov     [rsp+38h+var_10], eax
0x180002ecc  mov     [rsp+38h+var_18], rdx
0x180002ed1  mov     rdx, rcx
0x180002ed4  lea     rcx, __ImageBase
0x180002edb  call    cs:__imp_ResolveDelayLoadedAPI
0x180002ee1  add     rsp, 38h
0x180002ee5  retn
```
