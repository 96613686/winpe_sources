# SearchInAvailableReaders

- ea: `0x1800356fc`
- end: `0x180035d65`
- name: `SearchInAvailableReaders`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800354b8`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x180013aac`
- `0x18002b140`
- `0x18002ce34`
- `0x18002d740`
- `0x180034694`
- `0x180034df4`
- `0x1800356fc`
- `0x18003aec8`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18003588a`
- `msvcrt!wcsnlen` at `0x1800359d8`
- `msvcrt!wcsnlen` at `0x18003588a`
- `msvcrt!wcsnlen` at `0x1800359d8`
- `WinSCard!SCardListReadersW` at `0x180035822`
- `WinSCard!SCardListReadersW` at `0x180035822`
- `WinSCard!SCardListCardsW` at `0x180035ae2`
- `WinSCard!SCardListCardsW` at `0x180035ae2`
- `WinSCard!SCardFreeMemory` at `0x180035cae`
- `WinSCard!SCardFreeMemory` at `0x180035cdd`
- `WinSCard!SCardFreeMemory` at `0x180035cae`
- `WinSCard!SCardFreeMemory` at `0x180035cdd`
- `WinSCard!SCardReleaseContext` at `0x180035cec`
- `WinSCard!SCardReleaseContext` at `0x180035cec`
- `WinSCard!SCardGetStatusChangeW` at `0x1800359f5`
- `WinSCard!SCardGetStatusChangeW` at `0x1800359f5`
- `WinSCard!SCardEstablishContext` at `0x1800357b1`
- `WinSCard!SCardEstablishContext` at `0x1800357b1`

## pseudocode

```c
__int64 __fastcall SearchInAvailableReaders(__int64 a1, struct _CARD_STATE **a2, int a3)
{
  DWORD v3; // r14d
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v4; // r13
  char *v5; // r15
  struct _CARD_STATE *v6; // rdi
  __int64 v8; // rcx
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  DWORD v13; // edx
  DWORD v14; // ebx
  const wchar_t *v15; // rcx
  int v16; // eax
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  char *v21; // rax
  __int64 v22; // rcx
  DWORD v23; // ebx
  unsigned int i; // esi
  const WCHAR *v25; // rdx
  unsigned __int64 v26; // rax
  const wchar_t *v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // r8d
  unsigned int v31; // esi
  DWORD j; // edx
  int v33; // eax
  unsigned int v34; // r15d
  unsigned __int64 v35; // r14
  WCHAR *mszCards; // r12
  unsigned int v37; // eax
  int v38; // ecx
  unsigned int v39; // eax
  DWORD k; // edi
  const void *v41; // rdx
  SCARDCONTEXT v42; // rcx
  DWORD v44; // [rsp+38h] [rbp-39h]
  struct _CARD_STATE *v45; // [rsp+40h] [rbp-31h] BYREF
  char *v46; // [rsp+48h] [rbp-29h]
  SCARDCONTEXT phContext; // [rsp+50h] [rbp-21h] BYREF
  DWORD pcchCards; // [rsp+58h] [rbp-19h] BYREF
  unsigned int v49; // [rsp+5Ch] [rbp-15h]
  WCHAR mszReaders[4]; // [rsp+60h] [rbp-11h] BYREF
  void **v51; // [rsp+68h] [rbp-9h] BYREF
  __int64 v52; // [rsp+70h] [rbp-1h]
  int v53; // [rsp+78h] [rbp+7h]
  DWORD pcchReaders; // [rsp+F0h] [rbp+7Fh] BYREF

  pcchReaders = -1;
  phContext = 0;
  *(_QWORD *)mszReaders = 0;
  v3 = 0;
  pcchCards = 0;
  v4 = 0;
  v45 = 0;
  v5 = 0;
  v51 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v6 = 0;
  v52 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  *(_DWORD *)(a1 + 1196) = 0;
  v9 = SCardEstablishContext(0, 0, 0, &phContext);
  if ( v9 )
  {
    WppTraceIndent(v8, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v11 = 114;
    goto LABEL_10;
  }
  v9 = SCardListReadersW(phContext, 0, mszReaders, &pcchReaders);
  if ( v9 )
  {
    WppTraceIndent(v12, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v11 = 115;
    goto LABEL_10;
  }
  v13 = pcchReaders;
  v14 = 0;
  if ( !pcchReaders )
    goto LABEL_88;
  do
  {
    v15 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * v14);
    if ( !*v15 )
      break;
    ++v3;
    v16 = wcsnlen(v15, v13 - v14);
    v13 = pcchReaders;
    v14 += v16 + 1;
  }
  while ( v14 < pcchReaders );
  v44 = v3;
  if ( v14 >= v13 )
  {
LABEL_88:
    v9 = -2146435041;
    goto LABEL_89;
  }
  if ( !v3 )
  {
    v9 = -2146435026;
    goto LABEL_89;
  }
  v17 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)MIDL_user_allocate((unsigned __int64)v3 << 6);
  v4 = v17;
  if ( !v17 )
  {
    WppTraceIndent(v18, 2);
    v9 = 8;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v20 = 116;
    goto LABEL_27;
  }
  memset_0(v17, 0, (unsigned __int64)v3 << 6);
  v21 = (char *)MIDL_user_allocate(8LL * v3);
  v46 = v21;
  v5 = v21;
  if ( !v21 )
  {
    WppTraceIndent(v22, 2);
    v9 = 8;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v20 = 117;
LABEL_27:
    WPP_SF_s(v19[2], v20, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
    goto LABEL_89;
  }
  memset_0(v21, 0, 8LL * v3);
  v23 = 0;
  for ( i = 0; v23 < pcchReaders; v23 += v28 + 1 )
  {
    v25 = (const WCHAR *)(*(_QWORD *)mszReaders + 2LL * v23);
    if ( !*v25 )
      break;
    v26 = (unsigned __int64)i << 6;
    *(LPCWSTR *)((char *)&v4->szReader + v26) = v25;
    *(DWORD *)((char *)&v4->dwCurrentState + v26) = 0;
    v27 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * v23);
    v28 = v27 ? wcsnlen(v27, pcchReaders - v23) : 0;
    ++i;
  }
  v9 = SCardGetStatusChangeW(phContext, 0, v4, v3);
  if ( v9 )
  {
    WppTraceIndent(v29, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_89;
    }
    v11 = 118;
LABEL_10:
    WPP_SF_sd(v10[2], v11, (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, (_DWORD)WPP_pszIndent, v9);
    goto LABEL_89;
  }
  v49 = 0;
  v30 = 0;
  v31 = 0;
  for ( j = 0; j < v3; ++j )
  {
    v33 = v30 + 1;
    if ( (v4[(unsigned __int64)j].dwEventState & 0xA0) != 0x20 )
      v33 = v30;
    v30 = v33;
  }
  v53 = v33;
  v34 = 0;
  while ( 1 )
  {
    v35 = (unsigned __int64)v34 << 6;
    if ( (*(DWORD *)((_BYTE *)&v4->dwEventState + v35) & 0xA0) != 0x20 )
      goto LABEL_61;
    if ( !(unsigned int)MatchesRequiredReaderName(
                          *(unsigned __int16 **)(a1 + 1160),
                          *(unsigned __int16 **)((char *)&v4->szReader + v35)) )
      goto LABEL_61;
    pcchCards = -1;
    mszCards = (WCHAR *)&v46[8 * v34];
    v9 = SCardListCardsW(phContext, &v4->rgbAtr[v35], 0, 0, mszCards, &pcchCards);
    if ( v9 )
      goto LABEL_61;
    if ( v6 )
    {
      if ( *((_DWORD *)v6 + 148) )
        CspEndTransaction(v6);
      v52 = 0;
      CspLeaveCriticalSection((char *)v6 + 624);
      CardStateReleaseRef(v6, 0);
      v45 = 0;
    }
    v37 = VerifyCard(
            *(unsigned __int16 **)((char *)&v4->szReader + v35),
            *(unsigned __int16 **)mszCards,
            (struct _CARD_MATCH_DATA *)a1,
            &v45);
    v6 = v45;
    v9 = v37;
    if ( v37 )
    {
LABEL_61:
      v38 = a3;
      goto LABEL_62;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v51, (char *)v45 + 624);
    v38 = a3;
    ++v31;
    if ( !a3 )
      goto LABEL_64;
    if ( a3 == 1 )
      break;
LABEL_62:
    v3 = v44;
    if ( ++v34 >= v44 )
      goto LABEL_65;
  }
  if ( v31 <= 1 )
  {
    v49 = v34;
    goto LABEL_62;
  }
LABEL_64:
  v3 = v44;
LABEL_65:
  if ( !v53 )
  {
    v5 = v46;
    v9 = -2146435060;
LABEL_84:
    if ( v6 )
    {
      if ( *((_DWORD *)v6 + 148) )
        CspEndTransaction(v6);
      v52 = 0;
      CspLeaveCriticalSection((char *)v6 + 624);
      CardStateReleaseRef(v6, 0);
    }
    goto LABEL_89;
  }
  if ( v31 || v53 != 1 )
  {
    if ( v38 )
    {
      if ( v31 == 1 )
      {
        if ( v6 )
        {
          if ( *((_DWORD *)v6 + 148) )
            CspEndTransaction(v6);
          v52 = 0;
          CspLeaveCriticalSection((char *)v6 + 624);
          CardStateReleaseRef(v6, 0);
          v45 = 0;
        }
        v5 = v46;
        v39 = VerifyCard(
                (unsigned __int16 *)v4[(unsigned __int64)v49].szReader,
                *(unsigned __int16 **)&v46[8 * v49],
                (struct _CARD_MATCH_DATA *)a1,
                &v45);
        v6 = v45;
        v9 = v39;
        if ( !v39 )
        {
          Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v51, (char *)v45 + 624);
          goto LABEL_80;
        }
      }
      else
      {
        v5 = v46;
        v9 = -2146435024;
      }
    }
    else
    {
      v5 = v46;
      if ( v31 == 1 )
      {
        v9 = 0;
        goto LABEL_80;
      }
LABEL_69:
      v9 = -2146435024;
    }
    goto LABEL_84;
  }
  v5 = v46;
  if ( !v9 )
    goto LABEL_69;
LABEL_80:
  *a2 = v6;
LABEL_89:
  v52 = 0;
  if ( v5 )
  {
    for ( k = 0; k < v3; ++k )
    {
      v41 = *(const void **)&v5[8 * k];
      if ( v41 )
        SCardFreeMemory(phContext, v41);
    }
    CspFreeH(v5);
  }
  if ( v4 )
    CspFreeH(v4);
  if ( *(_QWORD *)mszReaders )
    SCardFreeMemory(phContext, *(LPCVOID *)mszReaders);
  v42 = phContext;
  if ( phContext )
    SCardReleaseContext(phContext);
  WppTraceIndent(v42, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v9);
  }
  v51 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v51);
  return v9;
}

