# AuthorizeSecurityContextForAppContainer

- ea: `0x100480a90`
- end: `0x100480d33`
- name: `AuthorizeSecurityContextForAppContainer`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x100480d40`

## callees

- `0x100478670`
- `0x100480a90`
- `0x100486af0`

## import_xrefs

- `KERNEL32!CheckTokenMembershipEx` at `0x100480c58`
- `KERNEL32!CheckTokenMembershipEx` at `0x100480c58`
- `KERNEL32!GetLastError` at `0x100480bbd`
- `KERNEL32!GetLastError` at `0x100480c62`
- `KERNEL32!GetLastError` at `0x100480caf`
- `KERNEL32!GetLastError` at `0x100480bbd`
- `KERNEL32!GetLastError` at `0x100480c62`
- `KERNEL32!GetLastError` at `0x100480caf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100480c3a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100480cff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100480c3a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100480cff`
- `sqldk!??_V@YAXPEAX@Z` at `0x100480bdc`
- `sqldk!??_V@YAXPEAX@Z` at `0x100480ca5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100480bdc`
- `sqldk!??_V@YAXPEAX@Z` at `0x100480ca5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100480b79`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100480b79`
- `sqldk!SystemThread_TlsIndex` at `0x100480b1a`
- `sqldk!SystemThread_TlsOffset` at `0x100480b23`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100480b3e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100480b3e`
- `ADVAPI32!GetTokenInformation` at `0x100480aeb`
- `ADVAPI32!GetTokenInformation` at `0x100480aeb`
- `ADVAPI32!CreateWellKnownSid` at `0x100480ba4`
- `ADVAPI32!CreateWellKnownSid` at `0x100480ba4`

## string_xrefs

- `0x100480b61`: `Sql\Ntdbms\extensibility\common\src\SatelliteUtils.cpp`
- `0x100480cc4`: `AuthorizeSecurityContext failed when calling GetTokenInformation.\n`
- `0x100480bf2`: `AuthorizeSecurityContext failed when calling GetWellKnownSid.\n`
- `0x100480c7d`: `AuthorizeSecurityContext failed when calling CheckTokenMembershipEx. ErrorCode:0x%08lx.\n`
- `0x100480c28`: `"Sql\\Ntdbms\\extensibility\\common\\src\\SatelliteAuthorizeConnection.cpp"`
- `0x100480cec`: `"Sql\\Ntdbms\\extensibility\\common\\src\\SatelliteAuthorizeConnection.cpp"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AuthorizeSecurityContextForAppContainer(void *a1, bool *a2)
{
  unsigned int v4; // esi
  PSID v5; // r14
  __int64 v6; // rbx
  __int64 v7; // rax
  signed int v8; // ebp
  void *v9; // rax
  void *v10; // r15
  void *v11; // rbx
  signed int LastError; // eax
  signed int v13; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  PDWORD ReturnLength; // [rsp+20h] [rbp-C8h]
  DWORD cbSid; // [rsp+30h] [rbp-B8h] BYREF
  DWORD v19; // [rsp+34h] [rbp-B4h] BYREF
  int v20; // [rsp+38h] [rbp-B0h] BYREF
  void *v21; // [rsp+40h] [rbp-A8h]
  void *v22; // [rsp+48h] [rbp-A0h]
  __int64 v23; // [rsp+50h] [rbp-98h]
  _BYTE TokenInformation[80]; // [rsp+60h] [rbp-88h] BYREF

  v23 = -2;
  v4 = 0;
  v19 = 76;
  if ( GetTokenInformation(a1, TokenAppContainerSid, TokenInformation, 0x4Cu, &v19) )
  {
    v5 = 0;
    v21 = 0;
    if ( dword_1005248A0 )
    {
      cbSid = 0;
      v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v7 = *(_QWORD *)(v6 + 256);
      if ( !v7 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v7 = *(_QWORD *)(v6 + 256);
      }
      v8 = 0;
      v9 = operator new[](
             0x44u,
             *(struct IMemObj **)(*(_QWORD *)(v7 + 992) + 320LL),
             1,
             "Sql\\Ntdbms\\extensibility\\common\\src\\SatelliteUtils.cpp",
             1369,
             6u);
      v10 = v9;
      v11 = v9;
      v22 = v9;
      if ( v9 )
      {
        cbSid = 68;
        if ( CreateWellKnownSid(WinLocalServiceSid, 0, v9, &cbSid) )
        {
          v11 = 0;
          v22 = 0;
          v21 = v10;
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v8 = -2147024882;
      }
      operator delete[](v11);
      v4 = v8;
      if ( v8 < 0 )
      {
        _mm_lfence();
        FireTraceEvent(1, (unsigned int)v8, 0, L"AuthorizeSecurityContext failed when calling GetWellKnownSid.\n");
      }
      else
      {
        v5 = v21;
      }
      if ( v8 < 0 )
        goto LABEL_24;
    }
    else
    {
      v5 = CSQLSatelliteConnection::sm_expectedNamedPipeOwner;
      if ( !CSQLSatelliteConnection::sm_expectedNamedPipeOwner )
      {
        utassert_fail(
          1u,
          "CSQLSatelliteConnection::sm_expectedNamedPipeOwner",
          "\"Sql\\\\Ntdbms\\\\extensibility\\\\common\\\\src\\\\SatelliteAuthorizeConnection.cpp\"",
          212,
          0);
        v5 = CSQLSatelliteConnection::sm_expectedNamedPipeOwner;
      }
    }
    if ( (unsigned int)CheckTokenMembershipEx(a1, v5, 1, &v20) )
    {
      *a2 = v20 != 0;
    }
    else
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v4 = (unsigned __int16)v13 | 0x80070000;
      else
        v4 = v13;
      LODWORD(ReturnLength) = v4;
      FireTraceEvent(
        1,
        v4,
        0,
        L"AuthorizeSecurityContext failed when calling CheckTokenMembershipEx. ErrorCode:0x%08lx.\n",
        ReturnLength);
    }
LABEL_24:
    operator delete[](v21);
    return v4;
  }
  v15 = GetLastError();
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  FireTraceEvent(1, v16, 0, L"AuthorizeSecurityContext failed when calling GetTokenInformation.\n");
  if ( v16 == -2147024774 )
    utassert_fail(
      1u,
      "hr != HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)",
      "\"Sql\\\\Ntdbms\\\\extensibility\\\\common\\\\src\\\\SatelliteAuthorizeConnection.cpp\"",
      256,
      0);
  return v16;
}

