# __delayLoadHelper2

- ea: `0x180017fd0`
- end: `0x180018006`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019f0`
- `0x180001b77`
- `0x180001c02`
- `0x180001d65`
- `0x180001e14`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180017ffb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180017ffb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180017fda`

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
0x180017fd0  sub     rsp, 38h
0x180017fd4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180017fda  mov     r9, cs:__imp_DelayLoadFailureHook
0x180017fe1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180017fe8  mov     [rsp+38h+var_10], eax
0x180017fec  mov     [rsp+38h+var_18], rdx
0x180017ff1  mov     rdx, rcx
0x180017ff4  lea     rcx, __ImageBase
0x180017ffb  call    cs:__imp_ResolveDelayLoadedAPI
0x180018001  add     rsp, 38h
0x180018005  retn
```
