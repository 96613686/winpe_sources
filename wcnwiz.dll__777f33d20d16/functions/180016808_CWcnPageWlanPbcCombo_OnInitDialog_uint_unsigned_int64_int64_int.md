# CWcnPageWlanPbcCombo::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x180016808`
- end: `0x180016a0f`
- name: `?OnInitDialog@CWcnPageWlanPbcCombo@@QEAA_JI_K_JAEAH@Z`
- size: `519`
- prototype: `__int64 __fastcall(CWcnPageWlanPbcCombo *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bf80`

## callees

- `0x18000d630`
- `0x180016808`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001687d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168af`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168f8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001692a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001695c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001698e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800169c0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001687d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168af`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800168f8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001692a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001695c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001698e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800169c0`
- `DUI70!StrToID` at `0x180016871`
- `DUI70!StrToID` at `0x1800168a3`
- `DUI70!StrToID` at `0x1800168ec`
- `DUI70!StrToID` at `0x18001691e`
- `DUI70!StrToID` at `0x180016950`
- `DUI70!StrToID` at `0x180016982`
- `DUI70!StrToID` at `0x1800169b4`
- `DUI70!StrToID` at `0x180016871`
- `DUI70!StrToID` at `0x1800168a3`
- `DUI70!StrToID` at `0x1800168ec`
- `DUI70!StrToID` at `0x18001691e`
- `DUI70!StrToID` at `0x180016950`
- `DUI70!StrToID` at `0x180016982`
- `DUI70!StrToID` at `0x1800169b4`
- `DUI70!?SetMaxLength@TouchEditBase@DirectUI@@QEAAJH@Z` at `0x1800168cd`
- `DUI70!?SetMaxLength@TouchEditBase@DirectUI@@QEAAJH@Z` at `0x1800168cd`

## string_xrefs

- `0x180016867`: `PageWlanPbcCombo_EditKey`
- `0x180016899`: `PageWlanPbcCombo_ErrorMessage`
- `0x1800168e2`: `PageWlanPbcCombo_EditKey_Padding`
- `0x180016914`: `PageWlanPbcCombo_Ring`
- `0x180016946`: `PageWlanPbcCombo_Text`
- `0x180016978`: `PageWlanPbcCombo_Icon`
- `0x1800169aa`: `PageWlanPbcCombo_ProfileMismatchWarning`

## pseudocode

```c
__int64 __fastcall CWcnPageWlanPbcCombo::OnInitDialog(CWcnPageWlanPbcCombo *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  char *v4; // rsi
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  struct DirectUI::Element *Descendent; // rax
  DirectUI::TouchEditBase *v10; // rcx
  DirectUI::Element *v11; // rbx
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  const char *v21; // rax
  __int64 v22; // r10

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 10, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, Indent);
  }
  v4 = (char *)this + 344;
  v5 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 43) + 48LL))((char *)this + 344);
  v6 = StrToID(L"PageWlanPbcCombo_EditKey");
  *((_QWORD *)this + 71) = DirectUI::Element::FindDescendent(v5, v6);
  v7 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 43) + 48LL))((char *)this + 344);
  v8 = StrToID(L"PageWlanPbcCombo_ErrorMessage");
  Descendent = DirectUI::Element::FindDescendent(v7, v8);
  v10 = (DirectUI::TouchEditBase *)*((_QWORD *)this + 71);
  *((_QWORD *)this + 72) = Descendent;
  if ( v10 )
    DirectUI::TouchEditBase::SetMaxLength(v10, 64);
  v11 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 48LL))((char *)this + 344);
  v12 = StrToID(L"PageWlanPbcCombo_EditKey_Padding");
  *((_QWORD *)this + 73) = DirectUI::Element::FindDescendent(v11, v12);
  v13 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 48LL))((char *)this + 344);
  v14 = StrToID(L"PageWlanPbcCombo_Ring");
  *((_QWORD *)this + 70) = DirectUI::Element::FindDescendent(v13, v14);
  v15 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 48LL))((char *)this + 344);
  v16 = StrToID(L"PageWlanPbcCombo_Text");
  *((_QWORD *)this + 74) = DirectUI::Element::FindDescendent(v15, v16);
  v17 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 48LL))((char *)this + 344);
  v18 = StrToID(L"PageWlanPbcCombo_Icon");
  *((_QWORD *)this + 75) = DirectUI::Element::FindDescendent(v17, v18);
  v19 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 48LL))((char *)this + 344);
  v20 = StrToID(L"PageWlanPbcCombo_ProfileMismatchWarning");
  *((_QWORD *)this + 76) = DirectUI::Element::FindDescendent(v19, v20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v21 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v22 + 16), 11, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids, v21);
  }
  return 1;
}

