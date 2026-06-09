# __delayLoadHelper2

- ea: `0x180018770`
- end: `0x1800187a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800109c6`
- `0x180010ab2`
- `0x180010b61`
- `0x180010bec`
- `0x180010cde`
- `0x180010d69`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001879b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18001879b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001877a`

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
0x180018770  sub     rsp, 38h
0x180018774  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001877a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180018781  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180018788  mov     [rsp+38h+var_10], eax
0x18001878c  mov     [rsp+38h+var_18], rdx
0x180018791  mov     rdx, rcx
0x180018794  lea     rcx, __ImageBase
0x18001879b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800187a1  add     rsp, 38h
0x1800187a5  retn
```
