# LookupOrCreateTokenFromHandle(void *,CToken * *)

- ea: `0x18002aa10`
- end: `0x18002b03c`
- name: `?LookupOrCreateTokenFromHandle@@YAJPEAXPEAPEAVCToken@@@Z`
- size: `1580`
- prototype: `__int64 __fastcall(void *, struct CToken **)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a130`
- `0x18001f340`
- `0x1800221a0`
- `0x18008e54c`
- `0x180090af8`
- `0x1800ff634`

## callees

- `0x18000ce5c`
- `0x18001c624`
- `0x18002aa10`
- `0x180030060`
- `0x180030140`
- `0x180074dec`
- `0x18009e160`
- `0x1800b7ac0`
- `0x180112d00`
- `0x180112d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002acdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ad66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ad66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002afa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002afa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002abb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002accc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002abb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002accc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aff4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002aa9b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ac17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002aecf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002af4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002aa9b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ac17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002aecf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002af4c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ad34`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002ad34`

## string_xrefs

- `0x18002aee6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18002af63`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18002aafd`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002ac81`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002af02`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002af7f`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18002aae8`: `LookupOrCreateTokenFromHandle`
- `0x18002ac5e`: `LookupOrCreateTokenFromHandle`
- `0x18002ae66`: `this:%p handle:%p LUID:%I64X LUIDMOD:%I64X SID:%!sid!`
- `0x18002ae35`: `CToken::CToken`
- `0x18002ae72`: `onecore\com\combase\rpcss\objex\token.hxx`

## pseudocode

