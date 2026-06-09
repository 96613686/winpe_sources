# LookupOrCreateTokenFromHandle(void *,CToken * *)

- ea: `0x180031ae0`
- end: `0x1800320aa`
- name: `?LookupOrCreateTokenFromHandle@@YAJPEAXPEAPEAVCToken@@@Z`
- size: `1482`
- prototype: `__int64 __fastcall(void *, struct CToken **)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009700`
- `0x180029db0`
- `0x18002cad0`
- `0x1800899b0`
- `0x18008b9c4`
- `0x1800f7600`

## callees

- `0x180018344`
- `0x18001ec28`
- `0x180025c30`
- `0x180025d00`
- `0x180031ae0`
- `0x1800706b0`
- `0x180098b54`
- `0x1800b27e0`
- `0x18010a000`
- `0x18010a084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031cd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031db0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031d7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031d7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031df3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031df3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031c0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003201f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031c0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003201f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032069`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031d71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032069`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b6b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031cc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031f56`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031fcd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031b6b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031cc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031f56`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180031fcd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180031dc7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180031dc7`

## string_xrefs

- `0x180031f67`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180031fde`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180031bc1`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180031d26`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180031f83`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180031ffa`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180031bac`: `LookupOrCreateTokenFromHandle`
- `0x180031d03`: `LookupOrCreateTokenFromHandle`
- `0x180031eed`: `this:%p handle:%p LUID:%I64X LUIDMOD:%I64X SID:%!sid!`
- `0x180031ebc`: `CToken::CToken`
- `0x180031ef9`: `onecore\com\combase\rpcss\objex\token.hxx`

## pseudocode

