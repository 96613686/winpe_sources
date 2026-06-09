# CVssFunctionTracer::LogSecurityAudit(ulong,CVssDebugInfo)

- ea: `0x140089a68`
- end: `0x14008a074`
- name: `?LogSecurityAudit@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@@Z`
- size: `1548`
- prototype: `void __high(unsigned int, struct CVssDebugInfo)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038a30`
- `0x140054884`
- `0x1400b9a3c`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140031730`
- `0x14003c174`
- `0x14004ce80`
- `0x140089a68`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140089d01`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140089d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140089f8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140089b82`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140089b82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140089b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140089b6d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140089c47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140089c47`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x140089e05`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x140089e05`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x140089e36`
- `AUTHZ!AuthzReportSecurityEventFromParams` at `0x140089e36`
- `AUTHZ!AuthzUnregisterSecurityEventSource` at `0x140089edb`
- `AUTHZ!AuthzUnregisterSecurityEventSource` at `0x140089edb`

## string_xrefs

- `0x140089aa8`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089bae`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089c7a`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089d14`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089e69`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089f23`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089fb3`: `CVssFunctionTracer::LogSecurityAudit`
- `0x140089f72`: `Fail to register security audit winerr %d`
- `0x14008a002`: `Fail to register security audit winerr %d`
- `0x140089bfd`: `Fail to find the current process token audit winerr %d`
- `0x140089eb8`: `Fail of AuthzReportSecurityEventFromParams to log security audit winerr %d`
- `0x140089ccc`: `Fail to GetTokenInformation winerr %d, HRESULT 0x%#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CVssFunctionTracer::LogSecurityAudit(__int64 a1, DWORD a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  void *v5; // r14
  HANDLE CurrentProcess; // rax
  BOOL v7; // eax
  signed int LastError; // eax
  signed int v9; // ebx
  unsigned int v10; // edi
  signed int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // esi
  AUDIT_PARAM *v14; // rax
  AUDIT_PARAM *v15; // rbx
  USHORT v16; // si
  USHORT v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  signed int v20; // eax
  signed int v21; // ebx
  unsigned int v22; // edi
  signed int v23; // eax
  signed int v24; // ebx
  unsigned int v25; // edi
  signed int v26; // eax
  signed int v27; // ebx
  unsigned int v28; // edi
  unsigned __int16 i; // cx
  PDWORD ReturnLength; // [rsp+20h] [rbp-2B8h]
  AUDIT_PARAM *v31; // [rsp+30h] [rbp-2A8h] BYREF
  AUTHZ_SECURITY_EVENT_PROVIDER_HANDLE phEventProvider; // [rsp+38h] [rbp-2A0h] BYREF
  const unsigned __int16 *v33; // [rsp+40h] [rbp-298h] BYREF
  const wchar_t *v34; // [rsp+48h] [rbp-290h]
  const unsigned __int16 *v35; // [rsp+50h] [rbp-288h]
  int v36; // [rsp+58h] [rbp-280h]
  int v37; // [rsp+5Ch] [rbp-27Ch]
  int v38; // [rsp+60h] [rbp-278h]
  _QWORD v39[15]; // [rsp+68h] [rbp-270h] BYREF
  int v40; // [rsp+E0h] [rbp-1F8h]
  DWORD v41[4]; // [rsp+E8h] [rbp-1F0h] BYREF
  void **v42; // [rsp+F8h] [rbp-1E0h] BYREF
  void *TokenHandle; // [rsp+100h] [rbp-1D8h] BYREF
  _AUDIT_PARAMS pParams; // [rsp+108h] [rbp-1D0h] BYREF
  unsigned int v45; // [rsp+120h] [rbp-1B8h] BYREF
  unsigned __int16 *v46; // [rsp+128h] [rbp-1B0h]
  LPVOID v47[14]; // [rsp+130h] [rbp-1A8h] BYREF
  _QWORD TokenInformation[32]; // [rsp+1A0h] [rbp-138h] BYREF

  v3 = a3;
  v46 = a3;
  v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
  v34 = L"CVssFunctionTracer::LogSecurityAudit";
  v35 = L"TRCTRCC";
  v36 = 2382;
  v37 = 11;
  v38 = 255;
  v40 = 0x1000000;
  memset_0(v39, 0, sizeof(v39));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v47, (__int64)&v33, 0);
  phEventProvider = 0;
  TokenHandle = (void *)-1LL;
  v42 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v5 = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  memset(&pParams, 0, sizeof(pParams));
  CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v42);
  CurrentProcess = GetCurrentProcess();
  v7 = OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle);
  try
  {
    if ( !v7 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      else
        v10 = LastError;
      v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v34 = L"CVssFunctionTracer::LogSecurityAudit";
      v35 = L"TRCTRCC";
      v36 = 2402;
      v37 = 11;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(v39, 0, sizeof(v39));
      LODWORD(ReturnLength) = v9;
      CVssFunctionTracer::Throw(v47, &v33, v10, L"Fail to find the current process token audit winerr %d", ReturnLength);
    }
    v41[0] = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, v41) )
    {
      v5 = (void *)TokenInformation[0];
    }
    else
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v13 = (unsigned __int16)v11 | 0x80070000;
      else
        v13 = v11;
      v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v34 = L"CVssFunctionTracer::LogSecurityAudit";
      v35 = L"TRCTRCC";
      v36 = 2410;
      v37 = 11;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(v39, 0, sizeof(v39));
      LODWORD(ReturnLength) = v13;
      CVssFunctionTracer::Trace(v47, &v33, L"Fail to GetTokenInformation winerr %d, HRESULT 0x%#x", v12, ReturnLength);
    }
    v14 = (AUDIT_PARAM *)malloc(32LL * v3[80]);
    v15 = v14;
    if ( !v14 )
    {
      v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v34 = L"CVssFunctionTracer::LogSecurityAudit";
      v35 = L"TRCTRCC";
      v36 = 2421;
      v37 = 11;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(v39, 0, sizeof(v39));
      CVssFunctionTracer::Throw(v47, &v33, 2147942414LL, L"Can't allocate auditParams");
    }
    v16 = v3[80];
    memset_0(v14, 0, 32LL * v16);
    v31 = v15;
    pParams.Flags = 1;
    pParams.Length = 24;
    pParams.Count = v16;
    pParams.Parameters = v15;
    v17 = 0;
    if ( v16 )
    {
      v18 = 0;
      do
      {
        v19 = v18;
        v15[v19].Type = APT_String;
        v15[v19].Length = 8;
        v15[v19].Data0 = *(_QWORD *)&v3[4 * v18 + 20];
        ++v17;
        ++v18;
      }
      while ( v17 < v16 );
    }
    if ( !AuthzRegisterSecurityEventSource(0, L"VSSAudit", &phEventProvider) || !phEventProvider )
    {
      v26 = GetLastError();
      v27 = v26;
      if ( v26 > 0 )
        v28 = (unsigned __int16)v26 | 0x80070000;
      else
        v28 = v26;
      v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v34 = L"CVssFunctionTracer::LogSecurityAudit";
      v35 = L"TRCTRCC";
      v36 = 2450;
      v37 = 11;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(v39, 0, sizeof(v39));
      LODWORD(ReturnLength) = v27;
      CVssFunctionTracer::Throw(v47, &v33, v28, L"Fail to register security audit winerr %d", ReturnLength);
    }
    if ( !AuthzReportSecurityEventFromParams(0, phEventProvider, a2, v5, &pParams) )
    {
      v20 = GetLastError();
      v21 = v20;
      if ( v20 > 0 )
        v22 = (unsigned __int16)v20 | 0x80070000;
      else
        v22 = v20;
      v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v34 = L"CVssFunctionTracer::LogSecurityAudit";
      v35 = L"TRCTRCC";
      v36 = 2465;
      v37 = 11;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(v39, 0, sizeof(v39));
      LODWORD(ReturnLength) = v21;
      CVssFunctionTracer::Throw(
        v47,
        &v33,
        v22,
        L"Fail of AuthzReportSecurityEventFromParams to log security audit winerr %d",
        ReturnLength);
    }
    if ( !AuthzUnregisterSecurityEventSource(0, &phEventProvider) )
    {
      v23 = GetLastError();
      v24 = v23;
      if ( v23 > 0 )
        v25 = (unsigned __int16)v23 | 0x80070000;
      else
        v25 = v23;
      v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
      v34 = L"CVssFunctionTracer::LogSecurityAudit";
      v35 = L"TRCTRCC";
      v36 = 2474;
      v37 = 11;
      v38 = 255;
      v40 = 0x1000000;
      memset_0(v39, 0, sizeof(v39));
      LODWORD(ReturnLength) = v24;
      CVssFunctionTracer::Throw(v47, &v33, v25, L"Fail to register security audit winerr %d", ReturnLength);
    }
    phEventProvider = 0;
    CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>::~CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>((void **)&v31);
  }
  catch ( long v45 )
  {
    v33 = L"base\\stor\\vss\\modules\\trace\\fntracer.cpp";
    v34 = L"CVssFunctionTracer::LogSecurityAudit";
    v35 = L"TRCTRCC";
    v36 = 2480;
    v37 = 11;
    v38 = 255;
    v40 = 0x1000000;
    for ( i = 0; i < 0xFu; ++i )
      v39[i] = 0;
    CVssFunctionTracer::Trace(v47, &v33, L"Fail to log the Security Audit event. HRESULT %#x", v45);
    v3 = v46;
  }
  CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>(&v42);
  CVssFunctionTracer::~CVssFunctionTracer(v47);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v3);
}

