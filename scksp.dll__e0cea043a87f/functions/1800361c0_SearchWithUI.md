# SearchWithUI

- ea: `0x1800361c0`
- end: `0x180036762`
- name: `SearchWithUI`
- size: `1442`
- prototype: `__int64 __fastcall(struct _CARD_MATCH_DATA *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800354b8`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d9d0`
- `0x180011444`
- `0x180011fd8`
- `0x180013734`
- `0x180013ce4`
- `0x18002b140`
- `0x180034df4`
- `0x1800361c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180036303`
- `msvcrt!memcpy_s` at `0x180036303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003658e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003658e`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x1800364ab`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x1800364ab`

## pseudocode

```c
__int64 __fastcall SearchWithUI(struct _CARD_MATCH_DATA *a1, struct _CARD_STATE **a2)
{
  bool v3; // zf
  ULONG ulInAuthBufferSize; // r13d
  unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  unsigned __int16 *v7; // rdi
  int v8; // ebx
  PVOID v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // ebx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  DWORD v19; // eax
  unsigned int *v20; // r14
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  unsigned __int16 *v23; // r12
  _BYTE *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  size_t v29; // rbx
  unsigned __int16 *v30; // rax
  __int64 v31; // rcx
  unsigned __int16 *v32; // r15
  __int64 v33; // rcx
  _CREDUI_INFOW pUiInfo; // [rsp+50h] [rbp-19h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+D0h] [rbp+67h] BYREF
  struct _CARD_STATE **v36; // [rsp+D8h] [rbp+6Fh]
  ULONG pulAuthPackage; // [rsp+E0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp+7Fh] BYREF

  v36 = a2;
  pulAuthPackage = -629;
  memset(&pUiInfo, 0, sizeof(pUiInfo));
  pv = 0;
  pulOutAuthBufferSize = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v3 = *((_DWORD *)a1 + 9) == 2;
  *((_DWORD *)a1 + 299) = 1;
  if ( v3 )
  {
    ulInAuthBufferSize = *((_DWORD *)a1 + 298) + 40;
    v5 = (unsigned __int16 *)MIDL_user_allocate(ulInAuthBufferSize);
    v7 = v5;
    if ( !v5 )
    {
      WppTraceIndent(v6, 2u);
      v8 = 8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_42;
    }
    memset_0(v5, 0, ulInAuthBufferSize);
    *((_DWORD *)v7 + 2) = 2;
    *((_DWORD *)v7 + 5) = *((_DWORD *)a1 + 14);
    *((_DWORD *)v7 + 3) = 40;
    v10 = *((_DWORD *)a1 + 298);
    *((_DWORD *)v7 + 4) = v10;
    memcpy_s(v7 + 20, v10, *((const void *const *)a1 + 148), *((unsigned int *)a1 + 298));
    goto LABEL_28;
  }
  v11 = *((_QWORD *)a1 + 145);
  v12 = -1;
  v13 = 0;
  v14 = 0;
  if ( v11 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v11 + 2 * v15) );
    v13 = v15 + 1;
  }
  v16 = *((_QWORD *)a1 + 146);
  if ( v16 )
  {
    do
      ++v12;
    while ( *(_WORD *)(v16 + 2 * v12) );
    v14 = v12 + 1;
  }
  ulInAuthBufferSize = 2 * (v14 + v13) + 40;
  v17 = (unsigned __int16 *)MIDL_user_allocate(ulInAuthBufferSize);
  v7 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, 2 * (v14 + v13) + 40);
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 7) = *((_DWORD *)a1 + 14);
    *((_DWORD *)v7 + 8) = *((_DWORD *)a1 + 8);
    *((_DWORD *)v7 + 5) = 2 * v13 + 40;
    *((_DWORD *)v7 + 3) = 40;
    *((_DWORD *)v7 + 4) = v13;
    *((_DWORD *)v7 + 6) = v14;
    if ( v13 )
    {
      v8 = StringCchCopyW(v7 + 20, v13, *((const unsigned __int16 **)a1 + 145));
      if ( v8 < 0 )
        goto LABEL_42;
    }
    if ( *((_DWORD *)v7 + 6) )
    {
      v8 = StringCchCopyW(
             (unsigned __int16 *)((char *)v7 + *((unsigned int *)v7 + 5)),
             *((unsigned int *)v7 + 6),
             *((const unsigned __int16 **)a1 + 146));
      if ( v8 < 0 )
        goto LABEL_42;
    }
