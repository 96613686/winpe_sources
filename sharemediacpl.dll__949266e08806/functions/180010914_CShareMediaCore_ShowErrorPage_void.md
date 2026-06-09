# CShareMediaCore::_ShowErrorPage(void)

- ea: `0x180010914`
- end: `0x180010be5`
- name: `?_ShowErrorPage@CShareMediaCore@@AEAAJXZ`
- size: `721`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c3d0`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x180010914`
- `0x180012c58`

## import_xrefs

- `USER32!LoadStringW` at `0x180010ad8`
- `USER32!LoadStringW` at `0x180010ad8`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010af4`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010af4`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010ae6`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180010ae6`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180010b51`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180010b51`
- `DUI70!StrToID` at `0x1800109d0`
- `DUI70!StrToID` at `0x180010a07`
- `DUI70!StrToID` at `0x180010a5e`
- `DUI70!StrToID` at `0x180010a98`
- `DUI70!StrToID` at `0x180010b05`
- `DUI70!StrToID` at `0x180010b35`
- `DUI70!StrToID` at `0x1800109d0`
- `DUI70!StrToID` at `0x180010a07`
- `DUI70!StrToID` at `0x180010a5e`
- `DUI70!StrToID` at `0x180010a98`
- `DUI70!StrToID` at `0x180010b05`
- `DUI70!StrToID` at `0x180010b35`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800109dc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010a13`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010a6a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010aa4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010b11`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010b41`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800109dc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010a13`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010a6a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010aa4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010b11`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010b41`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800109ef`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010a26`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010a87`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010b24`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800109ef`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010a26`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010a87`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180010b24`

## string_xrefs

- `0x180010a4b`: `LaunchServicesLinkArea`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_ShowErrorPage(CShareMediaCore *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  unsigned int v5; // esi
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rax
  UINT v12; // esi
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rax
  int v16; // edx
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // rbx
  DirectUI::Element *v20; // rbx
  unsigned __int16 v21; // ax
  DirectUI::Element *v22; // rax
  DirectUI::Element *v23; // rbx
  unsigned __int16 v24; // ax
  DirectUI::Element *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+38h] [rbp-C8h] BYREF
  int *v31; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[504]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    v29 = 0;
    v31 = &v29;
    v32 = 4;
    McGenEventWrite_EventWriteTransfer(
      (__int64)v4,
      (const EVENT_DESCRIPTOR *)ShareMediaCPL_ShowErrorPage_Start,
      a3,
      2u,
      &v30);
  }
  v5 = 0;
  v30.Ptr = (ULONGLONG)L"ShareMediaNormalArea";
  *(_QWORD *)&v30.Size = L"ShareMediaWarningArea";
  do
  {
    v6 = (DirectUI::Element *)*((_QWORD *)this + 2);
    v7 = StrToID(*(&v30.Ptr + (int)v5));
    Descendent = DirectUI::Element::FindDescendent(v6, v7);
    if ( Descendent )
      DirectUI::Element::SetLayoutPos(Descendent, -3);
    ++v5;
  }
  while ( v5 < 2 );
  v9 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v10 = StrToID(L"ShareMediaErrorArea");
  v11 = DirectUI::Element::FindDescendent(v9, v10);
  if ( v11 )
    DirectUI::Element::SetLayoutPos(v11, 1);
  v12 = 78;
  if ( *((_DWORD *)this + 47) == 2 )
  {
    g_bfSqm_USAGE |= 0x200000u;
    v12 = 79;
  }
  v13 = (DirectUI::Element *)*((_QWORD *)this + 2);
  if ( (*((_BYTE *)this + 52) & 0x40) != 0 )
    v12 = 81;
  v14 = StrToID(L"LaunchServicesLinkArea");
  v15 = DirectUI::Element::FindDescendent(v13, v14);
  if ( v15 )
  {
    v16 = 1;
    if ( v12 != 79 )
      v16 = -3;
    DirectUI::Element::SetLayoutPos(v15, v16);
  }
  v17 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v18 = StrToID(L"ShareMediaErrorText");
  v19 = DirectUI::Element::FindDescendent(v17, v18);
  if ( v19 )
  {
    memset_0(Buffer, 0, 0x3E8u);
    LoadStringW(g_hinst, v12, Buffer, 500);
    DirectUI::Element::SetContentString(v19, Buffer);
    DirectUI::Element::SetAccName(v19, Buffer);
  }
  v20 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v21 = StrToID(L"FooterArea");
  v22 = DirectUI::Element::FindDescendent(v20, v21);
  if ( v22 )
    DirectUI::Element::SetLayoutPos(v22, 3);
  v23 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v24 = StrToID(L"OKButton");
  v25 = DirectUI::Element::FindDescendent(v23, v24);
  if ( v25 )
    DirectUI::Element::SetEnabled(v25, 0);
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    v29 = 0;
    v31 = &v29;
    v32 = 4;
    McGenEventWrite_EventWriteTransfer(v26, (const EVENT_DESCRIPTOR *)ShareMediaCPL_ShowErrorPage_Stop, v27, 2u, &v30);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180010914  push    rbp
