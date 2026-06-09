# CShareMediaCore::_UpdateStatusText(void)

- ea: `0x1800120ec`
- end: `0x180012359`
- name: `?_UpdateStatusText@CShareMediaCore@@AEAAJXZ`
- size: `621`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180009900`
- `0x18000b78c`
- `0x18000ec90`
- `0x18000f020`
- `0x180010bec`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x180008e84`
- `0x18000a3d4`
- `0x18000d810`
- `0x1800120ec`

## import_xrefs

- `USER32!LoadStringW` at `0x18001225e`
- `USER32!LoadStringW` at `0x18001225e`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800122a3`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800122a3`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001226c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012293`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18001226c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012293`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800122d1`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800122ff`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800122d1`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800122ff`
- `DUI70!StrToID` at `0x18001217f`
- `DUI70!StrToID` at `0x1800122b4`
- `DUI70!StrToID` at `0x1800122e2`
- `DUI70!StrToID` at `0x18001217f`
- `DUI70!StrToID` at `0x1800122b4`
- `DUI70!StrToID` at `0x1800122e2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001218b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800122c0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800122ee`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001218b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800122c0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800122ee`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_UpdateStatusText(CShareMediaCore *this)
{
  _QWORD *v2; // rcx
  int v3; // r14d
  CShareWithList *v4; // rcx
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // r12
  __int64 v8; // rcx
  bool v9; // di
  bool v10; // r15
  CShareWithList *v11; // rcx
  UINT v12; // r13d
  int v13; // ebx
  WCHAR *v14; // rdx
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  DirectUI::Element *v17; // rax
  DirectUI::Element *v18; // rbx
  unsigned __int16 v19; // ax
  DirectUI::Element *v20; // rax
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Buffer[152]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 7) )
  {
    v4 = (CShareWithList *)*((_QWORD *)this + 7);
    v23[0] = 0;
    CShareWithList::GetAutoAllowDevices(v4, 0, v23);
    v5 = (DirectUI::Element *)*((_QWORD *)this + 2);
    v6 = StrToID(L"SharingStatusLabel");
    Descendent = DirectUI::Element::FindDescendent(v5, v6);
    if ( !Descendent )
    {
      v3 = -2147467259;
LABEL_21:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    v8 = *((_QWORD *)this + 7);
    v9 = 1;
    v22 = 0;
    v10 = 1;
    v3 = CShareWithList::AllAuthorizationsMatch(v8, 2, &v22);
    if ( v3 >= 0 )
    {
      v11 = (CShareWithList *)*((_QWORD *)this + 7);
      if ( v22 )
      {
        v12 = 60;
        CShareWithList::GetAutoAllowDevices(v11, 1, v23);
        v13 = v23[0];
        CShareWithList::SetAutoAllowDevices(*((CShareWithList **)this + 7), 0, v23[0]);
        v9 = v13 == 0;
LABEL_14:
        memset_0(Buffer, 0, 0x12Cu);
        LoadStringW(g_hinst, v12, Buffer, 150);
        DirectUI::Element::SetContentString(Descendent, Buffer);
        v14 = Buffer;
LABEL_17:
        DirectUI::Element::SetAccName(Descendent, v14);
        v15 = (DirectUI::Element *)*((_QWORD *)this + 2);
        v16 = StrToID(L"AllowAllButton");
        v17 = DirectUI::Element::FindDescendent(v15, v16);
        if ( v17 )
          DirectUI::Element::SetEnabled(v17, v9);
        v18 = (DirectUI::Element *)*((_QWORD *)this + 2);
        v19 = StrToID(L"BlockAllButton");
        v20 = DirectUI::Element::FindDescendent(v18, v19);
        if ( v20 )
          DirectUI::Element::SetEnabled(v20, v10);
        goto LABEL_21;
      }
      CShareWithList::SetAutoAllowDevices(v11, 0, 0);
      v3 = CShareWithList::AllAuthorizationsMatch(*((_QWORD *)this + 7), 3, &v22);
      if ( v3 >= 0 )
      {
        if ( v22 )
        {
          v12 = 71;
          v10 = 0;
          goto LABEL_14;
        }
        CShareWithList::GetAutoAllowDevices(*((CShareWithList **)this + 7), 0, v23);
      }
    }
    DirectUI::Element::SetContentString(Descendent, &word_180023190);
    v14 = (WCHAR *)&word_180023190;
    goto LABEL_17;
  }
  v3 = -2147024809;
LABEL_22:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 76, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800120ec  push    rbp
0x1800120ee  push    rbx
0x1800120ef  push    rsi
0x1800120f0  push    rdi
0x1800120f1  push    r12
0x1800120f3  push    r13
0x1800120f5  push    r14
0x1800120f7  push    r15
0x1800120f9  lea     rbp, [rsp-78h]
0x1800120fe  sub     rsp, 178h
0x180012105  mov     rax, cs:__security_cookie
0x18001210c  xor     rax, rsp
0x18001210f  mov     [rbp+0B0h+var_50], rax
0x180012113  mov     rsi, rcx
0x180012116  mov     rcx, cs:WPP_GLOBAL_Control
0x18001211d  lea     rax, WPP_GLOBAL_Control
0x180012124  cmp     rcx, rax
0x180012127  jz      short loc_18001214B
0x180012129  test    byte ptr [rcx+1Ch], 20h
0x18001212d  jz      short loc_18001214B
0x18001212f  mov     rcx, [rcx+10h]
0x180012133  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18001213a  mov     edx, 4Bh ; 'K'
0x18001213f  call    WPP_SF_
0x180012144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001214b  xor     r13d, r13d
0x18001214e  cmp     [rsi+38h], r13
0x180012152  jnz     short loc_18001215F
0x180012154  mov     r14d, 80070057h
0x18001215a  jmp     loc_18001230C
0x18001215f  mov     rcx, [rsi+38h]; this
0x180012163  lea     r8, [rsp+1B0h+var_18C]; int *
0x180012168  xor     edx, edx; int
0x18001216a  mov     [rsp+1B0h+var_18C], r13d
0x18001216f  call    ?GetAutoAllowDevices@CShareWithList@@QEAAJHPEAH@Z; CShareWithList::GetAutoAllowDevices(int,int *)
0x180012174  mov     rbx, [rsi+10h]
0x180012178  lea     rcx, aSharingstatusl; "SharingStatusLabel"
0x18001217f  call    cs:__imp_StrToID
0x180012185  movzx   edx, ax
0x180012188  mov     rcx, rbx
0x18001218b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012191  mov     r12, rax
0x180012194  test    rax, rax
0x180012197  jnz     short loc_1800121A4
0x180012199  mov     r14d, 80004005h
0x18001219f  jmp     loc_180012305
0x1800121a4  mov     rcx, [rsi+38h]
0x1800121a8  lea     r8, [rsp+1B0h+var_190]
0x1800121ad  mov     edi, 1
0x1800121b2  mov     [rsp+1B0h+var_190], r13d
0x1800121b7  mov     r15b, dil
0x1800121ba  lea     edx, [rdi+1]
0x1800121bd  call    ?AllAuthorizationsMatch@CShareWithList@@QEAAJW4AuthorizationStatus@@PEAH@Z; CShareWithList::AllAuthorizationsMatch(AuthorizationStatus,int *)
0x1800121c2  mov     r14d, eax
0x1800121c5  test    eax, eax
0x1800121c7  js      loc_180012289
0x1800121cd  mov     rcx, [rsi+38h]; this
0x1800121d1  cmp     [rsp+1B0h+var_190], r13d
0x1800121d6  jz      short loc_180012203
0x1800121d8  lea     r8, [rsp+1B0h+var_18C]; int *
0x1800121dd  mov     edx, edi; int
0x1800121df  lea     r13d, [rdi+3Bh]
0x1800121e3  call    ?GetAutoAllowDevices@CShareWithList@@QEAAJHPEAH@Z; CShareWithList::GetAutoAllowDevices(int,int *)
0x1800121e8  mov     ebx, [rsp+1B0h+var_18C]
0x1800121ec  xor     edx, edx; int
0x1800121ee  mov     rcx, [rsi+38h]; this
0x1800121f2  mov     r8d, ebx; int
0x1800121f5  call    ?SetAutoAllowDevices@CShareWithList@@QEAAJHH@Z; CShareWithList::SetAutoAllowDevices(int,int)
0x1800121fa  test    ebx, ebx
0x1800121fc  jz      short loc_180012237
0x1800121fe  xor     dil, dil
0x180012201  jmp     short loc_180012237
0x180012203  xor     r8d, r8d; int
0x180012206  xor     edx, edx; int
0x180012208  call    ?SetAutoAllowDevices@CShareWithList@@QEAAJHH@Z; CShareWithList::SetAutoAllowDevices(int,int)
0x18001220d  mov     rcx, [rsi+38h]
0x180012211  lea     r8, [rsp+1B0h+var_190]
0x180012216  mov     edx, 3
0x18001221b  call    ?AllAuthorizationsMatch@CShareWithList@@QEAAJW4AuthorizationStatus@@PEAH@Z; CShareWithList::AllAuthorizationsMatch(AuthorizationStatus,int *)
0x180012220  mov     r14d, eax
0x180012223  test    eax, eax
0x180012225  js      short loc_180012289
0x180012227  cmp     [rsp+1B0h+var_190], r13d
0x18001222c  jz      short loc_180012279
0x18001222e  mov     r13d, 47h ; 'G'
0x180012234  xor     r15b, r15b
0x180012237  xor     edx, edx; Val
0x180012239  lea     rcx, [rsp+1B0h+Buffer]; void *
0x18001223e  mov     r8d, 12Ch; Size
0x180012244  call    memset_0
0x180012249  mov     rcx, cs:g_hinst; hInstance
0x180012250  lea     r8, [rsp+1B0h+Buffer]; lpBuffer
0x180012255  mov     r9d, 96h; cchBufferMax
0x18001225b  mov     edx, r13d; uID
0x18001225e  call    cs:__imp_LoadStringW
0x180012264  lea     rdx, [rsp+1B0h+Buffer]
0x180012269  mov     rcx, r12
0x18001226c  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180012272  lea     rdx, [rsp+1B0h+Buffer]
0x180012277  jmp     short loc_1800122A0
0x180012279  mov     rcx, [rsi+38h]; this
0x18001227d  lea     r8, [rsp+1B0h+var_18C]; int *
0x180012282  xor     edx, edx; int
0x180012284  call    ?GetAutoAllowDevices@CShareWithList@@QEAAJHPEAH@Z; CShareWithList::GetAutoAllowDevices(int,int *)
0x180012289  lea     rdx, word_180023190
0x180012290  mov     rcx, r12
0x180012293  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180012299  lea     rdx, word_180023190
0x1800122a0  mov     rcx, r12
0x1800122a3  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x1800122a9  mov     rbx, [rsi+10h]
0x1800122ad  lea     rcx, aAllowallbutton; "AllowAllButton"
0x1800122b4  call    cs:__imp_StrToID
0x1800122ba  movzx   edx, ax
0x1800122bd  mov     rcx, rbx
0x1800122c0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800122c6  test    rax, rax
0x1800122c9  jz      short loc_1800122D7
0x1800122cb  mov     dl, dil
0x1800122ce  mov     rcx, rax
0x1800122d1  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x1800122d7  mov     rbx, [rsi+10h]
0x1800122db  lea     rcx, aBlockallbutton; "BlockAllButton"
0x1800122e2  call    cs:__imp_StrToID
0x1800122e8  movzx   edx, ax
0x1800122eb  mov     rcx, rbx
0x1800122ee  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800122f4  test    rax, rax
0x1800122f7  jz      short loc_180012305
0x1800122f9  mov     dl, r15b
0x1800122fc  mov     rcx, rax
0x1800122ff  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180012305  mov     rcx, cs:WPP_GLOBAL_Control
0x18001230c  lea     rax, WPP_GLOBAL_Control
0x180012313  cmp     rcx, rax
0x180012316  jz      short loc_180012336
0x180012318  test    byte ptr [rcx+1Ch], 20h
0x18001231c  jz      short loc_180012336
0x18001231e  mov     rcx, [rcx+10h]
0x180012322  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180012329  mov     edx, 4Ch ; 'L'
0x18001232e  mov     r9d, r14d
0x180012331  call    WPP_SF_d
0x180012336  mov     eax, r14d
0x180012339  mov     rcx, [rbp+0B0h+var_50]
0x18001233d  xor     rcx, rsp; StackCookie
0x180012340  call    __security_check_cookie
0x180012345  add     rsp, 178h
0x18001234c  pop     r15
0x18001234e  pop     r14
0x180012350  pop     r13
0x180012352  pop     r12
0x180012354  pop     rdi
0x180012355  pop     rsi
0x180012356  pop     rbx
0x180012357  pop     rbp
0x180012358  retn
```