LABEL_28:
    *(_DWORD *)v7 = *((_DWORD *)a1 + 22);
    *((_DWORD *)v7 + 1) = *((_DWORD *)a1 + 23);
    pUiInfo.hwndParent = (HWND)*((_QWORD *)a1 + 5);
    pUiInfo.pszCaptionText = (PCWSTR)*((_QWORD *)a1 + 143);
    pUiInfo.pszMessageText = (PCWSTR)*((_QWORD *)a1 + 144);
    pUiInfo.cbSize = 40;
    pUiInfo.hbmBanner = 0;
    v19 = CredUIPromptForWindowsCredentialsW(
            &pUiInfo,
            0,
            &pulAuthPackage,
            v7,
            ulInAuthBufferSize,
            &pv,
            &pulOutAuthBufferSize,
            0,
            0x10u);
    v8 = v19;
    if ( v19 == 1223 )
    {
      v8 = -2146434962;
    }
    else if ( !v19 )
    {
      if ( pulOutAuthBufferSize >= 0x10
        && (v20 = (unsigned int *)pv, *((_DWORD *)pv + 1))
        && *((_DWORD *)pv + 3)
        && (v9 = (PVOID)(2LL * *((unsigned int *)pv + 1)),
            pulOutAuthBufferSize >= (unsigned __int64)v9 + *(unsigned int *)pv)
        && pulOutAuthBufferSize >= *((unsigned int *)pv + 2) + 2 * (unsigned __int64)*((unsigned int *)pv + 3) )
      {
        v21 = (unsigned __int16 *)MIDL_user_allocate((size_t)v9);
        v23 = v21;
        if ( v21 )
        {
          memset_0(v21, 0, 2LL * v20[1]);
          v8 = StringCchCopyNW(v23, v20[1], (const unsigned __int16 *)((char *)v20 + *v20), v20[1]);
          if ( v8 >= 0 )
          {
            v29 = 2LL * (v20[3] + 1);
            v30 = (unsigned __int16 *)MIDL_user_allocate(v29);
            v32 = v30;
            if ( v30 )
            {
              memset_0(v30, 0, v29);
              v8 = StringCchCopyNW(v32, v20[3], (const unsigned __int16 *)((char *)v20 + v20[2]), v20[3]);
              if ( v8 >= 0 )
              {
                v8 = VerifyCard(v23, v32, a1, v36);
                if ( v8 )
                {
                  WppTraceIndent(v33, 2u);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      111,
                      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
                      (_DWORD)WPP_pszIndent,
                      v8);
                  }
                }
              }
              CspFreeH(v32);
            }
            else
            {
              WppTraceIndent(v31, 2u);
              v8 = 8;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  110,
                  &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
                  WPP_pszIndent);
              }
            }
          }
          CspFreeH(v23);
        }
        else
        {
          WppTraceIndent(v22, 2u);
          v8 = 8;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
              WPP_pszIndent);
          }
        }
      }
      else
      {
        v8 = 13;
      }
    }
    goto LABEL_42;
  }
  WppTraceIndent(v18, 2u);
  v8 = 8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
