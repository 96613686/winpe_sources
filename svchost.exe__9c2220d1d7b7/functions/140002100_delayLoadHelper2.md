# __delayLoadHelper2

- ea: `0x140002100`
- end: `0x14000213d`
- name: `__delayLoadHelper2`
- size: `61`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140005928`
- `0x140005a0a`
- `0x140005a95`
- `0x140005b44`
- `0x140005bcf`
- `0x140005d1a`

## import_xrefs

- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000212b`
- `api-ms-win-core-delayload-l1-1-1!ResolveDelayLoadedAPI` at `0x14000212b`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x14000210a`

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
0x140002100  sub     rsp, 38h
0x140002104  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x14000210a  mov     r9, cs:__imp_DelayLoadFailureHook
0x140002111  mov     r8, cs:__pfnDefaultDliFailureHook2
0x140002118  mov     [rsp+38h+var_10], eax
0x14000211c  mov     [rsp+38h+var_18], rdx
0x140002121  mov     rdx, rcx
0x140002124  lea     rcx, __ImageBase
0x14000212b  call    cs:__imp_ResolveDelayLoadedAPI
0x140002132  nop     dword ptr [rax+rax+00h]
0x140002137  add     rsp, 38h
0x14000213b  retn
```
