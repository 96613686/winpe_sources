# _p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::WriteConfigSpace_::_1_::catch$0

- ea: `0x180033b7c`
- end: `0x180033bb2`
- name: `_p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::WriteConfigSpace_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002751c`

## string_xrefs

- `0x180033b8d`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase_p9fs::Plan9VirtioDevice_::WriteConfigSpace_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x59,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180033b7c  mov     [rsp+arg_8], rdx
0x180033b81  push    rbp
0x180033b82  sub     rsp, 30h
0x180033b86  mov     rbp, rdx
0x180033b89  mov     rcx, [rbp+58h]; this
0x180033b8d  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180033b94  mov     edx, 59h ; 'Y'; void *
0x180033b99  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180033b9e  mov     [rbp+38h], eax
0x180033ba1  mov     rax, 0
0x180033bab  add     rsp, 30h
0x180033baf  pop     rbp
0x180033bb0  retn
```
