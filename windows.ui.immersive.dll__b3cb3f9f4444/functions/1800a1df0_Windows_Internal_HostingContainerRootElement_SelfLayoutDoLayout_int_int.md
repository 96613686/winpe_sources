# Windows::Internal::HostingContainerRootElement::_SelfLayoutDoLayout(int,int)

- ea: `0x1800a1df0`
- end: `0x1800a2093`
- name: `?_SelfLayoutDoLayout@HostingContainerRootElement@Internal@Windows@@EEAAXHH@Z`
- size: `675`
- prototype: `void __fastcall(Windows::Internal::HostingContainerRootElement *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18005e6b0`
- `0x1800a1df0`

## import_xrefs

- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a1e42`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a1f24`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a1ffd`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a1e42`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a1f24`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a1ffd`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800a1e56`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800a1f36`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800a1f70`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800a1e56`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800a1f36`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800a1f70`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800a1f9a`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800a1f9a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1e23`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1e83`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1f03`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1f5e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1e23`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1e83`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1f03`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a1f5e`
- `DUI70!StrToID` at `0x1800a1e11`
- `DUI70!StrToID` at `0x1800a1e71`
- `DUI70!StrToID` at `0x1800a1ef1`
- `DUI70!StrToID` at `0x1800a1f4c`
- `DUI70!StrToID` at `0x1800a1e11`
- `DUI70!StrToID` at `0x1800a1e71`
- `DUI70!StrToID` at `0x1800a1ef1`
- `DUI70!StrToID` at `0x1800a1f4c`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a1eb3`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a1ede`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a1fda`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a205f`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a1eb3`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a1ede`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a1fda`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800a205f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Internal::HostingContainerRootElement::_SelfLayoutDoLayout(
        Windows::Internal::HostingContainerRootElement *this,
        int a2,
        int a3)
{
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rdi
  unsigned __int16 v8; // ax
  struct DirectUI::Element *v9; // rax
  unsigned __int16 v10; // ax
  struct DirectUI::Element *v11; // rbx
  const struct tagRECT *v12; // r15
  __int64 v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // r13
  int v16; // r12d
  int v17; // edi
  const struct tagRECT *v18; // rax
  LONG bottom; // ecx
  int v20; // edi
  LONG top; // eax
  __int64 v22; // [rsp+40h] [rbp-78h]
  struct DirectUI::Value *v23; // [rsp+48h] [rbp-70h] BYREF
  struct DirectUI::Value *v24; // [rsp+50h] [rbp-68h] BYREF
  const struct tagRECT *Margin; // [rsp+58h] [rbp-60h]
  struct DirectUI::Element *v26; // [rsp+60h] [rbp-58h]
  struct DirectUI::Value *v27; // [rsp+D8h] [rbp+20h] BYREF

  v6 = StrToID(L"TitleBar");
  Descendent = DirectUI::Element::FindDescendent(this, v6);
  v24 = 0;
  Margin = DirectUI::Element::GetMargin(Descendent, &v24);
  v22 = (__int64)*DirectUI::Element::GetDesiredSize(Descendent);
  v8 = StrToID(L"OldTitleBarBackground");
  v9 = DirectUI::Element::FindDescendent(this, v8);
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v9, 0, 0, v22, HIDWORD(v22));
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, Descendent, 0, 0, v22, HIDWORD(v22));
  v10 = StrToID(L"ContentAreaContainer");
  v11 = DirectUI::Element::FindDescendent(this, v10);
  v26 = v11;
  v23 = 0;
  v12 = DirectUI::Element::GetMargin(v11, &v23);
  v13 = (__int64)*DirectUI::Element::GetDesiredSize(v11);
  v14 = StrToID(L"ButtonBar");
  v15 = DirectUI::Element::FindDescendent(this, v14);
  v27 = (struct DirectUI::Value *)*DirectUI::Element::GetDesiredSize(v15);
  v16 = (a2 - (int)v13) / 2;
  if ( DirectUI::Element::GetVisible(v15) )
  {
    v17 = 0;
    if ( a3 - HIDWORD(v27) >= 0 )
      v17 = a3 - HIDWORD(v27);
    DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v15, v16, v17, v13, HIDWORD(v27));
    v27 = 0;
    v18 = DirectUI::Element::GetMargin(v15, &v27);
    bottom = v12->bottom;
    if ( bottom <= v18->top )
      bottom = v18->top;
    v20 = v17 - bottom;
    CValuePtr::Release((CValuePtr *)&v27);
  }
  else
  {
    v20 = a3;
  }
  top = Margin->bottom;
  if ( top <= v12->top )
    top = v12->top;
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v26, v16, top + HIDWORD(v22), v13, v20 - (top + HIDWORD(v22)));
  CValuePtr::Release((CValuePtr *)&v23);
  CValuePtr::Release((CValuePtr *)&v24);
}

```

