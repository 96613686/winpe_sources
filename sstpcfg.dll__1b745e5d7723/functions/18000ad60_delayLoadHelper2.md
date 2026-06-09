# __delayLoadHelper2

- ea: `0x18000ad60`
- end: `0x18000ad96`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018d0`
- `0x1800019a3`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000ad8b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000ad8b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000ad6a`

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
0x18000ad60  sub     rsp, 38h
0x18000ad64  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000ad6a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000ad71  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000ad78  mov     [rsp+38h+var_10], eax
0x18000ad7c  mov     [rsp+38h+var_18], rdx
0x18000ad81  mov     rdx, rcx
0x18000ad84  lea     rcx, __ImageBase
0x18000ad8b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000ad91  add     rsp, 38h
0x18000ad95  retn
```
