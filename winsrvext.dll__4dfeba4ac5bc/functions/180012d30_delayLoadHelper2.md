# __delayLoadHelper2

- ea: `0x180012d30`
- end: `0x180012d6d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000146f`
- `0x180001a52`
- `0x180001af5`
- `0x180001b92`
- `0x180001c1d`
- `0x180001dd6`
- `0x180001eb6`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180012d5b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180012d5b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180012d3a`

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
0x180012d30  sub     rsp, 38h
0x180012d34  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180012d3a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180012d41  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180012d48  mov     [rsp+38h+var_10], eax
0x180012d4c  mov     [rsp+38h+var_18], rdx
0x180012d51  mov     rdx, rcx
0x180012d54  lea     rcx, __ImageBase
0x180012d5b  call    cs:__imp_ResolveDelayLoadedAPI
0x180012d62  nop     dword ptr [rax+rax+00h]
0x180012d67  add     rsp, 38h
0x180012d6b  retn
```
