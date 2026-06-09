# __delayLoadHelper2

- ea: `0x180006050`
- end: `0x180006086`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a2e2`
- `0x18000a36d`
- `0x18000a3f8`
- `0x18000a483`
- `0x18000a4fc`
- `0x18000a587`
- `0x18000a612`
- `0x18000a6d3`
- `0x18000a794`
- `0x18000a81f`
- `0x18000a928`
- `0x18000a9d7`
- `0x18000aabc`
- `0x18000ab47`
- `0x18000ad04`
- `0x18000ad8f`
- `0x18000ae50`
- `0x18000aedb`
- `0x18000af66`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000607b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000607b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000605a`

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
0x180006050  sub     rsp, 38h
0x180006054  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000605a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180006061  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180006068  mov     [rsp+38h+var_10], eax
0x18000606c  mov     [rsp+38h+var_18], rdx
0x180006071  mov     rdx, rcx
0x180006074  lea     rcx, __ImageBase
0x18000607b  call    cs:__imp_ResolveDelayLoadedAPI
0x180006081  add     rsp, 38h
0x180006085  retn
```
