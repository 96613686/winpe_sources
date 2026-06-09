# __delayLoadHelper2

- ea: `0x180001850`
- end: `0x180001886`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180002aef`
- `0x180002b86`
- `0x180002c5c`
- `0x180002d2f`
- `0x180002dba`
- `0x180002e33`
- `0x180002f2a`
- `0x180002fa3`
- `0x180003056`
- `0x180003384`
- `0x180003421`
- `0x1800034d0`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000187b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000187b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000185a`

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
0x180001850  sub     rsp, 38h
0x180001854  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000185a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180001861  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180001868  mov     [rsp+38h+var_10], eax
0x18000186c  mov     [rsp+38h+var_18], rdx
0x180001871  mov     rdx, rcx
0x180001874  lea     rcx, __ImageBase
0x18000187b  call    cs:__imp_ResolveDelayLoadedAPI
0x180001881  add     rsp, 38h
0x180001885  retn
```
