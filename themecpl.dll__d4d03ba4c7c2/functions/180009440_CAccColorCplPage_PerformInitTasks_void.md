# CAccColorCplPage::PerformInitTasks(void)

- ea: `0x180009440`
- end: `0x18000972e`
- name: `?PerformInitTasks@CAccColorCplPage@@UEAAXXZ`
- size: `750`
- prototype: `void __fastcall(CAccColorCplPage *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180009440`
- `0x18000aaa8`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800094f1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009599`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800095c9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800095f9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009630`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009667`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800094f1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009599`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800095c9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800095f9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009630`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180009667`
- `DUI70!StrToID` at `0x1800094df`
- `DUI70!StrToID` at `0x180009587`
- `DUI70!StrToID` at `0x1800095b7`
- `DUI70!StrToID` at `0x1800095e7`
- `DUI70!StrToID` at `0x18000961e`
- `DUI70!StrToID` at `0x180009655`
- `DUI70!StrToID` at `0x1800094df`
- `DUI70!StrToID` at `0x180009587`
- `DUI70!StrToID` at `0x1800095b7`
- `DUI70!StrToID` at `0x1800095e7`
- `DUI70!StrToID` at `0x18000961e`
- `DUI70!StrToID` at `0x180009655`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180009475`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180009475`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800094a7`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800094a7`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000970c`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000970c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180009535`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180009535`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180009551`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180009551`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800096e0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800096e0`

## pseudocode

```c
void __fastcall CAccColorCplPage::PerformInitTasks(CAccColorCplPage *this)
{
  DirectUI::Element *v2; // rbx
  unsigned int v3; // r12d
  __int64 v4; // r13
  DirectUI::DUIXmlParser *v5; // rdi
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rbx
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  struct DirectUI::Element *v10; // rax
  DirectUI::Element *v11; // rbx
  struct DirectUI::Element *v12; // r14
  unsigned __int16 v13; // ax
  struct DirectUI::Element *v14; // rax
  DirectUI::Element *v15; // rbx
  struct DirectUI::Element *v16; // rbp
  unsigned __int16 v17; // ax
  struct DirectUI::Element *v18; // rsi
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  struct DirectUI::Element *v21; // rdi
  DirectUI::Element *v22; // rbx
  unsigned __int16 v23; // ax
  struct DirectUI::Element *v24; // rbx
  CAccColorCplPage *v25; // rcx
  CAccColorCplPage *v26; // rcx
  CAccColorCplPage *v27; // rcx
  CAccColorCplPage *v28; // rcx
  CAccColorCplPage *v29; // rcx
  struct DirectUI::Element *v30; // [rsp+78h] [rbp+10h] BYREF
  struct DirectUI::DUIXmlParser *v31; // [rsp+80h] [rbp+18h] BYREF
  DirectUI::Element *v32; // [rsp+88h] [rbp+20h]

  v31 = 0;
  if ( (int)DirectUI::DUIXmlParser::Create(&v31, 0, 0, 0, 0) >= 0 )
  {
    if ( (int)DirectUI::DUIXmlParser::SetXMLFromResource(v31, 0x3EAu, g_hinst, &_ImageBase) >= 0 )
    {
      v2 = (CAccColorCplPage *)((char *)this - 200);
      v3 = 0;
      v32 = v2;
      v4 = 0;
      do
      {
        v5 = v31;
        v6 = StrToID(L"SystemColorRows");
        Descendent = DirectUI::Element::FindDescendent(v2, v6);
        if ( Descendent )
        {
          v30 = 0;
          if ( (int)DirectUI::DUIXmlParser::CreateElement(v5, L"SystemColorRow", 0, Descendent, 0, &v30) >= 0 )
          {
            if ( (int)DirectUI::Element::Add(Descendent, v30) < 0 )
            {
              DirectUI::Element::Destroy(v30, 1);
            }
            else
            {
              v8 = v30;
              qword_18006F220[9 * v4] = (__int64)v30;
              v9 = StrToID(L"PreviewBoxAndSpacing");
              v10 = DirectUI::Element::FindDescendent(v8, v9);
              v11 = (DirectUI::Element *)qword_18006F220[9 * v4];
              v12 = v10;
              v13 = StrToID(L"PreviewBox");
              v14 = DirectUI::Element::FindDescendent(v11, v13);
              v15 = (DirectUI::Element *)qword_18006F220[9 * v4];
              v16 = v14;
              v17 = StrToID(L"PreviewBoxText");
              v18 = DirectUI::Element::FindDescendent(v15, v17);
              v19 = (DirectUI::Element *)qword_18006F220[9 * v4];
              v20 = StrToID(L"LeftButton");
              v21 = DirectUI::Element::FindDescendent(v19, v20);
              v22 = (DirectUI::Element *)qword_18006F220[9 * v4];
              v23 = StrToID(L"RightButton");
              v24 = DirectUI::Element::FindDescendent(v22, v23);
              CAccColorCplPage::_RenameElement(v25, v12, L"PreviewBoxAndSpacing", v3);
              CAccColorCplPage::_RenameElement(v26, v16, L"PreviewBox", v3);
              CAccColorCplPage::_RenameElement(v27, v18, L"PreviewBoxText", v3);
              CAccColorCplPage::_RenameElement(v28, v21, L"LeftButton", v3);
              CAccColorCplPage::_RenameElement(v29, v24, L"RightButton", v3);
            }
          }
        }
        v2 = v32;
        ++v3;
        ++v4;
      }
      while ( v3 < 8 );
    }
    DirectUI::DUIXmlParser::Destroy(v31);
  }
}

```

