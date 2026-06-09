# __delayLoadHelper2

- ea: `0x14000d0d0`
- end: `0x14000d106`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001cd0`
- `0x140001d6d`
- `0x140001df8`
- `0x140001f13`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000d0fb`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000d0fb`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000d0da`

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
0x14000d0d0  sub     rsp, 38h
0x14000d0d4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000d0da  mov     r9, cs:__imp_DelayLoadFailureHook
0x14000d0e1  mov     r8, cs:__pfnDefaultDliFailureHook2
0x14000d0e8  mov     [rsp+38h+var_10], eax
0x14000d0ec  mov     [rsp+38h+var_18], rdx
0x14000d0f1  mov     rdx, rcx
0x14000d0f4  lea     rcx, __ImageBase
0x14000d0fb  call    cs:__imp_ResolveDelayLoadedAPI
0x14000d101  add     rsp, 38h
0x14000d105  retn
```
