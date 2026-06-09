# CardStateCacheFindOrAddItem(_CARD_MATCH_DATA *,_CARD_STATE * *,int *)

- ea: `0x180031a94`
- end: `0x180031f8f`
- name: `?CardStateCacheFindOrAddItem@@YAKPEAU_CARD_MATCH_DATA@@PEAPEAU_CARD_STATE@@PEAH@Z`
- size: `1275`
- prototype: `unsigned int __fastcall(struct _CARD_MATCH_DATA *, struct _CARD_STATE **, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180032770`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x180013734`
- `0x180013aac`
- `0x180013c94`
- `0x18002ce34`
- `0x18002e034`
- `0x18002e65c`
- `0x18002e7a0`
- `0x18002eb6c`
- `0x180030c84`
- `0x180031a94`
- `0x1800321f8`
- `0x1800335ec`
- `0x180036984`
- `0x18003ae44`
- `0x18003aec8`
- `0x18003c240`

## pseudocode

```c
__int64 __fastcall CardStateCacheFindOrAddItem(struct _CARD_MATCH_DATA *a1, struct _CARD_STATE **a2, int *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int CardLookupName; // ebx
  __int64 v9; // rcx
  unsigned int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  unsigned int v13; // eax
  struct _CARD_STATE *v14; // rdi
  int v15; // r13d
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rcx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  char *v23; // rcx
  struct _CARD_STATE *v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h]
  void **v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  void **v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v31[264]; // [rsp+60h] [rbp-A0h] BYREF

  v25 = 0;
  memset_0(v31, 0, 0x208u);
  v26 = 0;
  v27 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v29 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v28 = 0;
  v30 = 0;
  WppTraceIndent(v6, 0);
  v7 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( !a2 )
  {
    CardLookupName = 87;
    goto LABEL_47;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v29, (char *)*a2 + 624);
  if ( !*((_QWORD *)*a2 + 1) )
  {
    CardLookupName = 87;
    WppTraceIndent(v9, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        v11,
        (__int64)"(*ppCardState)->pCardData");
    }
    goto LABEL_47;
  }
  *a3 = 1;
  CardLookupName = GetCardLookupName(*a2, v31, v10);
  if ( CardLookupName )
  {
    WppTraceIndent(v12, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        CardLookupName);
    }
    goto LABEL_47;
  }
  v13 = ScCacheGetOrAddCardState(*((_QWORD *)a1 + 2), *a2, *((_QWORD *)a1 + 3), *((_QWORD *)*a2 + 69), v31, &v25);
  v14 = v25;
  CardLookupName = v13;
  if ( v13 )
  {
    v7 = v13 + 2146434960;
    v15 = 0;
    if ( (unsigned int)v7 <= 1 )
      CardLookupName = 0;
    goto LABEL_42;
  }
  v15 = 1;
  CardLookupName = CspEnterCriticalSection((char *)v25 + 624);
  if ( CardLookupName )
  {
    WppTraceIndent(v16, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 77;
LABEL_23:
      WPP_SF_sd(
        *(_QWORD *)(v7 + 16),
        v17,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        CardLookupName);
    }
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v27, (char *)v14 + 624);
    StringCbCopyW((unsigned __int16 *)v14 + 16, 0x208u, (const unsigned __int16 *)*a2 + 16);
    if ( !*((_QWORD *)v14 + 1) )
    {
      *((_QWORD *)v14 + 1) = *((_QWORD *)*a2 + 1);
      *((_QWORD *)*a2 + 1) = 0;
      *((_DWORD *)*a2 + 155) = 0;
      *(_QWORD *)(*((_QWORD *)v14 + 1) + 80LL) = v14;
      *a3 = 0;
    }
    CardLookupName = ValidateCardHandle(v14);
    if ( v26 )
      CspRemoveCachedPin((__int64)v14, *((_DWORD *)a1 + 303), 1u);
    if ( !CardLookupName )
      goto LABEL_39;
    CardLookupName = MakeCardHandles(
                       (struct _CARD_MATCH_DATA *)((char *)a1 + 56),
                       (unsigned __int64 *)(*((_QWORD *)v14 + 1) + 96LL),
                       (unsigned __int64 *)(*((_QWORD *)v14 + 1) + 104LL));
    if ( CardLookupName )
    {
      WppTraceIndent(v18, 2u);
      v7 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v21, (char)v14, CardLookupName);
      }
      goto LABEL_42;
    }
    CardLookupName = GetCardActivityCount(*(_QWORD *)(*((_QWORD *)v14 + 1) + 96LL));
    if ( !CardLookupName )
    {
LABEL_39:
      v23 = (char *)*a2 + 624;
      v30 = 0;
      CspLeaveCriticalSection(v23);
      v28 = 0;
      CspLeaveCriticalSection((char *)v14 + 624);
      CardStateReleaseRef(*a2, 0);
      CspEnterCriticalSection((char *)v14 + 624);
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v27, (char *)v14 + 624);
      *a2 = v14;
      goto LABEL_47;
    }
    WppTraceIndent(v22, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 79;
      goto LABEL_23;
    }
  }
