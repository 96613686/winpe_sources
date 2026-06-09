# DirectUI::ClassInfo<CShareWithListItemUsers,CShareWithListItemBase,DirectUI::StandardCreator<CShareWithListItemUsers>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800097a0`
- end: `0x1800097b1`
- name: `?CreateInstance@?$ClassInfo@VCShareWithListItemUsers@@VCShareWithListItemBase@@V?$StandardCreator@VCShareWithListItemUsers@@@DirectUI@@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009460`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CShareWithListItemUsers,CShareWithListItemBase,DirectUI::StandardCreator<CShareWithListItemUsers>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        struct DirectUI::Element **a4)
{
  return CShareWithListItemUsers::Create(a2, a3, a4);
}

```

## disassembly

```asm
0x1800097a0  mov     rax, r8
0x1800097a3  mov     rcx, rdx; struct DirectUI::Element *
0x1800097a6  mov     rdx, rax; unsigned int *
0x1800097a9  mov     r8, r9; struct DirectUI::Element **
0x1800097ac  jmp     ?Create@CShareWithListItemUsers@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z; CShareWithListItemUsers::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
```
