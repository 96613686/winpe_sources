# UpdateRedirectionStateForContext(_REDIRECTION_CONTEXT *)

- ea: `0x180013d34`
- end: `0x180014147`
- name: `?UpdateRedirectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `1043`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800093e4`
- `0x1800176a0`

## callees

- `0x180007bc0`
- `0x180013d34`
- `0x180014150`
- `0x180017c48`
- `0x180019644`
- `0x18001991c`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013f5c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013f5c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001410d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001410d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013d7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ddf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014067`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013d7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ddf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014067`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013e00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001407a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014134`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013e00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001407a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001401e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001401e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014117`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180013fa6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180013fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140fa`
- `WINSTA!WinStationGetCurrentSessionCapabilities` at `0x180013ff6`
- `WINSTA!WinStationGetCurrentSessionCapabilities` at `0x180013ff6`
- `WTSAPI32!WTSQueryUserToken` at `0x180013ed4`
- `WTSAPI32!WTSQueryUserToken` at `0x180013ed4`

## pseudocode

```c
void __fastcall UpdateRedirectionStateForContext(LPCRITICAL_SECTION lpCriticalSection)
{
  char v2; // r12
  __int64 v3; // rcx
  int SessionID; // eax
  __int64 v5; // rcx
  char v6; // r14
  int v7; // r9d
  __int64 v8; // rcx
  char LastError; // al
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char v15; // al
  unsigned int TokenInformation; // [rsp+70h] [rbp+38h] BYREF
  int v17; // [rsp+78h] [rbp+40h] BYREF
  void *phToken; // [rsp+80h] [rbp+48h] BYREF
  HANDLE Token; // [rsp+88h] [rbp+50h] BYREF

  v17 = 0;
  TokenInformation = 0;
  v2 = 0;
  phToken = 0;
  Token = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
    EnterCriticalSection(lpCriticalSection);
  if ( !LODWORD(lpCriticalSection[1].SpinCount) )
  {
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      EnterCriticalSection(lpCriticalSection);
    BYTE1(lpCriticalSection[1].DebugInfo) = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      LeaveCriticalSection(lpCriticalSection);
    goto LABEL_51;
  }
  SessionID = I_RedirectionContextGetSessionID(&TokenInformation);
  v6 = SessionID;
  if ( SessionID )
  {
    WppTraceIndent(v5, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids,
        v7,
        v6);
    }
    goto LABEL_51;
  }
  if ( TokenInformation != LODWORD(lpCriticalSection[1].SpinCount) )
  {
    WppTraceIndent(v5, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids,
        (_DWORD)WPP_pszIndent,
        TokenInformation,
        lpCriticalSection[1].SpinCount);
    }
    if ( !WTSQueryUserToken(lpCriticalSection[1].SpinCount, &phToken) )
    {
      WppTraceIndent(v8, 2);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      LastError = GetLastError();
      v10 = 17;
      goto LABEL_27;
    }
    if ( !DuplicateTokenEx(phToken, 6u, 0, SecurityImpersonation, TokenImpersonation, &Token) )
    {
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      LastError = GetLastError();
      v10 = 18;
      goto LABEL_27;
    }
    if ( !SetThreadToken(0, Token) )
    {
      WppTraceIndent(v12, 2);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      LastError = GetLastError();
      v10 = 19;
LABEL_27:
      WPP_SF_sDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids,
        (_DWORD)WPP_pszIndent,
        lpCriticalSection[1].SpinCount,
        LastError);
      goto LABEL_51;
    }
    v2 = 1;
  }
  if ( (unsigned __int8)WinStationGetCurrentSessionCapabilities(1, &v17) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
    {
      EnterCriticalSection(lpCriticalSection);
      BYTE1(lpCriticalSection[1].DebugInfo) = v17 == 0;
      LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      BYTE1(lpCriticalSection[1].DebugInfo) = v17 == 0;
    }
  }
  else
  {
    WppTraceIndent(v13, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = GetLastError();
      WPP_SF_sDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids,
        (_DWORD)WPP_pszIndent,
        lpCriticalSection[1].SpinCount,
        v15);
    }
  }
  WppTraceIndent(v14, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids,
      (_DWORD)WPP_pszIndent,
      lpCriticalSection[1].SpinCount,
      BYTE1(lpCriticalSection[1].DebugInfo) == 0);
  }
