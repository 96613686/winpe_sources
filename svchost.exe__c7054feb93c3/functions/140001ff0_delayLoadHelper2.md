# __delayLoadHelper2

- ea: `0x140001ff0`
- end: `0x140002026`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140005548`
- `0x14000562a`
- `0x1400056b5`
- `0x140005764`
- `0x1400057ef`
- `0x14000593a`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000201b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000201b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x140001ffa`

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
0x140001ff0  sub     rsp, 38h
0x140001ff4  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x140001ffa  mov     r9, cs:__imp_DelayLoadFailureHook
0x140002001  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140002008  mov     [rsp+38h+var_10], eax
0x14000200c  mov     [rsp+38h+var_18], rdx
0x140002011  mov     rdx, rcx
0x140002014  lea     rcx, __ImageBase
0x14000201b  call    cs:__imp_ResolveDelayLoadedAPI
0x140002021  add     rsp, 38h
0x140002025  retn
```
