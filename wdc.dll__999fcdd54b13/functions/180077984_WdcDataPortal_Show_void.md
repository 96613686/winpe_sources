# WdcDataPortal::Show(void)

- ea: `0x180077984`
- end: `0x180077ab8`
- name: `?Show@WdcDataPortal@@QEAAJXZ`
- size: `308`
- prototype: `__int64 __fastcall(WdcDataPortal *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18006d734`
- `0x18006eaa0`
- `0x18007751c`
- `0x180077c1c`

## callees

- `0x18000b854`
- `0x180023de4`
- `0x180077984`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180077a25`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180077a25`
- `DUI70!StrToID` at `0x180077a19`
- `DUI70!StrToID` at `0x180077a19`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800779b1`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800779b1`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180077a79`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180077a79`
- `DUI70!?SetExpanded@Expandable@DirectUI@@QEAAJ_N@Z` at `0x1800779bd`
- `DUI70!?SetExpanded@Expandable@DirectUI@@QEAAJ_N@Z` at `0x1800779bd`
- `DUI70!?SetAccState@Element@DirectUI@@QEAAJH@Z` at `0x180077a02`
- `DUI70!?SetAccState@Element@DirectUI@@QEAAJH@Z` at `0x180077a02`
- `DUI70!?SetAlpha@Element@DirectUI@@QEAAJH@Z` at `0x180077a3b`
- `DUI70!?SetAlpha@Element@DirectUI@@QEAAJH@Z` at `0x180077a3b`
- `DUI70!?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180077a47`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077a51`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180077a51`

## pseudocode

```c
__int64 __fastcall WdcDataPortal::Show(WdcDataPortal *this)
{
  unsigned int v2; // edi
  DirectUI::Element *v3; // rcx
  int v4; // eax
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v8; // rbx
  DirectUI::Element *v9; // rcx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+20h] [rbp-28h]
  DirectUI::Element *v14; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v15[4]; // [rsp+38h] [rbp-10h] BYREF

  v2 = 0;
  v3 = (DirectUI::Element *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    v14 = v3;
    v15[0] = 0;
    DirectUI::Element::StartDefer(v3, v15);
    v4 = DirectUI::Expandable::SetExpanded(*((DirectUI::Expandable **)this + 5), 1);
    v2 = v4;
    if ( v4 < 0 )
      goto LABEL_3;
    v4 = DirectUI::Element::SetAccState(*((DirectUI::Element **)this + 5), 512);
    v2 = v4;
    if ( v4 < 0 )
      goto LABEL_3;
    v5 = (DirectUI::Element *)*((_QWORD *)this + 5);
    v6 = StrToID(L"clipperp");
    Descendent = DirectUI::Element::FindDescendent(v5, v6);
    v8 = Descendent;
    if ( Descendent )
    {
      v4 = DirectUI::Element::SetAlpha(Descendent, 255);
      v2 = v4;
      if ( v4 < 0
        || (v4 = DirectUI::Element::RemoveLocalValue(
                   v8,
                   (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::HeightProp),
            v2 = v4,
            v4 < 0) )
      {
LABEL_3:
        v12 = v4;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
          "WdcDataPortal::Show",
          0,
          L"FAILURE: 0x%08x",
          v12);
        DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v14);
        return v2;
      }
    }
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v14);
  }
  v9 = (DirectUI::Element *)*((_QWORD *)this + 19);
  if ( v9 )
  {
    v10 = DirectUI::Element::SetEnabled(v9, 1);
    v2 = v10;
    if ( v10 < 0 )
    {
      v13 = v10;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\portal.cpp",
        "WdcDataPortal::Show",
        0,
        L"FAILURE: 0x%08x",
        v13);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180077984  mov     rax, rsp
0x180077987  mov     [rax+8], rbx
0x18007798b  mov     [rax+10h], rsi
0x18007798f  push    rdi
0x180077990  sub     rsp, 40h
0x180077994  mov     rsi, rcx
0x180077997  xor     edi, edi
0x180077999  mov     rcx, [rcx+28h]
0x18007799d  test    rcx, rcx
0x1800779a0  jz      loc_180077A6B
0x1800779a6  lea     rdx, [rax-10h]
0x1800779aa  mov     [rax-18h], rcx
0x1800779ae  mov     [rax-10h], edi
0x1800779b1  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1800779b7  mov     rcx, [rsi+28h]
0x1800779bb  mov     dl, 1
0x1800779bd  call    cs:__imp_?SetExpanded@Expandable@DirectUI@@QEAAJ_N@Z; DirectUI::Expandable::SetExpanded(bool)
0x1800779c3  mov     edi, eax
0x1800779c5  test    eax, eax
0x1800779c7  jns     short loc_1800779F9
0x1800779c9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800779d0  mov     [rsp+48h+var_28], eax
0x1800779d4  xor     r8d, r8d; int
0x1800779d7  lea     rdx, aWdcdataportalS; "WdcDataPortal::Show"
0x1800779de  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x1800779e5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800779ea  lea     rcx, [rsp+48h+var_18]; this
0x1800779ef  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x1800779f4  jmp     loc_180077AA6
0x1800779f9  mov     rcx, [rsi+28h]
0x1800779fd  mov     edx, 200h
0x180077a02  call    cs:__imp_?SetAccState@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccState(int)
0x180077a08  mov     edi, eax
0x180077a0a  test    eax, eax
0x180077a0c  js      short loc_1800779C9
0x180077a0e  mov     rbx, [rsi+28h]
0x180077a12  lea     rcx, aClipperp; "clipperp"
0x180077a19  call    cs:__imp_StrToID
0x180077a1f  movzx   edx, ax
0x180077a22  mov     rcx, rbx
0x180077a25  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180077a2b  mov     rbx, rax
0x180077a2e  test    rax, rax
0x180077a31  jz      short loc_180077A61
0x180077a33  mov     edx, 0FFh
0x180077a38  mov     rcx, rax
0x180077a3b  call    cs:__imp_?SetAlpha@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAlpha(int)
0x180077a41  mov     edi, eax
0x180077a43  test    eax, eax
0x180077a45  js      short loc_1800779C9
0x180077a47  mov     rdx, cs:__imp_?HeightProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::HeightProp(void)
0x180077a4e  mov     rcx, rbx
0x180077a51  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180077a57  mov     edi, eax
0x180077a59  test    eax, eax
0x180077a5b  js      loc_1800779C9
0x180077a61  lea     rcx, [rsp+48h+var_18]; this
0x180077a66  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180077a6b  mov     rcx, [rsi+98h]
0x180077a72  test    rcx, rcx
0x180077a75  jz      short loc_180077AA6
0x180077a77  mov     dl, 1
0x180077a79  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180077a7f  mov     edi, eax
0x180077a81  test    eax, eax
0x180077a83  jns     short loc_180077AA6
0x180077a85  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180077a8c  mov     [rsp+48h+var_28], eax
0x180077a90  xor     r8d, r8d; int
0x180077a93  lea     rdx, aWdcdataportalS; "WdcDataPortal::Show"
0x180077a9a  lea     rcx, aBaseDiagnosisP_14; "base\\diagnosis\\pdui\\perfmon\\mon\\po"...
0x180077aa1  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180077aa6  mov     rbx, [rsp+48h+arg_0]
0x180077aab  mov     eax, edi
0x180077aad  mov     rsi, [rsp+48h+arg_8]
0x180077ab2  add     rsp, 40h
0x180077ab6  pop     rdi
0x180077ab7  retn
```
