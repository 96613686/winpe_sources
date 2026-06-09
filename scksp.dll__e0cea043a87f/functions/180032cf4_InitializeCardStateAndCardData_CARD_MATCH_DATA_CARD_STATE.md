# InitializeCardStateAndCardData(_CARD_MATCH_DATA *,_CARD_STATE * *)

- ea: `0x180032cf4`
- end: `0x1800335e6`
- name: `?InitializeCardStateAndCardData@@YAKPEAU_CARD_MATCH_DATA@@PEAPEAU_CARD_STATE@@@Z`
- size: `2290`
- prototype: `unsigned int __fastcall(struct _CARD_MATCH_DATA *, struct _CARD_STATE **)`
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x180032770`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180013aac`
- `0x180013c94`
- `0x18002b140`
- `0x18002ce34`
- `0x18002d740`
- `0x18002e52c`
- `0x18002eb6c`
- `0x180030500`
- `0x18003083c`
- `0x180032318`
- `0x180032b58`
- `0x180032cf4`
- `0x1800346e8`
- `0x180034854`
- `0x180034edc`
- `0x18003ae44`
- `0x18003aea8`
- `0x18003aec8`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033070`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033048`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033061`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033048`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033061`
- `WinSCard!SCardReleaseContext` at `0x18003355a`
- `WinSCard!SCardReleaseContext` at `0x18003355a`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x180032e3b`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x180032e3b`
- `WinSCard!SCardEstablishContext` at `0x180032daf`
- `WinSCard!SCardEstablishContext` at `0x180032daf`

## string_xrefs

- `0x18003327d`: `Read Only Mode`
- `0x18003330d`: `Cache Mode`

## pseudocode

```c
__int64 __fastcall InitializeCardStateAndCardData(WCHAR *a1, struct _CARD_STATE **a2)
{
  __int64 v4; // rcx
  unsigned int CardTypeProviderNameW; // ebx
  _QWORD *v6; // rcx
  int v7; // edx
  _OWORD *v8; // rsi
  __int64 v9; // rcx
  char *v10; // rax
  __int64 v11; // rcx
  char *v12; // rdi
  unsigned int v13; // r14d
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  int v16; // edx
  __int64 v17; // rcx
  HMODULE *v18; // r14
  __int64 v19; // rcx
  FARPROC ProcAddress; // rax
  FARPROC v21; // rax
  __int64 v22; // rbx
  _OWORD *v23; // rax
  __int128 v24; // xmm1
  __int64 v25; // rcx
  int v26; // r9d
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  _DWORD *v30; // rcx
  __int64 v31; // rcx
  _DWORD *v32; // rcx
  __int64 v33; // rcx
  int v34; // ecx
  unsigned int CardContainerMap; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  SCARDCONTEXT v38; // rcx
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v41; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchProvider; // [rsp+40h] [rbp-C0h] BYREF
  SCARDCONTEXT phContext; // [rsp+48h] [rbp-B8h] BYREF
  void **v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  WCHAR szProvider[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcchProvider = 0;
  phContext = 0;
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v41 = 0;
  v40 = 0;
  v45 = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  CardTypeProviderNameW = SCardEstablishContext(0, 0, 0, &phContext);
  if ( CardTypeProviderNameW )
  {
    WppTraceIndent(v4, 2u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 82;
LABEL_10:
      WPP_SF_sd(
        v6[2],
        v7,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        CardTypeProviderNameW);
      goto LABEL_105;
    }
    goto LABEL_105;
  }
  v8 = a1 + 28;
  pcchProvider = 260;
  CardTypeProviderNameW = SCardGetCardTypeProviderNameW(phContext, a1 + 310, 0x80000001, szProvider, &pcchProvider);
  if ( !CardTypeProviderNameW )
  {
    v10 = (char *)MIDL_user_allocate(0x718u);
    v12 = v10;
    if ( !v10 )
    {
      WppTraceIndent(v11, 2u);
      CardTypeProviderNameW = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_103;
    }
    memset_0(v10, 0, 0x718u);
    *(_DWORD *)v12 = 1;
    v13 = CspInitializeCriticalSection(v12 + 624);
    if ( v13 )
    {
      DeleteCardState((struct _CARD_STATE *)v12, 0);
      CardTypeProviderNameW = v13;
      WppTraceIndent(v37, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          v13);
      }
      goto LABEL_98;
    }
    *((_DWORD *)v12 + 166) = 1;
    _InterlockedExchange((volatile __int32 *)v12 + 173, 1);
    CardTypeProviderNameW = CspEnterCriticalSection(v12 + 624);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v14, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 86;
      goto LABEL_92;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v44, v12 + 624);
    CardTypeProviderNameW = GetSessionID((unsigned int *)v12 + 179, (union _LARGE_INTEGER *)v12 + 90);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v17, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 87;
      goto LABEL_92;
    }
    StringCbCopyW((unsigned __int16 *)v12 + 16, 0x208u, a1 + 48);
    v18 = (HMODULE *)(v12 + 16);
    CardTypeProviderNameW = GetCardModuleHandle((LPCRITICAL_SECTION *)a1, szProvider, (HINSTANCE *)v12 + 2);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v19, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 88;
      goto LABEL_92;
    }
    ProcAddress = GetProcAddress(*v18, "CardAcquireContextInternal");
    *((_QWORD *)v12 + 3) = ProcAddress;
    if ( !ProcAddress )
    {
      v21 = GetProcAddress(*v18, "CardAcquireContext");
      *((_QWORD *)v12 + 3) = v21;
      if ( !v21 )
      {
        CardTypeProviderNameW = GetLastError();
        if ( CardTypeProviderNameW )
          goto LABEL_98;
LABEL_103:
        if ( v41 )
          CspFreeH(v41);
        goto LABEL_105;
      }
    }
    v22 = 8;
    v23 = v12 + 728;
    do
    {
      *v23 = *v8;
      v23[1] = v8[1];
      v23[2] = v8[2];
      v23[3] = v8[3];
      v23[4] = v8[4];
      v23[5] = v8[5];
      v23[6] = v8[6];
      v24 = v8[7];
      v8 += 8;
      v23[7] = v24;
      v23 += 8;
      --v22;
    }
    while ( v22 );
    *v23 = *v8;
    v23[1] = v8[1];
    v23[2] = v8[2];
    v23[3] = v8[3];
    CardTypeProviderNameW = AcquireCardContext(v12);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v25, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 89;
      goto LABEL_92;
    }
    if ( !*((_QWORD *)v12 + 1) )
    {
      CardTypeProviderNameW = 87;
      WppTraceIndent(v25, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          v26,
          (__int64)"pLocalCardState->pCardData");
      }
      goto LABEL_98;
    }
    CardTypeProviderNameW = InitializeCspCaching(v25, v12);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v27, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 91;
      goto LABEL_92;
    }
    CardTypeProviderNameW = ReadCardSerialNumber(
                              (struct _CARD_STATE *)v12,
                              (unsigned __int8 **)v12 + 69,
                              (unsigned int *)v12 + 140);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v28, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 92;
      goto LABEL_92;
    }
    if ( **((_DWORD **)v12 + 1) < 6u )
    {
      *((_QWORD *)v12 + 87) = 1;
      v34 = 1;
    }
    else
    {
      CardTypeProviderNameW = GetCachedCardProperty(
                                (_DWORD)v12,
                                (unsigned int)L"Read Only Mode",
                                (unsigned int)&v41,
                                (unsigned int)&v40,
                                0);
      if ( CardTypeProviderNameW )
      {
        WppTraceIndent(v29, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v16 = 93;
        goto LABEL_92;
      }
      if ( v40 != 4 )
      {
LABEL_70:
        CardTypeProviderNameW = -2146893820;
LABEL_98:
        if ( *((_DWORD *)v12 + 148) )
          CspEndTransaction((struct _CARD_STATE *)v12);
        if ( v45 )
        {
          v45 = 0;
          CspLeaveCriticalSection(v12 + 624);
        }
        CardStateReleaseRef(v12, 0);
        goto LABEL_103;
      }
      v30 = v41;
      *((_DWORD *)v12 + 175) = *(unsigned __int8 *)v41;
      CspFreeH(v30);
      v41 = 0;
      v40 = 0;
      CardTypeProviderNameW = GetCachedCardProperty(
                                (_DWORD)v12,
                                (unsigned int)L"Cache Mode",
                                (unsigned int)&v41,
                                (unsigned int)&v40,
                                0);
      if ( CardTypeProviderNameW )
      {
        WppTraceIndent(v31, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v16 = 94;
        goto LABEL_92;
      }
      if ( v40 != 4 )
        goto LABEL_70;
      v32 = v41;
      *((_DWORD *)v12 + 174) = *v41;
      CspFreeH(v32);
      v41 = 0;
      v40 = 0;
      CardTypeProviderNameW = GetCachedCardProperty(
                                (_DWORD)v12,
                                (unsigned int)L"Supports Windows x.509 Enrollment",
                                (unsigned int)&v41,
                                (unsigned int)&v40,
                                0);
      if ( CardTypeProviderNameW )
      {
        WppTraceIndent(v33, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v16 = 95;
        goto LABEL_92;
      }
      if ( v40 != 4 )
        goto LABEL_70;
      v34 = *(unsigned __int8 *)v41;
    }
    *((_DWORD *)v12 + 177) = v34;
    CardContainerMap = ReadCardContainerMap((struct _CARD_STATE *)v12);
    CardTypeProviderNameW = 0;
    if ( CardContainerMap != -2146435036 )
      CardTypeProviderNameW = CardContainerMap;
    if ( !CardTypeProviderNameW )
    {
      *a2 = (struct _CARD_STATE *)v12;
      CardTypeProviderNameW = 0;
      goto LABEL_103;
    }
    WppTraceIndent(v36, 2u);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_98;
    }
    v16 = 96;
LABEL_92:
    WPP_SF_sd(
      v15[2],
      v16,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardTypeProviderNameW);
    goto LABEL_98;
  }
  WppTraceIndent(v9, 2u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 83;
    goto LABEL_10;
  }
LABEL_105:
  v38 = phContext;
  if ( phContext )
    SCardReleaseContext(phContext);
  v45 = 0;
  WppTraceIndent(v38, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardTypeProviderNameW);
  }
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v44);
  return CardTypeProviderNameW;
}