## disassembly

```asm
0x180009440  mov     rax, rsp
0x180009443  mov     [rax+8], rbx
0x180009447  push    rbp
0x180009448  push    rsi
0x180009449  push    rdi
0x18000944a  push    r12
0x18000944c  push    r13
0x18000944e  push    r14
0x180009450  push    r15
0x180009452  sub     rsp, 30h
0x180009456  mov     rbx, rcx
0x180009459  mov     qword ptr [rax+18h], 0
0x180009461  lea     rcx, [rax+18h]
0x180009465  mov     qword ptr [rax-48h], 0
0x18000946d  xor     r9d, r9d
0x180009470  xor     r8d, r8d
0x180009473  xor     edx, edx
0x180009475  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18000947c  nop     dword ptr [rax+rax+00h]
0x180009481  test    eax, eax
0x180009483  js      loc_180009718
0x180009489  mov     r8, cs:g_hinst
0x180009490  lea     rsi, __ImageBase
0x180009497  mov     rcx, [rsp+68h+arg_10]
0x18000949f  mov     r9, rsi
0x1800094a2  mov     edx, 3EAh
0x1800094a7  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800094ae  nop     dword ptr [rax+rax+00h]
0x1800094b3  test    eax, eax
0x1800094b5  js      loc_180009704
0x1800094bb  add     rbx, 0FFFFFFFFFFFFFF38h
0x1800094c2  xor     r12d, r12d
0x1800094c5  mov     [rsp+68h+arg_18], rbx
0x1800094cd  xor     r13d, r13d
0x1800094d0  mov     rdi, [rsp+68h+arg_10]
0x1800094d8  lea     rcx, aSystemcolorrow; "SystemColorRows"
0x1800094df  call    cs:__imp_StrToID
0x1800094e6  nop     dword ptr [rax+rax+00h]
0x1800094eb  movzx   edx, ax
0x1800094ee  mov     rcx, rbx
0x1800094f1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800094f8  nop     dword ptr [rax+rax+00h]
0x1800094fd  mov     rbx, rax
0x180009500  test    rax, rax
0x180009503  jz      loc_1800096EC
0x180009509  lea     rax, [rsp+68h+arg_8]
0x18000950e  mov     [rsp+68h+arg_8], 0
0x180009517  mov     [rsp+68h+var_40], rax
0x18000951c  lea     rdx, aSystemcolorrow_0; "SystemColorRow"
0x180009523  mov     r9, rbx
0x180009526  mov     [rsp+68h+var_48], 0
0x18000952f  xor     r8d, r8d
0x180009532  mov     rcx, rdi
0x180009535  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000953c  nop     dword ptr [rax+rax+00h]
0x180009541  test    eax, eax
0x180009543  js      loc_1800096EC
0x180009549  mov     rdx, [rsp+68h+arg_8]
0x18000954e  mov     rcx, rbx
0x180009551  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180009558  nop     dword ptr [rax+rax+00h]
0x18000955d  test    eax, eax
0x18000955f  js      loc_1800096D9
0x180009565  mov     rax, [rsp+68h+arg_8]
0x18000956a  lea     r15, ds:0[r13*8]
0x180009572  add     r15, r13
0x180009575  lea     rcx, aPreviewboxands; "PreviewBoxAndSpacing"
0x18000957c  mov     rbx, rax
0x18000957f  mov     rva qword_18006F220[rsi+r15*8], rax
0x180009587  call    cs:__imp_StrToID
0x18000958e  nop     dword ptr [rax+rax+00h]
0x180009593  movzx   edx, ax
0x180009596  mov     rcx, rbx
0x180009599  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800095a0  nop     dword ptr [rax+rax+00h]
0x1800095a5  mov     rbx, rva qword_18006F220[rsi+r15*8]
0x1800095ad  lea     rcx, aPreviewbox; "PreviewBox"
0x1800095b4  mov     r14, rax
0x1800095b7  call    cs:__imp_StrToID
0x1800095be  nop     dword ptr [rax+rax+00h]
0x1800095c3  movzx   edx, ax
0x1800095c6  mov     rcx, rbx
0x1800095c9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800095d0  nop     dword ptr [rax+rax+00h]
0x1800095d5  mov     rbx, rva qword_18006F220[rsi+r15*8]
0x1800095dd  lea     rcx, aPreviewboxtext; "PreviewBoxText"
0x1800095e4  mov     rbp, rax
0x1800095e7  call    cs:__imp_StrToID
0x1800095ee  nop     dword ptr [rax+rax+00h]
0x1800095f3  movzx   edx, ax
0x1800095f6  mov     rcx, rbx
0x1800095f9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009600  nop     dword ptr [rax+rax+00h]
0x180009605  lea     rbx, __ImageBase
0x18000960c  mov     rsi, rax
0x18000960f  mov     rbx, rva qword_18006F220[rbx+r15*8]
0x180009617  lea     rcx, aLeftbutton; "LeftButton"
0x18000961e  call    cs:__imp_StrToID
0x180009625  nop     dword ptr [rax+rax+00h]
0x18000962a  movzx   edx, ax
0x18000962d  mov     rcx, rbx
0x180009630  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180009637  nop     dword ptr [rax+rax+00h]
0x18000963c  mov     rdi, rax
0x18000963f  lea     rcx, aRightbutton; "RightButton"
0x180009646  lea     rax, __ImageBase
0x18000964d  mov     rbx, rva qword_18006F220[rax+r15*8]
0x180009655  call    cs:__imp_StrToID
0x18000965c  nop     dword ptr [rax+rax+00h]
0x180009661  movzx   edx, ax
0x180009664  mov     rcx, rbx
0x180009667  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000966e  nop     dword ptr [rax+rax+00h]
0x180009673  mov     r9d, r12d; unsigned int
0x180009676  lea     r8, aPreviewboxands; "PreviewBoxAndSpacing"
0x18000967d  mov     rdx, r14; struct DirectUI::Element *
0x180009680  mov     rbx, rax
0x180009683  call    ?_RenameElement@CAccColorCplPage@@AEAAXPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_RenameElement(DirectUI::Element *,ushort const *,uint)
0x180009688  mov     r9d, r12d; unsigned int
0x18000968b  lea     r8, aPreviewbox; "PreviewBox"
0x180009692  mov     rdx, rbp; struct DirectUI::Element *
0x180009695  call    ?_RenameElement@CAccColorCplPage@@AEAAXPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_RenameElement(DirectUI::Element *,ushort const *,uint)
0x18000969a  mov     r9d, r12d; unsigned int
0x18000969d  lea     r8, aPreviewboxtext; "PreviewBoxText"
0x1800096a4  mov     rdx, rsi; struct DirectUI::Element *
0x1800096a7  call    ?_RenameElement@CAccColorCplPage@@AEAAXPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_RenameElement(DirectUI::Element *,ushort const *,uint)
0x1800096ac  mov     r9d, r12d; unsigned int
0x1800096af  lea     r8, aLeftbutton; "LeftButton"
0x1800096b6  mov     rdx, rdi; struct DirectUI::Element *
0x1800096b9  call    ?_RenameElement@CAccColorCplPage@@AEAAXPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_RenameElement(DirectUI::Element *,ushort const *,uint)
0x1800096be  mov     r9d, r12d; unsigned int
0x1800096c1  lea     r8, aRightbutton; "RightButton"
0x1800096c8  mov     rdx, rbx; struct DirectUI::Element *
0x1800096cb  call    ?_RenameElement@CAccColorCplPage@@AEAAXPEAVElement@DirectUI@@PEBGI@Z; CAccColorCplPage::_RenameElement(DirectUI::Element *,ushort const *,uint)
0x1800096d0  lea     rsi, __ImageBase
0x1800096d7  jmp     short loc_1800096EC
0x1800096d9  mov     rcx, [rsp+68h+arg_8]
0x1800096de  mov     dl, 1
0x1800096e0  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800096e7  nop     dword ptr [rax+rax+00h]
0x1800096ec  mov     rbx, [rsp+68h+arg_18]
0x1800096f4  inc     r12d
0x1800096f7  inc     r13
0x1800096fa  cmp     r12d, 8
0x1800096fe  jb      loc_1800094D0
0x180009704  mov     rcx, [rsp+68h+arg_10]
0x18000970c  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180009713  nop     dword ptr [rax+rax+00h]
0x180009718  mov     rbx, [rsp+68h+arg_0]
0x18000971d  add     rsp, 30h
0x180009721  pop     r15
0x180009723  pop     r14
0x180009725  pop     r13
0x180009727  pop     r12
0x180009729  pop     rdi
0x18000972a  pop     rsi
0x18000972b  pop     rbp
0x18000972c  retn
```
