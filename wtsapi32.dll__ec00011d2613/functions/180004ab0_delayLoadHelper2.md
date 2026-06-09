# __delayLoadHelper2

- ea: `0x180004ab0`
- end: `0x180004ae6`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180007200`
- `0x180007375`
- `0x180007400`
- `0x18000749d`
- `0x18000754c`
- `0x1800075e9`
- `0x1800078ea`
- `0x180007975`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180004adb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180004adb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180004aba`

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
0x180004ab0  sub     rsp, 38h
0x180004ab4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180004aba  mov     r9, cs:__imp_DelayLoadFailureHook
0x180004ac1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180004ac8  mov     [rsp+38h+var_10], eax
0x180004acc  mov     [rsp+38h+var_18], rdx
0x180004ad1  mov     rdx, rcx
0x180004ad4  lea     rcx, __ImageBase
0x180004adb  call    cs:__imp_ResolveDelayLoadedAPI
0x180004ae1  add     rsp, 38h
0x180004ae5  retn
```
