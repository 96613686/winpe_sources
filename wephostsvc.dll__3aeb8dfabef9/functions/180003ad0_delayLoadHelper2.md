# __delayLoadHelper2

- ea: `0x180003ad0`
- end: `0x180003b06`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001970`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003afb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180003afb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180003ada`

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
0x180003ad0  sub     rsp, 38h
0x180003ad4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180003ada  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003ae1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003ae8  mov     [rsp+38h+var_10], eax
0x180003aec  mov     [rsp+38h+var_18], rdx
0x180003af1  mov     rdx, rcx
0x180003af4  lea     rcx, __ImageBase
0x180003afb  call    cs:__imp_ResolveDelayLoadedAPI
0x180003b01  add     rsp, 38h
0x180003b05  retn
```