```

## disassembly

```asm
0x100480a90  mov     rax, rsp
0x100480a93  push    rsi
0x100480a94  push    rdi
0x100480a95  push    r12
0x100480a97  push    r14
0x100480a99  push    r15
0x100480a9b  sub     rsp, 0C0h
0x100480aa2  mov     [rsp+0E8h+var_98], 0FFFFFFFFFFFFFFFEh
0x100480aab  mov     [rax+18h], rbx
0x100480aaf  mov     [rax+20h], rbp
0x100480ab3  mov     rax, cs:__security_cookie
0x100480aba  xor     rax, rsp
0x100480abd  mov     [rsp+0E8h+var_38], rax
0x100480ac5  mov     r12, rdx
0x100480ac8  mov     rdi, rcx
0x100480acb  xor     esi, esi
0x100480acd  mov     [rsp+0E8h+var_B4], 4Ch ; 'L'
0x100480ad5  lea     rax, [rsp+0E8h+var_B4]
0x100480ada  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x100480adf  lea     r9d, [rsi+4Ch]; TokenInformationLength
0x100480ae3  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x100480ae8  lea     edx, [rsi+1Fh]; TokenInformationClass
0x100480aeb  call    cs:__imp_GetTokenInformation
0x100480af1  test    eax, eax
0x100480af3  jz      loc_100480CAF
0x100480af9  mov     r14d, esi
0x100480afc  mov     [rsp+0E8h+var_A8], rsi
0x100480b01  cmp     cs:dword_1005248A0, esi
0x100480b07  jz      loc_100480C11
0x100480b0d  mov     [rsp+0E8h+cbSid], esi
0x100480b11  mov     rdx, gs:58h
0x100480b1a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100480b21  mov     ecx, [rax]
0x100480b23  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100480b2a  mov     ebx, [rax]
0x100480b2c  add     rbx, [rdx+rcx*8]
0x100480b30  mov     rax, [rbx+100h]
0x100480b37  test    rax, rax
0x100480b3a  jnz     short loc_100480B4B
0x100480b3c  xor     ecx, ecx
0x100480b3e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100480b44  mov     rax, [rbx+100h]
0x100480b4b  mov     rax, [rax+3E0h]
0x100480b52  mov     ebp, esi
0x100480b54  mov     [rsp+0E8h+var_C0], 6
0x100480b59  mov     dword ptr [rsp+0E8h+ReturnLength], 559h
0x100480b61  lea     r9, aSqlNtdbmsExten_1; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100480b68  mov     r8d, 1
0x100480b6e  mov     rdx, [rax+140h]
0x100480b75  lea     ecx, [r8+43h]
0x100480b79  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100480b7f  mov     r15, rax
0x100480b82  mov     rbx, rax
0x100480b85  mov     [rsp+0E8h+var_A0], rax
0x100480b8a  test    rax, rax
0x100480b8d  jz      short loc_100480BD4
0x100480b8f  mov     [rsp+0E8h+cbSid], 44h ; 'D'
0x100480b97  lea     r9, [rsp+0E8h+cbSid]; cbSid
0x100480b9c  mov     r8, rax; pSid
0x100480b9f  xor     edx, edx; DomainSid
0x100480ba1  lea     ecx, [rdx+17h]; WellKnownSidType
0x100480ba4  call    cs:__imp_CreateWellKnownSid
0x100480baa  test    eax, eax
0x100480bac  jz      short loc_100480BBD
0x100480bae  mov     rbx, rsi
0x100480bb1  mov     [rsp+0E8h+var_A0], rbx
0x100480bb6  mov     [rsp+0E8h+var_A8], r15
0x100480bbb  jmp     short loc_100480BD9
0x100480bbd  call    cs:__imp_GetLastError
0x100480bc3  mov     ebp, eax
0x100480bc5  test    eax, eax
0x100480bc7  jle     short loc_100480BD9
0x100480bc9  movzx   ebp, ax
0x100480bcc  or      ebp, 80070000h
0x100480bd2  jmp     short loc_100480BD9
0x100480bd4  mov     ebp, 8007000Eh
0x100480bd9  mov     rcx, rbx
0x100480bdc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100480be2  mov     esi, ebp
0x100480be4  test    ebp, ebp
0x100480be6  js      short loc_100480BEF
0x100480be8  mov     r14, [rsp+0E8h+var_A8]
0x100480bed  jmp     short loc_100480C07
0x100480bef  lfence
0x100480bf2  lea     r9, aAuthorizesecur_2; "AuthorizeSecurityContext failed when ca"...
0x100480bf9  xor     r8d, r8d
0x100480bfc  mov     edx, ebp
0x100480bfe  lea     ecx, [r8+1]
0x100480c02  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100480c07  test    ebp, ebp
0x100480c09  js      loc_100480CA0
0x100480c0f  jmp     short loc_100480C47
0x100480c11  mov     r14, cs:?sm_expectedNamedPipeOwner@CSQLSatelliteConnection@@2PEAXEA; void * CSQLSatelliteConnection::sm_expectedNamedPipeOwner
0x100480c18  test    r14, r14
0x100480c1b  jnz     short loc_100480C47
0x100480c1d  mov     [rsp+0E8h+ReturnLength], rsi
0x100480c22  mov     r9d, 0D4h
0x100480c28  lea     r8, aSqlNtdbmsExten_16; "\"Sql\\\\Ntdbms\\\\extensibility\\\\com"...
0x100480c2f  lea     rdx, aCsqlsatellitec_5; "CSQLSatelliteConnection::sm_expectedNam"...
0x100480c36  lea     ecx, [r14+1]
0x100480c3a  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100480c40  mov     r14, cs:?sm_expectedNamedPipeOwner@CSQLSatelliteConnection@@2PEAXEA; void * CSQLSatelliteConnection::sm_expectedNamedPipeOwner
0x100480c47  lea     r9, [rsp+0E8h+var_B0]
0x100480c4c  mov     r8d, 1
0x100480c52  mov     rdx, r14
0x100480c55  mov     rcx, rdi
0x100480c58  call    cs:__imp_CheckTokenMembershipEx
0x100480c5e  test    eax, eax
0x100480c60  jnz     short loc_100480C94
0x100480c62  call    cs:__imp_GetLastError
0x100480c68  test    eax, eax
0x100480c6a  jg      short loc_100480C70
0x100480c6c  mov     esi, eax
0x100480c6e  jmp     short loc_100480C79
0x100480c70  movzx   esi, ax
0x100480c73  or      esi, 80070000h
0x100480c79  mov     dword ptr [rsp+0E8h+ReturnLength], esi
0x100480c7d  lea     r9, aAuthorizesecur_1; "AuthorizeSecurityContext failed when ca"...
0x100480c84  xor     r8d, r8d
0x100480c87  mov     edx, esi
0x100480c89  lea     ecx, [r8+1]
0x100480c8d  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100480c92  jmp     short loc_100480CA0
0x100480c94  cmp     [rsp+0E8h+var_B0], 0
0x100480c99  setnz   cl
0x100480c9c  mov     [r12], cl
0x100480ca0  mov     rcx, [rsp+0E8h+var_A8]
0x100480ca5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100480cab  mov     eax, esi
0x100480cad  jmp     short loc_100480D07
0x100480caf  call    cs:__imp_GetLastError
0x100480cb5  mov     ebx, eax
0x100480cb7  test    eax, eax
0x100480cb9  jle     short loc_100480CC4
0x100480cbb  movzx   ebx, ax
0x100480cbe  or      ebx, 80070000h
0x100480cc4  lea     r9, aAuthorizesecur; "AuthorizeSecurityContext failed when ca"...
0x100480ccb  xor     r8d, r8d
0x100480cce  mov     edx, ebx
0x100480cd0  lea     ecx, [r8+1]
0x100480cd4  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100480cd9  cmp     ebx, 8007007Ah
0x100480cdf  jnz     short loc_100480D05
0x100480ce1  mov     [rsp+0E8h+ReturnLength], rsi
0x100480ce6  mov     r9d, 100h
0x100480cec  lea     r8, aSqlNtdbmsExten_16; "\"Sql\\\\Ntdbms\\\\extensibility\\\\com"...
0x100480cf3  lea     rdx, aHrHresultFromW; "hr != HRESULT_FROM_WIN32(ERROR_INSUFFIC"...
0x100480cfa  mov     ecx, 1
0x100480cff  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100480d05  mov     eax, ebx
0x100480d07  mov     rcx, [rsp+0E8h+var_38]
0x100480d0f  xor     rcx, rsp; StackCookie
0x100480d12  call    __security_check_cookie
0x100480d17  lea     r11, [rsp+0E8h+var_28]
0x100480d1f  mov     rbx, [r11+40h]
0x100480d23  mov     rbp, [r11+48h]
0x100480d27  mov     rsp, r11
0x100480d2a  pop     r15
0x100480d2c  pop     r14
0x100480d2e  pop     r12
0x100480d30  pop     rdi
0x100480d31  pop     rsi
0x100480d32  retn
```
