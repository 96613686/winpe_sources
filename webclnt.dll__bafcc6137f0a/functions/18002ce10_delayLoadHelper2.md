# __delayLoadHelper2

- ea: `0x18002ce10`
- end: `0x18002ce46`
- name: `__delayLoadHelper2`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a50`
- `0x180001adb`
- `0x180001c86`
- `0x180001e31`
- `0x180001ee0`
- `0x180001f8f`
- `0x180002062`
- `0x180002147`
- `0x180002208`

## import_xrefs

- `KERNEL32!DelayLoadFailureHook` at `0x18002ce1a`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18002ce3b`
- `KERNEL32!ResolveDelayLoadedAPI` at `0x18002ce3b`

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
0x18002ce10  sub     rsp, 38h
0x18002ce14  mov     eax, cs:__ResolveDelayLoadedAPIFlags
0x18002ce1a  mov     r9, cs:__imp_DelayLoadFailureHook
0x18002ce21  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18002ce28  mov     [rsp+38h+var_10], eax
0x18002ce2c  mov     [rsp+38h+var_18], rdx
0x18002ce31  mov     rdx, rcx
0x18002ce34  lea     rcx, __ImageBase
0x18002ce3b  call    cs:__imp_ResolveDelayLoadedAPI
0x18002ce41  add     rsp, 38h
0x18002ce45  retn
```
