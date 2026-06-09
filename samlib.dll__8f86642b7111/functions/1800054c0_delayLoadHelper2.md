# __delayLoadHelper2

- ea: `0x1800054c0`
- end: `0x1800054f6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006f72`
- `0x180006ffd`
- `0x1800070f4`
- `0x180007257`
- `0x18000733c`
- `0x1800073fd`
- `0x1800074be`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800054eb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800054eb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800054ca`

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
0x1800054c0  sub     rsp, 38h
0x1800054c4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800054ca  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800054d1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800054d8  mov     [rsp+38h+var_10], eax
0x1800054dc  mov     [rsp+38h+var_18], rdx
0x1800054e1  mov     rdx, rcx
0x1800054e4  lea     rcx, __ImageBase
0x1800054eb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800054f1  add     rsp, 38h
0x1800054f5  retn
```