```

## disassembly

```asm
0x180032cf4  mov     [rsp-8+arg_10], rbx
0x180032cf9  push    rbp
0x180032cfa  push    rsi
0x180032cfb  push    rdi
0x180032cfc  push    r12
0x180032cfe  push    r13
0x180032d00  push    r14
0x180032d02  push    r15
0x180032d04  lea     rbp, [rsp-180h]
0x180032d0c  sub     rsp, 280h
0x180032d13  mov     rax, cs:__security_cookie
0x180032d1a  xor     rax, rsp
0x180032d1d  mov     [rbp+1B0h+var_40], rax
0x180032d24  mov     r12, rdx
0x180032d27  mov     [rsp+2B0h+var_270], 0
0x180032d2f  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180032d36  mov     [rsp+2B0h+phContext], 0
0x180032d3f  xor     edx, edx
0x180032d41  mov     [rsp+2B0h+var_260], rdi
0x180032d46  mov     r13, rcx
0x180032d49  mov     [rsp+2B0h+var_278], 0
0x180032d52  mov     [rsp+2B0h+var_280], 0
0x180032d5a  mov     [rsp+2B0h+var_258], 0
0x180032d63  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d6f  lea     r14, WPP_GLOBAL_Control
0x180032d76  cmp     rcx, r14
0x180032d79  jz      short loc_180032DA3
0x180032d7b  test    byte ptr [rcx+1Ch], 2
0x180032d7f  jz      short loc_180032DA3
0x180032d81  cmp     byte ptr [rcx+19h], 5
0x180032d85  jb      short loc_180032DA3
0x180032d87  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032d8e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032d95  mov     rcx, [rcx+10h]
0x180032d99  mov     edx, 51h ; 'Q'
0x180032d9e  call    WPP_SF_s
0x180032da3  lea     r9, [rsp+2B0h+phContext]; phContext
0x180032da8  xor     r8d, r8d; pvReserved2
0x180032dab  xor     edx, edx; pvReserved1
0x180032dad  xor     ecx, ecx; dwScope
0x180032daf  call    cs:__imp_SCardEstablishContext
0x180032db5  mov     ebx, eax
0x180032db7  test    eax, eax
0x180032db9  jz      short loc_180032E0E
0x180032dbb  mov     edx, 2
0x180032dc0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032dcc  cmp     rcx, r14
0x180032dcf  jz      loc_180033550
0x180032dd5  test    byte ptr [rcx+1Ch], 1
0x180032dd9  jz      loc_180033550
0x180032ddf  cmp     byte ptr [rcx+19h], 2
0x180032de3  jb      loc_180033550
0x180032de9  mov     edx, 52h ; 'R'
0x180032dee  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032df5  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032dfc  mov     rcx, [rcx+10h]
0x180032e00  mov     dword ptr [rsp+2B0h+pcchProvider], ebx
0x180032e04  call    WPP_SF_sd
0x180032e09  jmp     loc_180033550
0x180032e0e  mov     rcx, [rsp+2B0h+phContext]; hContext
0x180032e13  lea     rax, [rsp+2B0h+var_270]
0x180032e18  lea     rsi, [r13+38h]
0x180032e1c  mov     [rsp+2B0h+var_270], 104h
0x180032e24  lea     rdx, [rsi+234h]; szCardName
0x180032e2b  mov     [rsp+2B0h+pcchProvider], rax; pcchProvider
0x180032e30  lea     r9, [rsp+2B0h+szProvider]; szProvider
0x180032e35  mov     r8d, 80000001h; dwProviderId
0x180032e3b  call    cs:__imp_SCardGetCardTypeProviderNameW
0x180032e41  mov     ebx, eax
0x180032e43  test    eax, eax
0x180032e45  jz      short loc_180032E7F
0x180032e47  mov     edx, 2
0x180032e4c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e58  cmp     rcx, r14
0x180032e5b  jz      loc_180033550
0x180032e61  test    byte ptr [rcx+1Ch], 1
0x180032e65  jz      loc_180033550
0x180032e6b  cmp     byte ptr [rcx+19h], 2
0x180032e6f  jb      loc_180033550
0x180032e75  mov     edx, 53h ; 'S'
0x180032e7a  jmp     loc_180032DEE
0x180032e7f  mov     ebx, 718h
0x180032e84  mov     ecx, ebx; size
0x180032e86  call    MIDL_user_allocate
0x180032e8b  mov     rdi, rax
0x180032e8e  test    rax, rax
0x180032e91  jnz     short loc_180032EE1
0x180032e93  lea     edx, [rax+2]
0x180032e96  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032e9b  lea     ebx, [rdi+8]
0x180032e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ea5  cmp     rcx, r14
0x180032ea8  jz      loc_18003353A
0x180032eae  test    byte ptr [rcx+1Ch], 1
0x180032eb2  jz      loc_18003353A
0x180032eb8  cmp     byte ptr [rcx+19h], 2
0x180032ebc  jb      loc_18003353A
0x180032ec2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032ec9  lea     edx, [rdi+54h]
0x180032ecc  mov     rcx, [rcx+10h]
0x180032ed0  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180032ed7  call    WPP_SF_s
0x180032edc  jmp     loc_18003353A
0x180032ee1  mov     r8, rbx; Size
0x180032ee4  xor     edx, edx; Val
0x180032ee6  mov     rcx, rdi; void *
0x180032ee9  call    memset_0
0x180032eee  lea     r15, [rdi+270h]
0x180032ef5  mov     dword ptr [rdi], 1
0x180032efb  mov     rcx, r15
0x180032efe  call    CspInitializeCriticalSection
0x180032f03  mov     r14d, eax
0x180032f06  test    eax, eax
0x180032f08  jnz     loc_1800334A4
0x180032f0e  lea     eax, [r14+1]
0x180032f12  mov     dword ptr [rdi+298h], 1
0x180032f1c  xchg    eax, [rdi+2B4h]
0x180032f22  mov     rcx, r15
0x180032f25  call    CspEnterCriticalSection
0x180032f2a  mov     ebx, eax
0x180032f2c  test    eax, eax
0x180032f2e  jz      short loc_180032F6E
0x180032f30  lea     edx, [r14+2]
0x180032f34  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f40  lea     r14, WPP_GLOBAL_Control
0x180032f47  cmp     rcx, r14
0x180032f4a  jz      loc_180033502
0x180032f50  test    byte ptr [rcx+1Ch], 1
0x180032f54  jz      loc_180033502
0x180032f5a  cmp     byte ptr [rcx+19h], 2
0x180032f5e  jb      loc_180033502
0x180032f64  mov     edx, 56h ; 'V'
0x180032f69  jmp     loc_180033475
0x180032f6e  mov     rdx, r15
0x180032f71  lea     rcx, [rsp+2B0h+var_260]
0x180032f76  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180032f7b  lea     rdx, [rdi+2D0h]; union _LARGE_INTEGER *
0x180032f82  lea     rcx, [rdi+2CCh]; TokenInformation
0x180032f89  call    ?GetSessionID@@YAKPEAKPEAT_LARGE_INTEGER@@@Z; GetSessionID(ulong *,_LARGE_INTEGER *)
0x180032f8e  mov     ebx, eax
0x180032f90  test    eax, eax
0x180032f92  jz      short loc_180032FD3
0x180032f94  mov     edx, 2
0x180032f99  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fa5  lea     r14, WPP_GLOBAL_Control
0x180032fac  cmp     rcx, r14
0x180032faf  jz      loc_180033502
0x180032fb5  test    byte ptr [rcx+1Ch], 1
0x180032fb9  jz      loc_180033502
0x180032fbf  cmp     byte ptr [rcx+19h], 2
0x180032fc3  jb      loc_180033502
0x180032fc9  mov     edx, 57h ; 'W'
0x180032fce  jmp     loc_180033475
0x180032fd3  lea     r8, [rsi+28h]; unsigned __int16 *
0x180032fd7  mov     edx, 208h; unsigned __int64
0x180032fdc  lea     rcx, [rdi+20h]; unsigned __int16 *
0x180032fe0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180032fe5  lea     r14, [rdi+10h]
0x180032fe9  mov     rcx, r13; struct _CARD_MATCH_DATA *
0x180032fec  mov     r8, r14; HINSTANCE *
0x180032fef  lea     rdx, [rsp+2B0h+szProvider]; unsigned __int16 *
0x180032ff4  call    ?GetCardModuleHandle@@YAKPEAU_CARD_MATCH_DATA@@PEAGPEAPEAUHINSTANCE__@@@Z; GetCardModuleHandle(_CARD_MATCH_DATA *,ushort *,HINSTANCE__ * *)
0x180032ff9  mov     ebx, eax
0x180032ffb  test    eax, eax
0x180032ffd  jz      short loc_18003303E
0x180032fff  mov     edx, 2
0x180033004  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033009  mov     rcx, cs:WPP_GLOBAL_Control
0x180033010  lea     r14, WPP_GLOBAL_Control
0x180033017  cmp     rcx, r14
0x18003301a  jz      loc_180033502
0x180033020  test    byte ptr [rcx+1Ch], 1
0x180033024  jz      loc_180033502
0x18003302a  cmp     byte ptr [rcx+19h], 2
0x18003302e  jb      loc_180033502
0x180033034  mov     edx, 58h ; 'X'
0x180033039  jmp     loc_180033475
0x18003303e  mov     rcx, [r14]; hModule
0x180033041  lea     rdx, aCardacquirecon_0; "CardAcquireContextInternal"
0x180033048  call    cs:__imp_GetProcAddress
0x18003304e  mov     [rdi+18h], rax
0x180033052  test    rax, rax
0x180033055  jnz     short loc_18003308C
0x180033057  mov     rcx, [r14]; hModule
0x18003305a  lea     rdx, aCardacquirecon; "CardAcquireContext"
0x180033061  call    cs:__imp_GetProcAddress
0x180033067  mov     [rdi+18h], rax
0x18003306b  test    rax, rax
0x18003306e  jnz     short loc_18003308C
0x180033070  call    cs:__imp_GetLastError
0x180033076  lea     r14, WPP_GLOBAL_Control
0x18003307d  mov     ebx, eax
0x18003307f  test    eax, eax
0x180033081  jz      loc_18003353A
0x180033087  jmp     loc_180033502
0x18003308c  mov     ebx, 8
0x180033091  lea     rax, [rdi+2D8h]
0x180033098  lea     ecx, [rbx+78h]
0x18003309b  movups  xmm0, xmmword ptr [rsi]
0x18003309e  movups  xmmword ptr [rax], xmm0
0x1800330a1  movups  xmm1, xmmword ptr [rsi+10h]
0x1800330a5  movups  xmmword ptr [rax+10h], xmm1
0x1800330a9  movups  xmm0, xmmword ptr [rsi+20h]
0x1800330ad  movups  xmmword ptr [rax+20h], xmm0
0x1800330b1  movups  xmm1, xmmword ptr [rsi+30h]
0x1800330b5  movups  xmmword ptr [rax+30h], xmm1
0x1800330b9  movups  xmm0, xmmword ptr [rsi+40h]
0x1800330bd  movups  xmmword ptr [rax+40h], xmm0
0x1800330c1  movups  xmm1, xmmword ptr [rsi+50h]
0x1800330c5  movups  xmmword ptr [rax+50h], xmm1
0x1800330c9  movups  xmm0, xmmword ptr [rsi+60h]
0x1800330cd  movups  xmmword ptr [rax+60h], xmm0
0x1800330d1  movups  xmm1, xmmword ptr [rsi+70h]
0x1800330d5  add     rsi, rcx
0x1800330d8  movups  xmmword ptr [rax+70h], xmm1
0x1800330dc  add     rax, rcx
0x1800330df  sub     rbx, 1
0x1800330e3  jnz     short loc_18003309B
0x1800330e5  movups  xmm0, xmmword ptr [rsi]
0x1800330e8  mov     rcx, rdi
0x1800330eb  movups  xmmword ptr [rax], xmm0
0x1800330ee  movups  xmm1, xmmword ptr [rsi+10h]
0x1800330f2  movups  xmmword ptr [rax+10h], xmm1
0x1800330f6  movups  xmm0, xmmword ptr [rsi+20h]
0x1800330fa  movups  xmmword ptr [rax+20h], xmm0
0x1800330fe  movups  xmm1, xmmword ptr [rsi+30h]
0x180033102  movups  xmmword ptr [rax+30h], xmm1
0x180033106  call    AcquireCardContext
0x18003310b  mov     ebx, eax
0x18003310d  test    eax, eax
0x18003310f  jz      short loc_180033150
0x180033111  mov     edx, 2
0x180033116  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003311b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033122  lea     r14, WPP_GLOBAL_Control
0x180033129  cmp     rcx, r14
0x18003312c  jz      loc_180033502
0x180033132  test    byte ptr [rcx+1Ch], 1
0x180033136  jz      loc_180033502
0x18003313c  cmp     byte ptr [rcx+19h], 2
0x180033140  jb      loc_180033502
0x180033146  mov     edx, 59h ; 'Y'
0x18003314b  jmp     loc_180033475
0x180033150  cmp     qword ptr [rdi+8], 0
0x180033155  jnz     short loc_1800331B3
0x180033157  mov     ebx, 57h ; 'W'
0x18003315c  lea     edx, [rbx-55h]
0x18003315f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033164  mov     rcx, cs:WPP_GLOBAL_Control
0x18003316b  lea     r14, WPP_GLOBAL_Control
0x180033172  cmp     rcx, r14
0x180033175  jz      loc_180033502
0x18003317b  test    byte ptr [rcx+1Ch], 1
0x18003317f  jz      loc_180033502
0x180033185  cmp     byte ptr [rcx+19h], 2
0x180033189  jb      loc_180033502
0x18003318f  mov     rcx, [rcx+10h]
0x180033193  lea     rax, aPlocalcardstat; "pLocalCardState->pCardData"
0x18003319a  lea     edx, [rbx+3]
0x18003319d  mov     [rsp+2B0h+pcchProvider], rax
0x1800331a2  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800331a9  call    WPP_SF_ss
0x1800331ae  jmp     loc_180033502
0x1800331b3  mov     rdx, rdi
0x1800331b6  call    InitializeCspCaching
0x1800331bb  mov     ebx, eax
0x1800331bd  test    eax, eax
0x1800331bf  jz      short loc_180033200
0x1800331c1  mov     edx, 2
0x1800331c6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800331cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331d2  lea     r14, WPP_GLOBAL_Control
0x1800331d9  cmp     rcx, r14
0x1800331dc  jz      loc_180033502
0x1800331e2  test    byte ptr [rcx+1Ch], 1
0x1800331e6  jz      loc_180033502
0x1800331ec  cmp     byte ptr [rcx+19h], 2
0x1800331f0  jb      loc_180033502
0x1800331f6  mov     edx, 5Bh ; '['
0x1800331fb  jmp     loc_180033475
0x180033200  lea     r8, [rdi+230h]; unsigned int *
0x180033207  mov     rcx, rdi; struct _CARD_STATE *
0x18003320a  lea     rdx, [rdi+228h]; unsigned __int8 **
0x180033211  call    ?ReadCardSerialNumber@@YAKPEAU_CARD_STATE@@PEAPEAEPEAK@Z; ReadCardSerialNumber(_CARD_STATE *,uchar * *,ulong *)
0x180033216  mov     ebx, eax
0x180033218  test    eax, eax
0x18003321a  jz      short loc_18003325B
0x18003321c  mov     edx, 2
0x180033221  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033226  mov     rcx, cs:WPP_GLOBAL_Control
0x18003322d  lea     r14, WPP_GLOBAL_Control
0x180033234  cmp     rcx, r14
0x180033237  jz      loc_180033502
0x18003323d  test    byte ptr [rcx+1Ch], 1
0x180033241  jz      loc_180033502
  ... truncated ...
```
