# __delayLoadHelper2

- ea: `0x180003970`
- end: `0x1800039a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800089b0`
- `0x180008a4d`
- `0x180008b68`
- `0x180008bf3`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000399b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000399b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000397a`

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
0x180003970  sub     rsp, 38h
0x180003974  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000397a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003981  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003988  mov     [rsp+38h+var_10], eax
0x18000398c  mov     [rsp+38h+var_18], rdx
0x180003991  mov     rdx, rcx
0x180003994  lea     rcx, __ImageBase
0x18000399b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800039a1  add     rsp, 38h
0x1800039a5  retn
```
