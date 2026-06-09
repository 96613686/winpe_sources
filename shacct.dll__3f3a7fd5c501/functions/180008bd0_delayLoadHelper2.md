# __delayLoadHelper2

- ea: `0x180008bd0`
- end: `0x180008c06`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cb8a`
- `0x18000cced`
- `0x18000cd8a`
- `0x18000ce4b`
- `0x18000ced6`
- `0x18000cf85`
- `0x18000d07c`
- `0x18000d107`
- `0x18000d1c8`
- `0x18000d3a9`
- `0x18000d4e8`
- `0x18000d573`
- `0x18000d622`
- `0x18000d6ad`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180008bfb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180008bfb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180008bda`

## pseudocode

```c
__int64 __fastcall _delayLoadHelper2(__int64 a1, __int64 a2)
{
  return ResolveDelayLoadedAPI(
           _ImageBase,
           a1,
           _pfnDefaultDliFailureHook2,
           DelayLoadFailureHook,
           a2,
           _ResolveDelayLoadedAPIFlags);
}

```

## disassembly

```asm
0x180008bd0  sub     rsp, 38h
0x180008bd4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180008bda  mov     r9, cs:__imp_DelayLoadFailureHook
0x180008be1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180008be8  mov     [rsp+38h+var_10], eax
0x180008bec  mov     [rsp+38h+var_18], rdx
0x180008bf1  mov     rdx, rcx
0x180008bf4  lea     rcx, __ImageBase
0x180008bfb  call    cs:__imp_ResolveDelayLoadedAPI
0x180008c01  add     rsp, 38h
0x180008c05  retn
```
