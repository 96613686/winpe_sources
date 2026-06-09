# __delayLoadHelper2

- ea: `0x180003b30`
- end: `0x180003b66`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001930`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003b5b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003b5b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180003b3a`

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
0x180003b30  sub     rsp, 38h
0x180003b34  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180003b3a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003b41  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003b48  mov     [rsp+38h+var_10], eax
0x180003b4c  mov     [rsp+38h+var_18], rdx
0x180003b51  mov     rdx, rcx
0x180003b54  lea     rcx, __ImageBase
0x180003b5b  call    cs:__imp_ResolveDelayLoadedAPI
0x180003b61  add     rsp, 38h
0x180003b65  retn
```
