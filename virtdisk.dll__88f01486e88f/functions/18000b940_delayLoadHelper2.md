# __delayLoadHelper2

- ea: `0x18000b940`
- end: `0x18000b97d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006095`
- `0x180006120`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000b96b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x18000b96b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18000b94a`

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
0x18000b940  sub     rsp, 38h
0x18000b944  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18000b94a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18000b951  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18000b958  mov     [rsp+38h+var_10], eax
0x18000b95c  mov     [rsp+38h+var_18], rdx
0x18000b961  mov     rdx, rcx
0x18000b964  lea     rcx, __ImageBase
0x18000b96b  call    cs:__imp_ResolveDelayLoadedAPI
0x18000b972  nop     dword ptr [rax+rax+00h]
0x18000b977  add     rsp, 38h
0x18000b97b  retn
```
