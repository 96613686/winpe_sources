# __delayLoadHelper2

- ea: `0x18001be40`
- end: `0x18001be76`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000221f`
- `0x18000234c`
- `0x1800023fb`
- `0x180002498`
- `0x180002559`
- `0x180002976`
- `0x180002a13`
- `0x180002b16`

## import_xrefs

- `KERNEL32!ResolveDelayLoadedAPI` at `0x18001be6b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18001be6b`
- `KERNEL32!DelayLoadFailureHook` at `0x18001be4a`

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
0x18001be40  sub     rsp, 38h
0x18001be44  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18001be4a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18001be51  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001be58  mov     [rsp+38h+var_10], eax
0x18001be5c  mov     [rsp+38h+var_18], rdx
0x18001be61  mov     rdx, rcx
0x18001be64  lea     rcx, __ImageBase
0x18001be6b  call    cs:__imp_ResolveDelayLoadedAPI
0x18001be71  add     rsp, 38h
0x18001be75  retn
```
