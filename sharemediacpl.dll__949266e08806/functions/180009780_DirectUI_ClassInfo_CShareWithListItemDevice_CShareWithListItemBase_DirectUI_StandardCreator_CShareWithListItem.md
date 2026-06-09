# DirectUI::ClassInfo<CShareWithListItemDevice,CShareWithListItemBase,DirectUI::StandardCreator<CShareWithListItemDevice>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180009780`
- end: `0x180009791`
- name: `?CreateInstance@?$ClassInfo@VCShareWithListItemDevice@@VCShareWithListItemBase@@V?$StandardCreator@VCShareWithListItemDevice@@@DirectUI@@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800092d4`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CShareWithListItemDevice,CShareWithListItemBase,DirectUI::StandardCreator<CShareWithListItemDevice>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        struct DirectUI::Element **a4)
{
  return CShareWithListItemDevice::Create(a2, a3, a4);
}

```

## disassembly

```asm
0x180009780  mov     rax, r8
0x180009783  mov     rcx, rdx; struct DirectUI::Element *
0x180009786  mov     rdx, rax; unsigned int *
0x180009789  mov     r8, r9; struct DirectUI::Element **
0x18000978c  jmp     ?Create@CShareWithListItemDevice@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z; CShareWithListItemDevice::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
```
