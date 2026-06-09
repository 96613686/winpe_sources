# __delayLoadHelper2

- ea: `0x180006a50`
- end: `0x180006a86`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180008c26`
- `0x180008cc3`
- `0x180008d84`
- `0x180008e0f`
- `0x180008ebe`
- `0x180008f5b`
- `0x18000900a`
- `0x1800090cb`
- `0x180009156`
- `0x1800091e1`
- `0x18000927e`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180006a7b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x180006a7b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x180006a5a`

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
0x180006a50  sub     rsp, 38h
0x180006a54  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x180006a5a  mov     r9, cs:__imp_DelayLoadFailureHook
0x180006a61  mov     r8, cs:__pfnDefaultDliFailureHook2
0x180006a68  mov     [rsp+38h+var_10], eax
0x180006a6c  mov     [rsp+38h+var_18], rdx
0x180006a71  mov     rdx, rcx
0x180006a74  lea     rcx, __ImageBase
0x180006a7b  call    cs:__imp_ResolveDelayLoadedAPI
0x180006a81  add     rsp, 38h
0x180006a85  retn
```
