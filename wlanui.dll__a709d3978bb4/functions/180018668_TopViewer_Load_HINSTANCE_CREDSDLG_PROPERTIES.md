# TopViewer::Load(HINSTANCE__ *,_CREDSDLG_PROPERTIES *)

- ea: `0x180018668`
- end: `0x1800188bb`
- name: `?Load@TopViewer@@QEAAJPEAUHINSTANCE__@@PEAU_CREDSDLG_PROPERTIES@@@Z`
- size: `595`
- prototype: `int(TopViewer *__hidden this, HINSTANCE, struct _CREDSDLG_PROPERTIES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180017ca0`

## callees

- `0x1800182a8`
- `0x180018668`
- `0x1800190c0`
- `0x18001ad24`
- `0x18001d010`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800186b1`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800186b1`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800188a2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800188a2`
- `DUI70!?SetXML@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z` at `0x1800186d6`
- `DUI70!?SetXML@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z` at `0x1800186d6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001870f`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001870f`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180018726`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180018726`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x180018684`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x180018684`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001874c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001879e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800187e2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018877`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001874c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001879e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800187e2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018877`
- `DUI70!StrToID` at `0x18001873f`
- `DUI70!StrToID` at `0x180018791`
- `DUI70!StrToID` at `0x1800187d5`
- `DUI70!StrToID` at `0x18001886b`
- `DUI70!StrToID` at `0x18001873f`
- `DUI70!StrToID` at `0x180018791`
- `DUI70!StrToID` at `0x1800187d5`
- `DUI70!StrToID` at `0x18001886b`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180018776`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800187c8`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001880c`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180018776`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800187c8`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001880c`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180018732`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180018732`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180018765`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800187b7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800187fb`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180018765`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800187b7`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800187fb`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180018784`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180018784`

## pseudocode

```c
__int64 __fastcall TopViewer::Load(TopViewer *this, HINSTANCE a2, struct _CREDSDLG_PROPERTIES *a3)
{
  int v6; // edi
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v9; // r14
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rax
  DirectUI::Element *v12; // r14
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  DirectUI::Element *v15; // r14
  LogonScreenHelper *v16; // rcx
  DuiDataHandler *v17; // rcx
  _QWORD *v18; // rdx
  unsigned __int16 *DuiEditControlName; // rax
  unsigned __int16 v20; // ax
  struct DirectUI::Element *v21; // rax
  struct DirectUI::Element *v23; // [rsp+60h] [rbp+30h] BYREF
  struct DirectUI::DUIXmlParser *v24; // [rsp+78h] [rbp+48h] BYREF

  DirectUI::Element::RemoveAll(this);
  v24 = 0;
  *((_DWORD *)this + 72) = 0;
  v6 = DirectUI::DUIXmlParser::Create(&v24, 0, 0, 0, 0);
  if ( v6 >= 0 )
  {
    if ( (int)DirectUI::DUIXmlParser::SetXML(v24, *((const unsigned __int16 **)this + 102), a2, (HINSTANCE)&_ImageBase) < 0 )
    {
      v6 = -2147467259;
    }
    else
    {
      v23 = 0;
      v6 = DirectUI::DUIXmlParser::CreateElement(v24, L"main", 0, 0, 0, &v23);
      if ( v6 >= 0 )
      {
        DirectUI::Element::Add(this, v23);
        DirectUI::Element::SetAccessible(v23, 1);
        v7 = StrToID(L"MessageText");
        Descendent = DirectUI::Element::FindDescendent(v23, v7);
        v9 = Descendent;
        if ( Descendent )
        {
          DirectUI::Element::SetContentString(Descendent, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 32LL));
          DirectUI::Element::SetAccName(v9, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 32LL));
          DirectUI::Element::SetLayoutPos(v9, 1);
        }
        v10 = StrToID(L"OKButton");
        v11 = DirectUI::Element::FindDescendent(v23, v10);
        v12 = v11;
        if ( v11 )
        {
          DirectUI::Element::SetContentString(v11, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 40LL));
          DirectUI::Element::SetAccName(v12, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 40LL));
        }
        v13 = StrToID(L"CancelButton");
        v14 = DirectUI::Element::FindDescendent(v23, v13);
        v15 = v14;
        if ( v14 )
        {
          DirectUI::Element::SetContentString(v14, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 48LL));
          DirectUI::Element::SetAccName(v15, *(const unsigned __int16 **)(*((_QWORD *)a3 + 1) + 48LL));
        }
      }
      v16 = (LogonScreenHelper *)*((_QWORD *)this + 34);
      if ( v16 )
      {
        LogonScreenHelper::SetUIContrast(v16, a2);
        LogonScreenHelper::InitializeEditFields(*((LogonScreenHelper **)this + 34));
      }
      else
      {
        v17 = (DuiDataHandler *)*((_QWORD *)this + 103);
        v18 = (_QWORD *)*((_QWORD *)v17 + 1);
        if ( v18 )
        {
          if ( -1431655765 * (unsigned int)((__int64)(v18[1] - *v18) >> 3) )
          {
            DuiEditControlName = DuiDataHandler::GetDuiEditControlName(v17, 0);
            v20 = StrToID(DuiEditControlName);
            v21 = DirectUI::Element::FindDescendent(this, v20);
            if ( v21 )
              (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v21 + 168LL))(v21);
          }
        }
      }
    }
    DirectUI::DUIXmlParser::Destroy(v24);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018668  mov     [rsp-28h+arg_8], rbx
