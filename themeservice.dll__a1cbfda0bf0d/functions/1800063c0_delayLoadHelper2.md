# __delayLoadHelper2

- ea: `0x1800063c0`
- end: `0x1800063f6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007e20`
- `0x180007eab`
- `0x180007f9e`
- `0x18000804d`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800063eb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800063eb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x1800063ca`

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
0x1800063c0  sub     rsp, 38h
0x1800063c4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x1800063ca  mov     r9, cs:__imp_DelayLoadFailureHook
0x1800063d1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x1800063d8  mov     [rsp+38h+var_10], eax
0x1800063dc  mov     [rsp+38h+var_18], rdx
0x1800063e1  mov     rdx, rcx
0x1800063e4  lea     rcx, __ImageBase
0x1800063eb  call    cs:__imp_ResolveDelayLoadedAPI
0x1800063f1  add     rsp, 38h
0x1800063f5  retn
```
