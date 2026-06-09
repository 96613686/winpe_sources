# Windows::Internal::DialogRootElement::_SelfLayoutDoLayout(int,int)

- ea: `0x1800987b0`
- end: `0x180098a95`
- name: `?_SelfLayoutDoLayout@DialogRootElement@Internal@Windows@@EEAAXHH@Z`
- size: `741`
- prototype: `void __fastcall(Windows::Internal::DialogRootElement *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18005e6b0`
- `0x1800987b0`

## import_xrefs

- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800987e1`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800987e1`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098876`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098896`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800988b6`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098876`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180098896`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x1800988b6`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009882b`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180098841`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180098854`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009882b`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180098841`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180098854`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800988c9`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800988fa`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800988c9`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x1800988fa`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180098972`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800989e2`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180098a18`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180098a45`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180098972`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x1800989e2`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180098a18`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180098a45`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::DialogRootElement::_SelfLayoutDoLayout(
        Windows::Internal::DialogRootElement *this,
        int a2,
        int a3)
{
  __int64 Children; // rax
  _QWORD *v7; // rdx
  int v8; // ecx
  DirectUI::Element *v9; // r14
  __int64 v10; // rax
  DirectUI::Element *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rbx
  int v15; // r14d
  LONG left; // r14d
  bool v17; // al
  int v18; // ecx
  LONG bottom; // ecx
  int v20; // eax
  int v21; // edx
  DirectUI::Element *v22; // [rsp+40h] [rbp-39h]
  struct DirectUI::Element *v23; // [rsp+48h] [rbp-31h]
  DirectUI::Element *v24; // [rsp+50h] [rbp-29h]
  struct DirectUI::Value *v25; // [rsp+60h] [rbp-19h] BYREF
  struct DirectUI::Value *v26; // [rsp+68h] [rbp-11h] BYREF
  struct DirectUI::Value *v27; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+78h] [rbp-1h] BYREF
  const struct tagRECT *Margin; // [rsp+80h] [rbp+7h]
  __int64 v30; // [rsp+88h] [rbp+Fh]
  const struct tagRECT *v31; // [rsp+90h] [rbp+17h]
  bool Visible; // [rsp+E8h] [rbp+6Fh]
  int v33; // [rsp+F0h] [rbp+77h]
  const struct tagRECT *v34; // [rsp+F8h] [rbp+7Fh]
  int v35; // [rsp+F8h] [rbp+7Fh]

  v28 = 0;
  Children = DirectUI::Element::GetChildren(this, &v28);
  v7 = (_QWORD *)(Children + 8);
  v8 = *(_DWORD *)Children & 0x10000000;
  v9 = *(DirectUI::Element **)(Children + 8);
  v23 = v9;
  if ( v8 )
  {
    v10 = *(_QWORD *)(Children + 8);
    v9 = *(DirectUI::Element **)v9;
    v23 = v9;
  }
  else
  {
    v10 = Children + 8;
  }
  v11 = *(DirectUI::Element **)(v10 + 8);
  v24 = v11;
  if ( v8 )
    v7 = (_QWORD *)*v7;
  v22 = (DirectUI::Element *)v7[2];
  v12 = (__int64)*DirectUI::Element::GetDesiredSize(v9);
  v13 = (__int64)*DirectUI::Element::GetDesiredSize(v11);
  v14 = (__int64)*DirectUI::Element::GetDesiredSize(v22);
  v30 = v14;
  v27 = 0;
  Margin = DirectUI::Element::GetMargin(v9, &v27);
  v26 = 0;
  v34 = DirectUI::Element::GetMargin(v24, &v26);
  v25 = 0;
  v31 = DirectUI::Element::GetMargin(v22, &v25);
  Visible = DirectUI::Element::GetVisible(v9);
  v15 = 0;
  if ( Visible )
  {
    left = v34->left;
    if ( v34->left <= Margin->right )
      left = Margin->right;
    v15 = v12 + left;
  }
  v17 = DirectUI::Element::GetVisible(v22);
  v18 = 0;
  if ( v17 )
  {
    bottom = v34->bottom;
    if ( bottom <= v31->top )
      bottom = v31->top;
    v18 = HIDWORD(v30) + bottom;
  }
  v33 = a3 - v18;
  if ( (int)v13 + v15 <= a2 )
  {
    v20 = (a2 - (int)v13) / 2;
    if ( (int)v13 < (int)v14 )
      LODWORD(v14) = v13;
    v21 = 0;
    if ( v20 - v15 >= 0 )
      v21 = v20 - v15;
    v35 = v21;
    if ( v20 - v15 >= 0 )
      v15 = (a2 - (int)v13) / 2;
    DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v22, v13 + v15 - v14, a3 - HIDWORD(v30), v14, HIDWORD(v30));
    if ( Visible )
      DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v23, v35, 0, v12, HIDWORD(v12));
  }
  else
  {
    LODWORD(v13) = 0;
    if ( a2 - v15 >= 0 )
      LODWORD(v13) = a2 - v15;
    if ( (int)v13 < (int)v14 )
      LODWORD(v14) = v13;
    DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v22, a2 - v14, a3 - HIDWORD(v30), v14, HIDWORD(v30));
    if ( Visible )
      DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v23, 0, 0, v12, HIDWORD(v12));
  }
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v24, v15, 0, v13, v33);
  CValuePtr::Release((CValuePtr *)&v25);
  CValuePtr::Release((CValuePtr *)&v26);
  CValuePtr::Release((CValuePtr *)&v27);
  CValuePtr::Release((CValuePtr *)&v28);
}

