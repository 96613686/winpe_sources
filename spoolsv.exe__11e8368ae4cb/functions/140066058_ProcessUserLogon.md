# ProcessUserLogon

- ea: `0x140066058`
- end: `0x140066274`
- name: `ProcessUserLogon`
- size: `540`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140066330`

## callees

- `0x1400140cc`
- `0x140014fc4`
- `0x1400590f0`
- `0x1400633f8`
- `0x140066058`
- `0x14006abd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066247`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006612d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006615e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400661f6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140066215`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006612d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006615e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400661f6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140066215`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006619a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006622b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006623f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006619a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006622b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006623f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400660f0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400661e6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400660f0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400661e6`
- `WTSAPI32!WTSQueryUserToken` at `0x1400660c6`
- `WTSAPI32!WTSQueryUserToken` at `0x1400661b8`
- `WTSAPI32!WTSQueryUserToken` at `0x1400660c6`
- `WTSAPI32!WTSQueryUserToken` at `0x1400661b8`

## string_xrefs

- `0x140066100`: `DuplicateTokenEx failed!  Error hr: %d.`
- `0x1400660b7`: `GetImpersonationTokenForUserFromSessionViaBroker failed!  Error hr: %d.`
- `0x14006616e`: `SetThreadToken (NULL, NULL) failed!  Error hr: %d.`
- `0x14006617d`: `SetThreadToken (NULL, hImpToken) failed!  Error hr: %d.`
- `0x14006610f`: `WTSQueryUserToken failed!  Error hr: %d.`

## pseudocode

