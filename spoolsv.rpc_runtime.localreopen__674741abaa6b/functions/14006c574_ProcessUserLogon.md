# ProcessUserLogon

- ea: `0x14006c574`
- end: `0x14006c811`
- name: `ProcessUserLogon`
- size: `669`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14006c8d0`

## callees

- `0x140015378`
- `0x140016314`
- `0x14005e898`
- `0x140069514`
- `0x14006c574`
- `0x140071760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c6b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c79d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c7bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c6b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c79d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c7bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006c7dd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c669`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c6a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c762`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c78d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c669`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c6a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c762`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006c78d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006c6f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006c7af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006c7cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006c6f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006c7af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006c7cf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14006c616`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14006c74c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14006c616`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14006c74c`
- `WTSAPI32!WTSQueryUserToken` at `0x14006c5e6`
- `WTSAPI32!WTSQueryUserToken` at `0x14006c718`
- `WTSAPI32!WTSQueryUserToken` at `0x14006c5e6`
- `WTSAPI32!WTSQueryUserToken` at `0x14006c718`

## string_xrefs

- `0x14006c632`: `DuplicateTokenEx failed!  Error hr: %d.`
- `0x14006c647`: `WTSQueryUserToken failed!  Error hr: %d.`
- `0x14006c5d7`: `GetImpersonationTokenForUserFromSessionViaBroker failed!  Error hr: %d.`
- `0x14006c6d7`: `SetThreadToken (NULL, hImpToken) failed!  Error hr: %d.`
- `0x14006c6c2`: `SetThreadToken (NULL, NULL) failed!  Error hr: %d.`

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
      ImpersonationTokenForUserViaBroker = GetImpersonationTokenForUserViaBroker(2, 0, a1, &Token);
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
0x14006c574  mov     [rsp-18h+arg_0], rbx
0x14006c579  push    rbp
0x14006c57a  push    rsi
0x14006c57b  push    rdi
0x14006c57c  mov     rbp, rsp
0x14006c57f  sub     rsp, 30h
0x14006c583  mov     edi, ecx
0x14006c585  mov     [rbp+phToken], 0
0x14006c58d  mov     [rbp+Token], 0
0x14006c595  xor     ebx, ebx
0x14006c597  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14006c59e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14006c5a3  lea     rsi, aProcessuserlog; "ProcessUserLogon"
0x14006c5aa  test    al, al
0x14006c5ac  jz      loc_14006C712
0x14006c5b2  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14006c5b7  test    eax, eax
0x14006c5b9  jz      short loc_14006C5E0
0x14006c5bb  lea     r9, [rbp+Token]; void **
0x14006c5bf  mov     r8d, edi; unsigned int
0x14006c5c2  xor     edx, edx; unsigned __int16 *
0x14006c5c4  lea     ecx, [rbx+2]; unsigned int
0x14006c5c7  call    ?GetImpersonationTokenForUserViaBroker@@YAJKPEBGKPEAPEAX@Z; GetImpersonationTokenForUserViaBroker(ulong,ushort const *,ulong,void * *)
0x14006c5cc  movzx   ebx, ax
0x14006c5cf  test    ebx, ebx
0x14006c5d1  jz      loc_14006C663
0x14006c5d7  lea     rdx, aGetimpersonati_0; "GetImpersonationTokenForUserFromSession"...
0x14006c5de  jmp     short loc_14006C650
0x14006c5e0  lea     rdx, [rbp+phToken]; phToken
0x14006c5e4  mov     ecx, edi; SessionId
0x14006c5e6  call    cs:__imp_WTSQueryUserToken
0x14006c5ed  nop     dword ptr [rax+rax+00h]
0x14006c5f2  test    eax, eax
0x14006c5f4  jz      short loc_14006C63B
0x14006c5f6  mov     rcx, [rbp+phToken]; hExistingToken
0x14006c5fa  lea     rax, [rbp+Token]
0x14006c5fe  mov     [rsp+30h+phNewToken], rax; phNewToken
0x14006c603  mov     r9d, 2; ImpersonationLevel
0x14006c609  xor     r8d, r8d; lpTokenAttributes
0x14006c60c  mov     [rsp+30h+TokenType], 2; TokenType
0x14006c614  xor     edx, edx; dwDesiredAccess
0x14006c616  call    cs:__imp_DuplicateTokenEx
0x14006c61d  nop     dword ptr [rax+rax+00h]
0x14006c622  test    eax, eax
0x14006c624  jnz     short loc_14006C663
0x14006c626  call    cs:__imp_GetLastError
0x14006c62d  nop     dword ptr [rax+rax+00h]
0x14006c632  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed!  Error hr: %d."
0x14006c639  jmp     short loc_14006C64E
0x14006c63b  call    cs:__imp_GetLastError
0x14006c642  nop     dword ptr [rax+rax+00h]
0x14006c647  lea     rdx, aWtsqueryuserto_0; "WTSQueryUserToken failed!  Error hr: %d"...
0x14006c64e  mov     ebx, eax
0x14006c650  mov     rcx, rsi; char *
0x14006c653  mov     r8d, ebx
0x14006c656  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006c65b  test    ebx, ebx
0x14006c65d  jnz     loc_14006C6EB
0x14006c663  mov     rdx, [rbp+Token]; Token
0x14006c667  xor     ecx, ecx; Thread
0x14006c669  call    cs:__imp_SetThreadToken
0x14006c670  nop     dword ptr [rax+rax+00h]
0x14006c675  test    eax, eax
0x14006c677  jz      short loc_14006C6CB
0x14006c679  call    SpoolerInit
0x14006c67e  test    eax, eax
0x14006c680  jnz     short loc_14006C6A2
0x14006c682  call    cs:__imp_GetLastError
0x14006c689  nop     dword ptr [rax+rax+00h]
0x14006c68e  lea     rdx, aSpoolerinitFai; "SpoolerInit failed!  Error hr: %d."
0x14006c695  mov     rcx, rsi; char *
0x14006c698  mov     r8d, eax
0x14006c69b  mov     ebx, eax
0x14006c69d  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006c6a2  xor     edx, edx; Token
0x14006c6a4  xor     ecx, ecx; Thread
0x14006c6a6  call    cs:__imp_SetThreadToken
0x14006c6ad  nop     dword ptr [rax+rax+00h]
0x14006c6b2  test    eax, eax
0x14006c6b4  jnz     short loc_14006C6EB
0x14006c6b6  call    cs:__imp_GetLastError
0x14006c6bd  nop     dword ptr [rax+rax+00h]
0x14006c6c2  lea     rdx, aSetthreadtoken; "SetThreadToken (NULL, NULL) failed!  Er"...
0x14006c6c9  jmp     short loc_14006C6DE
0x14006c6cb  call    cs:__imp_GetLastError
0x14006c6d2  nop     dword ptr [rax+rax+00h]
0x14006c6d7  lea     rdx, aSetthreadtoken_0; "SetThreadToken (NULL, hImpToken) failed"...
0x14006c6de  mov     r8d, eax
0x14006c6e1  mov     rcx, rsi; char *
0x14006c6e4  mov     ebx, eax
0x14006c6e6  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006c6eb  mov     rcx, [rbp+Token]; hObject
0x14006c6ef  test    rcx, rcx
0x14006c6f2  jz      short loc_14006C700
0x14006c6f4  call    cs:__imp_CloseHandle
0x14006c6fb  nop     dword ptr [rax+rax+00h]
0x14006c700  mov     rcx, [rbp+phToken]
0x14006c704  test    rcx, rcx
0x14006c707  jz      loc_14006C7EB
0x14006c70d  jmp     loc_14006C7CF
0x14006c712  lea     rdx, [rbp+phToken]; phToken
0x14006c716  mov     ecx, edi; SessionId
0x14006c718  call    cs:__imp_WTSQueryUserToken
0x14006c71f  nop     dword ptr [rax+rax+00h]
0x14006c724  test    eax, eax
0x14006c726  jz      loc_14006C7DD
0x14006c72c  mov     rcx, [rbp+phToken]; hExistingToken
0x14006c730  lea     rax, [rbp+Token]
0x14006c734  mov     [rsp+30h+phNewToken], rax; phNewToken
0x14006c739  mov     r9d, 2; ImpersonationLevel
0x14006c73f  xor     r8d, r8d; lpTokenAttributes
0x14006c742  mov     [rsp+30h+TokenType], 2; TokenType
0x14006c74a  xor     edx, edx; dwDesiredAccess
0x14006c74c  call    cs:__imp_DuplicateTokenEx
0x14006c753  nop     dword ptr [rax+rax+00h]
0x14006c758  test    eax, eax
0x14006c75a  jz      short loc_14006C7BD
0x14006c75c  mov     rdx, [rbp+Token]; Token
0x14006c760  xor     ecx, ecx; Thread
0x14006c762  call    cs:__imp_SetThreadToken
0x14006c769  nop     dword ptr [rax+rax+00h]
0x14006c76e  test    eax, eax
0x14006c770  jz      short loc_14006C79D
0x14006c772  call    SpoolerInit
0x14006c777  test    eax, eax
0x14006c779  jnz     short loc_14006C789
0x14006c77b  call    cs:__imp_GetLastError
0x14006c782  nop     dword ptr [rax+rax+00h]
0x14006c787  mov     ebx, eax
0x14006c789  xor     edx, edx; Token
0x14006c78b  xor     ecx, ecx; Thread
0x14006c78d  call    cs:__imp_SetThreadToken
0x14006c794  nop     dword ptr [rax+rax+00h]
0x14006c799  test    eax, eax
0x14006c79b  jnz     short loc_14006C7AB
0x14006c79d  call    cs:__imp_GetLastError
0x14006c7a4  nop     dword ptr [rax+rax+00h]
0x14006c7a9  mov     ebx, eax
0x14006c7ab  mov     rcx, [rbp+Token]; hObject
0x14006c7af  call    cs:__imp_CloseHandle
0x14006c7b6  nop     dword ptr [rax+rax+00h]
0x14006c7bb  jmp     short loc_14006C7CB
0x14006c7bd  call    cs:__imp_GetLastError
0x14006c7c4  nop     dword ptr [rax+rax+00h]
0x14006c7c9  mov     ebx, eax
0x14006c7cb  mov     rcx, [rbp+phToken]; hObject
0x14006c7cf  call    cs:__imp_CloseHandle
0x14006c7d6  nop     dword ptr [rax+rax+00h]
0x14006c7db  jmp     short loc_14006C7EB
0x14006c7dd  call    cs:__imp_GetLastError
0x14006c7e4  nop     dword ptr [rax+rax+00h]
0x14006c7e9  mov     ebx, eax
0x14006c7eb  test    ebx, ebx
0x14006c7ed  jz      short loc_14006C801
0x14006c7ef  mov     r8d, ebx
0x14006c7f2  lea     rdx, aFailedErrorHrD; "Failed.  Error hr: %d."
0x14006c7f9  mov     rcx, rsi; char *
0x14006c7fc  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006c801  mov     eax, ebx
0x14006c803  mov     rbx, [rsp+30h+arg_0]
0x14006c808  add     rsp, 30h
0x14006c80c  pop     rdi
0x14006c80d  pop     rsi
0x14006c80e  pop     rbp
0x14006c80f  retn
```
