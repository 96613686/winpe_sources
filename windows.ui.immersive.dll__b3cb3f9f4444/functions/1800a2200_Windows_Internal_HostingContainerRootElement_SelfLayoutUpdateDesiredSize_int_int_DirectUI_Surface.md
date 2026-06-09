# Windows::Internal::HostingContainerRootElement::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x1800a2200`
- end: `0x1800a23d9`
- name: `?_SelfLayoutUpdateDesiredSize@HostingContainerRootElement@Internal@Windows@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `473`
- prototype: `struct tagSIZE __fastcall(Windows::Internal::HostingContainerRootElement *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18005e6b0`
- `0x1800a2200`

## import_xrefs

- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a225f`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a22c8`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a233b`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a225f`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a22c8`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800a233b`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800a231c`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800a231c`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a2284`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a2363`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a23a3`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a2284`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a2363`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800a23a3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a2241`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a22a9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a230a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a2241`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a22a9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800a230a`
- `DUI70!StrToID` at `0x1800a222f`
- `DUI70!StrToID` at `0x1800a2297`
- `DUI70!StrToID` at `0x1800a22f8`
- `DUI70!StrToID` at `0x1800a222f`
- `DUI70!StrToID` at `0x1800a2297`
- `DUI70!StrToID` at `0x1800a22f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct tagSIZE __fastcall Windows::Internal::HostingContainerRootElement::_SelfLayoutUpdateDesiredSize(
        Windows::Internal::HostingContainerRootElement *this,
        _DWORD *a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  unsigned int v4; // esi
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbx
  const struct tagRECT *Margin; // rdi
  unsigned __int16 v10; // ax
  const struct tagRECT *v11; // rax
  LONG bottom; // ecx
  int v13; // esi
  unsigned int v14; // r15d
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rsi
  LONG top; // ebx
  LONG v18; // edi
  int v19; // r15d
  unsigned __int64 v20; // r9
  struct DirectUI::Value *v22; // [rsp+30h] [rbp-48h] BYREF
  struct DirectUI::Value *v23; // [rsp+38h] [rbp-40h] BYREF
  struct DirectUI::Value *v24; // [rsp+40h] [rbp-38h] BYREF
  char v25; // [rsp+48h] [rbp-30h] BYREF
  int v26; // [rsp+4Ch] [rbp-2Ch]
  const struct tagRECT *v27; // [rsp+50h] [rbp-28h]
  _BYTE v28[4]; // [rsp+58h] [rbp-20h] BYREF
  int v29; // [rsp+5Ch] [rbp-1Ch]
  DirectUI::Element *v30; // [rsp+60h] [rbp-18h]

  v4 = (unsigned int)a4;
  *a2 = a3;
  a2[1] = (_DWORD)a4;
  v7 = StrToID(L"TitleBar");
  Descendent = DirectUI::Element::FindDescendent(this, v7);
  v24 = 0;
  Margin = DirectUI::Element::GetMargin(Descendent, &v24);
  DirectUI::Element::_UpdateDesiredSize(Descendent, (unsigned int)&v25, a3, (struct DirectUI::Surface *)v4);
  v10 = StrToID(L"ContentAreaContainer");
  v30 = DirectUI::Element::FindDescendent(this, v10);
  v23 = 0;
  v11 = DirectUI::Element::GetMargin(v30, &v23);
  v27 = v11;
  bottom = Margin->bottom;
  if ( bottom <= v11->top )
    bottom = v11->top;
  v13 = v4 - bottom - v26;
  v14 = 0;
  if ( v13 >= 0 )
    v14 = v13;
  v15 = StrToID(L"ButtonBar");
  v16 = DirectUI::Element::FindDescendent(this, v15);
  if ( DirectUI::Element::GetVisible(v16) )
  {
    v22 = 0;
    top = DirectUI::Element::GetMargin(v16, &v22)->top;
    v18 = v27->bottom;
    DirectUI::Element::_UpdateDesiredSize(v16, (unsigned int)v28, a3, (struct DirectUI::Surface *)v14);
    if ( v18 <= top )
      v18 = top;
    v19 = v14 - v18 - v29;
    CValuePtr::Release((CValuePtr *)&v22);
    v20 = 0;
    if ( v19 >= 0 )
      v20 = (unsigned int)v19;
  }
  else
  {
    v20 = v14;
  }
  DirectUI::Element::_UpdateDesiredSize(v30, (unsigned int)v28, a3, (struct DirectUI::Surface *)v20);
  CValuePtr::Release((CValuePtr *)&v23);
  CValuePtr::Release((CValuePtr *)&v24);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x1800a2200  mov     [rsp-40h+arg_8], rdx
0x1800a2205  push    rbp
0x1800a2206  push    rbx
0x1800a2207  push    rsi
0x1800a2208  push    rdi
0x1800a2209  push    r12
0x1800a220b  push    r13
0x1800a220d  push    r14
0x1800a220f  push    r15
0x1800a2211  mov     rbp, rsp
0x1800a2214  sub     rsp, 78h
0x1800a2218  mov     esi, r9d
0x1800a221b  mov     r12d, r8d
0x1800a221e  mov     r14, rcx
0x1800a2221  mov     [rdx], r8d
0x1800a2224  mov     [rdx+4], r9d
0x1800a2228  lea     rcx, aTitlebar; "TitleBar"
0x1800a222f  call    cs:__imp_StrToID
0x1800a2236  nop     dword ptr [rax+rax+00h]
0x1800a223b  movzx   edx, ax
0x1800a223e  mov     rcx, r14
0x1800a2241  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a2248  nop     dword ptr [rax+rax+00h]
0x1800a224d  mov     rbx, rax
0x1800a2250  mov     [rbp+var_38], 0
0x1800a2258  lea     rdx, [rbp+var_38]
0x1800a225c  mov     rcx, rax
0x1800a225f  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800a2266  nop     dword ptr [rax+rax+00h]
0x1800a226b  mov     rdi, rax
0x1800a226e  mov     r13, [rbp+arg_20]
0x1800a2272  mov     [rsp+78h+var_58], r13
0x1800a2277  mov     r9d, esi
0x1800a227a  mov     r8d, r12d
0x1800a227d  lea     rdx, [rbp+var_30]
0x1800a2281  mov     rcx, rbx
0x1800a2284  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x1800a228b  nop     dword ptr [rax+rax+00h]
0x1800a2290  lea     rcx, aContentareacon; "ContentAreaContainer"
0x1800a2297  call    cs:__imp_StrToID
0x1800a229e  nop     dword ptr [rax+rax+00h]
0x1800a22a3  movzx   edx, ax
0x1800a22a6  mov     rcx, r14
0x1800a22a9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a22b0  nop     dword ptr [rax+rax+00h]
0x1800a22b5  mov     [rbp+var_18], rax
0x1800a22b9  mov     [rbp+var_40], 0
0x1800a22c1  lea     rdx, [rbp+var_40]
0x1800a22c5  mov     rcx, rax
0x1800a22c8  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800a22cf  nop     dword ptr [rax+rax+00h]
0x1800a22d4  mov     [rbp+var_28], rax
0x1800a22d8  mov     ecx, [rdi+0Ch]
0x1800a22db  cmp     ecx, [rax+4]
0x1800a22de  cmovle  ecx, [rax+4]
0x1800a22e2  sub     esi, ecx
0x1800a22e4  sub     esi, [rbp+var_2C]
0x1800a22e7  mov     r15d, 0
0x1800a22ed  cmovns  r15d, esi
0x1800a22f1  lea     rcx, aButtonbar; "ButtonBar"
0x1800a22f8  call    cs:__imp_StrToID
0x1800a22ff  nop     dword ptr [rax+rax+00h]
0x1800a2304  movzx   edx, ax
0x1800a2307  mov     rcx, r14
0x1800a230a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800a2311  nop     dword ptr [rax+rax+00h]
0x1800a2316  mov     rsi, rax
0x1800a2319  mov     rcx, rax
0x1800a231c  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800a2323  nop     dword ptr [rax+rax+00h]
0x1800a2328  test    al, al
0x1800a232a  jz      short loc_1800A2390
0x1800a232c  mov     [rbp+var_48], 0
0x1800a2334  lea     rdx, [rbp+var_48]
0x1800a2338  mov     rcx, rsi
0x1800a233b  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800a2342  nop     dword ptr [rax+rax+00h]
0x1800a2347  mov     ebx, [rax+4]
0x1800a234a  mov     rdi, [rbp+var_28]
0x1800a234e  mov     edi, [rdi+0Ch]
0x1800a2351  mov     [rsp+78h+var_58], r13
0x1800a2356  mov     r9d, r15d
0x1800a2359  mov     r8d, r12d
0x1800a235c  lea     rdx, [rbp+var_20]
0x1800a2360  mov     rcx, rsi
0x1800a2363  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x1800a236a  nop     dword ptr [rax+rax+00h]
0x1800a236f  cmp     edi, ebx
0x1800a2371  cmovle  edi, ebx
0x1800a2374  sub     r15d, edi
0x1800a2377  sub     r15d, [rbp+var_1C]
0x1800a237b  lea     rcx, [rbp+var_48]; this
0x1800a237f  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800a2384  xor     r9d, r9d
0x1800a2387  test    r15d, r15d
0x1800a238a  cmovns  r9d, r15d
0x1800a238e  jmp     short loc_1800A2393
0x1800a2390  mov     r9d, r15d
0x1800a2393  mov     [rsp+78h+var_58], r13
0x1800a2398  mov     r8d, r12d
0x1800a239b  lea     rdx, [rbp+var_20]
0x1800a239f  mov     rcx, [rbp+var_18]
0x1800a23a3  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x1800a23aa  nop     dword ptr [rax+rax+00h]
0x1800a23af  nop
0x1800a23b0  lea     rcx, [rbp+var_40]; this
0x1800a23b4  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800a23b9  nop
0x1800a23ba  lea     rcx, [rbp+var_38]; this
0x1800a23be  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800a23c3  mov     rax, [rbp+arg_8]
0x1800a23c7  add     rsp, 78h
0x1800a23cb  pop     r15
0x1800a23cd  pop     r14
0x1800a23cf  pop     r13
0x1800a23d1  pop     r12
0x1800a23d3  pop     rdi
0x1800a23d4  pop     rsi
0x1800a23d5  pop     rbx
0x1800a23d6  pop     rbp
0x1800a23d7  retn
```
