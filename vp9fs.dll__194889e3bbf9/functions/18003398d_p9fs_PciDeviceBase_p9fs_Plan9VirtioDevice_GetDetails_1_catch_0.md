# _p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::GetDetails_::_1_::catch$0

- ea: `0x18003398d`
- end: `0x1800339c3`
- name: `_p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::GetDetails_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002751c`

## string_xrefs

- `0x18003399e`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::GetDetails_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x3D,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003398d  mov     [rsp+arg_8], rdx
0x180033992  push    rbp
0x180033993  sub     rsp, 20h
0x180033997  mov     rbp, rdx
0x18003399a  mov     rcx, [rbp+38h]; this
0x18003399e  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x1800339a5  mov     edx, 3Dh ; '='; void *
0x1800339aa  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800339af  mov     [rbp+20h], eax
0x1800339b2  mov     rax, 0
0x1800339bc  add     rsp, 20h
0x1800339c0  pop     rbp
0x1800339c1  retn
```
