# _p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::ReadConfigSpace_::_1_::catch$0

- ea: `0x180033a8c`
- end: `0x180033ac2`
- name: `_p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::ReadConfigSpace_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002751c`

## string_xrefs

- `0x180033a9d`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::ReadConfigSpace_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x52,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180033a8c  mov     [rsp+arg_8], rdx
0x180033a91  push    rbp
0x180033a92  sub     rsp, 30h
0x180033a96  mov     rbp, rdx
0x180033a99  mov     rcx, [rbp+68h]; this
0x180033a9d  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180033aa4  mov     edx, 52h ; 'R'; void *
0x180033aa9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180033aae  mov     [rbp+38h], eax
0x180033ab1  mov     rax, 0
0x180033abb  add     rsp, 30h
0x180033abf  pop     rbp
0x180033ac0  retn
```
