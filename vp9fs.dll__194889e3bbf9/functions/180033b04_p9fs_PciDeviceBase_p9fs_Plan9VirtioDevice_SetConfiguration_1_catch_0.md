# _p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::SetConfiguration_::_1_::catch$0

- ea: `0x180033b04`
- end: `0x180033b3a`
- name: `_p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::SetConfiguration_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002751c`

## string_xrefs

- `0x180033b15`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::SetConfiguration_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x2F,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180033b04  mov     [rsp+arg_8], rdx
0x180033b09  push    rbp
0x180033b0a  sub     rsp, 20h
0x180033b0e  mov     rbp, rdx
0x180033b11  mov     rcx, [rbp+28h]; this
0x180033b15  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180033b1c  mov     edx, 2Fh ; '/'; void *
0x180033b21  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180033b26  mov     [rbp+38h], eax
0x180033b29  mov     rax, 0
0x180033b33  add     rsp, 20h
0x180033b37  pop     rbp
0x180033b38  retn
```