```

## disassembly

```asm
0x140089a68  mov     [rsp+arg_0], rbx
0x140089a6d  push    rsi
0x140089a6e  push    rdi
0x140089a6f  push    r13
0x140089a71  push    r14
0x140089a73  push    r15
0x140089a75  sub     rsp, 2B0h
0x140089a7c  mov     rax, cs:__security_cookie
0x140089a83  xor     rax, rsp
0x140089a86  mov     [rsp+2D8h+var_38], rax
0x140089a8e  mov     rdi, r8
0x140089a91  mov     r15d, edx
0x140089a94  mov     [rsp+2D8h+var_1B0], r8
0x140089a9c  lea     rsi, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140089aa3  mov     [rsp+2D8h+var_298], rsi
0x140089aa8  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089aaf  mov     [rsp+2D8h+var_290], rax
0x140089ab4  lea     rax, aTrctrcc; "TRCTRCC"
0x140089abb  mov     [rsp+2D8h+var_288], rax
0x140089ac0  mov     [rsp+2D8h+var_280], 94Eh
0x140089ac8  mov     [rsp+2D8h+var_27C], 0Bh
0x140089ad0  mov     [rsp+2D8h+var_278], 0FFh
0x140089ad8  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089ae3  xor     edx, edx; Val
0x140089ae5  lea     r13d, [rdx+1]
0x140089ae9  lea     r8d, [rdx+78h]; Size
0x140089aed  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089af2  call    memset_0
0x140089af7  xor     r8d, r8d
0x140089afa  lea     rdx, [rsp+2D8h+var_298]
0x140089aff  lea     rcx, [rsp+2D8h+var_1A8]
0x140089b07  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140089b0c  nop
0x140089b0d  mov     [rsp+2D8h+phEventProvider], 0
0x140089b16  mov     [rsp+2D8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140089b22  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x140089b29  mov     [rsp+2D8h+var_1E0], rax
0x140089b31  xor     r14d, r14d
0x140089b34  mov     ebx, 100h
0x140089b39  mov     r8d, ebx; Size
0x140089b3c  xor     edx, edx; Val
0x140089b3e  lea     rcx, [rsp+2D8h+TokenInformation]; void *
0x140089b46  call    memset_0
0x140089b4b  xorps   xmm0, xmm0
0x140089b4e  xor     eax, eax
0x140089b50  movups  xmmword ptr [rsp+2D8h+pParams.Length], xmm0
0x140089b58  mov     [rsp+2D8h+pParams.Parameters], rax
0x140089b60  lea     rcx, [rsp+2D8h+var_1E0]
0x140089b68  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x140089b6d  call    cs:__imp_GetCurrentProcess
0x140089b73  lea     r8, [rsp+2D8h+TokenHandle]; TokenHandle
0x140089b7b  lea     edx, [r13+27h]; DesiredAccess
0x140089b7f  mov     rcx, rax; ProcessHandle
0x140089b82  call    cs:__imp_OpenProcessToken
0x140089b88  test    eax, eax
0x140089b8a  jnz     loc_140089C19
0x140089b90  call    cs:__imp_GetLastError
0x140089b96  mov     ebx, eax
0x140089b98  test    eax, eax
0x140089b9a  jg      short loc_140089BA0
0x140089b9c  mov     edi, eax
0x140089b9e  jmp     short loc_140089BA9
0x140089ba0  movzx   edi, bx
0x140089ba3  or      edi, 80070000h
0x140089ba9  mov     [rsp+2D8h+var_298], rsi
0x140089bae  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089bb5  mov     [rsp+2D8h+var_290], rax
0x140089bba  lea     rax, aTrctrcc; "TRCTRCC"
0x140089bc1  mov     [rsp+2D8h+var_288], rax
0x140089bc6  mov     [rsp+2D8h+var_280], 962h
0x140089bce  mov     [rsp+2D8h+var_27C], 0Bh
0x140089bd6  mov     [rsp+2D8h+var_278], 0FFh
0x140089bde  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089be9  xor     edx, edx; Val
0x140089beb  lea     r8d, [rdx+78h]; Size
0x140089bef  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089bf4  call    memset_0
0x140089bf9  mov     dword ptr [rsp+2D8h+ReturnLength], ebx
0x140089bfd  lea     r9, aFailToFindTheC; "Fail to find the current process token "...
0x140089c04  mov     r8d, edi
0x140089c07  lea     rdx, [rsp+2D8h+var_298]
0x140089c0c  lea     rcx, [rsp+2D8h+var_1A8]
0x140089c14  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140089c19  mov     [rsp+2D8h+var_1F0], 0
0x140089c24  lea     rax, [rsp+2D8h+var_1F0]
0x140089c2c  mov     [rsp+2D8h+ReturnLength], rax; ReturnLength
0x140089c31  mov     r9d, ebx; TokenInformationLength
0x140089c34  lea     r8, [rsp+2D8h+TokenInformation]; TokenInformation
0x140089c3c  mov     edx, r13d; TokenInformationClass
0x140089c3f  mov     rcx, [rsp+2D8h+TokenHandle]; TokenHandle
0x140089c47  call    cs:__imp_GetTokenInformation
0x140089c4d  test    eax, eax
0x140089c4f  jnz     loc_140089CEE
0x140089c55  call    cs:__imp_GetLastError
0x140089c5b  mov     ebx, eax
0x140089c5d  test    eax, eax
0x140089c5f  jg      short loc_140089C65
0x140089c61  mov     esi, eax
0x140089c63  jmp     short loc_140089C6E
0x140089c65  movzx   esi, bx
0x140089c68  or      esi, 80070000h
0x140089c6e  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140089c75  mov     [rsp+2D8h+var_298], rax
0x140089c7a  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089c81  mov     [rsp+2D8h+var_290], rax
0x140089c86  lea     rax, aTrctrcc; "TRCTRCC"
0x140089c8d  mov     [rsp+2D8h+var_288], rax
0x140089c92  mov     [rsp+2D8h+var_280], 96Ah
0x140089c9a  mov     [rsp+2D8h+var_27C], 0Bh
0x140089ca2  mov     [rsp+2D8h+var_278], 0FFh
0x140089caa  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089cb5  xor     edx, edx; Val
0x140089cb7  lea     r8d, [rdx+78h]; Size
0x140089cbb  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089cc0  call    memset_0
0x140089cc5  mov     dword ptr [rsp+2D8h+ReturnLength], esi
0x140089cc9  mov     r9d, ebx
0x140089ccc  lea     r8, aFailToGettoken; "Fail to GetTokenInformation winerr %d, "...
0x140089cd3  lea     rdx, [rsp+2D8h+var_298]
0x140089cd8  lea     rcx, [rsp+2D8h+var_1A8]
0x140089ce0  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140089ce5  lea     rsi, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140089cec  jmp     short loc_140089CF6
0x140089cee  mov     r14, [rsp+2D8h+TokenInformation]
0x140089cf6  movzx   ecx, word ptr [rdi+0A0h]
0x140089cfd  shl     rcx, 5; Size
0x140089d01  call    cs:__imp_malloc
0x140089d07  mov     rbx, rax
0x140089d0a  test    rax, rax
0x140089d0d  jnz     short loc_140089D7E
0x140089d0f  mov     [rsp+2D8h+var_298], rsi
0x140089d14  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089d1b  mov     [rsp+2D8h+var_290], rax
0x140089d20  lea     rax, aTrctrcc; "TRCTRCC"
0x140089d27  mov     [rsp+2D8h+var_288], rax
0x140089d2c  mov     [rsp+2D8h+var_280], 975h
0x140089d34  mov     [rsp+2D8h+var_27C], 0Bh
0x140089d3c  mov     [rsp+2D8h+var_278], 0FFh
0x140089d44  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089d4f  xor     edx, edx; Val
0x140089d51  lea     r8d, [rbx+78h]; Size
0x140089d55  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089d5a  call    memset_0
0x140089d5f  lea     r9, aCanTAllocateAu; "Can't allocate auditParams"
0x140089d66  mov     r8d, 8007000Eh
0x140089d6c  lea     rdx, [rsp+2D8h+var_298]
0x140089d71  lea     rcx, [rsp+2D8h+var_1A8]
0x140089d79  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140089d7e  movzx   esi, word ptr [rdi+0A0h]
0x140089d85  mov     r8d, esi
0x140089d88  shl     r8, 5; Size
0x140089d8c  xor     edx, edx; Val
0x140089d8e  mov     rcx, rbx; void *
0x140089d91  call    memset_0
0x140089d96  mov     [rsp+2D8h+var_2A8], rbx
0x140089d9b  mov     [rsp+2D8h+pParams.Flags], r13d
0x140089da3  mov     [rsp+2D8h+pParams.Length], 18h
0x140089dae  mov     [rsp+2D8h+pParams.Count], si
0x140089db6  mov     [rsp+2D8h+pParams.Parameters], rbx
0x140089dbe  xor     r8d, r8d
0x140089dc1  xor     eax, eax
0x140089dc3  cmp     ax, si
0x140089dc6  jnb     short loc_140089DF7
0x140089dc8  xor     edx, edx
0x140089dca  mov     rcx, rdx
0x140089dcd  shl     rcx, 5
0x140089dd1  mov     dword ptr [rcx+rbx], 2
0x140089dd8  mov     dword ptr [rcx+rbx+4], 8
0x140089de0  mov     rax, [rdi+rdx*8+28h]
0x140089de5  mov     [rcx+rbx+10h], rax
0x140089dea  add     r8w, r13w
0x140089dee  add     rdx, r13
0x140089df1  cmp     r8w, si
0x140089df5  jb      short loc_140089DCA
0x140089df7  lea     r8, [rsp+2D8h+phEventProvider]; phEventProvider
0x140089dfc  lea     rdx, szEventSourceName; "VSSAudit"
0x140089e03  xor     ecx, ecx; dwFlags
0x140089e05  call    cs:__imp_AuthzRegisterSecurityEventSource
0x140089e0b  test    eax, eax
0x140089e0d  jz      loc_140089F8E
0x140089e13  mov     rdx, [rsp+2D8h+phEventProvider]; hEventProvider
0x140089e18  test    rdx, rdx
0x140089e1b  jz      loc_140089F8E
0x140089e21  lea     rax, [rsp+2D8h+pParams]
0x140089e29  mov     [rsp+2D8h+ReturnLength], rax; pParams
0x140089e2e  mov     r9, r14; pUserSid
0x140089e31  mov     r8d, r15d; dwAuditId
0x140089e34  xor     ecx, ecx; dwFlags
0x140089e36  call    cs:__imp_AuthzReportSecurityEventFromParams
0x140089e3c  test    eax, eax
0x140089e3e  jnz     loc_140089ED4
0x140089e44  call    cs:__imp_GetLastError
0x140089e4a  mov     ebx, eax
0x140089e4c  test    eax, eax
0x140089e4e  jg      short loc_140089E54
0x140089e50  mov     edi, eax
0x140089e52  jmp     short loc_140089E5D
0x140089e54  movzx   edi, bx
0x140089e57  or      edi, 80070000h
0x140089e5d  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140089e64  mov     [rsp+2D8h+var_298], rax
0x140089e69  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089e70  mov     [rsp+2D8h+var_290], rax
0x140089e75  lea     rax, aTrctrcc; "TRCTRCC"
0x140089e7c  mov     [rsp+2D8h+var_288], rax
0x140089e81  mov     [rsp+2D8h+var_280], 9A1h
0x140089e89  mov     [rsp+2D8h+var_27C], 0Bh
0x140089e91  mov     [rsp+2D8h+var_278], 0FFh
0x140089e99  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089ea4  xor     edx, edx; Val
0x140089ea6  lea     r8d, [rdx+78h]; Size
0x140089eaa  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089eaf  call    memset_0
0x140089eb4  mov     dword ptr [rsp+2D8h+ReturnLength], ebx
0x140089eb8  lea     r9, aFailOfAuthzrep; "Fail of AuthzReportSecurityEventFromPar"...
0x140089ebf  mov     r8d, edi
0x140089ec2  lea     rdx, [rsp+2D8h+var_298]
0x140089ec7  lea     rcx, [rsp+2D8h+var_1A8]
0x140089ecf  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140089ed4  lea     rdx, [rsp+2D8h+phEventProvider]; phEventProvider
0x140089ed9  xor     ecx, ecx; dwFlags
0x140089edb  call    cs:__imp_AuthzUnregisterSecurityEventSource
0x140089ee1  test    eax, eax
0x140089ee3  jz      short loc_140089EFE
0x140089ee5  mov     [rsp+2D8h+phEventProvider], 0
0x140089eee  lea     rcx, [rsp+2D8h+var_2A8]
0x140089ef3  call    ??1?$CVssMallocAutoPtr@U_VM_GET_CLOSURE_OUTPUT@@@@QEAA@XZ; CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>::~CVssMallocAutoPtr<_VM_GET_CLOSURE_OUTPUT>(void)
0x140089ef8  nop
0x140089ef9  jmp     loc_14008A027
0x140089efe  call    cs:__imp_GetLastError
0x140089f04  mov     ebx, eax
0x140089f06  test    eax, eax
0x140089f08  jg      short loc_140089F0E
0x140089f0a  mov     edi, eax
0x140089f0c  jmp     short loc_140089F17
0x140089f0e  movzx   edi, bx
0x140089f11  or      edi, 80070000h
0x140089f17  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140089f1e  mov     [rsp+2D8h+var_298], rax
0x140089f23  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089f2a  mov     [rsp+2D8h+var_290], rax
0x140089f2f  lea     rax, aTrctrcc; "TRCTRCC"
0x140089f36  mov     [rsp+2D8h+var_288], rax
0x140089f3b  mov     [rsp+2D8h+var_280], 9AAh
0x140089f43  mov     [rsp+2D8h+var_27C], 0Bh
0x140089f4b  mov     [rsp+2D8h+var_278], 0FFh
0x140089f53  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089f5e  xor     edx, edx; Val
0x140089f60  lea     r8d, [rdx+78h]; Size
0x140089f64  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089f69  call    memset_0
0x140089f6e  mov     dword ptr [rsp+2D8h+ReturnLength], ebx
0x140089f72  lea     r9, aFailToRegister; "Fail to register security audit winerr "...
0x140089f79  mov     r8d, edi
0x140089f7c  lea     rdx, [rsp+2D8h+var_298]
0x140089f81  lea     rcx, [rsp+2D8h+var_1A8]
0x140089f89  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140089f8e  call    cs:__imp_GetLastError
0x140089f94  mov     ebx, eax
0x140089f96  test    eax, eax
0x140089f98  jg      short loc_140089F9E
0x140089f9a  mov     edi, eax
0x140089f9c  jmp     short loc_140089FA7
0x140089f9e  movzx   edi, bx
0x140089fa1  or      edi, 80070000h
0x140089fa7  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\trace\\fntrac"...
0x140089fae  mov     [rsp+2D8h+var_298], rax
0x140089fb3  lea     rax, aCvssfunctiontr_6; "CVssFunctionTracer::LogSecurityAudit"
0x140089fba  mov     [rsp+2D8h+var_290], rax
0x140089fbf  lea     rax, aTrctrcc; "TRCTRCC"
0x140089fc6  mov     [rsp+2D8h+var_288], rax
0x140089fcb  mov     [rsp+2D8h+var_280], 992h
0x140089fd3  mov     [rsp+2D8h+var_27C], 0Bh
0x140089fdb  mov     [rsp+2D8h+var_278], 0FFh
0x140089fe3  mov     [rsp+2D8h+var_1F8], 1000000h
0x140089fee  xor     edx, edx; Val
0x140089ff0  lea     r8d, [rdx+78h]; Size
0x140089ff4  lea     rcx, [rsp+2D8h+var_270]; void *
0x140089ff9  call    memset_0
0x140089ffe  mov     dword ptr [rsp+2D8h+ReturnLength], ebx
0x14008a002  lea     r9, aFailToRegister; "Fail to register security audit winerr "...
0x14008a009  mov     r8d, edi
0x14008a00c  lea     rdx, [rsp+2D8h+var_298]
0x14008a011  lea     rcx, [rsp+2D8h+var_1A8]
0x14008a019  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14008a01f  mov     rdi, [rsp+2D8h+var_1B0]
0x14008a027  lea     rcx, [rsp+2D8h+var_1E0]
0x14008a02f  call    ??1?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@UEAA@XZ; CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::~CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>(void)
0x14008a034  nop
0x14008a035  lea     rcx, [rsp+2D8h+var_1A8]; this
0x14008a03d  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14008a042  nop
0x14008a043  mov     rcx, rdi; this
0x14008a046  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14008a04b  nop
0x14008a04c  mov     rcx, [rsp+2D8h+var_38]
0x14008a054  xor     rcx, rsp; StackCookie
0x14008a057  call    __security_check_cookie
0x14008a05c  mov     rbx, [rsp+2D8h+arg_0]
0x14008a064  add     rsp, 2B0h
  ... truncated ...
```
