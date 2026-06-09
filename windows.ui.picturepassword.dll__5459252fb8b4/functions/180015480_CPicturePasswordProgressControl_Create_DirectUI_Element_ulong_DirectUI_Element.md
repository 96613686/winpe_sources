# CPicturePasswordProgressControl::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x180015480`
- end: `0x1800155c3`
- name: `?Create@CPicturePasswordProgressControl@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z`
- size: `323`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800155d0`

## callees

- `0x18000e9cc`
- `0x180010d04`
- `0x180015480`
- `0x180015840`
- `0x1800158ec`
- `0x18001d920`

## import_xrefs

- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x1800154b6`
- `DUI70!??0Element@DirectUI@@QEAA@XZ` at `0x1800154b6`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x1800154d1`
- `DUI70!?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z` at `0x1800154d1`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18001556a`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18001556a`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180015516`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180015516`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800155a6`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800155a6`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18001553a`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18001553a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800154e9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800154e9`

## pseudocode

```c
__int64 __fastcall CPicturePasswordProgressControl::Create(
        struct DirectUI::Element *a1,
        unsigned int *a2,
        struct DirectUI::Element **a3)
{
  DirectUI::Element *v6; // rax
  DirectUI::Element *v7; // rbx
  int v8; // edi
  struct DirectUI::Element *v9; // rsi
  const unsigned __int16 *v10; // r8
  _DWORD *Children; // rax
  struct DirectUI::Element **v12; // rbx
  struct DirectUI::Element *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  struct DirectUI::DUIXmlParser *v17; // [rsp+60h] [rbp+18h] BYREF
  __int64 v18; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = (DirectUI::Element *)DirectUI::HAllocAndZero((DirectUI *)0xC8, (unsigned __int64)a2);
  v7 = v6;
  if ( v6 )
  {
    DirectUI::Element::Element(v6);
    *(_QWORD *)v7 = &CPicturePasswordProgressControl::`vftable';
    v8 = DirectUI::Element::Initialize(v7, 0, a1, a2);
    if ( v8 < 0 )
    {
      v9 = 0;
      DirectUI::Element::Destroy(v7, 0);
    }
    else
    {
      v9 = v7;
    }
    if ( v8 >= 0 )
    {
      v17 = 0;
      v8 = DirectUI::DUIXmlParser::Create(&v17, 0, 0, 0, 0);
      if ( v8 >= 0 )
      {
        v8 = DirectUI::DUIXmlParser::SetXMLFromResource(v17, 0x445Eu, &_ImageBase, &_ImageBase);
        if ( v8 >= 0 )
        {
          v8 = FillElementFromLayout(v9, v17, v10);
          if ( v8 >= 0 )
          {
            v18 = 0;
            Children = (_DWORD *)DirectUI::Element::GetChildren(v9, &v18);
            v12 = (struct DirectUI::Element **)(Children + 2);
            if ( (*Children & 0x10000000) != 0 )
              v12 = (struct DirectUI::Element **)*v12;
            v13 = *v12;
            _SetGestureProgress(v13, 0);
            _HandleRTLLanguageLTRNumbers(v13, v14, v15);
            *a3 = v9;
            CValuePtr::Release((CValuePtr *)&v18);
          }
        }
        DirectUI::DUIXmlParser::Destroy(v17);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015480  mov     [rsp+arg_0], rbx
0x180015485  push    rsi
0x180015486  push    rdi
0x180015487  push    r14
0x180015489  sub     rsp, 30h
0x18001548d  mov     rsi, rcx
0x180015490  mov     qword ptr [r8], 0
0x180015497  mov     ecx, 0C8h; this
0x18001549c  mov     r14, r8
0x18001549f  mov     rdi, rdx
0x1800154a2  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800154a7  mov     rbx, rax
0x1800154aa  test    rax, rax
0x1800154ad  jz      loc_1800155AE
0x1800154b3  mov     rcx, rax
0x1800154b6  call    cs:__imp_??0Element@DirectUI@@QEAA@XZ; DirectUI::Element::Element(void)
0x1800154bc  lea     rax, ??_7CPicturePasswordProgressControl@@6B@; const CPicturePasswordProgressControl::`vftable'
0x1800154c3  mov     r9, rdi
0x1800154c6  mov     r8, rsi
0x1800154c9  mov     [rbx], rax
0x1800154cc  xor     edx, edx
0x1800154ce  mov     rcx, rbx
0x1800154d1  call    cs:__imp_?Initialize@Element@DirectUI@@QEAAJIPEAV12@PEAK@Z; DirectUI::Element::Initialize(uint,DirectUI::Element *,ulong *)
0x1800154d7  mov     edi, eax
0x1800154d9  test    eax, eax
0x1800154db  js      short loc_1800154E2
0x1800154dd  mov     rsi, rbx
0x1800154e0  jmp     short loc_1800154EF
0x1800154e2  xor     esi, esi
0x1800154e4  xor     edx, edx
0x1800154e6  mov     rcx, rbx
0x1800154e9  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800154ef  test    edi, edi
0x1800154f1  js      loc_1800155B3
0x1800154f7  xor     r9d, r9d
0x1800154fa  mov     [rsp+48h+arg_10], 0
0x180015503  xor     r8d, r8d
0x180015506  mov     [rsp+48h+var_28], 0
0x18001550f  xor     edx, edx
0x180015511  lea     rcx, [rsp+48h+arg_10]
0x180015516  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18001551c  mov     edi, eax
0x18001551e  test    eax, eax
0x180015520  js      loc_1800155B3
0x180015526  mov     rcx, [rsp+48h+arg_10]
0x18001552b  lea     r8, __ImageBase
0x180015532  mov     r9, r8
0x180015535  mov     edx, 445Eh
0x18001553a  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180015540  mov     edi, eax
0x180015542  test    eax, eax
0x180015544  js      short loc_1800155A1
0x180015546  mov     rdx, [rsp+48h+arg_10]; struct DirectUI::DUIXmlParser *
0x18001554b  mov     rcx, rsi; struct DirectUI::Element *
0x18001554e  call    ?FillElementFromLayout@@YAJPEAVElement@DirectUI@@PEAVDUIXmlParser@2@PEBG@Z; FillElementFromLayout(DirectUI::Element *,DirectUI::DUIXmlParser *,ushort const *)
0x180015553  mov     edi, eax
0x180015555  test    eax, eax
0x180015557  js      short loc_1800155A1
0x180015559  lea     rdx, [rsp+48h+arg_18]
0x18001555e  mov     [rsp+48h+arg_18], 0
0x180015567  mov     rcx, rsi
0x18001556a  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180015570  test    dword ptr [rax], 10000000h
0x180015576  lea     rbx, [rax+8]
0x18001557a  jz      short loc_18001557F
0x18001557c  mov     rbx, [rbx]
0x18001557f  mov     rbx, [rbx]
0x180015582  xor     edx, edx; int
0x180015584  mov     rcx, rbx; struct DirectUI::Element *
0x180015587  call    ?_SetGestureProgress@@YAXPEAVElement@DirectUI@@H@Z; _SetGestureProgress(DirectUI::Element *,int)
0x18001558c  mov     rcx, rbx; struct DirectUI::Element *
0x18001558f  call    ?_HandleRTLLanguageLTRNumbers@@YAXPEAVElement@DirectUI@@@Z; _HandleRTLLanguageLTRNumbers(DirectUI::Element *)
0x180015594  lea     rcx, [rsp+48h+arg_18]; this
0x180015599  mov     [r14], rsi
0x18001559c  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800155a1  mov     rcx, [rsp+48h+arg_10]
0x1800155a6  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800155ac  jmp     short loc_1800155B3
0x1800155ae  mov     edi, 8007000Eh
0x1800155b3  mov     rbx, [rsp+48h+arg_0]
0x1800155b8  mov     eax, edi
0x1800155ba  add     rsp, 30h
0x1800155be  pop     r14
0x1800155c0  pop     rdi
0x1800155c1  pop     rsi
0x1800155c2  retn
```
