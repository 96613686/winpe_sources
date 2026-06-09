# __delayLoadHelper2

- ea: `0x180009770`
- end: `0x1800097a6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c275`
- `0x18000c300`
- `0x18000c4e1`
- `0x18000c56c`
- `0x18000c65e`
- `0x18000c7af`
- `0x18000c83a`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000979b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000979b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000977a`

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
0x180009770  sub     rsp, 38h
0x180009774  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000977a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180009781  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180009788  mov     [rsp+38h+var_10], eax
0x18000978c  mov     [rsp+38h+var_18], rdx
0x180009791  mov     rdx, rcx
0x180009794  lea     rcx, __ImageBase
0x18000979b  call    cs:__imp_ResolveDelayLoadedAPI
0x1800097a1  add     rsp, 38h
0x1800097a5  retn
```