```

## disassembly

```asm
0x180016808  push    rbx
0x18001680a  push    rsi
0x18001680b  push    rdi
0x18001680c  push    r14
0x18001680e  sub     rsp, 28h
0x180016812  mov     rdi, rcx
0x180016815  mov     r10, cs:WPP_GLOBAL_Control
0x18001681c  lea     r14, WPP_GLOBAL_Control
0x180016823  cmp     r10, r14
0x180016826  jz      short loc_180016851
0x180016828  cmp     byte ptr [r10+19h], 6
0x18001682d  jb      short loc_180016851
0x18001682f  mov     ecx, 1; int
0x180016834  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016839  mov     rcx, [r10+10h]
0x18001683d  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x180016844  mov     edx, 0Ah
0x180016849  mov     r9, rax
0x18001684c  call    WPP_SF_s
0x180016851  lea     rsi, [rdi+158h]
0x180016858  mov     rax, [rsi]
0x18001685b  mov     rcx, rsi
0x18001685e  mov     rax, [rax+30h]
0x180016862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016867  lea     rcx, aPagewlanpbccom_6; "PageWlanPbcCombo_EditKey"
0x18001686e  mov     rbx, rax
0x180016871  call    cs:__imp_StrToID
0x180016877  movzx   edx, ax
0x18001687a  mov     rcx, rbx
0x18001687d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016883  mov     [rdi+238h], rax
0x18001688a  mov     rcx, rsi
0x18001688d  mov     rax, [rsi]
0x180016890  mov     rax, [rax+30h]
0x180016894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016899  lea     rcx, aPagewlanpbccom_1; "PageWlanPbcCombo_ErrorMessage"
0x1800168a0  mov     rbx, rax
0x1800168a3  call    cs:__imp_StrToID
0x1800168a9  movzx   edx, ax
0x1800168ac  mov     rcx, rbx
0x1800168af  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800168b5  mov     rcx, [rdi+238h]
0x1800168bc  mov     [rdi+240h], rax
0x1800168c3  test    rcx, rcx
0x1800168c6  jz      short loc_1800168D3
0x1800168c8  mov     edx, 40h ; '@'
0x1800168cd  call    cs:__imp_?SetMaxLength@TouchEditBase@DirectUI@@QEAAJH@Z; DirectUI::TouchEditBase::SetMaxLength(int)
0x1800168d3  mov     rax, [rsi]
0x1800168d6  mov     rcx, rsi
0x1800168d9  mov     rax, [rax+30h]
0x1800168dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e2  lea     rcx, aPagewlanpbccom_2; "PageWlanPbcCombo_EditKey_Padding"
0x1800168e9  mov     rbx, rax
0x1800168ec  call    cs:__imp_StrToID
0x1800168f2  movzx   edx, ax
0x1800168f5  mov     rcx, rbx
0x1800168f8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800168fe  mov     [rdi+248h], rax
0x180016905  mov     rcx, rsi
0x180016908  mov     rax, [rsi]
0x18001690b  mov     rax, [rax+30h]
0x18001690f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016914  lea     rcx, aPagewlanpbccom_5; "PageWlanPbcCombo_Ring"
0x18001691b  mov     rbx, rax
0x18001691e  call    cs:__imp_StrToID
0x180016924  movzx   edx, ax
0x180016927  mov     rcx, rbx
0x18001692a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016930  mov     [rdi+230h], rax
0x180016937  mov     rcx, rsi
0x18001693a  mov     rax, [rsi]
0x18001693d  mov     rax, [rax+30h]
0x180016941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016946  lea     rcx, aPagewlanpbccom_3; "PageWlanPbcCombo_Text"
0x18001694d  mov     rbx, rax
0x180016950  call    cs:__imp_StrToID
0x180016956  movzx   edx, ax
0x180016959  mov     rcx, rbx
0x18001695c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016962  mov     [rdi+250h], rax
0x180016969  mov     rcx, rsi
0x18001696c  mov     rax, [rsi]
0x18001696f  mov     rax, [rax+30h]
0x180016973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016978  lea     rcx, aPagewlanpbccom_4; "PageWlanPbcCombo_Icon"
0x18001697f  mov     rbx, rax
0x180016982  call    cs:__imp_StrToID
0x180016988  movzx   edx, ax
0x18001698b  mov     rcx, rbx
0x18001698e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016994  mov     [rdi+258h], rax
0x18001699b  mov     rcx, rsi
0x18001699e  mov     rax, [rsi]
0x1800169a1  mov     rax, [rax+30h]
0x1800169a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169aa  lea     rcx, aPagewlanpbccom_7; "PageWlanPbcCombo_ProfileMismatchWarning"
0x1800169b1  mov     rbx, rax
0x1800169b4  call    cs:__imp_StrToID
0x1800169ba  movzx   edx, ax
0x1800169bd  mov     rcx, rbx
0x1800169c0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800169c6  mov     [rdi+260h], rax
0x1800169cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800169d4  cmp     r10, r14
0x1800169d7  jz      short loc_180016A00
0x1800169d9  cmp     byte ptr [r10+19h], 6
0x1800169de  jb      short loc_180016A00
0x1800169e0  or      ecx, 0FFFFFFFFh; int
0x1800169e3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800169e8  mov     rcx, [r10+10h]
0x1800169ec  lea     r8, WPP_5d28c7bb4c503e99a1827b75a81abd2f_Traceguids
0x1800169f3  mov     edx, 0Bh
0x1800169f8  mov     r9, rax
0x1800169fb  call    WPP_SF_s
0x180016a00  mov     eax, 1
0x180016a05  add     rsp, 28h
0x180016a09  pop     r14
0x180016a0b  pop     rdi
0x180016a0c  pop     rsi
0x180016a0d  pop     rbx
0x180016a0e  retn
```