0x180010916  push    rbx
0x180010917  push    rsi
0x180010918  push    rdi
0x180010919  lea     rbp, [rsp-368h]
0x180010921  sub     rsp, 468h
0x180010928  mov     rax, cs:__security_cookie
0x18001092f  xor     rax, rsp
0x180010932  mov     [rbp+380h+var_30], rax
0x180010939  mov     rdi, rcx
0x18001093c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010943  lea     rax, WPP_GLOBAL_Control
0x18001094a  cmp     rcx, rax
0x18001094d  jz      short loc_18001096A
0x18001094f  test    byte ptr [rcx+1Ch], 20h
0x180010953  jz      short loc_18001096A
0x180010955  mov     rcx, [rcx+10h]
0x180010959  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180010960  mov     edx, 2Bh ; '+'
0x180010965  call    WPP_SF_
0x18001096a  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x180010971  jz      short loc_1800109AA
0x180010973  lea     rax, [rsp+480h+var_450]
0x180010978  mov     [rsp+480h+var_450], 0
0x180010980  mov     [rsp+480h+var_438], rax
0x180010985  lea     rdx, ShareMediaCPL_ShowErrorPage_Start
0x18001098c  lea     rax, [rsp+480h+var_448]
0x180010991  mov     [rsp+480h+var_430], 4
0x18001099a  mov     r9d, 2
0x1800109a0  mov     [rsp+480h+var_460], rax
0x1800109a5  call    McGenEventWrite_EventWriteTransfer
0x1800109aa  lea     rax, aSharemedianorm; "ShareMediaNormalArea"
0x1800109b1  xor     esi, esi
0x1800109b3  mov     [rsp+480h+var_448], rax
0x1800109b8  lea     rax, aSharemediawarn_1; "ShareMediaWarningArea"
0x1800109bf  mov     [rsp+480h+var_440], rax
0x1800109c4  mov     rbx, [rdi+10h]
0x1800109c8  movsxd  rcx, esi
0x1800109cb  mov     rcx, [rsp+rcx*8+480h+var_448]
0x1800109d0  call    cs:__imp_StrToID
0x1800109d6  movzx   edx, ax
0x1800109d9  mov     rcx, rbx
0x1800109dc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800109e2  test    rax, rax
0x1800109e5  jz      short loc_1800109F5
0x1800109e7  mov     edx, 0FFFFFFFDh
0x1800109ec  mov     rcx, rax
0x1800109ef  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800109f5  inc     esi
0x1800109f7  cmp     esi, 2
0x1800109fa  jb      short loc_1800109C4
0x1800109fc  mov     rbx, [rdi+10h]
0x180010a00  lea     rcx, aSharemediaerro; "ShareMediaErrorArea"
0x180010a07  call    cs:__imp_StrToID
0x180010a0d  movzx   edx, ax
0x180010a10  mov     rcx, rbx
0x180010a13  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010a19  test    rax, rax
0x180010a1c  jz      short loc_180010A2C
0x180010a1e  mov     edx, 1
0x180010a23  mov     rcx, rax
0x180010a26  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180010a2c  cmp     dword ptr [rdi+0BCh], 2
0x180010a33  mov     esi, 4Eh ; 'N'
0x180010a38  jnz     short loc_180010A47
0x180010a3a  bts     cs:?g_bfSqm_USAGE@@3KA, 15h; ulong g_bfSqm_USAGE
0x180010a42  mov     esi, 4Fh ; 'O'
0x180010a47  test    byte ptr [rdi+34h], 40h
0x180010a4b  lea     rcx, aLaunchservices; "LaunchServicesLinkArea"
0x180010a52  mov     rbx, [rdi+10h]
0x180010a56  mov     eax, 51h ; 'Q'
0x180010a5b  cmovnz  esi, eax
0x180010a5e  call    cs:__imp_StrToID
0x180010a64  movzx   edx, ax
0x180010a67  mov     rcx, rbx
0x180010a6a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010a70  test    rax, rax
0x180010a73  jz      short loc_180010A8D
0x180010a75  mov     rcx, rax
0x180010a78  mov     edx, 1
0x180010a7d  cmp     esi, 4Fh ; 'O'
0x180010a80  jz      short loc_180010A87
0x180010a82  mov     edx, 0FFFFFFFDh
0x180010a87  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180010a8d  mov     rbx, [rdi+10h]
0x180010a91  lea     rcx, aSharemediaerro_0; "ShareMediaErrorText"
0x180010a98  call    cs:__imp_StrToID
0x180010a9e  movzx   edx, ax
0x180010aa1  mov     rcx, rbx
0x180010aa4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010aaa  mov     rbx, rax
0x180010aad  test    rax, rax
0x180010ab0  jz      short loc_180010AFA
0x180010ab2  xor     edx, edx; Val
0x180010ab4  lea     rcx, [rsp+480h+Buffer]; void *
0x180010ab9  mov     r8d, 3E8h; Size
0x180010abf  call    memset_0
0x180010ac4  mov     rcx, cs:g_hinst; hInstance
0x180010acb  lea     r8, [rsp+480h+Buffer]; lpBuffer
0x180010ad0  mov     r9d, 1F4h; cchBufferMax
0x180010ad6  mov     edx, esi; uID
0x180010ad8  call    cs:__imp_LoadStringW
0x180010ade  lea     rdx, [rsp+480h+Buffer]
0x180010ae3  mov     rcx, rbx
0x180010ae6  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180010aec  lea     rdx, [rsp+480h+Buffer]
0x180010af1  mov     rcx, rbx
0x180010af4  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180010afa  mov     rbx, [rdi+10h]
0x180010afe  lea     rcx, aFooterarea; "FooterArea"
0x180010b05  call    cs:__imp_StrToID
0x180010b0b  movzx   edx, ax
0x180010b0e  mov     rcx, rbx
0x180010b11  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010b17  test    rax, rax
0x180010b1a  jz      short loc_180010B2A
0x180010b1c  mov     edx, 3
0x180010b21  mov     rcx, rax
0x180010b24  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180010b2a  mov     rbx, [rdi+10h]
0x180010b2e  lea     rcx, aOkbutton; "OKButton"
0x180010b35  call    cs:__imp_StrToID
0x180010b3b  movzx   edx, ax
0x180010b3e  mov     rcx, rbx
0x180010b41  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010b47  test    rax, rax
0x180010b4a  jz      short loc_180010B57
0x180010b4c  xor     edx, edx
0x180010b4e  mov     rcx, rax
0x180010b51  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180010b57  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x180010b5e  jz      short loc_180010B97
0x180010b60  lea     rax, [rsp+480h+var_450]
0x180010b65  mov     [rsp+480h+var_450], 0
0x180010b6d  mov     [rsp+480h+var_438], rax
0x180010b72  lea     rdx, ShareMediaCPL_ShowErrorPage_Stop
0x180010b79  lea     rax, [rsp+480h+var_448]
0x180010b7e  mov     [rsp+480h+var_430], 4
0x180010b87  mov     r9d, 2
0x180010b8d  mov     [rsp+480h+var_460], rax
0x180010b92  call    McGenEventWrite_EventWriteTransfer
0x180010b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b9e  lea     rax, WPP_GLOBAL_Control
0x180010ba5  cmp     rcx, rax
0x180010ba8  jz      short loc_180010BC8
0x180010baa  test    byte ptr [rcx+1Ch], 20h
0x180010bae  jz      short loc_180010BC8
0x180010bb0  mov     rcx, [rcx+10h]
0x180010bb4  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180010bbb  mov     edx, 2Ch ; ','
0x180010bc0  xor     r9d, r9d
0x180010bc3  call    WPP_SF_d
0x180010bc8  xor     eax, eax
0x180010bca  mov     rcx, [rbp+380h+var_30]
0x180010bd1  xor     rcx, rsp; StackCookie
0x180010bd4  call    __security_check_cookie
0x180010bd9  add     rsp, 468h
0x180010be0  pop     rdi
0x180010be1  pop     rsi
0x180010be2  pop     rbx
0x180010be3  pop     rbp
0x180010be4  retn
```