LABEL_42:
  v24 = pv;
  if ( pv )
  {
    v25 = pulOutAuthBufferSize;
    if ( pulOutAuthBufferSize )
    {
      do
      {
        *v24++ = 0;
        --v25;
      }
      while ( v25 );
    }
    CoTaskMemFree(pv);
  }
  if ( v7 )
  {
    v26 = ulInAuthBufferSize;
    v27 = v7;
    if ( ulInAuthBufferSize )
    {
      do
      {
        *(_BYTE *)v27 = 0;
        v27 = (unsigned __int16 *)((char *)v27 + 1);
        --v26;
      }
      while ( v26 );
    }
    CspFreeH(v7);
  }
  WppTraceIndent((__int64)v9, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800361c0  mov     [rsp-8+arg_8], rdx
0x1800361c5  push    rbp
0x1800361c6  push    rbx
0x1800361c7  push    rsi
0x1800361c8  push    rdi
0x1800361c9  push    r12
0x1800361cb  push    r13
0x1800361cd  push    r14
0x1800361cf  push    r15
0x1800361d1  lea     rbp, [rsp-1Fh]
0x1800361d6  sub     rsp, 88h
0x1800361dd  xorps   xmm0, xmm0
0x1800361e0  mov     [rbp+57h+pulAuthPackage], 0FFFFFD8Bh
0x1800361e7  xor     r12d, r12d
0x1800361ea  xor     eax, eax
0x1800361ec  xor     edx, edx
0x1800361ee  mov     [rbp+57h+pUiInfo.hbmBanner], rax
0x1800361f2  movups  xmmword ptr [rbp+57h+pUiInfo.cbSize], xmm0
0x1800361f6  mov     [rbp+57h+pv], r12
0x1800361fa  mov     rsi, rcx
0x1800361fd  movups  xmmword ptr [rbp+57h+pUiInfo.pszMessageText], xmm0
0x180036201  mov     [rbp+57h+arg_0], r12d
0x180036205  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003620a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036211  lea     r15, WPP_GLOBAL_Control
0x180036218  cmp     rcx, r15
0x18003621b  jz      short loc_180036245
0x18003621d  test    byte ptr [rcx+1Ch], 2
0x180036221  jz      short loc_180036245
0x180036223  cmp     byte ptr [rcx+19h], 5
0x180036227  jb      short loc_180036245
0x180036229  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180036230  lea     edx, [r12+6Ah]
0x180036235  mov     rcx, [rcx+10h]
0x180036239  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180036240  call    WPP_SF_s
0x180036245  cmp     dword ptr [rsi+24h], 2
0x180036249  mov     dword ptr [rsi+4ACh], 1
0x180036253  jnz     loc_18003630E
0x180036259  mov     r13d, [rsi+4A8h]
0x180036260  add     r13d, 28h ; '('
0x180036264  mov     ecx, r13d; size
0x180036267  mov     ebx, r13d
0x18003626a  call    MIDL_user_allocate
0x18003626f  mov     rdi, rax
0x180036272  test    rax, rax
0x180036275  jnz     short loc_1800362C5
0x180036277  lea     edx, [rax+2]
0x18003627a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003627f  lea     ebx, [rdi+8]
0x180036282  mov     rcx, cs:WPP_GLOBAL_Control
0x180036289  cmp     rcx, r15
0x18003628c  jz      loc_180036566
0x180036292  test    byte ptr [rcx+1Ch], 1
0x180036296  jz      loc_180036566
0x18003629c  cmp     byte ptr [rcx+19h], 2
0x1800362a0  jb      loc_180036566
0x1800362a6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800362ad  lea     edx, [rdi+6Bh]
0x1800362b0  mov     rcx, [rcx+10h]
0x1800362b4  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800362bb  call    WPP_SF_s
0x1800362c0  jmp     loc_180036566
0x1800362c5  mov     r8, rbx; Size
0x1800362c8  xor     edx, edx; Val
0x1800362ca  mov     rcx, rdi; void *
0x1800362cd  call    memset_0
0x1800362d2  mov     dword ptr [rdi+8], 2
0x1800362d9  lea     rcx, [rdi+28h]; Destination
0x1800362dd  mov     eax, [rsi+38h]
0x1800362e0  mov     [rdi+14h], eax
0x1800362e3  mov     dword ptr [rdi+0Ch], 28h ; '('
0x1800362ea  mov     eax, [rsi+4A8h]
0x1800362f0  mov     [rdi+10h], eax
0x1800362f3  mov     edx, eax; DestinationSize
0x1800362f5  mov     r9d, [rsi+4A8h]; SourceSize
0x1800362fc  mov     r8, [rsi+4A0h]; Source
0x180036303  call    cs:__imp_memcpy_s
0x180036309  jmp     loc_180036446
0x18003630e  mov     rdx, [rsi+488h]
0x180036315  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036319  mov     ebx, r12d
0x18003631c  mov     r14d, r12d
0x18003631f  test    rdx, rdx
0x180036322  jz      short loc_180036334
0x180036324  mov     rcx, rax
0x180036327  inc     rcx
0x18003632a  cmp     [rdx+rcx*2], r12w
0x18003632f  jnz     short loc_180036327
0x180036331  lea     ebx, [rcx+1]
0x180036334  mov     rcx, [rsi+490h]
0x18003633b  test    rcx, rcx
0x18003633e  jz      short loc_18003634E
0x180036340  inc     rax
0x180036343  cmp     [rcx+rax*2], r12w
0x180036348  jnz     short loc_180036340
0x18003634a  lea     r14d, [rax+1]
0x18003634e  lea     eax, [r14+rbx]
0x180036352  lea     r13d, ds:28h[rax*2]
0x18003635a  mov     ecx, r13d; size
0x18003635d  mov     r15d, r13d
0x180036360  call    MIDL_user_allocate
0x180036365  mov     rdi, rax
0x180036368  test    rax, rax
0x18003636b  jnz     short loc_1800363C2
0x18003636d  lea     edx, [rax+2]
0x180036370  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180036375  lea     ebx, [rdi+8]
0x180036378  mov     rcx, cs:WPP_GLOBAL_Control
0x18003637f  lea     rsi, WPP_GLOBAL_Control
0x180036386  cmp     rcx, rsi
0x180036389  jz      loc_18003656D
0x18003638f  test    byte ptr [rcx+1Ch], 1
0x180036393  jz      loc_18003656D
0x180036399  cmp     byte ptr [rcx+19h], 2
0x18003639d  jb      loc_18003656D
0x1800363a3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800363aa  lea     edx, [rdi+6Ch]
0x1800363ad  mov     rcx, [rcx+10h]
0x1800363b1  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800363b8  call    WPP_SF_s
0x1800363bd  jmp     loc_18003656D
0x1800363c2  mov     r8, r15; Size
0x1800363c5  xor     edx, edx; Val
0x1800363c7  mov     rcx, rdi; void *
0x1800363ca  call    memset_0
0x1800363cf  mov     dword ptr [rdi+8], 1
0x1800363d6  mov     eax, [rsi+38h]
0x1800363d9  mov     [rdi+1Ch], eax
0x1800363dc  mov     eax, [rsi+20h]
0x1800363df  mov     [rdi+20h], eax
0x1800363e2  lea     eax, ds:28h[rbx*2]
0x1800363e9  mov     [rdi+14h], eax
0x1800363ec  mov     dword ptr [rdi+0Ch], 28h ; '('
0x1800363f3  mov     [rdi+10h], ebx
0x1800363f6  mov     [rdi+18h], r14d
0x1800363fa  test    ebx, ebx
0x1800363fc  jz      short loc_18003641A
0x1800363fe  mov     r8, [rsi+488h]; unsigned __int16 *
0x180036405  lea     rcx, [rdi+28h]; unsigned __int16 *
0x180036409  mov     edx, ebx; unsigned __int64
0x18003640b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036410  mov     ebx, eax
0x180036412  test    eax, eax
0x180036414  js      loc_180036566
0x18003641a  cmp     [rdi+18h], r12d
0x18003641e  jbe     short loc_18003643F
0x180036420  mov     ecx, [rdi+14h]
0x180036423  mov     edx, [rdi+18h]; unsigned __int64
0x180036426  add     rcx, rdi; unsigned __int16 *
0x180036429  mov     r8, [rsi+490h]; unsigned __int16 *
0x180036430  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036435  mov     ebx, eax
0x180036437  test    eax, eax
0x180036439  js      loc_180036566
0x18003643f  lea     r15, WPP_GLOBAL_Control
0x180036446  mov     eax, [rsi+58h]
0x180036449  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x18003644d  mov     [rdi], eax
0x18003644f  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x180036453  mov     eax, [rsi+5Ch]
0x180036456  mov     r9, rdi; pvInAuthBuffer
0x180036459  mov     [rdi+4], eax
0x18003645c  xor     edx, edx; dwAuthError
0x18003645e  mov     rax, [rsi+28h]
0x180036462  mov     [rbp+57h+pUiInfo.hwndParent], rax
0x180036466  mov     rax, [rsi+478h]
0x18003646d  mov     [rbp+57h+pUiInfo.pszCaptionText], rax
0x180036471  mov     rax, [rsi+480h]
0x180036478  mov     [rsp+0C0h+dwFlags], 10h; dwFlags
0x180036480  mov     [rbp+57h+pUiInfo.pszMessageText], rax
0x180036484  lea     rax, [rbp+57h+arg_0]
0x180036488  mov     [rsp+0C0h+pfSave], r12; pfSave
0x18003648d  mov     [rsp+0C0h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180036492  lea     rax, [rbp+57h+pv]
0x180036496  mov     [rsp+0C0h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x18003649b  mov     [rsp+0C0h+ulInAuthBufferSize], r13d; ulInAuthBufferSize
0x1800364a0  mov     [rbp+57h+pUiInfo.cbSize], 28h ; '('
0x1800364a7  mov     [rbp+57h+pUiInfo.hbmBanner], r12
0x1800364ab  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x1800364b1  mov     ebx, eax
0x1800364b3  cmp     eax, 4C7h
0x1800364b8  jnz     short loc_1800364C4
0x1800364ba  mov     ebx, 8010006Eh
0x1800364bf  jmp     loc_180036566
0x1800364c4  test    eax, eax
0x1800364c6  jnz     loc_180036566
0x1800364cc  cmp     [rbp+57h+arg_0], 10h
0x1800364d0  jnb     short loc_1800364DC
0x1800364d2  mov     ebx, 0Dh
0x1800364d7  jmp     loc_180036566
0x1800364dc  mov     r14, [rbp+57h+pv]
0x1800364e0  cmp     [r14+4], r12d
0x1800364e4  jz      short loc_1800364D2
0x1800364e6  cmp     [r14+0Ch], r12d
0x1800364ea  jz      short loc_1800364D2
0x1800364ec  mov     ecx, [r14+4]
0x1800364f0  mov     eax, [r14]
0x1800364f3  add     rcx, rcx; size
0x1800364f6  mov     r8d, [rbp+57h+arg_0]
0x1800364fa  add     rax, rcx
0x1800364fd  cmp     r8, rax
0x180036500  jb      short loc_1800364D2
0x180036502  mov     edx, [r14+0Ch]
0x180036506  mov     eax, [r14+8]
0x18003650a  lea     rdx, [rax+rdx*2]
0x18003650e  cmp     r8, rdx
0x180036511  jb      short loc_1800364D2
0x180036513  call    MIDL_user_allocate
0x180036518  mov     r12, rax
0x18003651b  test    rax, rax
0x18003651e  jnz     loc_180036610
0x180036524  lea     edx, [rax+2]
0x180036527  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003652c  lea     ebx, [r12+8]
0x180036531  mov     rcx, cs:WPP_GLOBAL_Control
0x180036538  cmp     rcx, r15
0x18003653b  jz      short loc_180036563
0x18003653d  test    byte ptr [rcx+1Ch], 1
0x180036541  jz      short loc_180036563
0x180036543  cmp     byte ptr [rcx+19h], 2
0x180036547  jb      short loc_180036563
0x180036549  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180036550  lea     edx, [rbx+65h]
0x180036553  mov     rcx, [rcx+10h]
0x180036557  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003655e  call    WPP_SF_s
0x180036563  xor     r12d, r12d
0x180036566  lea     rsi, WPP_GLOBAL_Control
0x18003656d  mov     rax, [rbp+57h+pv]
0x180036571  test    rax, rax
0x180036574  jz      short loc_180036594
0x180036576  mov     ecx, [rbp+57h+arg_0]
0x180036579  test    rcx, rcx
0x18003657c  jz      short loc_18003658A
0x18003657e  mov     [rax], r12b
0x180036581  inc     rax
0x180036584  sub     rcx, 1
0x180036588  jnz     short loc_18003657E
0x18003658a  mov     rcx, [rbp+57h+pv]; pv
0x18003658e  call    cs:__imp_CoTaskMemFree
0x180036594  test    rdi, rdi
0x180036597  jz      short loc_1800365B8
0x180036599  mov     ecx, r13d
0x18003659c  mov     rax, rdi
0x18003659f  test    r13d, r13d
0x1800365a2  jz      short loc_1800365B0
0x1800365a4  mov     [rax], r12b
0x1800365a7  inc     rax
0x1800365aa  sub     rcx, 1
0x1800365ae  jnz     short loc_1800365A4
0x1800365b0  mov     rcx, rdi
0x1800365b3  call    CspFreeH
0x1800365b8  mov     edx, 1
0x1800365bd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800365c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365c9  cmp     rcx, rsi
0x1800365cc  jz      short loc_1800365FA
0x1800365ce  test    byte ptr [rcx+1Ch], 2
0x1800365d2  jz      short loc_1800365FA
0x1800365d4  cmp     byte ptr [rcx+19h], 5
0x1800365d8  jb      short loc_1800365FA
0x1800365da  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800365e1  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800365e8  mov     rcx, [rcx+10h]
0x1800365ec  mov     edx, 70h ; 'p'
0x1800365f1  mov     [rsp+0C0h+ulInAuthBufferSize], ebx
0x1800365f5  call    WPP_SF_sd
0x1800365fa  mov     eax, ebx
0x1800365fc  add     rsp, 88h
0x180036603  pop     r15
0x180036605  pop     r14
0x180036607  pop     r13
0x180036609  pop     r12
0x18003660b  pop     rdi
0x18003660c  pop     rsi
0x18003660d  pop     rbx
0x18003660e  pop     rbp
0x18003660f  retn
0x180036610  mov     r8d, [r14+4]
0x180036614  xor     edx, edx; Val
0x180036616  add     r8, r8; Size
0x180036619  mov     rcx, r12; void *
0x18003661c  call    memset_0
0x180036621  mov     edx, [r14+4]; unsigned __int64
0x180036625  mov     rcx, r12; unsigned __int16 *
0x180036628  mov     r8d, [r14]
0x18003662b  mov     r9d, edx; unsigned __int64
0x18003662e  add     r8, r14; unsigned __int16 *
0x180036631  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180036636  mov     ebx, eax
0x180036638  test    eax, eax
0x18003663a  jns     short loc_180036648
0x18003663c  lea     rsi, WPP_GLOBAL_Control
0x180036643  jmp     loc_180036752
0x180036648  mov     ebx, [r14+0Ch]
0x18003664c  inc     ebx
0x18003664e  add     rbx, rbx
0x180036651  mov     rcx, rbx; size
0x180036654  call    MIDL_user_allocate
  ... truncated ...
```