LABEL_42:
  if ( v14 )
  {
    if ( v28 )
    {
      v28 = 0;
      CspLeaveCriticalSection((char *)v14 + 624);
    }
    if ( v15 )
      CardStateReleaseRef(v14, 0);
  }
LABEL_47:
  v28 = 0;
  v30 = 0;
  WppTraceIndent(v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardLookupName);
  }
  v29 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v29);
  v27 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v27);
  return CardLookupName;
}

```

## disassembly

```asm
0x180031a94  mov     [rsp-8+arg_18], rbx
0x180031a99  push    rbp
0x180031a9a  push    rsi
0x180031a9b  push    rdi
0x180031a9c  push    r12
0x180031a9e  push    r13
0x180031aa0  push    r14
0x180031aa2  push    r15
0x180031aa4  lea     rbp, [rsp-180h]
0x180031aac  sub     rsp, 280h
0x180031ab3  mov     rax, cs:__security_cookie
0x180031aba  xor     rax, rsp
0x180031abd  mov     [rbp+1B0h+var_40], rax
0x180031ac4  mov     r12, r8
0x180031ac7  mov     [rsp+2B0h+var_280], 0
0x180031ad0  mov     rsi, rdx
0x180031ad3  mov     r15, rcx
0x180031ad6  xor     edx, edx; Val
0x180031ad8  lea     rcx, [rsp+2B0h+var_250]; void *
0x180031add  mov     r8d, 208h; Size
0x180031ae3  call    memset_0
0x180031ae8  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180031aef  mov     [rsp+2B0h+var_278], 0
0x180031af7  xor     edx, edx
0x180031af9  mov     [rsp+2B0h+var_270], rdi
0x180031afe  mov     [rsp+2B0h+var_260], rdi
0x180031b03  mov     [rsp+2B0h+var_268], 0
0x180031b0c  mov     [rsp+2B0h+var_258], 0
0x180031b15  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b21  lea     rax, WPP_GLOBAL_Control
0x180031b28  mov     r14d, 2
0x180031b2e  cmp     rcx, rax
0x180031b31  jz      short loc_180031B5A
0x180031b33  test    [rcx+1Ch], r14b
0x180031b37  jz      short loc_180031B5A
0x180031b39  cmp     byte ptr [rcx+19h], 5
0x180031b3d  jb      short loc_180031B5A
0x180031b3f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180031b46  lea     edx, [r14+48h]
0x180031b4a  mov     rcx, [rcx+10h]
0x180031b4e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180031b55  call    WPP_SF_s
0x180031b5a  test    rsi, rsi
0x180031b5d  jnz     short loc_180031B6E
0x180031b5f  lea     ebx, [rsi+57h]
0x180031b62  lea     rsi, WPP_GLOBAL_Control
0x180031b69  jmp     loc_180031EF1
0x180031b6e  mov     rdx, [rsi]
0x180031b71  lea     rcx, [rsp+2B0h+var_260]
0x180031b76  add     rdx, 270h
0x180031b7d  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180031b82  mov     rax, [rsi]
0x180031b85  cmp     qword ptr [rax+8], 0
0x180031b8a  jnz     short loc_180031BE8
0x180031b8c  mov     edx, r14d
0x180031b8f  mov     ebx, 57h ; 'W'
0x180031b94  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ba0  lea     rsi, WPP_GLOBAL_Control
0x180031ba7  cmp     rcx, rsi
0x180031baa  jz      loc_180031EF1
0x180031bb0  test    byte ptr [rcx+1Ch], 1
0x180031bb4  jz      loc_180031EF1
0x180031bba  cmp     [rcx+19h], r14b
0x180031bbe  jb      loc_180031EF1
0x180031bc4  mov     rcx, [rcx+10h]
0x180031bc8  lea     rax, aPpcardstatePca; "(*ppCardState)->pCardData"
0x180031bcf  lea     edx, [rbx-0Ch]
0x180031bd2  mov     [rsp+2B0h+var_290], rax
0x180031bd7  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180031bde  call    WPP_SF_ss
0x180031be3  jmp     loc_180031EF1
0x180031be8  mov     dword ptr [r12], 1
0x180031bf0  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180031bf5  mov     rcx, [rsi]; struct _CARD_STATE *
0x180031bf8  call    ?GetCardLookupName@@YAKPEAU_CARD_STATE@@PEAGK@Z; GetCardLookupName(_CARD_STATE *,ushort *,ulong)
0x180031bfd  mov     ebx, eax
0x180031bff  test    eax, eax
0x180031c01  jz      short loc_180031C5B
0x180031c03  mov     edx, r14d
0x180031c06  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c12  lea     rsi, WPP_GLOBAL_Control
0x180031c19  cmp     rcx, rsi
0x180031c1c  jz      loc_180031EF1
0x180031c22  test    byte ptr [rcx+1Ch], 1
0x180031c26  jz      loc_180031EF1
0x180031c2c  cmp     [rcx+19h], r14b
0x180031c30  jb      loc_180031EF1
0x180031c36  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180031c3d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180031c44  mov     rcx, [rcx+10h]
0x180031c48  mov     edx, 4Ch ; 'L'
0x180031c4d  mov     dword ptr [rsp+2B0h+var_290], ebx
0x180031c51  call    WPP_SF_sd
0x180031c56  jmp     loc_180031EF1
0x180031c5b  mov     rdx, [rsi]
0x180031c5e  lea     rax, [rsp+2B0h+var_280]
0x180031c63  mov     r8, [r15+18h]
0x180031c67  mov     rcx, [r15+10h]
0x180031c6b  mov     [rsp+2B0h+var_288], rax
0x180031c70  lea     rax, [rsp+2B0h+var_250]
0x180031c75  mov     r9, [rdx+228h]
0x180031c7c  mov     [rsp+2B0h+var_290], rax
0x180031c81  call    ScCacheGetOrAddCardState
0x180031c86  mov     rdi, [rsp+2B0h+var_280]
0x180031c8b  mov     ebx, eax
0x180031c8d  test    eax, eax
0x180031c8f  jnz     loc_180031EA1
0x180031c95  lea     r14, [rdi+270h]
0x180031c9c  mov     rcx, r14
0x180031c9f  lea     r13d, [rax+1]
0x180031ca3  call    CspEnterCriticalSection
0x180031ca8  mov     ebx, eax
0x180031caa  test    eax, eax
0x180031cac  jz      short loc_180031D09
0x180031cae  lea     r14d, [r13+1]
0x180031cb2  mov     edx, r14d
0x180031cb5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180031cc1  lea     rsi, WPP_GLOBAL_Control
0x180031cc8  cmp     rcx, rsi
0x180031ccb  jz      loc_180031EB9
0x180031cd1  test    [rcx+1Ch], r13b
0x180031cd5  jz      loc_180031EB9
0x180031cdb  cmp     [rcx+19h], r14b
0x180031cdf  jb      loc_180031EB9
0x180031ce5  lea     edx, [r13+4Ch]
0x180031ce9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180031cf0  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180031cf7  mov     rcx, [rcx+10h]
0x180031cfb  mov     dword ptr [rsp+2B0h+var_290], ebx
0x180031cff  call    WPP_SF_sd
0x180031d04  jmp     loc_180031EB9
0x180031d09  mov     rdx, r14
0x180031d0c  lea     rcx, [rsp+2B0h+var_270]
0x180031d11  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180031d16  mov     r8, [rsi]
0x180031d19  lea     rcx, [rdi+20h]; unsigned __int16 *
0x180031d1d  add     r8, 20h ; ' '; unsigned __int16 *
0x180031d21  mov     edx, 208h; unsigned __int64
0x180031d26  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180031d2b  xor     edx, edx
0x180031d2d  cmp     [rdi+8], rdx
0x180031d31  jnz     short loc_180031D5A
0x180031d33  mov     rax, [rsi]
0x180031d36  mov     rcx, [rax+8]
0x180031d3a  mov     [rdi+8], rcx
0x180031d3e  mov     rax, [rsi]
0x180031d41  mov     [rax+8], rdx
0x180031d45  mov     rax, [rsi]
0x180031d48  mov     [rax+26Ch], edx
0x180031d4e  mov     rax, [rdi+8]
0x180031d52  mov     [rax+50h], rdi
0x180031d56  mov     [r12], edx
0x180031d5a  lea     r8, [rsp+2B0h+var_278]
0x180031d5f  mov     rcx, rdi; struct _CARD_STATE *
0x180031d62  call    ValidateCardHandle
0x180031d67  cmp     [rsp+2B0h+var_278], 0
0x180031d6c  mov     ebx, eax
0x180031d6e  jz      short loc_180031D82
0x180031d70  mov     edx, [r15+4BCh]
0x180031d77  mov     r8d, r13d
0x180031d7a  mov     rcx, rdi
0x180031d7d  call    CspRemoveCachedPin
0x180031d82  test    ebx, ebx
0x180031d84  jz      loc_180031E4D
0x180031d8a  mov     rdx, [rdi+8]
0x180031d8e  lea     rcx, [r15+38h]; struct _CARD_DATA_INFO *
0x180031d92  lea     r8, [rdx+68h]; unsigned __int64 *
0x180031d96  add     rdx, 60h ; '`'; unsigned __int64 *
0x180031d9a  call    ?MakeCardHandles@@YAKPEAU_CARD_DATA_INFO@@PEA_K1@Z; MakeCardHandles(_CARD_DATA_INFO *,unsigned __int64 *,unsigned __int64 *)
0x180031d9f  mov     ebx, eax
0x180031da1  test    eax, eax
0x180031da3  jz      short loc_180031DF5
0x180031da5  mov     r14d, 2
0x180031dab  mov     edx, r14d
0x180031dae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dba  lea     rsi, WPP_GLOBAL_Control
0x180031dc1  cmp     rcx, rsi
0x180031dc4  jz      loc_180031EB9
0x180031dca  test    [rcx+1Ch], r13b
0x180031dce  jz      loc_180031EB9
0x180031dd4  cmp     [rcx+19h], r14b
0x180031dd8  jb      loc_180031EB9
0x180031dde  mov     rcx, [rcx+10h]
0x180031de2  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180031de6  mov     [rsp+2B0h+var_290], rdi
0x180031deb  call    WPP_SF_sqD
0x180031df0  jmp     loc_180031EB9
0x180031df5  mov     rcx, [rdi+8]
0x180031df9  lea     r8, [rdi+2C0h]
0x180031e00  lea     rdx, [rdi+20h]
0x180031e04  mov     rcx, [rcx+60h]; hContext
0x180031e08  call    GetCardActivityCount
0x180031e0d  mov     ebx, eax
0x180031e0f  test    eax, eax
0x180031e11  jz      short loc_180031E4D
0x180031e13  mov     r14d, 2
0x180031e19  mov     edx, r14d
0x180031e1c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e28  lea     rsi, WPP_GLOBAL_Control
0x180031e2f  cmp     rcx, rsi
0x180031e32  jz      loc_180031EB9
0x180031e38  test    [rcx+1Ch], r13b
0x180031e3c  jz      short loc_180031EB9
0x180031e3e  cmp     [rcx+19h], r14b
0x180031e42  jb      short loc_180031EB9
0x180031e44  lea     edx, [r14+4Dh]
0x180031e48  jmp     loc_180031CE9
0x180031e4d  mov     rcx, [rsi]
0x180031e50  add     rcx, 270h
0x180031e57  mov     [rsp+2B0h+var_258], 0
0x180031e60  call    CspLeaveCriticalSection
0x180031e65  mov     rcx, r14
0x180031e68  mov     [rsp+2B0h+var_268], 0
0x180031e71  call    CspLeaveCriticalSection
0x180031e76  mov     rcx, [rsi]
0x180031e79  xor     edx, edx
0x180031e7b  call    CardStateReleaseRef
0x180031e80  mov     rcx, r14
0x180031e83  call    CspEnterCriticalSection
0x180031e88  mov     rdx, r14
0x180031e8b  lea     rcx, [rsp+2B0h+var_270]
0x180031e90  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180031e95  mov     [rsi], rdi
0x180031e98  lea     rsi, WPP_GLOBAL_Control
0x180031e9f  jmp     short loc_180031EEA
0x180031ea1  lea     ecx, [rax+7FEFFF90h]
0x180031ea7  xor     r13d, r13d
0x180031eaa  xor     eax, eax
0x180031eac  lea     rsi, WPP_GLOBAL_Control
0x180031eb3  cmp     ecx, 1
0x180031eb6  cmovbe  ebx, eax
0x180031eb9  test    rdi, rdi
0x180031ebc  jz      short loc_180031EEA
0x180031ebe  cmp     [rsp+2B0h+var_268], 0
0x180031ec4  jz      short loc_180031EDB
0x180031ec6  lea     rcx, [rdi+270h]
0x180031ecd  mov     [rsp+2B0h+var_268], 0
0x180031ed6  call    CspLeaveCriticalSection
0x180031edb  test    r13d, r13d
0x180031ede  jz      short loc_180031EEA
0x180031ee0  xor     edx, edx
0x180031ee2  mov     rcx, rdi
0x180031ee5  call    CardStateReleaseRef
0x180031eea  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180031ef1  mov     edx, 1
0x180031ef6  mov     [rsp+2B0h+var_268], 0
0x180031eff  mov     [rsp+2B0h+var_258], 0
0x180031f08  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f14  cmp     rcx, rsi
0x180031f17  jz      short loc_180031F45
0x180031f19  test    byte ptr [rcx+1Ch], 2
0x180031f1d  jz      short loc_180031F45
0x180031f1f  cmp     byte ptr [rcx+19h], 5
0x180031f23  jb      short loc_180031F45
0x180031f25  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180031f2c  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180031f33  mov     rcx, [rcx+10h]
0x180031f37  mov     edx, 50h ; 'P'
0x180031f3c  mov     dword ptr [rsp+2B0h+var_290], ebx
0x180031f40  call    WPP_SF_sd
0x180031f45  lea     rcx, [rsp+2B0h+var_260]
0x180031f4a  mov     [rsp+2B0h+var_260], rdi
0x180031f4f  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180031f54  lea     rcx, [rsp+2B0h+var_270]
0x180031f59  mov     [rsp+2B0h+var_270], rdi
0x180031f5e  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180031f63  mov     eax, ebx
0x180031f65  mov     rcx, [rbp+1B0h+var_40]
0x180031f6c  xor     rcx, rsp; StackCookie
0x180031f6f  call    __security_check_cookie
0x180031f74  mov     rbx, [rsp+2B0h+arg_18]
0x180031f7c  add     rsp, 280h
0x180031f83  pop     r15
0x180031f85  pop     r14
0x180031f87  pop     r13
0x180031f89  pop     r12
0x180031f8b  pop     rdi
0x180031f8c  pop     rsi
0x180031f8d  pop     rbp
0x180031f8e  retn
```