```

## disassembly

```asm
0x1800987b0  mov     [rsp-8+arg_0], rbx
0x1800987b5  push    rbp
0x1800987b6  push    rsi
0x1800987b7  push    rdi
0x1800987b8  push    r12
0x1800987ba  push    r13
0x1800987bc  push    r14
0x1800987be  push    r15
0x1800987c0  lea     rbp, [rsp-27h]
0x1800987c5  sub     rsp, 0A0h
0x1800987cc  mov     r12d, r8d
0x1800987cf  mov     r15d, edx
0x1800987d2  mov     r13, rcx
0x1800987d5  mov     [rbp+57h+var_58], 0
0x1800987dd  lea     rdx, [rbp+57h+var_58]
0x1800987e1  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1800987e8  nop     dword ptr [rax+rax+00h]
0x1800987ed  lea     rdx, [rax+8]
0x1800987f1  mov     ecx, [rax]
0x1800987f3  and     ecx, 10000000h
0x1800987f9  mov     r14, [rdx]
0x1800987fc  mov     [rbp+57h+var_88], r14
0x180098800  jz      short loc_18009880E
0x180098802  mov     rax, r14
0x180098805  mov     r14, [r14]
0x180098808  mov     [rbp+57h+var_88], r14
0x18009880c  jmp     short loc_180098811
0x18009880e  mov     rax, rdx
0x180098811  mov     rbx, [rax+8]
0x180098815  mov     [rbp+57h+var_80], rbx
0x180098819  test    ecx, ecx
0x18009881b  jz      short loc_180098820
0x18009881d  mov     rdx, [rdx]
0x180098820  mov     rax, [rdx+10h]
0x180098824  mov     [rbp+57h+var_90], rax
0x180098828  mov     rcx, r14
0x18009882b  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x180098832  nop     dword ptr [rax+rax+00h]
0x180098837  mov     rdi, [rax]
0x18009883a  mov     [rbp+57h+var_78], rdi
0x18009883e  mov     rcx, rbx
0x180098841  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x180098848  nop     dword ptr [rax+rax+00h]
0x18009884d  mov     rsi, [rax]
0x180098850  mov     rcx, [rbp+57h+var_90]
0x180098854  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18009885b  nop     dword ptr [rax+rax+00h]
0x180098860  mov     rbx, [rax]
0x180098863  mov     [rbp+57h+var_48], rbx
0x180098867  mov     [rbp+57h+var_60], 0
0x18009886f  lea     rdx, [rbp+57h+var_60]
0x180098873  mov     rcx, r14
0x180098876  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009887d  nop     dword ptr [rax+rax+00h]
0x180098882  mov     [rbp+57h+var_50], rax
0x180098886  mov     [rbp+57h+var_68], 0
0x18009888e  lea     rdx, [rbp+57h+var_68]
0x180098892  mov     rcx, [rbp+57h+var_80]
0x180098896  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009889d  nop     dword ptr [rax+rax+00h]
0x1800988a2  mov     [rbp+57h+arg_18], rax
0x1800988a6  mov     [rbp+57h+var_70], 0
0x1800988ae  lea     rdx, [rbp+57h+var_70]
0x1800988b2  mov     rcx, [rbp+57h+var_90]
0x1800988b6  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x1800988bd  nop     dword ptr [rax+rax+00h]
0x1800988c2  mov     [rbp+57h+var_40], rax
0x1800988c6  mov     rcx, r14
0x1800988c9  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x1800988d0  nop     dword ptr [rax+rax+00h]
0x1800988d5  mov     [rbp+57h+arg_8], al
0x1800988d8  xor     r14d, r14d
0x1800988db  test    al, al
0x1800988dd  jz      short loc_1800988F6
0x1800988df  mov     r14, [rbp+57h+arg_18]
0x1800988e3  mov     r14d, [r14]
0x1800988e6  mov     rax, [rbp+57h+var_50]
0x1800988ea  cmp     r14d, [rax+8]
0x1800988ee  cmovle  r14d, [rax+8]
0x1800988f3  add     r14d, edi
0x1800988f6  mov     rcx, [rbp+57h+var_90]
0x1800988fa  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180098901  nop     dword ptr [rax+rax+00h]
0x180098906  xor     ecx, ecx
0x180098908  mov     r8d, dword ptr [rbp+57h+var_48+4]
0x18009890c  test    al, al
0x18009890e  jz      short loc_180098925
0x180098910  mov     rax, [rbp+57h+arg_18]
0x180098914  mov     ecx, [rax+0Ch]
0x180098917  mov     rax, [rbp+57h+var_40]
0x18009891b  cmp     ecx, [rax+4]
0x18009891e  cmovle  ecx, [rax+4]
0x180098922  add     ecx, r8d
0x180098925  mov     eax, r12d
0x180098928  sub     eax, ecx
0x18009892a  mov     [rbp+57h+arg_10], eax
0x18009892d  lea     eax, [rsi+r14]
0x180098931  mov     [rsp+0D0h+var_98], r8d
0x180098936  mov     r9, [rbp+57h+var_90]
0x18009893a  cmp     eax, r15d
0x18009893d  mov     eax, r15d
0x180098940  jle     short loc_18009899E
0x180098942  sub     eax, r14d
0x180098945  mov     esi, 0
0x18009894a  cmovns  esi, eax
0x18009894d  cmp     esi, ebx
0x18009894f  cmovl   ebx, esi
0x180098952  mov     ecx, r12d
0x180098955  sub     ecx, r8d
0x180098958  mov     eax, r15d
0x18009895b  sub     eax, ebx
0x18009895d  mov     [rsp+0D0h+var_A0], ebx
0x180098961  mov     [rsp+0D0h+var_A8], ecx
0x180098965  mov     [rsp+0D0h+var_B0], eax
0x180098969  mov     r8d, r12d
0x18009896c  mov     edx, r15d
0x18009896f  mov     rcx, r13
0x180098972  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x180098979  nop     dword ptr [rax+rax+00h]
0x18009897e  xor     ebx, ebx
0x180098980  cmp     [rbp+57h+arg_8], bl
0x180098983  jz      loc_180098A24
0x180098989  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18009898c  mov     [rsp+0D0h+var_98], eax
0x180098990  mov     [rsp+0D0h+var_A0], edi
0x180098994  mov     [rsp+0D0h+var_A8], ebx
0x180098998  mov     [rsp+0D0h+var_B0], ebx
0x18009899c  jmp     short loc_180098A0B
0x18009899e  sub     eax, esi
0x1800989a0  cdq
0x1800989a1  mov     ecx, 2
0x1800989a6  idiv    ecx
0x1800989a8  mov     ecx, eax
0x1800989aa  cmp     esi, ebx
0x1800989ac  cmovl   ebx, esi
0x1800989af  xor     edx, edx
0x1800989b1  sub     ecx, r14d
0x1800989b4  cmovns  edx, ecx
0x1800989b7  mov     dword ptr [rbp+57h+arg_18], edx
0x1800989ba  test    ecx, ecx
0x1800989bc  cmovns  r14d, eax
0x1800989c0  mov     ecx, r12d
0x1800989c3  sub     ecx, r8d
0x1800989c6  mov     eax, r14d
0x1800989c9  sub     eax, ebx
0x1800989cb  add     eax, esi
0x1800989cd  mov     [rsp+0D0h+var_A0], ebx
0x1800989d1  mov     [rsp+0D0h+var_A8], ecx
0x1800989d5  mov     [rsp+0D0h+var_B0], eax
0x1800989d9  mov     r8d, r12d
0x1800989dc  mov     edx, r15d
0x1800989df  mov     rcx, r13
0x1800989e2  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x1800989e9  nop     dword ptr [rax+rax+00h]
0x1800989ee  xor     ebx, ebx
0x1800989f0  cmp     [rbp+57h+arg_8], bl
0x1800989f3  jz      short loc_180098A24
0x1800989f5  mov     eax, dword ptr [rbp+57h+var_78+4]
0x1800989f8  mov     [rsp+0D0h+var_98], eax
0x1800989fc  mov     [rsp+0D0h+var_A0], edi
0x180098a00  mov     [rsp+0D0h+var_A8], ebx
0x180098a04  mov     eax, dword ptr [rbp+57h+arg_18]
0x180098a07  mov     [rsp+0D0h+var_B0], eax
0x180098a0b  mov     r9, [rbp+57h+var_88]
0x180098a0f  mov     r8d, r12d
0x180098a12  mov     edx, r15d
0x180098a15  mov     rcx, r13
0x180098a18  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x180098a1f  nop     dword ptr [rax+rax+00h]
0x180098a24  mov     eax, [rbp+57h+arg_10]
0x180098a27  mov     [rsp+0D0h+var_98], eax
0x180098a2b  mov     [rsp+0D0h+var_A0], esi
0x180098a2f  mov     [rsp+0D0h+var_A8], ebx
0x180098a33  mov     [rsp+0D0h+var_B0], r14d
0x180098a38  mov     r9, [rbp+57h+var_80]
0x180098a3c  mov     r8d, r12d
0x180098a3f  mov     edx, r15d
0x180098a42  mov     rcx, r13
0x180098a45  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x180098a4c  nop     dword ptr [rax+rax+00h]
0x180098a51  nop
0x180098a52  lea     rcx, [rbp+57h+var_70]; this
0x180098a56  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098a5b  nop
0x180098a5c  lea     rcx, [rbp+57h+var_68]; this
0x180098a60  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098a65  nop
0x180098a66  lea     rcx, [rbp+57h+var_60]; this
0x180098a6a  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098a6f  nop
0x180098a70  lea     rcx, [rbp+57h+var_58]; this
0x180098a74  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180098a79  mov     rbx, [rsp+0D0h+arg_0]
0x180098a81  add     rsp, 0A0h
0x180098a88  pop     r15
0x180098a8a  pop     r14
0x180098a8c  pop     r13
0x180098a8e  pop     r12
0x180098a90  pop     rdi
0x180098a91  pop     rsi
0x180098a92  pop     rbp
0x180098a93  retn
```