0x18001866d  push    rbp
0x18001866e  push    rsi
0x18001866f  push    rdi
0x180018670  push    r14
0x180018672  push    r15
0x180018674  mov     rbp, rsp
0x180018677  sub     rsp, 30h
0x18001867b  mov     rsi, r8
0x18001867e  mov     r15, rdx
0x180018681  mov     rbx, rcx
0x180018684  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x18001868a  xor     r9d, r9d
0x18001868d  mov     [rbp+arg_18], 0
0x180018695  xor     r8d, r8d
0x180018698  mov     dword ptr [rbx+120h], 0
0x1800186a2  xor     edx, edx
0x1800186a4  mov     [rsp+30h+var_10], 0
0x1800186ad  lea     rcx, [rbp+arg_18]
0x1800186b1  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800186b7  mov     edi, eax
0x1800186b9  test    eax, eax
0x1800186bb  js      loc_1800188A8
0x1800186c1  mov     rdx, [rbx+330h]
0x1800186c8  lea     r9, __ImageBase
0x1800186cf  mov     rcx, [rbp+arg_18]
0x1800186d3  mov     r8, r15
0x1800186d6  call    cs:__imp_?SetXML@DUIXmlParser@DirectUI@@QEAAJPEBGPEAUHINSTANCE__@@1@Z; DirectUI::DUIXmlParser::SetXML(ushort const *,HINSTANCE__ *,HINSTANCE__ *)
0x1800186dc  test    eax, eax
0x1800186de  js      loc_180018899
0x1800186e4  mov     rcx, [rbp+arg_18]
0x1800186e8  lea     rax, [rbp+arg_0]
0x1800186ec  mov     [rsp+30h+var_8], rax
0x1800186f1  lea     rdx, aMain; "main"
0x1800186f8  xor     r9d, r9d
0x1800186fb  mov     [rsp+30h+var_10], 0
0x180018704  xor     r8d, r8d
0x180018707  mov     [rbp+arg_0], 0
0x18001870f  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180018715  mov     edi, eax
0x180018717  test    eax, eax
0x180018719  js      loc_180018812
0x18001871f  mov     rdx, [rbp+arg_0]
0x180018723  mov     rcx, rbx
0x180018726  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18001872c  mov     rcx, [rbp+arg_0]
0x180018730  mov     dl, 1
0x180018732  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x180018738  lea     rcx, aMessagetext; "MessageText"
0x18001873f  call    cs:__imp_StrToID
0x180018745  mov     rcx, [rbp+arg_0]
0x180018749  movzx   edx, ax
0x18001874c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018752  mov     r14, rax
0x180018755  test    rax, rax
0x180018758  jz      short loc_18001878A
0x18001875a  mov     rdx, [rsi+8]
0x18001875e  mov     rcx, rax
0x180018761  mov     rdx, [rdx+20h]
0x180018765  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18001876b  mov     rdx, [rsi+8]
0x18001876f  mov     rcx, r14
0x180018772  mov     rdx, [rdx+20h]
0x180018776  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18001877c  mov     edx, 1
0x180018781  mov     rcx, r14
0x180018784  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18001878a  lea     rcx, aOkbutton; "OKButton"
0x180018791  call    cs:__imp_StrToID
0x180018797  mov     rcx, [rbp+arg_0]
0x18001879b  movzx   edx, ax
0x18001879e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800187a4  mov     r14, rax
0x1800187a7  test    rax, rax
0x1800187aa  jz      short loc_1800187CE
0x1800187ac  mov     rdx, [rsi+8]
0x1800187b0  mov     rcx, rax
0x1800187b3  mov     rdx, [rdx+28h]
0x1800187b7  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800187bd  mov     rdx, [rsi+8]
0x1800187c1  mov     rcx, r14
0x1800187c4  mov     rdx, [rdx+28h]
0x1800187c8  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x1800187ce  lea     rcx, aCancelbutton; "CancelButton"
0x1800187d5  call    cs:__imp_StrToID
0x1800187db  mov     rcx, [rbp+arg_0]
0x1800187df  movzx   edx, ax
0x1800187e2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800187e8  mov     r14, rax
0x1800187eb  test    rax, rax
0x1800187ee  jz      short loc_180018812
0x1800187f0  mov     rdx, [rsi+8]
0x1800187f4  mov     rcx, rax
0x1800187f7  mov     rdx, [rdx+30h]
0x1800187fb  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180018801  mov     rdx, [rsi+8]
0x180018805  mov     rcx, r14
0x180018808  mov     rdx, [rdx+30h]
0x18001880c  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180018812  mov     rcx, [rbx+110h]; this
0x180018819  test    rcx, rcx
0x18001881c  jz      short loc_180018834
0x18001881e  mov     rdx, r15; HINSTANCE
0x180018821  call    ?SetUIContrast@LogonScreenHelper@@QEAAXPEAUHINSTANCE__@@@Z; LogonScreenHelper::SetUIContrast(HINSTANCE__ *)
0x180018826  mov     rcx, [rbx+110h]; this
0x18001882d  call    ?InitializeEditFields@LogonScreenHelper@@QEAAXXZ; LogonScreenHelper::InitializeEditFields(void)
0x180018832  jmp     short loc_18001889E
0x180018834  mov     rcx, [rbx+338h]; this
0x18001883b  mov     rdx, [rcx+8]
0x18001883f  test    rdx, rdx
0x180018842  jz      short loc_18001889E
0x180018844  mov     rax, [rdx+8]
0x180018848  sub     rax, [rdx]
0x18001884b  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180018855  sar     rax, 3
0x180018859  imul    rax, rdx
0x18001885d  test    eax, eax
0x18001885f  jz      short loc_18001889E
0x180018861  xor     edx, edx; unsigned int
0x180018863  call    ?GetDuiEditControlName@DuiDataHandler@@QEAAPEAGK@Z; DuiDataHandler::GetDuiEditControlName(ulong)
0x180018868  mov     rcx, rax
0x18001886b  call    cs:__imp_StrToID
0x180018871  movzx   edx, ax
0x180018874  mov     rcx, rbx
0x180018877  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001887d  mov     rdx, rax
0x180018880  test    rax, rax
0x180018883  jz      short loc_18001889E
0x180018885  mov     rcx, [rax]
0x180018888  mov     rax, [rcx+0A8h]
0x18001888f  mov     rcx, rdx
0x180018892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018897  jmp     short loc_18001889E
0x180018899  mov     edi, 80004005h
0x18001889e  mov     rcx, [rbp+arg_18]
0x1800188a2  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800188a8  mov     rbx, [rsp+30h+arg_8]
0x1800188ad  mov     eax, edi
0x1800188af  add     rsp, 30h
0x1800188b3  pop     r15
0x1800188b5  pop     r14
0x1800188b7  pop     rdi
0x1800188b8  pop     rsi
0x1800188b9  pop     rbp
0x1800188ba  retn
```
