# LogonScreenHelper::SetUIContrast(HINSTANCE__ *)

- ea: `0x1800190c0`
- end: `0x18001927b`
- name: `?SetUIContrast@LogonScreenHelper@@QEAAXPEAUHINSTANCE__@@@Z`
- size: `443`
- prototype: `void(LogonScreenHelper *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180018668`

## callees

- `0x1800176d0`
- `0x1800190c0`
- `0x1800199f8`
- `0x18001ad24`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180019120`
- `USER32!SystemParametersInfoW` at `0x180019120`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800191e1`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180019248`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800191e1`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180019248`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001916f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800191cc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019233`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001916f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800191cc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180019233`
- `DUI70!StrToID` at `0x180019163`
- `DUI70!StrToID` at `0x1800191c0`
- `DUI70!StrToID` at `0x180019227`
- `DUI70!StrToID` at `0x180019163`
- `DUI70!StrToID` at `0x1800191c0`
- `DUI70!StrToID` at `0x180019227`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18001925b`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18001925b`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x18001913f`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180019180`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x18001913f`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180019180`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800191d7`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18001923e`

## pseudocode

```c
void __fastcall LogonScreenHelper::SetUIContrast(DirectUI::Element **this, HINSTANCE a2)
{
  _QWORD *v4; // rax
  unsigned __int64 v5; // rdi
  LogonScreenHelper *v6; // rcx
  __int64 v7; // rsi
  unsigned int i; // ebp
  DirectUI::Element *v9; // rbx
  unsigned __int16 *DuiEditControlName; // rax
  unsigned __int16 v11; // ax
  DirectUI::Element *Descendent; // rax
  __int64 j; // rbp
  DirectUI::Element *v14; // rbx
  unsigned __int16 *v15; // rax
  unsigned __int16 v16; // ax
  DirectUI::Element *v17; // rax
  DirectUI::Element *v18; // rbx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  unsigned __int16 v21; // ax
  DirectUI::Element *v22; // rax
  DirectUI::Element *v23; // rbx
  __int64 ClassInfoPtr; // rax
  __int64 v25; // r8
  _QWORD pvParam[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = *(_QWORD **)(*((_QWORD *)*this + 103) + 8LL);
  if ( v4 )
    v5 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v4[1] - *v4) >> 3);
  else
    LODWORD(v5) = 0;
  pvParam[0] = 16;
  pvParam[1] = 0;
  if ( SystemParametersInfoW(0x42u, 0, pvParam, 0) )
  {
    v7 = BYTE4(pvParam[0]) & 1;
    if ( (pvParam[0] & 0x100000000LL) != 0 )
    {
      DirectUI::Element::SetBackgroundStdColor(*this, 10005);
      for ( i = 0; i < (unsigned int)v5; ++i )
      {
        v9 = *this;
        DuiEditControlName = DuiDataHandler::GetDuiEditControlName(*((DuiDataHandler **)*this + 103), i);
        v11 = StrToID(DuiEditControlName);
        Descendent = DirectUI::Element::FindDescendent(v9, v11);
        if ( Descendent )
          DirectUI::Element::SetBackgroundStdColor(Descendent, 10005);
      }
      goto LABEL_22;
    }
  }
  else
  {
    v7 = 0;
  }
  LogonScreenHelper::ClipAndAddBackground(v6, *this, a2, this[1]);
  for ( j = 0; (unsigned int)j < (unsigned int)v5; j = (unsigned int)(j + 1) )
  {
    v14 = *this;
    v15 = DuiDataHandler::GetDuiEditControlName(*((DuiDataHandler **)*this + 103), j);
    v16 = StrToID(v15);
    v17 = DirectUI::Element::FindDescendent(v14, v16);
    if ( v17 )
      DirectUI::Element::RemoveLocalValue(
        v17,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp);
    v18 = *this;
    v19 = *(_QWORD **)(*((_QWORD *)*this + 103) + 8LL);
    if ( v19 && (unsigned int)j < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v19[1] - *v19) >> 3) )
      v20 = *(_QWORD *)(*v19 + 24 * j + 8);
    else
      v20 = 0;
    v21 = StrToID(v20);
    v22 = DirectUI::Element::FindDescendent(v18, v21);
    if ( v22 )
      DirectUI::Element::RemoveLocalValue(
        v22,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp);
  }
LABEL_22:
  v23 = *this;
  ClassInfoPtr = DirectUI::Element::GetClassInfoPtr();
  TraverseTree(v23, ClassInfoPtr, v25, v7);
}

