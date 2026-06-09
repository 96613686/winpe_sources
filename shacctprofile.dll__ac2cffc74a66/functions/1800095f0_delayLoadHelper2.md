# __delayLoadHelper2

- ea: `0x1800095f0`
- end: `0x180009626`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002bea`
- `0x180002c99`
- `0x180002d36`
- `0x180002dd3`
- `0x180002e70`
- `0x180002f31`
- `0x180002ff2`
- `0x1800030e9`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000961b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000961b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800095fa`

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
0x1800095f0  sub     rsp, 38h
0x1800095f4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800095fa  mov     r9, cs:__imp_DelayLoadFailureHook
0x180009601  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180009608  mov     [rsp+38h+var_10], eax
0x18000960c  mov     [rsp+38h+var_18], rdx
0x180009611  mov     rdx, rcx
0x180009614  lea     rcx, __ImageBase
0x18000961b  call    cs:__imp_ResolveDelayLoadedAPI
0x180009621  add     rsp, 38h
0x180009625  retn
```