```c
__int64 __fastcall ProcessUserLogon(unsigned int a1)
{
  __int64 v2; // rbx
  unsigned __int16 ImpersonationTokenForUserViaBroker; // ax
  DWORD LastError; // eax
  unsigned __int16 *v5; // rdx
  DWORD v6; // eax
  unsigned __int16 *v7; // rdx
  HANDLE v8; // rcx
  HANDLE Token; // [rsp+58h] [rbp+28h] BYREF
  HANDLE phToken; // [rsp+60h] [rbp+30h] BYREF

  phToken = 0;
  Token = 0;
  LODWORD(v2) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
    {
      ImpersonationTokenForUserViaBroker = GetImpersonationTokenForUserViaBroker(2u, 0, a1, &Token);
      LODWORD(v2) = ImpersonationTokenForUserViaBroker;
      if ( !ImpersonationTokenForUserViaBroker )
        goto LABEL_11;
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "ProcessUserLogon",
        L"GetImpersonationTokenForUserFromSessionViaBroker failed!  Error hr: %d.",
        ImpersonationTokenForUserViaBroker);
    }
    else
    {
      if ( WTSQueryUserToken(a1, &phToken) )
      {
        if ( DuplicateTokenEx(phToken, 0, 0, SecurityImpersonation, TokenImpersonation, &Token) )
          goto LABEL_11;
        LastError = GetLastError();
        v5 = L"DuplicateTokenEx failed!  Error hr: %d.";
      }
      else
      {
        LastError = GetLastError();
        v5 = L"WTSQueryUserToken failed!  Error hr: %d.";
      }
      LODWORD(v2) = LastError;
      PrvSpoolssTelemetry::WriteDbgTraceError("ProcessUserLogon", v5, LastError);
    }
    if ( (_DWORD)v2 )
      goto LABEL_18;
LABEL_11:
    if ( SetThreadToken(0, Token) )
    {
      if ( !(unsigned int)SpoolerInit() )
      {
        v2 = GetLastError();
        PrvSpoolssTelemetry::WriteDbgTraceError("ProcessUserLogon", L"SpoolerInit failed!  Error hr: %d.", v2);
      }
      if ( SetThreadToken(0, 0) )
      {
LABEL_18:
        if ( Token )
          CloseHandle(Token);
        v8 = phToken;
        if ( phToken )
        {
LABEL_32:
          CloseHandle(v8);
          goto LABEL_34;
        }
        goto LABEL_34;
      }
      v6 = GetLastError();
      v7 = L"SetThreadToken (NULL, NULL) failed!  Error hr: %d.";
    }
    else
    {
      v6 = GetLastError();
      v7 = L"SetThreadToken (NULL, hImpToken) failed!  Error hr: %d.";
    }
    LODWORD(v2) = v6;
    PrvSpoolssTelemetry::WriteDbgTraceError("ProcessUserLogon", v7, v6);
    goto LABEL_18;
  }
  if ( WTSQueryUserToken(a1, &phToken) )
  {
    if ( DuplicateTokenEx(phToken, 0, 0, SecurityImpersonation, TokenImpersonation, &Token) )
    {
      if ( !SetThreadToken(0, Token) )
        goto LABEL_28;
      if ( !(unsigned int)SpoolerInit() )
        LODWORD(v2) = GetLastError();
      if ( !SetThreadToken(0, 0) )
LABEL_28:
        LODWORD(v2) = GetLastError();
      CloseHandle(Token);
    }
    else
    {
      LODWORD(v2) = GetLastError();
    }
    v8 = phToken;
    goto LABEL_32;
  }
  LODWORD(v2) = GetLastError();
LABEL_34:
  if ( (_DWORD)v2 )
    PrvSpoolssTelemetry::WriteDbgTraceError("ProcessUserLogon", L"Failed.  Error hr: %d.", (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140066058  mov     [rsp-18h+arg_0], rbx
0x14006605d  push    rbp
0x14006605e  push    rsi
0x14006605f  push    rdi
0x140066060  mov     rbp, rsp
0x140066063  sub     rsp, 30h
0x140066067  mov     edi, ecx
0x140066069  mov     [rbp+phToken], 0
0x140066071  mov     [rbp+Token], 0
0x140066079  xor     ebx, ebx
0x14006607b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140066082  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140066087  lea     rsi, aProcessuserlog; "ProcessUserLogon"
0x14006608e  test    al, al
0x140066090  jz      loc_1400661B2
0x140066096  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14006609b  test    eax, eax
0x14006609d  jz      short loc_1400660C0
0x14006609f  lea     r9, [rbp+Token]; void **
0x1400660a3  mov     r8d, edi; unsigned int
0x1400660a6  xor     edx, edx; unsigned __int16 *
0x1400660a8  lea     ecx, [rbx+2]; unsigned int
0x1400660ab  call    ?GetImpersonationTokenForUserViaBroker@@YAJKPEBGKPEAPEAX@Z; GetImpersonationTokenForUserViaBroker(ulong,ushort const *,ulong,void * *)
0x1400660b0  movzx   ebx, ax
0x1400660b3  test    ebx, ebx
0x1400660b5  jz      short loc_140066127
0x1400660b7  lea     rdx, aGetimpersonati_0; "GetImpersonationTokenForUserFromSession"...
0x1400660be  jmp     short loc_140066118
0x1400660c0  lea     rdx, [rbp+phToken]; phToken
0x1400660c4  mov     ecx, edi; SessionId
0x1400660c6  call    cs:__imp_WTSQueryUserToken
0x1400660cc  test    eax, eax
0x1400660ce  jz      short loc_140066109
0x1400660d0  mov     rcx, [rbp+phToken]; hExistingToken
0x1400660d4  lea     rax, [rbp+Token]
0x1400660d8  mov     [rsp+30h+phNewToken], rax; phNewToken
0x1400660dd  mov     r9d, 2; ImpersonationLevel
0x1400660e3  xor     r8d, r8d; lpTokenAttributes
0x1400660e6  mov     [rsp+30h+TokenType], 2; TokenType
0x1400660ee  xor     edx, edx; dwDesiredAccess
0x1400660f0  call    cs:__imp_DuplicateTokenEx
0x1400660f6  test    eax, eax
0x1400660f8  jnz     short loc_140066127
0x1400660fa  call    cs:__imp_GetLastError
0x140066100  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed!  Error hr: %d."
0x140066107  jmp     short loc_140066116
0x140066109  call    cs:__imp_GetLastError
0x14006610f  lea     rdx, aWtsqueryuserto_0; "WTSQueryUserToken failed!  Error hr: %d"...
0x140066116  mov     ebx, eax
0x140066118  mov     rcx, rsi; char *
0x14006611b  mov     r8d, ebx
0x14006611e  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066123  test    ebx, ebx
0x140066125  jnz     short loc_140066191
0x140066127  mov     rdx, [rbp+Token]; Token
0x14006612b  xor     ecx, ecx; Thread
0x14006612d  call    cs:__imp_SetThreadToken
0x140066133  test    eax, eax
0x140066135  jz      short loc_140066177
0x140066137  call    SpoolerInit
0x14006613c  test    eax, eax
0x14006613e  jnz     short loc_14006615A
0x140066140  call    cs:__imp_GetLastError
0x140066146  lea     rdx, aSpoolerinitFai; "SpoolerInit failed!  Error hr: %d."
0x14006614d  mov     rcx, rsi; char *
0x140066150  mov     r8d, eax
0x140066153  mov     ebx, eax
0x140066155  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006615a  xor     edx, edx; Token
0x14006615c  xor     ecx, ecx; Thread
0x14006615e  call    cs:__imp_SetThreadToken
0x140066164  test    eax, eax
0x140066166  jnz     short loc_140066191
0x140066168  call    cs:__imp_GetLastError
0x14006616e  lea     rdx, aSetthreadtoken; "SetThreadToken (NULL, NULL) failed!  Er"...
0x140066175  jmp     short loc_140066184
0x140066177  call    cs:__imp_GetLastError
0x14006617d  lea     rdx, aSetthreadtoken_0; "SetThreadToken (NULL, hImpToken) failed"...
0x140066184  mov     r8d, eax
0x140066187  mov     rcx, rsi; char *
0x14006618a  mov     ebx, eax
0x14006618c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066191  mov     rcx, [rbp+Token]; hObject
0x140066195  test    rcx, rcx
0x140066198  jz      short loc_1400661A0
0x14006619a  call    cs:__imp_CloseHandle
0x1400661a0  mov     rcx, [rbp+phToken]
0x1400661a4  test    rcx, rcx
0x1400661a7  jz      loc_14006624F
0x1400661ad  jmp     loc_14006623F
0x1400661b2  lea     rdx, [rbp+phToken]; phToken
0x1400661b6  mov     ecx, edi; SessionId
0x1400661b8  call    cs:__imp_WTSQueryUserToken
0x1400661be  test    eax, eax
0x1400661c0  jz      loc_140066247
0x1400661c6  mov     rcx, [rbp+phToken]; hExistingToken
0x1400661ca  lea     rax, [rbp+Token]
0x1400661ce  mov     [rsp+30h+phNewToken], rax; phNewToken
0x1400661d3  mov     r9d, 2; ImpersonationLevel
0x1400661d9  xor     r8d, r8d; lpTokenAttributes
0x1400661dc  mov     [rsp+30h+TokenType], 2; TokenType
0x1400661e4  xor     edx, edx; dwDesiredAccess
0x1400661e6  call    cs:__imp_DuplicateTokenEx
0x1400661ec  test    eax, eax
0x1400661ee  jz      short loc_140066233
0x1400661f0  mov     rdx, [rbp+Token]; Token
0x1400661f4  xor     ecx, ecx; Thread
0x1400661f6  call    cs:__imp_SetThreadToken
0x1400661fc  test    eax, eax
0x1400661fe  jz      short loc_14006621F
0x140066200  call    SpoolerInit
0x140066205  test    eax, eax
0x140066207  jnz     short loc_140066211
0x140066209  call    cs:__imp_GetLastError
0x14006620f  mov     ebx, eax
0x140066211  xor     edx, edx; Token
0x140066213  xor     ecx, ecx; Thread
0x140066215  call    cs:__imp_SetThreadToken
0x14006621b  test    eax, eax
0x14006621d  jnz     short loc_140066227
0x14006621f  call    cs:__imp_GetLastError
0x140066225  mov     ebx, eax
0x140066227  mov     rcx, [rbp+Token]; hObject
0x14006622b  call    cs:__imp_CloseHandle
0x140066231  jmp     short loc_14006623B
0x140066233  call    cs:__imp_GetLastError
0x140066239  mov     ebx, eax
0x14006623b  mov     rcx, [rbp+phToken]; hObject
0x14006623f  call    cs:__imp_CloseHandle
0x140066245  jmp     short loc_14006624F
0x140066247  call    cs:__imp_GetLastError
0x14006624d  mov     ebx, eax
0x14006624f  test    ebx, ebx
0x140066251  jz      short loc_140066265
0x140066253  mov     r8d, ebx
0x140066256  lea     rdx, aFailedErrorHrD; "Failed.  Error hr: %d."
0x14006625d  mov     rcx, rsi; char *
0x140066260  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140066265  mov     eax, ebx
0x140066267  mov     rbx, [rsp+30h+arg_0]
0x14006626c  add     rsp, 30h
0x140066270  pop     rdi
0x140066271  pop     rsi
0x140066272  pop     rbp
0x140066273  retn
```
