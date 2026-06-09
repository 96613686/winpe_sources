# __delayLoadHelper2

- ea: `0x18000b9e0`
- end: `0x18000ba16`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d46`
- `0x180001e07`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000ba0b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000ba0b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000b9ea`

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
0x18000b9e0  sub     rsp, 38h
0x18000b9e4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000b9ea  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000b9f1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000b9f8  mov     [rsp+38h+var_10], eax
0x18000b9fc  mov     [rsp+38h+var_18], rdx
0x18000ba01  mov     rdx, rcx
0x18000ba04  lea     rcx, __ImageBase
0x18000ba0b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000ba11  add     rsp, 38h
0x18000ba15  retn
```
