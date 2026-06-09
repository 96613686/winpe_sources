# __delayLoadHelper2

- ea: `0x180001010`
- end: `0x18000104d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800013fa`
- `0x1800014da`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000103b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000103b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000101a`

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
0x180001010  sub     rsp, 38h
0x180001014  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000101a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180001021  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180001028  mov     [rsp+38h+var_10], eax
0x18000102c  mov     [rsp+38h+var_18], rdx
0x180001031  mov     rdx, rcx
0x180001034  lea     rcx, __ImageBase
0x18000103b  call    cs:__imp_ResolveDelayLoadedAPI
0x180001042  nop     dword ptr [rax+rax+00h]
0x180001047  add     rsp, 38h
0x18000104b  retn
```