```c
__int64 __fastcall LookupOrCreateTokenFromHandle(void *a1, struct CToken **a2)
{
  __int64 v2; // r15
  DWORD LastError; // eax
  __int64 v4; // r9
  unsigned int v5; // ebx
  unsigned int v6; // edi
  __int64 result; // rax
  __int64 v8; // r13
  __int64 *v9; // r14
  __int64 *v10; // rsi
  __int64 v11; // r12
  DWORD v12; // r9d
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  PSID v17; // r12
  _QWORD *v18; // rax
  _QWORD *v19; // r14
  int v20; // r8d
  DWORD v21; // eax
  _QWORD *v22; // rbx
  const char *v23; // r9
  int v24; // eax
  const char *v25; // r9
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rdx
  PDWORD ReturnLength; // [rsp+20h] [rbp-40h]
  int ReturnLengtha; // [rsp+20h] [rbp-40h]
  int ReturnLengthb; // [rsp+20h] [rbp-40h]
  PSID v33; // [rsp+60h] [rbp+0h] BYREF
  DWORD v34[2]; // [rsp+68h] [rbp+8h] BYREF
  DWORD v35[2]; // [rsp+70h] [rbp+10h] BYREF
  __int64 v36; // [rsp+78h] [rbp+18h] BYREF
  _OWORD TokenInformation[3]; // [rsp+80h] [rbp+20h] BYREF
  __int64 v38; // [rsp+B0h] [rbp+50h]
  _TOKEN_APPCONTAINER_INFORMATION v39[2]; // [rsp+C0h] [rbp+60h] BYREF
  __int128 v40; // [rsp+D0h] [rbp+70h]
  __int128 v41; // [rsp+E0h] [rbp+80h]
  __int128 v42; // [rsp+F0h] [rbp+90h]
  __int128 v43; // [rsp+100h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+F8h]

  *(_QWORD *)v34 = a2;
  LODWORD(v33) = 56;
  v38 = 0;
  v2 = (__int64)a1;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  *(_OWORD *)&v39[0].TokenAppContainer = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( GetTokenInformation(a1, TokenStatistics, TokenInformation, 0x38u, (PDWORD)&v33) )
  {
    v5 = DWORD2(TokenInformation[0]);
    v6 = v38;
    *(_QWORD *)v35 = *((_QWORD *)&TokenInformation[0] + 1);
    v36 = v38;
    LODWORD(result) = GetTokenPackageSid((void *)v2, v39);
    if ( (_DWORD)result )
    {
      return (unsigned __int16)result;
    }
    else
    {
      EnterCriticalSection(&gcsTokenLock);
      v8 = SHIDWORD(v36);
      v9 = *(__int64 **)gpTokenList;
      if ( *(_QWORD *)gpTokenList )
      {
        while ( 1 )
        {
          v10 = v9 - 6;
          if ( v5 == *((_DWORD *)v9 + 8) )
          {
            v11 = (int)v35[1];
            if ( v35[1] == *((_DWORD *)v10 + 21)
              && *((_DWORD *)v10 + 22) == v6
              && *((_DWORD *)v10 + 23) == (_DWORD)v8
              && !CToken::ComparePackageSids((CToken *)(v9 - 6), v39, 0)
              && !CToken::CompareToken((CToken *)(v9 - 6), (void *)v2) )
            {
              break;
            }
          }
          v9 = (__int64 *)*v9;
          if ( !v9 )
            goto LABEL_17;
        }
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          LODWORD(ReturnLength) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
            "LookupOrCreateTokenFromHandle",
            689,
            ReturnLength,
            L"Found:%p HANDLE:%p LUID:%I64X LUIDMOD:%I64X",
            v9 - 6,
            v2,
            v5 + (v11 << 32),
            v6 + (v8 << 32));
        }
        _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
        **(_QWORD **)v34 = v10;
        LeaveCriticalSection(&gcsTokenLock);
        CloseHandle((HANDLE)v2);
        return 0;
      }
      else
      {
LABEL_17:
        LeaveCriticalSection(&gcsTokenLock);
        v12 = 44;
        LODWORD(v33) = 44;
        while ( 1 )
        {
          v13 = v12 + 15LL;
          if ( v13 <= v12 )
            v13 = 0xFFFFFFFFFFFFFF0LL;
          v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
          v15 = alloca(v14);
          v16 = alloca(v14);
          if ( GetTokenInformation((HANDLE)v2, TokenUser, &v33, v12, (PDWORD)&v33) )
            break;
          if ( GetLastError() != 122 )
          {
            if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              LastError = GetLastError();
              v4 = 735;
              goto LABEL_6;
            }
            return 14;
          }
          v12 = (unsigned int)v33;
        }
        v17 = v33;
        LODWORD(v33) = GetLengthSid(v33) - 12;
        v18 = HeapAlloc(g_hHeap, 0, (unsigned int)v33 + 168LL);
        v19 = v18;
        if ( !v18 )
        {
          **(_QWORD **)v34 = 0;
          return 14;
        }
        v20 = (int)v33;
        *v18 = &CToken::`vftable';
        v21 = v35[1];
        v19[6] = 0;
        v19[7] = 0;
        *((_BYTE *)v19 + 64) = 0;
        *((_DWORD *)v19 + 20) = v5;
        *((_DWORD *)v19 + 21) = v21;
        *((_DWORD *)v19 + 22) = v6;
        *((_DWORD *)v19 + 23) = v8;
        v19[12] = -1;
        *((_DWORD *)v19 + 26) = -1;
        *((_DWORD *)v19 + 27) = 4;
        v19[14] = -1;
        v19[15] = 0;
        v19[16] = 0;
        *((_BYTE *)v19 + 136) = 0;
        v19[18] = 0;
        *((_BYTE *)v19 + 152) = 0;
        v19[1] = 1;
        v19[2] = 0;
        v19[3] = 0;
        v19[4] = 0;
        v19[5] = 0;
        v19[9] = v2;
        memcpy_0((char *)v19 + 156, v17, (unsigned int)(v20 + 12));
        if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          LODWORD(ReturnLength) = 4;
          ComTraceMessage(
            0xFFFFFFFFLL,
            "onecore\\com\\combase\\rpcss\\objex\\token.hxx",
            "CToken::CToken",
            112,
            ReturnLength,
            L"this:%p handle:%p LUID:%I64X LUIDMOD:%I64X SID:%!sid!",
            v19,
            v2,
            v5 + ((__int64)(int)v35[1] << 32),
            v6 + (v8 << 32),
            v17);
        }
        v22 = *(_QWORD **)v34;
        LODWORD(v36) = 0;
        v34[0] = 4;
        if ( !v2 )
          v2 = -6;
        *v22 = v19;
        if ( !GetTokenInformation((HANDLE)v2, TokenType, &v36, 4u, v34) )
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
              (void *)0x2FD,
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
              (const char *)(unsigned int)v24,
              ReturnLengtha);
            return 0;
          }
        }
        if ( (_DWORD)v36 == 2 )
        {
          v34[0] = 0;
          v35[0] = 4;
          if ( !GetTokenInformation((HANDLE)v2, TokenImpersonationLevel, v34, 4u, v35) )
          {
            v26 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x128,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                    v25);
            if ( v26 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x301,
                (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\token.cxx",
                (const char *)(unsigned int)v26,
                ReturnLengthb);
              return 0;
            }
          }
          if ( (int)v34[0] >= 2 )
          {
            EnterCriticalSection(&gcsTokenLock);
            v27 = gpTokenList;
            v28 = *v22 + 48LL;
            v29 = *(_QWORD *)(gpTokenList + 8);
            if ( v29 )
            {
              if ( *(_QWORD *)v29 )
                *(_QWORD *)(*(_QWORD *)v29 + 8LL) = v28;
              *(_QWORD *)v28 = *(_QWORD *)v29;
              *(_QWORD *)(v28 + 8) = v29;
              *(_QWORD *)v29 = v28;
            }
            else
            {
              *(_QWORD *)gpTokenList = v28;
            }
            *(_QWORD *)(v27 + 8) = v28;
            *(_BYTE *)(v28 + 16) = 1;
            LeaveCriticalSection(&gcsTokenLock);
          }
        }
        return 0;
      }
    }
  }
  else
  {
    if ( dword_1801574B8 || gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v4 = 648;
LABEL_6:
      LODWORD(ReturnLength) = 0;
      ComTraceMessage(
        0xFFFFFFFFLL,
        "onecore\\com\\combase\\rpcss\\objex\\token.cxx",
        "LookupOrCreateTokenFromHandle",
        v4,
        ReturnLength,
        L"%!WINERROR!",
        LastError);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x18002aa10  push    rbp
0x18002aa12  push    rsi
0x18002aa13  push    rdi
0x18002aa14  push    r12
0x18002aa16  push    r13
0x18002aa18  push    r14
0x18002aa1a  push    r15
0x18002aa1c  sub     rsp, 120h
0x18002aa23  lea     rbp, [rsp+60h]
0x18002aa28  mov     [rbp+0F0h+arg_10], rbx
0x18002aa2f  mov     rax, cs:__security_cookie
0x18002aa36  xor     rax, rbp
0x18002aa39  mov     [rbp+0F0h+var_40], rax
0x18002aa40  xorps   xmm1, xmm1
0x18002aa43  mov     qword ptr [rbp+0F0h+var_E8], rdx
0x18002aa47  xorps   xmm0, xmm0
0x18002aa4a  mov     dword ptr [rbp+0F0h+var_F0], 38h ; '8'
0x18002aa51  xor     eax, eax
0x18002aa53  lea     r8, [rbp+0F0h+TokenInformation]; TokenInformation
0x18002aa57  mov     [rbp+0F0h+var_A0], rax
0x18002aa5b  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002aa61  lea     rax, [rbp+0F0h+var_F0]
0x18002aa65  mov     edx, 0Ah; TokenInformationClass
0x18002aa6a  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x18002aa6f  mov     r15, rcx
0x18002aa72  movups  [rbp+0F0h+TokenInformation], xmm0
0x18002aa76  movups  [rbp+0F0h+var_C0], xmm0
0x18002aa7a  movups  [rbp+0F0h+var_B0], xmm0
0x18002aa7e  movups  xmmword ptr [rbp+0F0h+var_90.TokenAppContainer], xmm1
0x18002aa82  movups  [rbp+0F0h+var_80], xmm1
0x18002aa86  movups  [rbp+0F0h+var_70], xmm1
0x18002aa8d  movups  [rbp+0F0h+var_60], xmm1
0x18002aa94  movups  [rbp+0F0h+var_50], xmm1
0x18002aa9b  call    cs:__imp_GetTokenInformation
0x18002aaa2  nop     dword ptr [rax+rax+00h]
0x18002aaa7  test    eax, eax
0x18002aaa9  jnz     short loc_18002AB17
0x18002aaab  mov     eax, cs:dword_1801574B8
0x18002aab1  test    eax, eax
0x18002aab3  jnz     short loc_18002AAD2
0x18002aab5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18002aabb  jz      loc_18002B00D
0x18002aac1  mov     rax, cs:WPP_GLOBAL_Control
0x18002aac8  test    byte ptr [rax+1Ch], 1
0x18002aacc  jz      loc_18002B00D
0x18002aad2  call    cs:__imp_GetLastError
0x18002aad9  nop     dword ptr [rax+rax+00h]
0x18002aade  mov     r9d, 288h
0x18002aae4  mov     dword ptr [rsp+150h+var_120], eax
0x18002aae8  lea     r8, aLookuporcreate; "LookupOrCreateTokenFromHandle"
0x18002aaef  lea     rax, aWinerror; "%!WINERROR!"
0x18002aaf6  xor     esi, esi
0x18002aaf8  mov     [rsp+150h+var_128], rax
0x18002aafd  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002ab04  mov     ecx, 0FFFFFFFFh
0x18002ab09  mov     dword ptr [rsp+150h+ReturnLength], esi
0x18002ab0d  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18002ab12  jmp     loc_18002B00D
0x18002ab17  mov     rbx, qword ptr [rbp+0F0h+TokenInformation+8]
0x18002ab1b  lea     rdx, [rbp+0F0h+var_90]; struct _TOKEN_APPCONTAINER_INFORMATION *
0x18002ab1f  mov     rdi, [rbp+0F0h+var_A0]
0x18002ab23  mov     rcx, r15; void *
0x18002ab26  mov     qword ptr [rbp+0F0h+var_E0], rbx
0x18002ab2a  mov     [rbp+0F0h+var_D8], rdi
0x18002ab2e  call    ?GetTokenPackageSid@@YAJPEAXPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; GetTokenPackageSid(void *,_TOKEN_APPCONTAINER_INFORMATION *)
0x18002ab33  test    eax, eax
0x18002ab35  jz      short loc_18002AB3F
0x18002ab37  movzx   eax, ax
0x18002ab3a  jmp     loc_18002B012
0x18002ab3f  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ab46  call    cs:__imp_EnterCriticalSection
0x18002ab4d  nop     dword ptr [rax+rax+00h]
0x18002ab52  mov     rax, cs:?gpTokenList@@3PEAV?$CListBase@$00$00@@EA; CListBase<1,1> * gpTokenList
0x18002ab59  movsxd  r13, dword ptr [rbp+0F0h+var_D8+4]
0x18002ab5d  mov     r14, [rax]
0x18002ab60  test    r14, r14
0x18002ab63  jz      short loc_18002ABB2
0x18002ab65  cmp     ebx, [r14+20h]
0x18002ab69  lea     rsi, [r14-30h]
0x18002ab6d  jnz     short loc_18002ABAA
0x18002ab6f  movsxd  r12, [rbp+0F0h+var_E0+4]
0x18002ab73  cmp     r12d, [rsi+54h]
0x18002ab77  jnz     short loc_18002ABAA
0x18002ab79  cmp     [rsi+58h], edi
0x18002ab7c  jnz     short loc_18002ABAA
0x18002ab7e  cmp     [rsi+5Ch], r13d
0x18002ab82  jnz     short loc_18002ABAA
0x18002ab84  xor     r8d, r8d; bool
0x18002ab87  lea     rdx, [rbp+0F0h+var_90]; void *
0x18002ab8b  mov     rcx, rsi; this
0x18002ab8e  call    ?ComparePackageSids@CToken@@QEAAJPEAX_N@Z; CToken::ComparePackageSids(void *,bool)
0x18002ab93  test    eax, eax
0x18002ab95  jnz     short loc_18002ABAA
0x18002ab97  mov     rdx, r15; void *
0x18002ab9a  mov     rcx, rsi; this
0x18002ab9d  call    ?CompareToken@CToken@@QEAAJPEAX@Z; CToken::CompareToken(void *)
0x18002aba2  test    eax, eax
0x18002aba4  jz      loc_18002AC46
0x18002abaa  mov     r14, [r14]
0x18002abad  test    r14, r14
0x18002abb0  jnz     short loc_18002AB65
0x18002abb2  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002abb9  call    cs:__imp_LeaveCriticalSection
0x18002abc0  nop     dword ptr [rax+rax+00h]
0x18002abc5  mov     r9d, 2Ch ; ','
0x18002abcb  mov     r14, 0FFFFFFFFFFFFFF0h
0x18002abd5  mov     dword ptr [rbp+0F0h+var_F0], r9d
0x18002abd9  nop     dword ptr [rax+00000000h]
0x18002abe0  mov     eax, r9d
0x18002abe3  lea     rcx, [rax+0Fh]
0x18002abe7  cmp     rcx, rax
0x18002abea  ja      short loc_18002ABEF
0x18002abec  mov     rcx, r14
0x18002abef  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002abf3  mov     rax, rcx
0x18002abf6  call    _alloca_probe
0x18002abfb  sub     rsp, rcx
0x18002abfe  lea     rax, [rbp+0F0h+var_F0]
0x18002ac02  mov     edx, 1; TokenInformationClass
0x18002ac07  mov     rcx, r15; TokenHandle
0x18002ac0a  lea     rsi, [rsp+150h+var_F0]
0x18002ac0f  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x18002ac14  mov     r8, rsi; TokenInformation
0x18002ac17  call    cs:__imp_GetTokenInformation
0x18002ac1e  nop     dword ptr [rax+rax+00h]
0x18002ac23  test    eax, eax
0x18002ac25  jnz     loc_18002AD2E
0x18002ac2b  call    cs:__imp_GetLastError
0x18002ac32  nop     dword ptr [rax+rax+00h]
0x18002ac37  cmp     eax, 7Ah ; 'z'
0x18002ac3a  jnz     loc_18002ACF0
0x18002ac40  mov     r9d, dword ptr [rbp+0F0h+var_F0]
0x18002ac44  jmp     short loc_18002ABE0
0x18002ac46  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18002ac4d  jz      short loc_18002ACBA
0x18002ac4f  mov     rax, cs:WPP_GLOBAL_Control
0x18002ac56  test    byte ptr [rax+1Ch], 10h
0x18002ac5a  jz      short loc_18002ACBA
0x18002ac5c  mov     eax, edi
0x18002ac5e  lea     r8, aLookuporcreate; "LookupOrCreateTokenFromHandle"
0x18002ac65  mov     rdx, r13
0x18002ac68  mov     rcx, r12
0x18002ac6b  shl     rdx, 20h
0x18002ac6f  mov     r9d, 2B1h
0x18002ac75  add     rdx, rax
0x18002ac78  shl     rcx, 20h
0x18002ac7c  mov     [rsp+150h+var_108], rdx
0x18002ac81  lea     rdx, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002ac88  mov     eax, ebx
0x18002ac8a  add     rcx, rax
0x18002ac8d  lea     rax, aFoundPHandlePL; "Found:%p HANDLE:%p LUID:%I64X LUIDMOD:%"...
0x18002ac94  mov     [rsp+150h+var_110], rcx
0x18002ac99  mov     ecx, 0FFFFFFFFh
0x18002ac9e  mov     [rsp+150h+var_118], r15
0x18002aca3  mov     [rsp+150h+var_120], rsi
0x18002aca8  mov     [rsp+150h+var_128], rax
0x18002acad  mov     dword ptr [rsp+150h+ReturnLength], 4
0x18002acb5  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18002acba  lock inc dword ptr [rsi+8]
0x18002acbe  mov     rbx, qword ptr [rbp+0F0h+var_E8]
0x18002acc2  lea     rcx, ?gcsTokenLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002acc9  mov     [rbx], rsi
0x18002accc  call    cs:__imp_LeaveCriticalSection
0x18002acd3  nop     dword ptr [rax+rax+00h]
0x18002acd8  mov     rcx, r15; hObject
0x18002acdb  xor     esi, esi
0x18002acdd  call    cs:__imp_CloseHandle
0x18002ace4  nop     dword ptr [rax+rax+00h]
0x18002ace9  mov     eax, esi
0x18002aceb  jmp     loc_18002B012
0x18002acf0  mov     eax, cs:dword_1801574B8
0x18002acf6  test    eax, eax
0x18002acf8  jnz     short loc_18002AD17
0x18002acfa  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18002ad00  jz      loc_18002B00D
0x18002ad06  mov     rax, cs:WPP_GLOBAL_Control
0x18002ad0d  test    byte ptr [rax+1Ch], 1
0x18002ad11  jz      loc_18002B00D
0x18002ad17  call    cs:__imp_GetLastError
0x18002ad1e  nop     dword ptr [rax+rax+00h]
0x18002ad23  mov     r9d, 2DFh
0x18002ad29  jmp     loc_18002AAE4
0x18002ad2e  mov     r12, [rsi]
0x18002ad31  mov     rcx, r12; pSid
0x18002ad34  call    cs:__imp_GetLengthSid
0x18002ad3b  nop     dword ptr [rax+rax+00h]
0x18002ad40  add     eax, 0FFFFFFF4h
0x18002ad43  mov     r8d, eax
0x18002ad46  add     r8, 0A8h; dwBytes
0x18002ad4d  mov     dword ptr [rbp+0F0h+var_F0], eax
0x18002ad50  cmp     r8, 0A8h
0x18002ad57  jb      loc_18002B004
0x18002ad5d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002ad64  xor     edx, edx; dwFlags
0x18002ad66  call    cs:__imp_HeapAlloc
0x18002ad6d  nop     dword ptr [rax+rax+00h]
0x18002ad72  mov     r14, rax
0x18002ad75  test    rax, rax
0x18002ad78  jz      loc_18002B004
0x18002ad7e  mov     r8d, dword ptr [rbp+0F0h+var_F0]
0x18002ad82  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x18002ad89  xor     esi, esi
0x18002ad8b  mov     [r14], rax
0x18002ad8e  mov     eax, [rbp+0F0h+var_E0+4]
0x18002ad91  lea     rcx, [r14+9Ch]; void *
0x18002ad98  mov     [r14+30h], rsi
0x18002ad9c  add     r8d, 0Ch; Size
0x18002ada0  mov     [r14+38h], rsi
0x18002ada4  mov     rdx, r12; Src
0x18002ada7  mov     [r14+40h], sil
0x18002adab  mov     [r14+50h], ebx
0x18002adaf  mov     [r14+54h], eax
0x18002adb3  mov     [r14+58h], edi
0x18002adb7  mov     [r14+5Ch], r13d
0x18002adbb  mov     qword ptr [r14+60h], 0FFFFFFFFFFFFFFFFh
0x18002adc3  mov     dword ptr [r14+68h], 0FFFFFFFFh
0x18002adcb  mov     dword ptr [r14+6Ch], 4
0x18002add3  mov     qword ptr [r14+70h], 0FFFFFFFFFFFFFFFFh
0x18002addb  mov     [r14+78h], rsi
0x18002addf  mov     [r14+80h], rsi
0x18002ade6  mov     [r14+88h], sil
0x18002aded  mov     [r14+90h], rsi
0x18002adf4  mov     [r14+98h], sil
0x18002adfb  mov     qword ptr [r14+8], 1
0x18002ae03  mov     [r14+10h], rsi
0x18002ae07  mov     [r14+18h], rsi
0x18002ae0b  mov     [r14+20h], rsi
0x18002ae0f  mov     [r14+28h], rsi
0x18002ae13  mov     [r14+48h], r15
0x18002ae17  call    memcpy_0
0x18002ae1c  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18002ae22  jz      short loc_18002AE95
0x18002ae24  mov     rax, cs:WPP_GLOBAL_Control
0x18002ae2b  test    byte ptr [rax+1Ch], 10h
0x18002ae2f  jz      short loc_18002AE95
0x18002ae31  movsxd  rcx, [rbp+0F0h+var_E0+4]
0x18002ae35  lea     r8, aCtokenCtoken_0; "CToken::CToken"
0x18002ae3c  mov     [rsp+150h+var_100], r12
0x18002ae41  mov     rdx, r13
0x18002ae44  shl     rdx, 20h
0x18002ae48  mov     r9d, 70h ; 'p'
0x18002ae4e  shl     rcx, 20h
0x18002ae52  mov     eax, edi
0x18002ae54  add     rdx, rax
0x18002ae57  mov     eax, ebx
0x18002ae59  mov     [rsp+150h+var_108], rdx
0x18002ae5e  add     rcx, rax
0x18002ae61  mov     [rsp+150h+var_110], rcx
0x18002ae66  lea     rax, aThisPHandlePLu; "this:%p handle:%p LUID:%I64X LUIDMOD:%I"...
0x18002ae6d  mov     [rsp+150h+var_118], r15
0x18002ae72  lea     rdx, aOnecoreComComb_103; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002ae79  mov     [rsp+150h+var_120], r14
0x18002ae7e  mov     ecx, 0FFFFFFFFh
0x18002ae83  mov     [rsp+150h+var_128], rax
0x18002ae88  mov     dword ptr [rsp+150h+ReturnLength], 4
0x18002ae90  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18002ae95  mov     rbx, qword ptr [rbp+0F0h+var_E8]
0x18002ae99  lea     r8, [rbp+0F0h+var_D8]; TokenInformation
0x18002ae9d  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18002aea4  mov     dword ptr [rbp+0F0h+var_D8], esi
0x18002aea7  test    r15, r15
0x18002aeaa  mov     [rbp+0F0h+var_E8], 4
0x18002aeb1  mov     r9d, 4; TokenInformationLength
0x18002aeb7  mov     edx, 8; TokenInformationClass
0x18002aebc  cmovz   r15, rax
0x18002aec0  mov     [rbx], r14
0x18002aec3  lea     rax, [rbp+0F0h+var_E8]
0x18002aec7  mov     rcx, r15; TokenHandle
0x18002aeca  mov     [rsp+150h+ReturnLength], rax; int
0x18002aecf  call    cs:__imp_GetTokenInformation
0x18002aed6  nop     dword ptr [rax+rax+00h]
0x18002aedb  test    eax, eax
0x18002aedd  jnz     short loc_18002AF1D
0x18002aedf  mov     rcx, [rbp+0F8h]; this
0x18002aee6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002aeed  mov     edx, 128h; void *
0x18002aef2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002aef7  test    eax, eax
0x18002aef9  jns     short loc_18002AF1D
0x18002aefb  mov     rcx, [rbp+0F8h]; this
0x18002af02  lea     r8, aOnecoreComComb_100; "onecore\\com\\combase\\rpcss\\objex\\to"...
0x18002af09  mov     r9d, eax; char *
0x18002af0c  mov     edx, 2FDh; void *
0x18002af11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002af16  mov     eax, esi
0x18002af18  jmp     loc_18002B012
0x18002af1d  cmp     dword ptr [rbp+0F0h+var_D8], 2
0x18002af21  jnz     loc_18002B000
0x18002af27  lea     rax, [rbp+0F0h+var_E0]
0x18002af2b  mov     [rbp+0F0h+var_E8], esi
0x18002af2e  mov     r9d, 4; TokenInformationLength
0x18002af34  mov     [rsp+150h+ReturnLength], rax; int
0x18002af39  lea     r8, [rbp+0F0h+var_E8]; TokenInformation
0x18002af3d  mov     [rbp+0F0h+var_E0], 4
0x18002af44  mov     edx, 9; TokenInformationClass
0x18002af49  mov     rcx, r15; TokenHandle
0x18002af4c  call    cs:__imp_GetTokenInformation
0x18002af53  nop     dword ptr [rax+rax+00h]
0x18002af58  test    eax, eax
0x18002af5a  jnz     short loc_18002AF97
  ... truncated ...
```
