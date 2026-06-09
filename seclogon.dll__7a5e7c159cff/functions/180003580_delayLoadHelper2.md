# __delayLoadHelper2

- ea: `0x180003580`
- end: `0x1800035b6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b90`
- `0x180003c51`
- `0x180003cdc`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800035ab`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x1800035ab`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000358a`

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
0x180003580  sub     rsp, 38h
0x180003584  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000358a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180003591  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180003598  mov     [rsp+38h+var_10], eax
0x18000359c  mov     [rsp+38h+var_18], rdx
0x1800035a1  mov     rdx, rcx
0x1800035a4  lea     rcx, __ImageBase
0x1800035ab  call    cs:__imp_ResolveDelayLoadedAPI
0x1800035b1  add     rsp, 38h
0x1800035b5  retn
```