## disassembly

```asm
0x1800a1df0  push    rbx
0x1800a1df2  push    rbp
0x1800a1df3  push    rsi
0x1800a1df4  push    rdi
0x1800a1df5  push    r12
0x1800a1df7  push    r13
0x1800a1df9  push    r14
0x1800a1dfb  push    r15
0x1800a1dfd  sub     rsp, 78h
0x1800a1e01  mov     esi, r8d
0x1800a1e04  mov     r14d, edx
0x1800a1e07  mov     rbp, rcx
0x1800a1e0a  lea     rcx, aTitlebar; "TitleBar"
0x1800a1e11  call    cs:__imp_StrToID
0x1800a1e18  nop     dword ptr [rax+rax+00h]
0x1800a1e1d  movzx   edx, ax
0x1800a1e20  mov     rcx, rbp
0x1800a1e23  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a1e2a  nop     dword ptr [rax+rax+00h]
0x1800a1e2f  mov     rdi, rax
0x1800a1e32  xor     r12d, r12d
0x1800a1e35  mov     [rsp+0B8h+var_68], r12
0x1800a1e3a  lea     rdx, [rsp+0B8h+var_68]
0x1800a1e3f  mov     rcx, rax
0x1800a1e42  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800a1e49  nop     dword ptr [rax+rax+00h]
0x1800a1e4e  mov     [rsp+0B8h+var_60], rax
0x1800a1e53  mov     rcx, rdi
0x1800a1e56  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x1800a1e5d  nop     dword ptr [rax+rax+00h]
0x1800a1e62  mov     rbx, [rax]
0x1800a1e65  mov     [rsp+0B8h+var_78], rbx
0x1800a1e6a  lea     rcx, aOldtitlebarbac; "OldTitleBarBackground"
0x1800a1e71  call    cs:__imp_StrToID
0x1800a1e78  nop     dword ptr [rax+rax+00h]
0x1800a1e7d  movzx   edx, ax
0x1800a1e80  mov     rcx, rbp
0x1800a1e83  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a1e8a  nop     dword ptr [rax+rax+00h]
0x1800a1e8f  mov     r15d, dword ptr [rsp+0B8h+var_78+4]
0x1800a1e94  mov     [rsp+0B8h+var_80], r15d
0x1800a1e99  mov     [rsp+0B8h+var_88], ebx
0x1800a1e9d  mov     [rsp+0B8h+var_90], r12d
0x1800a1ea2  mov     [rsp+0B8h+var_98], r12d
0x1800a1ea7  mov     r9, rax
0x1800a1eaa  mov     r8d, esi
0x1800a1ead  mov     edx, r14d
0x1800a1eb0  mov     rcx, rbp
0x1800a1eb3  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800a1eba  nop     dword ptr [rax+rax+00h]
0x1800a1ebf  mov     [rsp+0B8h+var_80], r15d
0x1800a1ec4  mov     [rsp+0B8h+var_88], ebx
0x1800a1ec8  mov     [rsp+0B8h+var_90], r12d
0x1800a1ecd  mov     [rsp+0B8h+var_98], r12d
0x1800a1ed2  mov     r9, rdi
0x1800a1ed5  mov     r8d, esi
0x1800a1ed8  mov     edx, r14d
0x1800a1edb  mov     rcx, rbp
0x1800a1ede  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800a1ee5  nop     dword ptr [rax+rax+00h]
0x1800a1eea  lea     rcx, aContentareacon; "ContentAreaContainer"
0x1800a1ef1  call    cs:__imp_StrToID
0x1800a1ef8  nop     dword ptr [rax+rax+00h]
0x1800a1efd  movzx   edx, ax
0x1800a1f00  mov     rcx, rbp
0x1800a1f03  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a1f0a  nop     dword ptr [rax+rax+00h]
0x1800a1f0f  mov     rbx, rax
0x1800a1f12  mov     [rsp+0B8h+var_58], rax
0x1800a1f17  mov     [rsp+0B8h+var_70], r12
0x1800a1f1c  lea     rdx, [rsp+0B8h+var_70]
0x1800a1f21  mov     rcx, rax
0x1800a1f24  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800a1f2b  nop     dword ptr [rax+rax+00h]
0x1800a1f30  mov     r15, rax
0x1800a1f33  mov     rcx, rbx
0x1800a1f36  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x1800a1f3d  nop     dword ptr [rax+rax+00h]
0x1800a1f42  mov     rbx, [rax]
0x1800a1f45  lea     rcx, aButtonbar; "ButtonBar"
0x1800a1f4c  call    cs:__imp_StrToID
0x1800a1f53  nop     dword ptr [rax+rax+00h]
0x1800a1f58  movzx   edx, ax
0x1800a1f5b  mov     rcx, rbp
0x1800a1f5e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a1f65  nop     dword ptr [rax+rax+00h]
0x1800a1f6a  mov     r13, rax
0x1800a1f6d  mov     rcx, rax
0x1800a1f70  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x1800a1f77  nop     dword ptr [rax+rax+00h]
0x1800a1f7c  mov     rcx, [rax]
0x1800a1f7f  mov     [rsp+0B8h+arg_18], rcx
0x1800a1f87  mov     eax, r14d
0x1800a1f8a  sub     eax, ebx
0x1800a1f8c  cdq
0x1800a1f8d  lea     ecx, [r12+2]
0x1800a1f92  idiv    ecx
0x1800a1f94  mov     r12d, eax
0x1800a1f97  mov     rcx, r13
0x1800a1f9a  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800a1fa1  nop     dword ptr [rax+rax+00h]
0x1800a1fa6  test    al, al
0x1800a1fa8  jz      short loc_1800A2025
0x1800a1faa  mov     ecx, esi
0x1800a1fac  mov     edx, dword ptr [rsp+0B8h+arg_18+4]
0x1800a1fb3  sub     ecx, edx
0x1800a1fb5  mov     edi, 0
0x1800a1fba  cmovns  edi, ecx
0x1800a1fbd  mov     [rsp+0B8h+var_80], edx
0x1800a1fc1  mov     [rsp+0B8h+var_88], ebx
0x1800a1fc5  mov     [rsp+0B8h+var_90], edi
0x1800a1fc9  mov     [rsp+0B8h+var_98], r12d
0x1800a1fce  mov     r9, r13
0x1800a1fd1  mov     r8d, esi
0x1800a1fd4  mov     edx, r14d
0x1800a1fd7  mov     rcx, rbp
0x1800a1fda  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800a1fe1  nop     dword ptr [rax+rax+00h]
0x1800a1fe6  mov     [rsp+0B8h+arg_18], 0
0x1800a1ff2  lea     rdx, [rsp+0B8h+arg_18]
0x1800a1ffa  mov     rcx, r13
0x1800a1ffd  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800a2004  nop     dword ptr [rax+rax+00h]
0x1800a2009  mov     ecx, [r15+0Ch]
0x1800a200d  cmp     ecx, [rax+4]
0x1800a2010  cmovle  ecx, [rax+4]
0x1800a2014  sub     edi, ecx
0x1800a2016  lea     rcx, [rsp+0B8h+arg_18]; this
0x1800a201e  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800a2023  jmp     short loc_1800A2027
0x1800a2025  mov     edi, esi
0x1800a2027  mov     rax, [rsp+0B8h+var_60]
0x1800a202c  mov     eax, [rax+0Ch]
0x1800a202f  cmp     eax, [r15+4]
0x1800a2033  cmovle  eax, [r15+4]
0x1800a2038  mov     ecx, dword ptr [rsp+0B8h+var_78+4]
0x1800a203c  add     ecx, eax
0x1800a203e  sub     edi, ecx
0x1800a2040  mov     [rsp+0B8h+var_80], edi
0x1800a2044  mov     [rsp+0B8h+var_88], ebx
0x1800a2048  mov     [rsp+0B8h+var_90], ecx
0x1800a204c  mov     [rsp+0B8h+var_98], r12d
0x1800a2051  mov     r9, [rsp+0B8h+var_58]
0x1800a2056  mov     r8d, esi
0x1800a2059  mov     edx, r14d
0x1800a205c  mov     rcx, rbp
0x1800a205f  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800a2066  nop     dword ptr [rax+rax+00h]
0x1800a206b  nop
0x1800a206c  lea     rcx, [rsp+0B8h+var_70]; this
0x1800a2071  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800a2076  nop
0x1800a2077  lea     rcx, [rsp+0B8h+var_68]; this
0x1800a207c  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800a2081  add     rsp, 78h
0x1800a2085  pop     r15
0x1800a2087  pop     r14
0x1800a2089  pop     r13
0x1800a208b  pop     r12
0x1800a208d  pop     rdi
0x1800a208e  pop     rsi
0x1800a208f  pop     rbp
0x1800a2090  pop     rbx
0x1800a2091  retn
```