```c
__int64 __fastcall LookupOrCreateTokenFromHandle(void *a1, struct CToken **a2)
{
  __int64 v2; // r15
  __int64 v3; // r9
  int v4; // ebx
  int v5; // edi
  __int64 result; // rax
  int v7; // r13d
  __int64 *v8; // r14
  __int64 *v9; // rsi
  DWORD v10; // r9d
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  PSID v15; // r12
  _QWORD *v16; // rax
  _QWORD *v17; // r14
  int v18; // r8d
  DWORD v19; // eax
  _QWORD *v20; // rbx
  const char *v21; // r9
  int LastError; // eax
  const char *v23; // r9
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rdx
  int ReturnLength; // [rsp+20h] [rbp-40h]
  int ReturnLengtha; // [rsp+20h] [rbp-40h]
  PSID v30; // [rsp+60h] [rbp+0h] BYREF
  DWORD v31[2]; // [rsp+68h] [rbp+8h] BYREF
  DWORD v32[2]; // [rsp+70h] [rbp+10h] BYREF
  __int64 v33; // [rsp+78h] [rbp+18h] BYREF
  _OWORD TokenInformation[3]; // [rsp+80h] [rbp+20h] BYREF
  __int64 v35; // [rsp+B0h] [rbp+50h]
  struct _TOKEN_APPCONTAINER_INFORMATION v36[2]; // [rsp+C0h] [rbp+60h] BYREF
  __int128 v37; // [rsp+D0h] [rbp+70h]
  __int128 v38; // [rsp+E0h] [rbp+80h]
  __int128 v39; // [rsp+F0h] [rbp+90h]
  __int128 v40; // [rsp+100h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+F8h]

  *(_QWORD *)v31 = a2;
  LODWORD(v30) = 56;
  v35 = 0;
  v2 = (__int64)a1;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  *(_OWORD *)&v36[0].TokenAppContainer = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  if ( GetTokenInformation(a1, TokenStatistics, TokenInformation, 0x38u, (PDWORD)&v30) )
  {
    v4 = DWORD2(TokenInformation[0]);
    v5 = v35;
    *(_QWORD *)v32 = *((_QWORD *)&TokenInformation[0] + 1);
    v33 = v35;
    LODWORD(result) = GetTokenPackageSid((void *)v2, v36);
    if ( (_DWORD)result )
    {
      return (unsigned __int16)result;
    }
    else
    {
      EnterCriticalSection(&gcsTokenLock);
      v7 = HIDWORD(v33);
      v8 = *(__int64 **)gpTokenList;
      if ( *(_QWORD *)gpTokenList )
      {
        while ( 1 )
        {
          v9 = v8 - 6;
          if ( v4 == *((_DWORD *)v8 + 8)
            && v32[1] == *((_DWORD *)v9 + 21)
            && *((_DWORD *)v9 + 22) == v5
            && *((_DWORD *)v9 + 23) == v7
            && !CToken::ComparePackageSids((CToken *)(v8 - 6), v36, 0)
            && !CToken::CompareToken((CToken *)(v8 - 6), (void *)v2) )
          {
            break;
          }
          v8 = (__int64 *)*v8;
          if ( !v8 )
            goto LABEL_17;
        }
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            "LookupOrCreateTokenFromHandle",
            689);
        _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
        **(_QWORD **)v31 = v9;
        LeaveCriticalSection(&gcsTokenLock);
        CloseHandle((HANDLE)v2);
        return 0;
      }
      else
      {
LABEL_17:
        LeaveCriticalSection(&gcsTokenLock);
        v10 = 44;
        LODWORD(v30) = 44;
        while ( 1 )
        {
          v11 = v10 + 15LL;
          if ( v11 <= v10 )
            v11 = 0xFFFFFFFFFFFFFF0LL;
          v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
          v13 = alloca(v12);
          v14 = alloca(v12);
          if ( GetTokenInformation((HANDLE)v2, TokenUser, &v30, v10, (PDWORD)&v30) )
            break;
          if ( GetLastError() != 122 )
          {
            if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              GetLastError();
              v3 = 735;
              goto LABEL_6;
            }
            return 14;
          }
          v10 = (unsigned int)v30;
        }
        v15 = v30;
        LODWORD(v30) = GetLengthSid(v30) - 12;
        v16 = HeapAlloc(g_hHeap, 0, (unsigned int)v30 + 168LL);
        v17 = v16;
        if ( !v16 )
        {
          **(_QWORD **)v31 = 0;
          return 14;
        }
        v18 = (int)v30;
        *v16 = &CToken::`vftable';
        v19 = v32[1];
        v17[6] = 0;
        v17[7] = 0;
        *((_BYTE *)v17 + 64) = 0;
        *((_DWORD *)v17 + 20) = v4;
        *((_DWORD *)v17 + 21) = v19;
        *((_DWORD *)v17 + 22) = v5;
        *((_DWORD *)v17 + 23) = v7;
        v17[12] = -1;
        *((_DWORD *)v17 + 26) = -1;
        *((_DWORD *)v17 + 27) = 4;
        v17[14] = -1;
        v17[15] = 0;
        v17[16] = 0;
        *((_BYTE *)v17 + 136) = 0;
        v17[18] = 0;
        *((_BYTE *)v17 + 152) = 0;
        v17[1] = 1;
        v17[2] = 0;
        v17[3] = 0;
        v17[4] = 0;
        v17[5] = 0;
        v17[9] = v2;
        memcpy_0((char *)v17 + 156, v15, (unsigned int)(v18 + 12));
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          ComTraceMessage(0xFFFFFFFFLL, "onecore\\com\\combase\\rpcss\\objex\\token.hxx", "CToken::CToken", 112);
        v20 = *(_QWORD **)v31;
        LODWORD(v33) = 0;
        v31[0] = 4;
        if ( !v2 )
          v2 = -6;
        *v20 = v17;
        if ( !GetTokenInformation((HANDLE)v2, TokenType, &v33, 4u, v31) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x128,
                        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                        v21);
          if ( LastError < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2FD,
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
              (const char *)(unsigned int)LastError,
              ReturnLength);
            return 0;
          }
        }
        if ( (_DWORD)v33 == 2 )
        {
          v31[0] = 0;
          v32[0] = 4;
          if ( !GetTokenInformation((HANDLE)v2, TokenImpersonationLevel, v31, 4u, v32) )
          {
            v24 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x128,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v23);
            if ( v24 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x301,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                (const char *)(unsigned int)v24,
                ReturnLengtha);
              return 0;
            }
          }
          if ( (int)v31[0] >= 2 )
          {
            EnterCriticalSection(&gcsTokenLock);
            v25 = gpTokenList;
            v26 = *v20 + 48LL;
            v27 = *(_QWORD *)(gpTokenList + 8);
            if ( v27 )
            {
              if ( *(_QWORD *)v27 )
                *(_QWORD *)(*(_QWORD *)v27 + 8LL) = v26;
              *(_QWORD *)v26 = *(_QWORD *)v27;
              *(_QWORD *)(v26 + 8) = v27;
              *(_QWORD *)v27 = v26;
            }
            else
            {
              *(_QWORD *)gpTokenList = v26;
            }
            *(_QWORD *)(v25 + 8) = v26;
            *(_BYTE *)(v26 + 16) = 1;
            LeaveCriticalSection(&gcsTokenLock);
          }
        }
        return 0;
      }
    }
  }
  else
  {
    if ( dword_18014E4B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      v3 = 648;
LABEL_6:
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        "LookupOrCreateTokenFromHandle",
        v3);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x180031ae0  push    rbp
0x180031ae2  push    rsi
0x180031ae3  push    rdi
0x180031ae4  push    r12
0x180031ae6  push    r13
0x180031ae8  push    r14
0x180031aea  push    r15
0x180031aec  sub     rsp, 120h
0x180031af3  lea     rbp, [rsp+60h]
0x180031af8  mov     [rbp+0F0h+arg_10], rbx
0x180031aff  mov     rax, cs:__security_cookie
0x180031b06  xor     rax, rbp
0x180031b09  mov     [rbp+0F0h+var_40], rax
0x180031b10  xorps   xmm1, xmm1
0x180031b13  mov     qword ptr [rbp+0F0h+var_E8], rdx
0x180031b17  xorps   xmm0, xmm0
0x180031b1a  mov     dword ptr [rbp+0F0h+var_F0], 38h ; '8'
0x180031b21  xor     eax, eax
0x180031b23  lea     r8, [rbp+0F0h+TokenInformation]; TokenInformation
0x180031b27  mov     [rbp+0F0h+var_A0], rax
0x180031b2b  mov     r9d, 38h ; '8'; TokenInformationLength
0x180031b31  lea     rax, [rbp+0F0h+var_F0]
0x180031b35  mov     edx, 0Ah; TokenInformationClass
0x180031b3a  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x180031b3f  mov     r15, rcx
0x180031b42  movups  [rbp+0F0h+TokenInformation], xmm0
0x180031b46  movups  [rbp+0F0h+var_C0], xmm0
0x180031b4a  movups  [rbp+0F0h+var_B0], xmm0
0x180031b4e  movups  xmmword ptr [rbp+0F0h+var_90.TokenAppContainer], xmm1
0x180031b52  movups  [rbp+0F0h+var_80], xmm1
0x180031b56  movups  [rbp+0F0h+var_70], xmm1
0x180031b5d  movups  [rbp+0F0h+var_60], xmm1
0x180031b64  movups  [rbp+0F0h+var_50], xmm1
0x180031b6b  call    cs:__imp_GetTokenInformation
0x180031b71  test    eax, eax
0x180031b73  jnz     short loc_180031BDB
0x180031b75  mov     eax, cs:dword_18014E4B8
0x180031b7b  test    eax, eax
0x180031b7d  jnz     short loc_180031B9C
0x180031b7f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180031b85  jz      loc_18003207C
0x180031b8b  mov     rax, cs:WPP_GLOBAL_Control
0x180031b92  test    byte ptr [rax+1Ch], 1
0x180031b96  jz      loc_18003207C
0x180031b9c  call    cs:__imp_GetLastError
0x180031ba2  mov     r9d, 288h
0x180031ba8  mov     dword ptr [rsp+150h+var_120], eax
0x180031bac  lea     r8, aLookuporcreate; "LookupOrCreateTokenFromHandle"
0x180031bb3  lea     rax, aWinerror; "%!WINERROR!"
0x180031bba  xor     esi, esi
0x180031bbc  mov     [rsp+150h+var_128], rax
0x180031bc1  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180031bc8  mov     ecx, 0FFFFFFFFh
0x180031bcd  mov     dword ptr [rsp+150h+ReturnLength], esi
0x180031bd1  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180031bd6  jmp     loc_18003207C
0x180031bdb  mov     rbx, qword ptr [rbp+0F0h+TokenInformation+8]
0x180031bdf  lea     rdx, [rbp+0F0h+var_90]; struct _TOKEN_APPCONTAINER_INFORMATION *
0x180031be3  mov     rdi, [rbp+0F0h+var_A0]
0x180031be7  mov     rcx, r15; void *
0x180031bea  mov     qword ptr [rbp+0F0h+var_E0], rbx
0x180031bee  mov     [rbp+0F0h+var_D8], rdi
0x180031bf2  call    ?GetTokenPackageSid@@YAJPEAXPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; GetTokenPackageSid(void *,_TOKEN_APPCONTAINER_INFORMATION *)
0x180031bf7  test    eax, eax
0x180031bf9  jz      short loc_180031C03
0x180031bfb  movzx   eax, ax
0x180031bfe  jmp     loc_180032081
0x180031c03  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031c0a  call    cs:__imp_EnterCriticalSection
0x180031c10  mov     rax, cs:?gpTokenList@@3PEAV?$CListBase@$00$00@@EA; CListBase<1,1> * gpTokenList
0x180031c17  movsxd  r13, dword ptr [rbp+0F0h+var_D8+4]
0x180031c1b  mov     r14, [rax]
0x180031c1e  test    r14, r14
0x180031c21  jz      short loc_180031C70
0x180031c23  cmp     ebx, [r14+20h]
0x180031c27  lea     rsi, [r14-30h]
0x180031c2b  jnz     short loc_180031C68
0x180031c2d  movsxd  r12, [rbp+0F0h+var_E0+4]
0x180031c31  cmp     r12d, [rsi+54h]
0x180031c35  jnz     short loc_180031C68
0x180031c37  cmp     [rsi+58h], edi
0x180031c3a  jnz     short loc_180031C68
0x180031c3c  cmp     [rsi+5Ch], r13d
0x180031c40  jnz     short loc_180031C68
0x180031c42  xor     r8d, r8d; bool
0x180031c45  lea     rdx, [rbp+0F0h+var_90]; void *
0x180031c49  mov     rcx, rsi; this
0x180031c4c  call    ?ComparePackageSids@CToken@@QEAAJPEAX_N@Z; CToken::ComparePackageSids(void *,bool)
0x180031c51  test    eax, eax
0x180031c53  jnz     short loc_180031C68
0x180031c55  mov     rdx, r15; void *
0x180031c58  mov     rcx, rsi; this
0x180031c5b  call    ?CompareToken@CToken@@QEAAJPEAX@Z; CToken::CompareToken(void *)
0x180031c60  test    eax, eax
0x180031c62  jz      loc_180031CEB
0x180031c68  mov     r14, [r14]
0x180031c6b  test    r14, r14
0x180031c6e  jnz     short loc_180031C23
0x180031c70  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031c77  call    cs:__imp_LeaveCriticalSection
0x180031c7d  mov     r9d, 2Ch ; ','
0x180031c83  mov     r14, 0FFFFFFFFFFFFFF0h
0x180031c8d  mov     dword ptr [rbp+0F0h+var_F0], r9d
0x180031c91  mov     eax, r9d
0x180031c94  lea     rcx, [rax+0Fh]
0x180031c98  cmp     rcx, rax
0x180031c9b  ja      short loc_180031CA0
0x180031c9d  mov     rcx, r14
0x180031ca0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180031ca4  mov     rax, rcx
0x180031ca7  call    _alloca_probe
0x180031cac  sub     rsp, rcx
0x180031caf  lea     rax, [rbp+0F0h+var_F0]
0x180031cb3  mov     edx, 1; TokenInformationClass
0x180031cb8  mov     rcx, r15; TokenHandle
0x180031cbb  lea     rsi, [rsp+150h+var_F0]
0x180031cc0  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x180031cc5  mov     r8, rsi; TokenInformation
0x180031cc8  call    cs:__imp_GetTokenInformation
0x180031cce  test    eax, eax
0x180031cd0  jnz     loc_180031DC1
0x180031cd6  call    cs:__imp_GetLastError
0x180031cdc  cmp     eax, 7Ah ; 'z'
0x180031cdf  jnz     loc_180031D89
0x180031ce5  mov     r9d, dword ptr [rbp+0F0h+var_F0]
0x180031ce9  jmp     short loc_180031C91
0x180031ceb  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180031cf2  jz      short loc_180031D5F
0x180031cf4  mov     rax, cs:WPP_GLOBAL_Control
0x180031cfb  test    byte ptr [rax+1Ch], 10h
0x180031cff  jz      short loc_180031D5F
0x180031d01  mov     eax, edi
0x180031d03  lea     r8, aLookuporcreate; "LookupOrCreateTokenFromHandle"
0x180031d0a  mov     rdx, r13
0x180031d0d  mov     rcx, r12
0x180031d10  shl     rdx, 20h
0x180031d14  mov     r9d, 2B1h
0x180031d1a  add     rdx, rax
0x180031d1d  shl     rcx, 20h
0x180031d21  mov     [rsp+150h+var_108], rdx
0x180031d26  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180031d2d  mov     eax, ebx
0x180031d2f  add     rcx, rax
0x180031d32  lea     rax, aFoundPHandlePL; "Found:%p HANDLE:%p LUID:%I64X LUIDMOD:%"...
0x180031d39  mov     [rsp+150h+var_110], rcx
0x180031d3e  mov     ecx, 0FFFFFFFFh
0x180031d43  mov     [rsp+150h+var_118], r15
0x180031d48  mov     [rsp+150h+var_120], rsi
0x180031d4d  mov     [rsp+150h+var_128], rax
0x180031d52  mov     dword ptr [rsp+150h+ReturnLength], 4
0x180031d5a  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180031d5f  lock inc dword ptr [rsi+8]
0x180031d63  mov     rbx, qword ptr [rbp+0F0h+var_E8]
0x180031d67  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180031d6e  mov     [rbx], rsi
0x180031d71  call    cs:__imp_LeaveCriticalSection
0x180031d77  mov     rcx, r15; hObject
0x180031d7a  xor     esi, esi
0x180031d7c  call    cs:__imp_CloseHandle
0x180031d82  mov     eax, esi
0x180031d84  jmp     loc_180032081
0x180031d89  mov     eax, cs:dword_18014E4B8
0x180031d8f  test    eax, eax
0x180031d91  jnz     short loc_180031DB0
0x180031d93  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180031d99  jz      loc_18003207C
0x180031d9f  mov     rax, cs:WPP_GLOBAL_Control
0x180031da6  test    byte ptr [rax+1Ch], 1
0x180031daa  jz      loc_18003207C
0x180031db0  call    cs:__imp_GetLastError
0x180031db6  mov     r9d, 2DFh
0x180031dbc  jmp     loc_180031BA8
0x180031dc1  mov     r12, [rsi]
0x180031dc4  mov     rcx, r12; pSid
0x180031dc7  call    cs:__imp_GetLengthSid
0x180031dcd  add     eax, 0FFFFFFF4h
0x180031dd0  mov     r8d, eax
0x180031dd3  add     r8, 0A8h; dwBytes
0x180031dda  mov     dword ptr [rbp+0F0h+var_F0], eax
0x180031ddd  cmp     r8, 0A8h
0x180031de4  jb      loc_180032073
0x180031dea  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180031df1  xor     edx, edx; dwFlags
0x180031df3  call    cs:__imp_HeapAlloc
0x180031df9  mov     r14, rax
0x180031dfc  test    rax, rax
0x180031dff  jz      loc_180032073
0x180031e05  mov     r8d, dword ptr [rbp+0F0h+var_F0]
0x180031e09  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x180031e10  xor     esi, esi
0x180031e12  mov     [r14], rax
0x180031e15  mov     eax, [rbp+0F0h+var_E0+4]
0x180031e18  lea     rcx, [r14+9Ch]; void *
0x180031e1f  mov     [r14+30h], rsi
0x180031e23  add     r8d, 0Ch; Size
0x180031e27  mov     [r14+38h], rsi
0x180031e2b  mov     rdx, r12; Src
0x180031e2e  mov     [r14+40h], sil
0x180031e32  mov     [r14+50h], ebx
0x180031e36  mov     [r14+54h], eax
0x180031e3a  mov     [r14+58h], edi
0x180031e3e  mov     [r14+5Ch], r13d
0x180031e42  mov     qword ptr [r14+60h], 0FFFFFFFFFFFFFFFFh
0x180031e4a  mov     dword ptr [r14+68h], 0FFFFFFFFh
0x180031e52  mov     dword ptr [r14+6Ch], 4
0x180031e5a  mov     qword ptr [r14+70h], 0FFFFFFFFFFFFFFFFh
0x180031e62  mov     [r14+78h], rsi
0x180031e66  mov     [r14+80h], rsi
0x180031e6d  mov     [r14+88h], sil
0x180031e74  mov     [r14+90h], rsi
0x180031e7b  mov     [r14+98h], sil
0x180031e82  mov     qword ptr [r14+8], 1
0x180031e8a  mov     [r14+10h], rsi
0x180031e8e  mov     [r14+18h], rsi
0x180031e92  mov     [r14+20h], rsi
0x180031e96  mov     [r14+28h], rsi
0x180031e9a  mov     [r14+48h], r15
0x180031e9e  call    memcpy_0
0x180031ea3  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x180031ea9  jz      short loc_180031F1C
0x180031eab  mov     rax, cs:WPP_GLOBAL_Control
0x180031eb2  test    byte ptr [rax+1Ch], 10h
0x180031eb6  jz      short loc_180031F1C
0x180031eb8  movsxd  rcx, [rbp+0F0h+var_E0+4]
0x180031ebc  lea     r8, aCtokenCtoken_0; "CToken::CToken"
0x180031ec3  mov     [rsp+150h+var_100], r12
0x180031ec8  mov     rdx, r13
0x180031ecb  shl     rdx, 20h
0x180031ecf  mov     r9d, 70h ; 'p'
0x180031ed5  shl     rcx, 20h
0x180031ed9  mov     eax, edi
0x180031edb  add     rdx, rax
0x180031ede  mov     eax, ebx
0x180031ee0  mov     [rsp+150h+var_108], rdx
0x180031ee5  add     rcx, rax
0x180031ee8  mov     [rsp+150h+var_110], rcx
0x180031eed  lea     rax, aThisPHandlePLu; "this:%p handle:%p LUID:%I64X LUIDMOD:%I"...
0x180031ef4  mov     [rsp+150h+var_118], r15
0x180031ef9  lea     rdx, aOnecoreComComb_103; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180031f00  mov     [rsp+150h+var_120], r14
0x180031f05  mov     ecx, 0FFFFFFFFh
0x180031f0a  mov     [rsp+150h+var_128], rax
0x180031f0f  mov     dword ptr [rsp+150h+ReturnLength], 4
0x180031f17  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x180031f1c  mov     rbx, qword ptr [rbp+0F0h+var_E8]
0x180031f20  lea     r8, [rbp+0F0h+var_D8]; TokenInformation
0x180031f24  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180031f2b  mov     dword ptr [rbp+0F0h+var_D8], esi
0x180031f2e  test    r15, r15
0x180031f31  mov     [rbp+0F0h+var_E8], 4
0x180031f38  mov     r9d, 4; TokenInformationLength
0x180031f3e  mov     edx, 8; TokenInformationClass
0x180031f43  cmovz   r15, rax
0x180031f47  mov     [rbx], r14
0x180031f4a  lea     rax, [rbp+0F0h+var_E8]
0x180031f4e  mov     rcx, r15; TokenHandle
0x180031f51  mov     [rsp+150h+ReturnLength], rax; int
0x180031f56  call    cs:__imp_GetTokenInformation
0x180031f5c  test    eax, eax
0x180031f5e  jnz     short loc_180031F9E
0x180031f60  mov     rcx, [rbp+0F8h]; this
0x180031f67  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180031f6e  mov     edx, 128h; void *
0x180031f73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031f78  test    eax, eax
0x180031f7a  jns     short loc_180031F9E
0x180031f7c  mov     rcx, [rbp+0F8h]; this
0x180031f83  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180031f8a  mov     r9d, eax; char *
0x180031f8d  mov     edx, 2FDh; void *
0x180031f92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031f97  mov     eax, esi
0x180031f99  jmp     loc_180032081
0x180031f9e  cmp     dword ptr [rbp+0F0h+var_D8], 2
0x180031fa2  jnz     loc_18003206F
0x180031fa8  lea     rax, [rbp+0F0h+var_E0]
0x180031fac  mov     [rbp+0F0h+var_E8], esi
0x180031faf  mov     r9d, 4; TokenInformationLength
0x180031fb5  mov     [rsp+150h+ReturnLength], rax; int
0x180031fba  lea     r8, [rbp+0F0h+var_E8]; TokenInformation
0x180031fbe  mov     [rbp+0F0h+var_E0], 4
0x180031fc5  mov     edx, 9; TokenInformationClass
0x180031fca  mov     rcx, r15; TokenHandle
0x180031fcd  call    cs:__imp_GetTokenInformation
0x180031fd3  test    eax, eax
0x180031fd5  jnz     short loc_180032012
0x180031fd7  mov     rcx, [rbp+0F8h]; this
0x180031fde  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180031fe5  mov     edx, 128h; void *
0x180031fea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031fef  test    eax, eax
0x180031ff1  jns     short loc_180032012
0x180031ff3  mov     rcx, [rbp+0F8h]; this
0x180031ffa  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x180032001  mov     r9d, eax; char *
0x180032004  mov     edx, 301h; void *
0x180032009  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003200e  mov     eax, esi
0x180032010  jmp     short loc_180032081
0x180032012  cmp     [rbp+0F0h+var_E8], 2
  ... truncated ...
```
