# __delayLoadHelper2

- ea: `0x140006020`
- end: `0x140006056`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140007e30`
- `0x140008a07`
- `0x140008a92`
- `0x140008be3`
- `0x140008cc8`
- `0x140008d65`
- `0x140008e38`
- `0x140008ec3`
- `0x140008ffe`
- `0x14000909b`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000604b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000604b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000602a`

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
0x140006020  sub     rsp, 38h
0x140006024  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000602a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140006031  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140006038  mov     [rsp+38h+var_10], eax
0x14000603c  mov     [rsp+38h+var_18], rdx
0x140006041  mov     rdx, rcx
0x140006044  lea     rcx, __ImageBase
0x14000604b  call    cs:__imp_ResolveDelayLoadedAPI
0x140006051  add     rsp, 38h
0x140006055  retn
```
