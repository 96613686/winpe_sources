# __delayLoadHelper2

- ea: `0x14000b0a0`
- end: `0x14000b0d6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1400022ba`
- `0x140002369`
- `0x14000247e`
- `0x140002509`
- `0x1400025ca`
- `0x140002667`
- `0x140002728`
- `0x1400027e9`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000b0cb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000b0cb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000b0aa`

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
0x14000b0a0  sub     rsp, 38h
0x14000b0a4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000b0aa  mov     r9, cs:__imp_DelayLoadFailureHook
0x14000b0b1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x14000b0b8  mov     [rsp+38h+var_10], eax
0x14000b0bc  mov     [rsp+38h+var_18], rdx
0x14000b0c1  mov     rdx, rcx
0x14000b0c4  lea     rcx, __ImageBase
0x14000b0cb  call    cs:__imp_ResolveDelayLoadedAPI
0x14000b0d1  add     rsp, 38h
0x14000b0d5  retn
```
