# CreateDUIElement(DirectUI::DUIXmlParser *,uint,ushort const *,DirectUI::Element *,DirectUI::Element *,DirectUI::Element * *)

- ea: `0x180026294`
- end: `0x18002634a`
- name: `?CreateDUIElement@@YAJPEAVDUIXmlParser@DirectUI@@IPEBGPEAVElement@2@2PEAPEAV32@@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct DirectUI::DUIXmlParser *, unsigned int, const unsigned __int16 *, struct DirectUI::Element *, struct DirectUI::Element *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180026350`

## callees

- `0x180026294`

## import_xrefs

- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180026332`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180026332`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800262e8`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800262e8`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800262bf`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800262bf`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18002631b`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18002631b`

## pseudocode

```c
__int64 __fastcall CreateDUIElement(
        struct DirectUI::DUIXmlParser *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct DirectUI::Element *a4,
        struct DirectUI::Element *a5,
        struct DirectUI::Element **a6)
{
  int Element; // ebx
  char v8; // di
  struct DirectUI::DUIXmlParser *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = a1;
  if ( a1 )
  {
    v8 = 0;
  }
  else
  {
    Element = DirectUI::DUIXmlParser::Create(&v10, 0, 0, 0, 0);
    if ( Element < 0 )
      return (unsigned int)Element;
    a1 = v10;
    v8 = 1;
  }
  Element = DirectUI::DUIXmlParser::SetXMLFromResource(a1, a2, g_hinst, &_ImageBase);
  if ( Element >= 0 )
    Element = DirectUI::DUIXmlParser::CreateElement(v10, L"main", 0, a5, 0, a6);
  if ( v8 && v10 )
    DirectUI::DUIXmlParser::Destroy(v10);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180026294  mov     rax, rsp
0x180026297  mov     [rax+10h], rbx
0x18002629b  mov     [rax+18h], rsi
0x18002629f  mov     [rax+8], rcx
0x1800262a3  push    rdi
0x1800262a4  sub     rsp, 30h
0x1800262a8  mov     esi, edx
0x1800262aa  test    rcx, rcx
0x1800262ad  jnz     short loc_1800262D5
0x1800262af  mov     [rax-18h], rcx
0x1800262b3  xor     r9d, r9d
0x1800262b6  lea     rcx, [rax+8]
0x1800262ba  xor     r8d, r8d
0x1800262bd  xor     edx, edx
0x1800262bf  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800262c5  mov     ebx, eax
0x1800262c7  test    eax, eax
0x1800262c9  js      short loc_180026338
0x1800262cb  mov     rcx, [rsp+38h+arg_0]
0x1800262d0  mov     dil, 1
0x1800262d3  jmp     short loc_1800262D8
0x1800262d5  xor     dil, dil
0x1800262d8  mov     r8, cs:g_hinst
0x1800262df  lea     r9, __ImageBase
0x1800262e6  mov     edx, esi
0x1800262e8  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800262ee  mov     ebx, eax
0x1800262f0  test    eax, eax
0x1800262f2  js      short loc_180026323
0x1800262f4  mov     rax, [rsp+38h+arg_28]
0x1800262f9  lea     rdx, aMain; "main"
0x180026300  mov     r9, [rsp+38h+arg_20]
0x180026305  xor     r8d, r8d
0x180026308  mov     rcx, [rsp+38h+arg_0]
0x18002630d  mov     [rsp+38h+var_10], rax
0x180026312  mov     [rsp+38h+var_18], 0
0x18002631b  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180026321  mov     ebx, eax
0x180026323  test    dil, dil
0x180026326  jz      short loc_180026338
0x180026328  mov     rcx, [rsp+38h+arg_0]
0x18002632d  test    rcx, rcx
0x180026330  jz      short loc_180026338
0x180026332  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180026338  mov     rsi, [rsp+38h+arg_10]
0x18002633d  mov     eax, ebx
0x18002633f  mov     rbx, [rsp+38h+arg_8]
0x180026344  add     rsp, 30h
0x180026348  pop     rdi
0x180026349  retn
```
