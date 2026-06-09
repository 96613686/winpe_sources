# _p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::Initialize_::_1_::catch$5

- ea: `0x1800339db`
- end: `0x180033a11`
- name: `_p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::Initialize_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002751c`

## string_xrefs

- `0x1800339ec`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::Initialize_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x20,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800339db  mov     [rsp+arg_8], rdx
0x1800339e0  push    rbp
0x1800339e1  sub     rsp, 30h
0x1800339e5  mov     rbp, rdx
0x1800339e8  mov     rcx, [rbp+58h]; this
0x1800339ec  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x1800339f3  mov     edx, 20h ; ' '; void *
0x1800339f8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800339fd  mov     [rbp+30h], eax
0x180033a00  mov     rax, 0
0x180033a0a  add     rsp, 30h
0x180033a0e  pop     rbp
0x180033a0f  retn
```