LABEL_51:
  if ( phToken )
  {
    CloseHandle(phToken);
    phToken = 0;
  }
  if ( Token )
  {
    CloseHandle(Token);
    Token = 0;
  }
  if ( v2 && !RevertToSelf() )
    __fastfail(GetLastError());
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180013d34  push    rbp
0x180013d36  push    rbx
0x180013d37  push    rsi
0x180013d38  push    rdi
0x180013d39  push    r12
0x180013d3b  push    r14
0x180013d3d  mov     rbp, rsp
0x180013d40  sub     rsp, 38h
0x180013d44  mov     rdi, rcx
0x180013d47  mov     [rbp+arg_8], 0
0x180013d4e  mov     [rbp+TokenInformation], 0
0x180013d55  xor     r12b, r12b
0x180013d58  mov     [rbp+phToken], 0
0x180013d60  mov     [rbp+Token], 0
0x180013d68  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180013d6f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180013d74  test    al, al
0x180013d76  jnz     short loc_180013D81
0x180013d78  mov     rcx, rdi; lpCriticalSection
0x180013d7b  call    cs:__imp_EnterCriticalSection
0x180013d81  cmp     dword ptr [rdi+48h], 0
0x180013d85  jnz     loc_180013E0B
0x180013d8b  mov     edx, 2
0x180013d90  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d9c  lea     rsi, WPP_GLOBAL_Control
0x180013da3  cmp     rcx, rsi
0x180013da6  jz      short loc_180013DCC
0x180013da8  mov     r14b, 4
0x180013dab  test    [rcx+1Ch], r14b
0x180013daf  jz      short loc_180013DCC
0x180013db1  cmp     [rcx+19h], r14b
0x180013db5  jb      short loc_180013DCC
0x180013db7  mov     rcx, [rcx+10h]
0x180013dbb  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180013dc2  mov     edx, 0Eh
0x180013dc7  call    WPP_SF_s
0x180013dcc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180013dd3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180013dd8  test    al, al
0x180013dda  jz      short loc_180013DE5
0x180013ddc  mov     rcx, rdi; lpCriticalSection
0x180013ddf  call    cs:__imp_EnterCriticalSection
0x180013de5  mov     byte ptr [rdi+29h], 1
0x180013de9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180013df0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180013df5  test    al, al
0x180013df7  jz      loc_1800140DA
0x180013dfd  mov     rcx, rdi; lpCriticalSection
0x180013e00  call    cs:__imp_LeaveCriticalSection
0x180013e06  jmp     loc_1800140DA
0x180013e0b  lea     rcx, [rbp+TokenInformation]; TokenInformation
0x180013e0f  call    ?I_RedirectionContextGetSessionID@@YAKPEAK@Z; I_RedirectionContextGetSessionID(ulong *)
0x180013e14  mov     r14d, eax
0x180013e17  mov     ebx, 2
0x180013e1c  test    eax, eax
0x180013e1e  jz      short loc_180013E6E
0x180013e20  mov     edx, ebx
0x180013e22  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e2e  lea     rsi, WPP_GLOBAL_Control
0x180013e35  cmp     rcx, rsi
0x180013e38  jz      loc_1800140DA
0x180013e3e  test    byte ptr [rcx+1Ch], 1
0x180013e42  jz      loc_1800140DA
0x180013e48  cmp     [rcx+19h], bl
0x180013e4b  jb      loc_1800140DA
0x180013e51  mov     rcx, [rcx+10h]
0x180013e55  lea     edx, [rbx+0Dh]
0x180013e58  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180013e5f  mov     [rsp+38h+TokenType], r14d
0x180013e64  call    WPP_SF_sd
0x180013e69  jmp     loc_1800140DA
0x180013e6e  mov     eax, [rdi+48h]
0x180013e71  lea     rsi, WPP_GLOBAL_Control
0x180013e78  mov     r14b, 4
0x180013e7b  cmp     [rbp+TokenInformation], eax
0x180013e7e  jz      loc_180013FED
0x180013e84  mov     edx, ebx
0x180013e86  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e92  cmp     rcx, rsi
0x180013e95  jz      short loc_180013ECD
0x180013e97  test    byte ptr [rcx+1Ch], 1
0x180013e9b  jz      short loc_180013ECD
0x180013e9d  cmp     [rcx+19h], r14b
0x180013ea1  jb      short loc_180013ECD
0x180013ea3  mov     eax, [rdi+48h]
0x180013ea6  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180013ead  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180013eb4  mov     edx, 10h
0x180013eb9  mov     rcx, [rcx+10h]
0x180013ebd  mov     dword ptr [rsp+38h+phNewToken], eax
0x180013ec1  mov     eax, [rbp+TokenInformation]
0x180013ec4  mov     [rsp+38h+TokenType], eax
0x180013ec8  call    WPP_SF_sDD
0x180013ecd  mov     ecx, [rdi+48h]; SessionId
0x180013ed0  lea     rdx, [rbp+phToken]; phToken
0x180013ed4  call    cs:__imp_WTSQueryUserToken
0x180013eda  test    eax, eax
0x180013edc  jnz     short loc_180013F41
0x180013ede  mov     edx, ebx
0x180013ee0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013ee5  mov     rax, cs:WPP_GLOBAL_Control
0x180013eec  cmp     rax, rsi
0x180013eef  jz      loc_1800140DA
0x180013ef5  test    byte ptr [rax+1Ch], 1
0x180013ef9  jz      loc_1800140DA
0x180013eff  cmp     [rax+19h], bl
0x180013f02  jb      loc_1800140DA
0x180013f08  call    cs:__imp_GetLastError
0x180013f0e  mov     edx, 11h
0x180013f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f1a  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180013f21  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180013f28  mov     dword ptr [rsp+38h+phNewToken], eax
0x180013f2c  mov     eax, [rdi+48h]
0x180013f2f  mov     rcx, [rcx+10h]
0x180013f33  mov     [rsp+38h+TokenType], eax
0x180013f37  call    WPP_SF_sDD
0x180013f3c  jmp     loc_1800140DA
0x180013f41  mov     rcx, [rbp+phToken]; hExistingToken
0x180013f45  lea     rax, [rbp+Token]
0x180013f49  xor     r8d, r8d; lpTokenAttributes
0x180013f4c  mov     [rsp+38h+phNewToken], rax; phNewToken
0x180013f51  mov     r9d, ebx; ImpersonationLevel
0x180013f54  mov     [rsp+38h+TokenType], ebx; TokenType
0x180013f58  lea     edx, [r8+6]; dwDesiredAccess
0x180013f5c  call    cs:__imp_DuplicateTokenEx
0x180013f62  test    eax, eax
0x180013f64  jnz     short loc_180013FA0
0x180013f66  mov     edx, ebx
0x180013f68  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013f6d  mov     rax, cs:WPP_GLOBAL_Control
0x180013f74  cmp     rax, rsi
0x180013f77  jz      loc_1800140DA
0x180013f7d  test    byte ptr [rax+1Ch], 1
0x180013f81  jz      loc_1800140DA
0x180013f87  cmp     [rax+19h], bl
0x180013f8a  jb      loc_1800140DA
0x180013f90  call    cs:__imp_GetLastError
0x180013f96  mov     edx, 12h
0x180013f9b  jmp     loc_180013F13
0x180013fa0  mov     rdx, [rbp+Token]; Token
0x180013fa4  xor     ecx, ecx; Thread
0x180013fa6  call    cs:__imp_SetThreadToken
0x180013fac  test    eax, eax
0x180013fae  jnz     short loc_180013FEA
0x180013fb0  mov     edx, ebx
0x180013fb2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180013fb7  mov     rax, cs:WPP_GLOBAL_Control
0x180013fbe  cmp     rax, rsi
0x180013fc1  jz      loc_1800140DA
0x180013fc7  test    byte ptr [rax+1Ch], 1
0x180013fcb  jz      loc_1800140DA
0x180013fd1  cmp     [rax+19h], bl
0x180013fd4  jb      loc_1800140DA
0x180013fda  call    cs:__imp_GetLastError
0x180013fe0  mov     edx, 13h
0x180013fe5  jmp     loc_180013F13
0x180013fea  mov     r12b, 1
0x180013fed  lea     rdx, [rbp+arg_8]
0x180013ff1  mov     ecx, 1
0x180013ff6  call    cs:__imp_WinStationGetCurrentSessionCapabilities
0x180013ffc  test    al, al
0x180013ffe  jnz     short loc_180014054
0x180014000  mov     edx, ebx
0x180014002  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180014007  mov     rax, cs:WPP_GLOBAL_Control
0x18001400e  cmp     rax, rsi
0x180014011  jz      short loc_18001408C
0x180014013  test    [rax+1Ch], r14b
0x180014017  jz      short loc_18001408C
0x180014019  cmp     [rax+19h], bl
0x18001401c  jb      short loc_18001408C
0x18001401e  call    cs:__imp_GetLastError
0x180014024  mov     rcx, cs:WPP_GLOBAL_Control
0x18001402b  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x180014032  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180014039  mov     edx, 14h
0x18001403e  mov     dword ptr [rsp+38h+phNewToken], eax
0x180014042  mov     eax, [rdi+48h]
0x180014045  mov     rcx, [rcx+10h]
0x180014049  mov     [rsp+38h+TokenType], eax
0x18001404d  call    WPP_SF_sDD
0x180014052  jmp     short loc_18001408C
0x180014054  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x18001405b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x180014060  test    al, al
0x180014062  jz      short loc_180014082
0x180014064  mov     rcx, rdi; lpCriticalSection
0x180014067  call    cs:__imp_EnterCriticalSection
0x18001406d  cmp     [rbp+arg_8], 0
0x180014071  mov     rcx, rdi; lpCriticalSection
0x180014074  setz    al
0x180014077  mov     [rdi+29h], al
0x18001407a  call    cs:__imp_LeaveCriticalSection
0x180014080  jmp     short loc_18001408C
0x180014082  cmp     [rbp+arg_8], 0
0x180014086  setz    al
0x180014089  mov     [rdi+29h], al
0x18001408c  mov     edx, ebx
0x18001408e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180014093  mov     rcx, cs:WPP_GLOBAL_Control
0x18001409a  cmp     rcx, rsi
0x18001409d  jz      short loc_1800140DA
0x18001409f  test    [rcx+1Ch], r14b
0x1800140a3  jz      short loc_1800140DA
0x1800140a5  cmp     [rcx+19h], r14b
0x1800140a9  jb      short loc_1800140DA
0x1800140ab  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800140b2  lea     r8, WPP_0f55e2acaaa83a3969cd8483ac59b923_Traceguids
0x1800140b9  mov     rcx, [rcx+10h]
0x1800140bd  xor     eax, eax
0x1800140bf  cmp     [rdi+29h], al
0x1800140c2  mov     edx, 15h
0x1800140c7  setz    al
0x1800140ca  mov     dword ptr [rsp+38h+phNewToken], eax
0x1800140ce  mov     eax, [rdi+48h]
0x1800140d1  mov     [rsp+38h+TokenType], eax
0x1800140d5  call    WPP_SF_sDD
0x1800140da  mov     rcx, [rbp+phToken]; hObject
0x1800140de  test    rcx, rcx
0x1800140e1  jz      short loc_1800140F1
0x1800140e3  call    cs:__imp_CloseHandle
0x1800140e9  mov     [rbp+phToken], 0
0x1800140f1  mov     rcx, [rbp+Token]; hObject
0x1800140f5  test    rcx, rcx
0x1800140f8  jz      short loc_180014108
0x1800140fa  call    cs:__imp_CloseHandle
0x180014100  mov     [rbp+Token], 0
0x180014108  test    r12b, r12b
0x18001410b  jz      short loc_180014121
0x18001410d  call    cs:__imp_RevertToSelf
0x180014113  test    eax, eax
0x180014115  jnz     short loc_180014121
0x180014117  call    cs:__imp_GetLastError
0x18001411d  mov     ecx, eax
0x18001411f  int     29h; Win8: RtlFailFast(ecx)
0x180014121  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x180014128  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x18001412d  test    al, al
0x18001412f  jnz     short loc_18001413A
0x180014131  mov     rcx, rdi; lpCriticalSection
0x180014134  call    cs:__imp_LeaveCriticalSection
0x18001413a  add     rsp, 38h
0x18001413e  pop     r14
0x180014140  pop     r12
0x180014142  pop     rdi
0x180014143  pop     rsi
0x180014144  pop     rbx
0x180014145  pop     rbp
0x180014146  retn
```
