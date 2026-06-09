# CTaskPageHost::_CreateDUI(HINSTANCE__ *)

- ea: `0x18003a21c`
- end: `0x18003a33b`
- name: `?_CreateDUI@CTaskPageHost@@AEAAJPEAUHINSTANCE__@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CTaskPageHost *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180039e7c`

## callees

- `0x18003a21c`
- `0x18003a344`

## import_xrefs

- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18003a2d7`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18003a2d7`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18003a323`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18003a323`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18003a273`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18003a273`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18003a24e`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18003a24e`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18003a2b1`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18003a2b1`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a304`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a318`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a304`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a318`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18003a2f3`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18003a2f3`

## pseudocode

```c
__int64 __fastcall CTaskPageHost::_CreateDUI(CTaskPageHost *this, HINSTANCE a2)
{
  int UniqueElement; // ebx
  CTaskPageHost *v5; // rcx
  DirectUI::Element **v6; // rdi
  struct DirectUI::DUIXmlParser *v8; // [rsp+50h] [rbp+18h] BYREF
  struct DirectUI::Element *v9; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  UniqueElement = DirectUI::DUIXmlParser::Create(&v8, 0, 0, 0, 0);
  if ( UniqueElement >= 0 )
  {
    UniqueElement = DirectUI::DUIXmlParser::SetXMLFromResource(v8, *((_DWORD *)this + 268), a2, &_ImageBase);
    if ( UniqueElement < 0 )
      goto LABEL_9;
    v9 = 0;
    UniqueElement = DirectUI::DUIXmlParser::CreateElement(v8, (const unsigned __int16 *)this + 538, 0, 0, 0, &v9);
    if ( UniqueElement < 0 )
      goto LABEL_9;
    v6 = (DirectUI::Element **)((char *)this + 24);
    UniqueElement = CTaskPageHost::_CreateUniqueElement(v5, (struct DirectUI::Element **)this + 3);
    if ( UniqueElement >= 0 )
    {
      UniqueElement = DirectUI::Element::Add(*v6, v9);
      if ( UniqueElement >= 0 )
      {
        UniqueElement = DirectUI::Element::AddListener(
                          *v6,
                          (struct DirectUI::IElementListener *)(((unsigned __int64)this + 16) & -(__int64)(this != 0)));
        if ( UniqueElement >= 0 )
          goto LABEL_9;
      }
      DirectUI::Element::Destroy(*v6, 1);
      *v6 = 0;
    }
    DirectUI::Element::Destroy(v9, 1);
LABEL_9:
    DirectUI::DUIXmlParser::Destroy(v8);
  }
  return (unsigned int)UniqueElement;
}

```

## disassembly

```asm
0x18003a21c  mov     rax, rsp
0x18003a21f  mov     [rax+8], rbx
0x18003a223  mov     [rax+10h], rsi
0x18003a227  push    rdi
0x18003a228  sub     rsp, 30h
0x18003a22c  mov     rdi, rdx
0x18003a22f  mov     qword ptr [rax+18h], 0
0x18003a237  mov     rsi, rcx
0x18003a23a  mov     qword ptr [rax-18h], 0
0x18003a242  xor     edx, edx
0x18003a244  lea     rcx, [rax+18h]
0x18003a248  xor     r9d, r9d
0x18003a24b  xor     r8d, r8d
0x18003a24e  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18003a254  mov     ebx, eax
0x18003a256  test    eax, eax
0x18003a258  js      loc_18003A329
0x18003a25e  mov     edx, [rsi+430h]
0x18003a264  lea     r9, __ImageBase
0x18003a26b  mov     rcx, [rsp+38h+arg_10]
0x18003a270  mov     r8, rdi
0x18003a273  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18003a279  mov     ebx, eax
0x18003a27b  test    eax, eax
0x18003a27d  js      loc_18003A31E
0x18003a283  mov     rcx, [rsp+38h+arg_10]
0x18003a288  lea     rax, [rsp+38h+arg_18]
0x18003a28d  mov     [rsp+38h+var_10], rax
0x18003a292  lea     rdx, [rsi+434h]
0x18003a299  xor     r9d, r9d
0x18003a29c  mov     [rsp+38h+var_18], 0
0x18003a2a5  xor     r8d, r8d
0x18003a2a8  mov     [rsp+38h+arg_18], 0
0x18003a2b1  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18003a2b7  mov     ebx, eax
0x18003a2b9  test    eax, eax
0x18003a2bb  js      short loc_18003A31E
0x18003a2bd  lea     rdi, [rsi+18h]
0x18003a2c1  mov     rdx, rdi; struct DirectUI::Element **
0x18003a2c4  call    ?_CreateUniqueElement@CTaskPageHost@@AEAAJPEAPEAVElement@DirectUI@@@Z; CTaskPageHost::_CreateUniqueElement(DirectUI::Element * *)
0x18003a2c9  mov     ebx, eax
0x18003a2cb  test    eax, eax
0x18003a2cd  js      short loc_18003A311
0x18003a2cf  mov     rdx, [rsp+38h+arg_18]
0x18003a2d4  mov     rcx, [rdi]
0x18003a2d7  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18003a2dd  mov     ebx, eax
0x18003a2df  test    eax, eax
0x18003a2e1  js      short loc_18003A2FF
0x18003a2e3  mov     rcx, [rdi]
0x18003a2e6  lea     rax, [rsi+10h]
0x18003a2ea  neg     rsi
0x18003a2ed  sbb     rdx, rdx
0x18003a2f0  and     rdx, rax
0x18003a2f3  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18003a2f9  mov     ebx, eax
0x18003a2fb  test    eax, eax
0x18003a2fd  jns     short loc_18003A31E
0x18003a2ff  mov     rcx, [rdi]
0x18003a302  mov     dl, 1
0x18003a304  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18003a30a  mov     qword ptr [rdi], 0
0x18003a311  mov     rcx, [rsp+38h+arg_18]
0x18003a316  mov     dl, 1
0x18003a318  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18003a31e  mov     rcx, [rsp+38h+arg_10]
0x18003a323  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18003a329  mov     rsi, [rsp+38h+arg_8]
0x18003a32e  mov     eax, ebx
0x18003a330  mov     rbx, [rsp+38h+arg_0]
0x18003a335  add     rsp, 30h
0x18003a339  pop     rdi
0x18003a33a  retn
```