```

## disassembly

```asm
0x1800356fc  mov     rax, rsp
0x1800356ff  mov     [rax+18h], r8d
0x180035703  mov     [rax+10h], rdx
0x180035707  mov     [rax+8], rcx
0x18003570b  push    rbp
0x18003570c  push    rbx
0x18003570d  push    rsi
0x18003570e  push    rdi
0x18003570f  push    r12
0x180035711  push    r13
0x180035713  push    r14
0x180035715  push    r15
0x180035717  lea     rbp, [rax-5Fh]
0x18003571b  sub     rsp, 88h
0x180035722  xor     r12d, r12d
0x180035725  mov     [rbp+57h+pcchReaders], 0FFFFFFFFh
0x18003572c  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180035733  mov     [rbp+57h+phContext], r12
0x180035737  xor     edx, edx
0x180035739  mov     qword ptr [rbp+57h+mszReaders], r12
0x18003573d  mov     r14d, r12d
0x180035740  mov     [rbp+57h+pcchCards], r12d
0x180035744  mov     r13d, r12d
0x180035747  mov     [rbp+57h+var_88], r12
0x18003574b  mov     r15d, r12d
0x18003574e  mov     [rbp+57h+var_60], rax
0x180035752  mov     edi, r12d
0x180035755  mov     [rbp+57h+var_58], r12
0x180035759  mov     rbx, rcx
0x18003575c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035761  mov     rcx, cs:WPP_GLOBAL_Control
0x180035768  lea     rax, WPP_GLOBAL_Control
0x18003576f  lea     esi, [r12+2]
0x180035774  cmp     rcx, rax
0x180035777  jz      short loc_18003579F
0x180035779  test    [rcx+1Ch], sil
0x18003577d  jz      short loc_18003579F
0x18003577f  cmp     byte ptr [rcx+19h], 5
0x180035783  jb      short loc_18003579F
0x180035785  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003578c  lea     edx, [rsi+6Fh]
0x18003578f  mov     rcx, [rcx+10h]
0x180035793  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003579a  call    WPP_SF_s
0x18003579f  lea     r9, [rbp+57h+phContext]; phContext
0x1800357a3  mov     [rbx+4ACh], r12d
0x1800357aa  xor     r8d, r8d; pvReserved2
0x1800357ad  xor     edx, edx; pvReserved1
0x1800357af  xor     ecx, ecx; dwScope
0x1800357b1  call    cs:__imp_SCardEstablishContext
0x1800357b7  mov     ebx, eax
0x1800357b9  test    eax, eax
0x1800357bb  jz      short loc_180035814
0x1800357bd  mov     edx, esi
0x1800357bf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800357c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357cb  lea     rax, WPP_GLOBAL_Control
0x1800357d2  cmp     rcx, rax
0x1800357d5  jz      loc_180035C8E
0x1800357db  test    byte ptr [rcx+1Ch], 1
0x1800357df  jz      loc_180035C8E
0x1800357e5  cmp     [rcx+19h], sil
0x1800357e9  jb      loc_180035C8E
0x1800357ef  mov     edx, 72h ; 'r'
0x1800357f4  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800357fb  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180035802  mov     rcx, [rcx+10h]
0x180035806  mov     dword ptr [rsp+0C0h+mszCards], ebx
0x18003580a  call    WPP_SF_sd
0x18003580f  jmp     loc_180035C8E
0x180035814  mov     rcx, [rbp+57h+phContext]; hContext
0x180035818  lea     r9, [rbp+57h+pcchReaders]; pcchReaders
0x18003581c  lea     r8, [rbp+57h+mszReaders]; mszReaders
0x180035820  xor     edx, edx; mszGroups
0x180035822  call    cs:__imp_SCardListReadersW
0x180035828  mov     ebx, eax
0x18003582a  test    eax, eax
0x18003582c  jz      short loc_180035867
0x18003582e  mov     edx, esi
0x180035830  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035835  mov     rcx, cs:WPP_GLOBAL_Control
0x18003583c  lea     rax, WPP_GLOBAL_Control
0x180035843  cmp     rcx, rax
0x180035846  jz      loc_180035C8E
0x18003584c  test    byte ptr [rcx+1Ch], 1
0x180035850  jz      loc_180035C8E
0x180035856  cmp     [rcx+19h], sil
0x18003585a  jb      loc_180035C8E
0x180035860  mov     edx, 73h ; 's'
0x180035865  jmp     short loc_1800357F4
0x180035867  mov     edx, [rbp+57h+pcchReaders]
0x18003586a  mov     ebx, r12d
0x18003586d  test    edx, edx
0x18003586f  jz      loc_180035C89
0x180035875  mov     rax, qword ptr [rbp+57h+mszReaders]
0x180035879  mov     ecx, ebx
0x18003587b  lea     rcx, [rax+rcx*2]; Source
0x18003587f  cmp     r12w, [rcx]
0x180035883  jz      short loc_18003589B
0x180035885  sub     edx, ebx; MaxCount
0x180035887  inc     r14d
0x18003588a  call    cs:__imp_wcsnlen
0x180035890  mov     edx, [rbp+57h+pcchReaders]
0x180035893  inc     ebx
0x180035895  add     ebx, eax
0x180035897  cmp     ebx, edx
0x180035899  jb      short loc_180035875
0x18003589b  mov     [rbp+57h+var_90], r14d
0x18003589f  cmp     ebx, edx
0x1800358a1  jnb     loc_180035C89
0x1800358a7  test    r14d, r14d
0x1800358aa  jnz     short loc_1800358B6
0x1800358ac  mov     ebx, 8010002Eh
0x1800358b1  jmp     loc_180035C8E
0x1800358b6  mov     ebx, r14d
0x1800358b9  shl     rbx, 6
0x1800358bd  mov     rcx, rbx; size
0x1800358c0  mov     esi, r14d
0x1800358c3  call    MIDL_user_allocate
0x1800358c8  mov     r13, rax
0x1800358cb  test    rax, rax
0x1800358ce  jnz     short loc_180035927
0x1800358d0  lea     esi, [rax+2]
0x1800358d3  mov     edx, esi
0x1800358d5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800358da  lea     ebx, [rsi+6]
0x1800358dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358e4  lea     rax, WPP_GLOBAL_Control
0x1800358eb  cmp     rcx, rax
0x1800358ee  jz      loc_180035C8E
0x1800358f4  test    byte ptr [rcx+1Ch], 1
0x1800358f8  jz      loc_180035C8E
0x1800358fe  cmp     [rcx+19h], sil
0x180035902  jb      loc_180035C8E
0x180035908  lea     edx, [rsi+72h]
0x18003590b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180035912  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180035919  mov     rcx, [rcx+10h]
0x18003591d  call    WPP_SF_s
0x180035922  jmp     loc_180035C8E
0x180035927  mov     r8, rbx; Size
0x18003592a  xor     edx, edx; Val
0x18003592c  mov     rcx, r13; void *
0x18003592f  call    memset_0
0x180035934  shl     rsi, 3
0x180035938  mov     rcx, rsi; size
0x18003593b  call    MIDL_user_allocate
0x180035940  mov     [rbp+57h+var_80], rax
0x180035944  mov     r15, rax
0x180035947  test    rax, rax
0x18003594a  jnz     short loc_180035989
0x18003594c  lea     esi, [rax+2]
0x18003594f  mov     edx, esi
0x180035951  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035956  lea     ebx, [rsi+6]
0x180035959  mov     rcx, cs:WPP_GLOBAL_Control
0x180035960  lea     rax, WPP_GLOBAL_Control
0x180035967  cmp     rcx, rax
0x18003596a  jz      loc_180035C8E
0x180035970  test    byte ptr [rcx+1Ch], 1
0x180035974  jz      loc_180035C8E
0x18003597a  cmp     [rcx+19h], sil
0x18003597e  jb      loc_180035C8E
0x180035984  lea     edx, [rsi+73h]
0x180035987  jmp     short loc_18003590B
0x180035989  mov     r8, rsi; Size
0x18003598c  xor     edx, edx; Val
0x18003598e  mov     rcx, rax; void *
0x180035991  call    memset_0
0x180035996  mov     ebx, r12d
0x180035999  mov     esi, r12d
0x18003599c  cmp     [rbp+57h+pcchReaders], r12d
0x1800359a0  jbe     short loc_1800359E9
0x1800359a2  mov     rax, qword ptr [rbp+57h+mszReaders]
0x1800359a6  mov     ecx, ebx
0x1800359a8  lea     rdx, [rax+rcx*2]
0x1800359ac  cmp     r12w, [rdx]
0x1800359b0  jz      short loc_1800359E9
0x1800359b2  mov     eax, esi
0x1800359b4  shl     rax, 6
0x1800359b8  mov     [rax+r13], rdx
0x1800359bc  mov     [rax+r13+10h], r12d
0x1800359c1  mov     rax, qword ptr [rbp+57h+mszReaders]
0x1800359c5  lea     rcx, [rax+rcx*2]; Source
0x1800359c9  test    rcx, rcx
0x1800359cc  jnz     short loc_1800359D3
0x1800359ce  mov     rax, r12
0x1800359d1  jmp     short loc_1800359DE
0x1800359d3  mov     edx, [rbp+57h+pcchReaders]
0x1800359d6  sub     edx, ebx; MaxCount
0x1800359d8  call    cs:__imp_wcsnlen
0x1800359de  inc     ebx
0x1800359e0  inc     esi
0x1800359e2  add     ebx, eax
0x1800359e4  cmp     ebx, [rbp+57h+pcchReaders]
0x1800359e7  jb      short loc_1800359A2
0x1800359e9  mov     rcx, [rbp+57h+phContext]; hContext
0x1800359ed  mov     r9d, r14d; cReaders
0x1800359f0  mov     r8, r13; rgReaderStates
0x1800359f3  xor     edx, edx; dwTimeout
0x1800359f5  call    cs:__imp_SCardGetStatusChangeW
0x1800359fb  mov     ebx, eax
0x1800359fd  test    eax, eax
0x1800359ff  jz      short loc_180035A40
0x180035a01  mov     esi, 2
0x180035a06  mov     edx, esi
0x180035a08  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180035a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a14  lea     rax, WPP_GLOBAL_Control
0x180035a1b  cmp     rcx, rax
0x180035a1e  jz      loc_180035C8E
0x180035a24  test    byte ptr [rcx+1Ch], 1
0x180035a28  jz      loc_180035C8E
0x180035a2e  cmp     [rcx+19h], sil
0x180035a32  jb      loc_180035C8E
0x180035a38  lea     edx, [rsi+74h]
0x180035a3b  jmp     loc_1800357F4
0x180035a40  mov     [rbp+57h+var_6C], r12d
0x180035a44  mov     r8d, r12d
0x180035a47  mov     esi, r12d
0x180035a4a  mov     edx, r12d
0x180035a4d  test    r14d, r14d
0x180035a50  jz      loc_180035C52
0x180035a56  mov     eax, edx
0x180035a58  shl     rax, 6
0x180035a5c  mov     ecx, [rax+r13+14h]
0x180035a61  lea     eax, [r8+1]
0x180035a65  and     cl, 0A0h
0x180035a68  cmp     cl, 20h ; ' '
0x180035a6b  cmovnz  eax, r8d
0x180035a6f  inc     edx
0x180035a71  mov     r8d, eax
0x180035a74  cmp     edx, r14d
0x180035a77  jb      short loc_180035A56
0x180035a79  mov     [rbp+57h+var_50], eax
0x180035a7c  mov     r15d, r12d
0x180035a7f  mov     r14d, r15d
0x180035a82  shl     r14, 6
0x180035a86  mov     r12d, r15d
0x180035a89  mov     eax, [r14+r13+14h]
0x180035a8e  and     al, 0A0h
0x180035a90  cmp     al, 20h ; ' '
0x180035a92  jnz     loc_180035B6D
0x180035a98  mov     rax, [rbp+57h+arg_0]
0x180035a9c  mov     rdx, [r14+r13]; unsigned __int16 *
0x180035aa0  mov     rcx, [rax+488h]; unsigned __int16 *
0x180035aa7  call    ?MatchesRequiredReaderName@@YAHPEAG0@Z; MatchesRequiredReaderName(ushort *,ushort *)
0x180035aac  test    eax, eax
0x180035aae  jz      loc_180035B6D
0x180035ab4  mov     rax, [rbp+57h+var_80]
0x180035ab8  lea     rdx, [r13+1Ch]
0x180035abc  mov     rcx, [rbp+57h+phContext]; hContext
0x180035ac0  add     rdx, r14; pbAtr
0x180035ac3  xor     r9d, r9d; cguidInterfaceCount
0x180035ac6  mov     [rbp+57h+pcchCards], 0FFFFFFFFh
0x180035acd  xor     r8d, r8d; rgquidInterfaces
0x180035ad0  lea     r12, [rax+r12*8]
0x180035ad4  lea     rax, [rbp+57h+pcchCards]
0x180035ad8  mov     [rsp+28h], rax; pcchCards
0x180035add  mov     [rsp+0C0h+mszCards], r12; mszCards
0x180035ae2  call    cs:__imp_SCardListCardsW
0x180035ae8  mov     ebx, eax
0x180035aea  test    eax, eax
0x180035aec  jnz     short loc_180035B6D
0x180035aee  xor     ebx, ebx
0x180035af0  test    rdi, rdi
0x180035af3  jz      short loc_180035B23
0x180035af5  cmp     [rdi+250h], ebx
0x180035afb  jz      short loc_180035B05
0x180035afd  mov     rcx, rdi; struct _CARD_STATE *
0x180035b00  call    CspEndTransaction
0x180035b05  lea     rcx, [rdi+270h]
0x180035b0c  mov     [rbp+57h+var_58], rbx
0x180035b10  call    CspLeaveCriticalSection
0x180035b15  xor     edx, edx
0x180035b17  mov     rcx, rdi
0x180035b1a  call    CardStateReleaseRef
0x180035b1f  mov     [rbp+57h+var_88], rbx
0x180035b23  mov     r8, [rbp+57h+arg_0]; struct _CARD_MATCH_DATA *
0x180035b27  lea     r9, [rbp+57h+var_88]; struct _CARD_STATE **
0x180035b2b  mov     rdx, [r12]; unsigned __int16 *
0x180035b2f  mov     rcx, [r14+r13]; unsigned __int16 *
0x180035b33  call    ?VerifyCard@@YAKPEAG0PEAU_CARD_MATCH_DATA@@PEAPEAU_CARD_STATE@@@Z; VerifyCard(ushort *,ushort *,_CARD_MATCH_DATA *,_CARD_STATE * *)
0x180035b38  mov     rdi, [rbp+57h+var_88]
0x180035b3c  xor     r12d, r12d
0x180035b3f  mov     ebx, eax
0x180035b41  test    eax, eax
0x180035b43  jnz     short loc_180035B70
0x180035b45  lea     rdx, [rdi+270h]
0x180035b4c  lea     rcx, [rbp+57h+var_60]
0x180035b50  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180035b55  mov     ecx, [rbp+57h+arg_10]
0x180035b58  inc     esi
0x180035b5a  test    ecx, ecx
0x180035b5c  jz      short loc_180035B85
0x180035b5e  cmp     ecx, 1
0x180035b61  jnz     short loc_180035B73
0x180035b63  cmp     esi, ecx
0x180035b65  ja      short loc_180035B85
0x180035b67  mov     [rbp+57h+var_6C], r15d
  ... truncated ...
```