```

## disassembly

```asm
0x1800190c0  push    rbx
0x1800190c2  push    rbp
0x1800190c3  push    rsi
0x1800190c4  push    rdi
0x1800190c5  push    r14
0x1800190c7  push    r15
0x1800190c9  sub     rsp, 38h
0x1800190cd  mov     rax, [rcx]
0x1800190d0  mov     rbx, rdx
0x1800190d3  mov     r14, rcx
0x1800190d6  mov     r15, 0AAAAAAAAAAAAAAABh
0x1800190e0  mov     r8, [rax+338h]
0x1800190e7  mov     rax, [r8+8]
0x1800190eb  test    rax, rax
0x1800190ee  jnz     short loc_1800190F4
0x1800190f0  xor     edi, edi
0x1800190f2  jmp     short loc_180019103
0x1800190f4  mov     rdi, [rax+8]
0x1800190f8  sub     rdi, [rax]
0x1800190fb  sar     rdi, 3
0x1800190ff  imul    rdi, r15
0x180019103  xor     eax, eax
0x180019105  mov     [rsp+68h+pvParam], 10h
0x18001910e  xor     r9d, r9d; fWinIni
0x180019111  mov     [rsp+68h+var_40], rax
0x180019116  lea     r8, [rsp+68h+pvParam]; pvParam
0x18001911b  xor     edx, edx; uiParam
0x18001911d  lea     ecx, [rax+42h]; uiAction
0x180019120  call    cs:__imp_SystemParametersInfoW
0x180019126  test    eax, eax
0x180019128  jz      short loc_180019191
0x18001912a  mov     esi, dword ptr [rsp+68h+pvParam+4]
0x18001912e  and     esi, 1
0x180019131  jz      short loc_180019193
0x180019133  mov     rcx, [r14]
0x180019136  mov     r15d, 2715h
0x18001913c  mov     edx, r15d
0x18001913f  call    cs:__imp_?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetBackgroundStdColor(int)
0x180019145  xor     ebp, ebp
0x180019147  test    edi, edi
0x180019149  jz      loc_180019258
0x18001914f  mov     rbx, [r14]
0x180019152  mov     edx, ebp; unsigned int
0x180019154  mov     rcx, [rbx+338h]; this
0x18001915b  call    ?GetDuiEditControlName@DuiDataHandler@@QEAAPEAGK@Z; DuiDataHandler::GetDuiEditControlName(ulong)
0x180019160  mov     rcx, rax
0x180019163  call    cs:__imp_StrToID
0x180019169  movzx   edx, ax
0x18001916c  mov     rcx, rbx
0x18001916f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019175  test    rax, rax
0x180019178  jz      short loc_180019186
0x18001917a  mov     edx, r15d
0x18001917d  mov     rcx, rax
0x180019180  call    cs:__imp_?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetBackgroundStdColor(int)
0x180019186  inc     ebp
0x180019188  cmp     ebp, edi
0x18001918a  jb      short loc_18001914F
0x18001918c  jmp     loc_180019258
0x180019191  xor     esi, esi
0x180019193  mov     r9, [r14+8]; struct _CREDSDLG_PROPERTIES *
0x180019197  mov     r8, rbx; HINSTANCE
0x18001919a  mov     rdx, [r14]; struct TopViewer *
0x18001919d  call    ?ClipAndAddBackground@LogonScreenHelper@@QEAAXPEAVTopViewer@@PEAUHINSTANCE__@@PEAU_CREDSDLG_PROPERTIES@@@Z; LogonScreenHelper::ClipAndAddBackground(TopViewer *,HINSTANCE__ *,_CREDSDLG_PROPERTIES *)
0x1800191a2  xor     ebp, ebp
0x1800191a4  test    edi, edi
0x1800191a6  jz      loc_180019258
0x1800191ac  mov     rbx, [r14]
0x1800191af  mov     edx, ebp; unsigned int
0x1800191b1  mov     rcx, [rbx+338h]; this
0x1800191b8  call    ?GetDuiEditControlName@DuiDataHandler@@QEAAPEAGK@Z; DuiDataHandler::GetDuiEditControlName(ulong)
0x1800191bd  mov     rcx, rax
0x1800191c0  call    cs:__imp_StrToID
0x1800191c6  movzx   edx, ax
0x1800191c9  mov     rcx, rbx
0x1800191cc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800191d2  test    rax, rax
0x1800191d5  jz      short loc_1800191E7
0x1800191d7  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x1800191de  mov     rcx, rax
0x1800191e1  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800191e7  mov     rbx, [r14]
0x1800191ea  mov     rax, [rbx+338h]
0x1800191f1  mov     rax, [rax+8]
0x1800191f5  test    rax, rax
0x1800191f8  jz      short loc_180019225
0x1800191fa  mov     rdx, [rax]
0x1800191fd  mov     rax, [rax+8]
0x180019201  sub     rax, rdx
0x180019204  mov     ecx, ebp
0x180019206  sar     rax, 3
0x18001920a  imul    rax, r15
0x18001920e  cmp     rcx, rax
0x180019211  jnb     short loc_180019225
0x180019213  lea     rax, ds:0[rbp*2]
0x18001921b  add     rax, rbp
0x18001921e  mov     rcx, [rdx+rax*8+8]
0x180019223  jmp     short loc_180019227
0x180019225  xor     ecx, ecx
0x180019227  call    cs:__imp_StrToID
0x18001922d  movzx   edx, ax
0x180019230  mov     rcx, rbx
0x180019233  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180019239  test    rax, rax
0x18001923c  jz      short loc_18001924E
0x18001923e  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x180019245  mov     rcx, rax
0x180019248  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18001924e  inc     ebp
0x180019250  cmp     ebp, edi
0x180019252  jb      loc_1800191AC
0x180019258  mov     rbx, [r14]
0x18001925b  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x180019261  mov     r9, rsi
0x180019264  mov     rcx, rbx
0x180019267  mov     rdx, rax
0x18001926a  add     rsp, 38h
0x18001926e  pop     r15
0x180019270  pop     r14
0x180019272  pop     rdi
0x180019273  pop     rsi
0x180019274  pop     rbp
0x180019275  pop     rbx
0x180019276  jmp     _TraverseTree
```
