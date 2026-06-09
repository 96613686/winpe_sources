# DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x18000c080`
- end: `0x18000c08a`
- name: `?CreateInstance@?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bda4`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::HWNDHost **a4)
{
  return DirectUI::CreateAndInit<CCRichEdit,unsigned int>(3u, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c080  mov     ecx, 3
0x18000c085  jmp     ??$CreateAndInit@VCCRichEdit@@I@DirectUI@@YAJIPEAVElement@0@PEAKPEAPEAV10@@Z; DirectUI::CreateAndInit<CCRichEdit,uint>(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
```
