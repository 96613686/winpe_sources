# RemoteConnectionListener::EnsureCertificateInstalled(void)

- ea: `0x140631794`
- end: `0x140631c2d`
- name: `?EnsureCertificateInstalled@RemoteConnectionListener@@AEAAJXZ`
- size: `1177`
- prototype: `__int64 __fastcall(RemoteConnectionListener *__hidden this)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1406310bc`
- `0x140631490`
- `0x140632760`

## callees

- `0x140034404`
- `0x14005c630`
- `0x14008e064`
- `0x1400b971c`
- `0x1400bd87c`
- `0x1400c6d70`
- `0x1401be65c`
- `0x1402caba8`
- `0x14046d29c`
- `0x14046d3b8`
- `0x1404828e0`
- `0x140631794`
- `0x140631c7c`
- `0x1407df298`
- `0x1407dfb88`
- `0x1407dfd24`
- `0x1407e0294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140631839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406318ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140631a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140631a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140631839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1406318ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140631a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140631a89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140631986`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140631986`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14063194c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14063194c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140631972`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140631999`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140631972`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140631999`
- `CRYPT32!CertFreeCertificateContext` at `0x140631bc0`
- `CRYPT32!CertFreeCertificateContext` at `0x140631bc0`
- `CRYPT32!CertCloseStore` at `0x140631bd6`
- `CRYPT32!CertCloseStore` at `0x140631bec`
- `CRYPT32!CertCloseStore` at `0x140631bd6`
- `CRYPT32!CertCloseStore` at `0x140631bec`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140631a21`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140631a79`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140631a21`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140631a79`
- `CRYPT32!CertOpenStore` at `0x140631822`
- `CRYPT32!CertOpenStore` at `0x140631898`
- `CRYPT32!CertOpenStore` at `0x140631822`
- `CRYPT32!CertOpenStore` at `0x140631898`

## string_xrefs

- `0x140631868`: `Unable to open trusted root machine certificate store (0x%x).\n`
- `0x1406318db`: `Unable to open service 'my' certificate store (0x%x).\n`
- `0x140631908`: `Failed to delete expired certificates (0x%x).\n`
- `0x140631a60`: `Unable to cache self-signed certificate (0x%x).\n`
- `0x140631ab8`: `Unable to cache self-signed certificate in trusted root (0x%x).\n`
- `0x140631935`: `Failed to impersonate Worker Process account: error 0x%08lX\n`

## pseudocode

```c
__int64 __fastcall RemoteConnectionListener::EnsureCertificateInstalled(RemoteConnectionListener *this)
{
  unsigned int v2; // edi
  PCCERT_CONTEXT v3; // rsi
  HCERTSTORE v4; // r12
  void *v5; // r15
  signed int LastError; // eax
  HCERTSTORE v7; // rax
  signed int v8; // eax
  RemoteConnectionListener *v9; // rcx
  int v10; // ebx
  int BestCertificate; // ebx
  const struct _GUID *v12; // r8
  const struct _GUID *v13; // r8
  int v14; // eax
  const struct _GUID *v15; // r8
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v18; // edx
  unsigned __int64 v19; // rcx
  const unsigned int *v21; // [rsp+28h] [rbp-81h]
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-79h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-71h] BYREF
  __int64 v24; // [rsp+40h] [rbp-69h] BYREF
  __int128 v25; // [rsp+48h] [rbp-61h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int8 v27[16]; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-39h]
  __int64 v29[4]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v30[32]; // [rsp+98h] [rbp-11h] BYREF

  v25 = 0;
  Vml::VmAutoLock::VmAutoLock((Vml::VmAutoLock *)&v25, (RemoteConnectionListener *)((char *)this + 896));
  if ( !*((_QWORD *)this + 62) )
  {
    v2 = -2147418113;
    goto LABEL_56;
  }
  pCertContext = 0;
  v28 = 0;
  v24 = 0;
  SystemTimeAsFileTime = 0;
  v3 = 0;
  *(_OWORD *)v27 = 0;
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"Root");
  if ( !v4 )
  {
    v5 = 0;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16602) )
      VmlDebugTrace(16602, L"Unable to open trusted root machine certificate store (0x%x).\n", v2);
    goto LABEL_47;
  }
  v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x50000u, L"vmms\\MY");
  v5 = v7;
  if ( !v7 )
  {
    v8 = GetLastError();
    v2 = v8;
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    if ( (unsigned int)VmlIsDebugTraceEnabled(16602) )
      VmlDebugTrace(16602, L"Unable to open service 'my' certificate store (0x%x).\n", v2);
    goto LABEL_47;
  }
  v10 = CertHelper::DeleteExpiredCertificates(v7, v4);
  if ( v10 < 0 && (unsigned int)VmlIsDebugTraceEnabled(32986) )
    VmlDebugTrace(32986, L"Failed to delete expired certificates (0x%x).\n", (unsigned int)v10);
  v2 = RemoteConnectionListener::ImpersonateVmWorker(v9);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16481) )
      VmlDebugTrace(16481, L"Failed to impersonate Worker Process account: error 0x%08lX\n", v2);
    goto LABEL_47;
  }
  BestCertificate = CertHelper::FindBestCertificate(&pCertContext);
  RevertToSelf();
  if ( BestCertificate >= 0 )
  {
    v3 = pCertContext;
  }
  else
  {
    FileTime2 = 0;
    if ( CompareFileTime((const FILETIME *)this + 117, &FileTime2) )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime((const FILETIME *)this + 117, &SystemTimeAsFileTime) <= 0 )
        VmEventWriteCommon(&CERT_EXPIRED_ERROR, 1u, v13, 0, 0, v21);
    }
    VmEventWriteCommon(&CERT_CREATE_WARNING, 1u, v13, 0, 0, v21);
    v14 = CertHelper::CreateSelfSignedCertificate(&pCertContext);
    v2 = v14;
    if ( v14 < 0 )
    {
      v3 = pCertContext;
LABEL_48:
      _snwprintf_s<16>(v30, 16, L"%%%%%u", v2 & 0xEFFFFFFF);
      _snwprintf_s<16>(v29, 16, L"0x%08X", v2 & 0xEFFFFFFF);
      VmEventWrite<unsigned short (&)[16],unsigned short (&)[16]>(&CERT_CREATE_ERROR, 1u, (__int64)v29);
      *((_QWORD *)this + 117) = 0;
      goto LABEL_49;
    }
    if ( v14 == 1 )
    {
      VmEventWriteCommon(&CERT_CREATEPOLICYNOTALLOW_WARNING, 1u, v15, 0, 0, v21);
      v3 = pCertContext;
      goto LABEL_49;
    }
    v3 = pCertContext;
    if ( !CertAddCertificateContextToStore(v5, pCertContext, 1u, 0) )
    {
      v16 = GetLastError();
      v2 = v16;
      if ( v16 > 0 )
        v2 = (unsigned __int16)v16 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16602) )
        VmlDebugTrace(16602, L"Unable to cache self-signed certificate (0x%x).\n", v2);
      goto LABEL_47;
    }
    if ( !CertAddCertificateContextToStore(v4, v3, 1u, 0) )
    {
      v17 = GetLastError();
      v2 = v17;
      if ( v17 > 0 )
        v2 = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)VmlIsDebugTraceEnabled(16602) )
        VmlDebugTrace(16602, L"Unable to cache self-signed certificate in trusted root (0x%x).\n", v2);
      goto LABEL_47;
    }
  }
  VmEventWriteCommon(&CERT_INIT_SUCCESS, 1u, v12, 0, 0, v21);
  CertHelper::GetCertHash(v3, v27);
  v18 = v28;
  v19 = *(_QWORD *)v27 - *((_QWORD *)this + 118);
  if ( *(_QWORD *)v27 == *((_QWORD *)this + 118) )
  {
    v19 = *(_QWORD *)&v27[8] - *((_QWORD *)this + 119);
    if ( *(_QWORD *)&v27[8] == *((_QWORD *)this + 119) )
      v19 = v28 - (unsigned __int64)*((unsigned int *)this + 240);
  }
  if ( v19 )
  {
    *((_OWORD *)this + 59) = *(_OWORD *)v27;
    *((_DWORD *)this + 240) = v18;
    Vml::VmDelegateInterface<void,>::Dispatch((char *)this + 512);
  }
  if ( v3 )
    RemoteConnectionListener::SetCertExpirationTimer(this, v3);
  v2 = 0;
LABEL_47:
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_48;
LABEL_49:
  if ( v3 )
    CertFreeCertificateContext(v3);
  if ( v5 )
    CertCloseStore(v5, 0);
  if ( v4 )
    CertCloseStore(v4, 0);
  Vml::VmAccessToken::~VmAccessToken((Vml::VmAccessToken *)&v24);
LABEL_56:
  Vml::VmAutoLock::~VmAutoLock((Vml::VmAutoLock *)&v25);
  return v2;
}

```

## disassembly

```asm
0x140631794  push    rbp
0x140631796  push    rbx
0x140631797  push    rsi
0x140631798  push    rdi
0x140631799  push    r12
0x14063179b  push    r13
0x14063179d  push    r14
0x14063179f  push    r15
0x1406317a1  lea     rbp, [rsp-1Fh]
0x1406317a6  sub     rsp, 0C8h
0x1406317ad  mov     rax, cs:__security_cookie
0x1406317b4  xor     rax, rsp
0x1406317b7  mov     [rbp+57h+var_48], rax
0x1406317bb  mov     r14, rcx
0x1406317be  lea     rdx, [rcx+380h]; struct Vml::VmCriticalSection *
0x1406317c5  xorps   xmm0, xmm0
0x1406317c8  lea     rcx, [rbp+57h+var_B8]; this
0x1406317cc  movups  [rbp+57h+var_B8], xmm0
0x1406317d0  call    ??0VmAutoLock@Vml@@QEAA@PEBVVmCriticalSection@1@@Z; Vml::VmAutoLock::VmAutoLock(Vml::VmCriticalSection const *)
0x1406317d5  xor     r13d, r13d
0x1406317d8  cmp     [r14+1F0h], r13
0x1406317df  jnz     short loc_1406317EB
0x1406317e1  mov     edi, 8000FFFFh
0x1406317e6  jmp     loc_140631C01
0x1406317eb  xor     eax, eax
0x1406317ed  mov     [rbp+57h+pCertContext], r13
0x1406317f1  xor     edx, edx; dwEncodingType
0x1406317f3  mov     [rbp+57h+var_90], eax
0x1406317f6  xorps   xmm0, xmm0
0x1406317f9  mov     [rbp+57h+var_C0], r13
0x1406317fd  lea     rax, aRoot_0; "Root"
0x140631804  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r13
0x140631808  mov     r9d, 20000h; dwFlags
0x14063180e  mov     [rsp+100h+pvPara], rax; pvPara
0x140631813  lea     ebx, [rdx+0Ah]
0x140631816  xor     r8d, r8d; hCryptProv
0x140631819  mov     ecx, ebx; lpszStoreProvider
0x14063181b  mov     rsi, r13
0x14063181e  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x140631822  call    cs:__imp_CertOpenStore
0x140631829  nop     dword ptr [rax+rax+00h]
0x14063182e  mov     r12, rax
0x140631831  test    rax, rax
0x140631834  jnz     short loc_14063187E
0x140631836  mov     r15, r13
0x140631839  call    cs:__imp_GetLastError
0x140631840  nop     dword ptr [rax+rax+00h]
0x140631845  mov     edi, eax
0x140631847  test    eax, eax
0x140631849  jle     short loc_140631854
0x14063184b  movzx   edi, ax
0x14063184e  or      edi, 80070000h
0x140631854  mov     ebx, 40DAh
0x140631859  mov     ecx, ebx
0x14063185b  call    VmlIsDebugTraceEnabled
0x140631860  test    eax, eax
0x140631862  jz      loc_140631B55
0x140631868  lea     rdx, aUnableToOpenTr; "Unable to open trusted root machine cer"...
0x14063186f  mov     r8d, edi
0x140631872  mov     ecx, ebx
0x140631874  call    VmlDebugTrace
0x140631879  jmp     loc_140631B55
0x14063187e  lea     rax, aVmmsMy; "vmms\\MY"
0x140631885  mov     r9d, 50000h; dwFlags
0x14063188b  xor     r8d, r8d; hCryptProv
0x14063188e  mov     [rsp+100h+pvPara], rax; pvPara
0x140631893  xor     edx, edx; dwEncodingType
0x140631895  mov     rcx, rbx; lpszStoreProvider
0x140631898  call    cs:__imp_CertOpenStore
0x14063189f  nop     dword ptr [rax+rax+00h]
0x1406318a4  mov     r15, rax
0x1406318a7  test    rax, rax
0x1406318aa  jnz     short loc_1406318E4
0x1406318ac  call    cs:__imp_GetLastError
0x1406318b3  nop     dword ptr [rax+rax+00h]
0x1406318b8  mov     edi, eax
0x1406318ba  test    eax, eax
0x1406318bc  jle     short loc_1406318C7
0x1406318be  movzx   edi, ax
0x1406318c1  or      edi, 80070000h
0x1406318c7  mov     ebx, 40DAh
0x1406318cc  mov     ecx, ebx
0x1406318ce  call    VmlIsDebugTraceEnabled
0x1406318d3  test    eax, eax
0x1406318d5  jz      loc_140631B55
0x1406318db  lea     rdx, aUnableToOpenSe; "Unable to open service 'my' certificate"...
0x1406318e2  jmp     short loc_14063186F
0x1406318e4  mov     rdx, r12; HCERTSTORE
0x1406318e7  mov     rcx, r15; hCertStore
0x1406318ea  call    ?DeleteExpiredCertificates@CertHelper@@SAJPEAX0@Z; CertHelper::DeleteExpiredCertificates(void *,void *)
0x1406318ef  mov     ebx, eax
0x1406318f1  test    eax, eax
0x1406318f3  jns     short loc_140631916
0x1406318f5  mov     edi, 80DAh
0x1406318fa  mov     ecx, edi
0x1406318fc  call    VmlIsDebugTraceEnabled
0x140631901  test    eax, eax
0x140631903  jz      short loc_140631916
0x140631905  mov     r8d, ebx
0x140631908  lea     rdx, aFailedToDelete_2; "Failed to delete expired certificates ("...
0x14063190f  mov     ecx, edi
0x140631911  call    VmlDebugTrace
0x140631916  call    ?ImpersonateVmWorker@RemoteConnectionListener@@AEAAJXZ; RemoteConnectionListener::ImpersonateVmWorker(void)
0x14063191b  mov     edi, eax
0x14063191d  test    eax, eax
0x14063191f  jns     short loc_140631941
0x140631921  mov     ebx, 4061h
0x140631926  mov     ecx, ebx
0x140631928  call    VmlIsDebugTraceEnabled
0x14063192d  test    eax, eax
0x14063192f  jz      loc_140631B55
0x140631935  lea     rdx, aFailedToImpers; "Failed to impersonate Worker Process ac"...
0x14063193c  jmp     loc_14063186F
0x140631941  lea     rcx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT **
0x140631945  call    ?FindBestCertificate@CertHelper@@SAJPEAPEBU_CERT_CONTEXT@@@Z; CertHelper::FindBestCertificate(_CERT_CONTEXT const * *)
0x14063194a  mov     ebx, eax
0x14063194c  call    cs:__imp_RevertToSelf
0x140631953  nop     dword ptr [rax+rax+00h]
0x140631958  test    ebx, ebx
0x14063195a  jns     loc_140631ACD
0x140631960  lea     rbx, [r14+3A8h]
0x140631967  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], r13
0x14063196b  mov     rcx, rbx; lpFileTime1
0x14063196e  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x140631972  call    cs:__imp_CompareFileTime
0x140631979  nop     dword ptr [rax+rax+00h]
0x14063197e  test    eax, eax
0x140631980  jz      short loc_1406319C1
0x140631982  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140631986  call    cs:__imp_GetSystemTimeAsFileTime
0x14063198d  nop     dword ptr [rax+rax+00h]
0x140631992  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x140631996  mov     rcx, rbx; lpFileTime1
0x140631999  call    cs:__imp_CompareFileTime
0x1406319a0  nop     dword ptr [rax+rax+00h]
0x1406319a5  test    eax, eax
0x1406319a7  jg      short loc_1406319C1
0x1406319a9  xor     r9d, r9d; unsigned int
0x1406319ac  mov     [rsp+100h+pvPara], r13; struct _EVENT_DATA_DESCRIPTOR *
0x1406319b1  lea     rcx, CERT_EXPIRED_ERROR; EventDescriptor
0x1406319b8  lea     edx, [r9+1]; unsigned int
0x1406319bc  call    ?VmEventWriteCommon@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@KPEBU_EVENT_DATA_DESCRIPTOR@@PEBI@Z; VmEventWriteCommon(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ulong,_EVENT_DATA_DESCRIPTOR const *,uint const *)
0x1406319c1  xor     r9d, r9d; unsigned int
0x1406319c4  mov     [rsp+100h+pvPara], r13; struct _EVENT_DATA_DESCRIPTOR *
0x1406319c9  lea     rcx, CERT_CREATE_WARNING; EventDescriptor
0x1406319d0  lea     edx, [r9+1]; unsigned int
0x1406319d4  call    ?VmEventWriteCommon@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@KPEBU_EVENT_DATA_DESCRIPTOR@@PEBI@Z; VmEventWriteCommon(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ulong,_EVENT_DATA_DESCRIPTOR const *,uint const *)
0x1406319d9  lea     rcx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT **
0x1406319dd  call    ?CreateSelfSignedCertificate@CertHelper@@SAJPEAPEBU_CERT_CONTEXT@@@Z; CertHelper::CreateSelfSignedCertificate(_CERT_CONTEXT const * *)
0x1406319e2  mov     edi, eax
0x1406319e4  test    eax, eax
0x1406319e6  js      loc_140631AC4
0x1406319ec  cmp     eax, 1
0x1406319ef  jnz     short loc_140631A10
0x1406319f1  xor     r9d, r9d; unsigned int
0x1406319f4  mov     [rsp+100h+pvPara], r13; struct _EVENT_DATA_DESCRIPTOR *
0x1406319f9  mov     edx, eax; unsigned int
0x1406319fb  lea     rcx, CERT_CREATEPOLICYNOTALLOW_WARNING; EventDescriptor
0x140631a02  call    ?VmEventWriteCommon@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@KPEBU_EVENT_DATA_DESCRIPTOR@@PEBI@Z; VmEventWriteCommon(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ulong,_EVENT_DATA_DESCRIPTOR const *,uint const *)
0x140631a07  mov     rsi, [rbp+57h+pCertContext]
0x140631a0b  jmp     loc_140631BB8
0x140631a10  mov     rsi, [rbp+57h+pCertContext]
0x140631a14  xor     r9d, r9d; ppStoreContext
0x140631a17  mov     rdx, rsi; pCertContext
0x140631a1a  mov     rcx, r15; hCertStore
0x140631a1d  lea     r8d, [r9+1]; dwAddDisposition
0x140631a21  call    cs:__imp_CertAddCertificateContextToStore
0x140631a28  nop     dword ptr [rax+rax+00h]
0x140631a2d  test    eax, eax
0x140631a2f  jnz     short loc_140631A6C
0x140631a31  call    cs:__imp_GetLastError
0x140631a38  nop     dword ptr [rax+rax+00h]
0x140631a3d  mov     edi, eax
0x140631a3f  test    eax, eax
0x140631a41  jle     short loc_140631A4C
0x140631a43  movzx   edi, ax
0x140631a46  or      edi, 80070000h
0x140631a4c  mov     ebx, 40DAh
0x140631a51  mov     ecx, ebx
0x140631a53  call    VmlIsDebugTraceEnabled
0x140631a58  test    eax, eax
0x140631a5a  jz      loc_140631B55
0x140631a60  lea     rdx, aUnableToCacheS_0; "Unable to cache self-signed certificate"...
0x140631a67  jmp     loc_14063186F
0x140631a6c  xor     r9d, r9d; ppStoreContext
0x140631a6f  mov     rdx, rsi; pCertContext
0x140631a72  mov     rcx, r12; hCertStore
0x140631a75  lea     r8d, [r9+1]; dwAddDisposition
0x140631a79  call    cs:__imp_CertAddCertificateContextToStore
0x140631a80  nop     dword ptr [rax+rax+00h]
0x140631a85  test    eax, eax
0x140631a87  jnz     short loc_140631AD1
0x140631a89  call    cs:__imp_GetLastError
0x140631a90  nop     dword ptr [rax+rax+00h]
0x140631a95  mov     edi, eax
0x140631a97  test    eax, eax
0x140631a99  jle     short loc_140631AA4
0x140631a9b  movzx   edi, ax
0x140631a9e  or      edi, 80070000h
0x140631aa4  mov     ebx, 40DAh
0x140631aa9  mov     ecx, ebx
0x140631aab  call    VmlIsDebugTraceEnabled
0x140631ab0  test    eax, eax
0x140631ab2  jz      loc_140631B55
0x140631ab8  lea     rdx, aUnableToCacheS; "Unable to cache self-signed certificate"...
0x140631abf  jmp     loc_14063186F
0x140631ac4  mov     rsi, [rbp+57h+pCertContext]
0x140631ac8  jmp     loc_140631B59
0x140631acd  mov     rsi, [rbp+57h+pCertContext]
0x140631ad1  xor     r9d, r9d; unsigned int
0x140631ad4  mov     [rsp+100h+pvPara], r13; struct _EVENT_DATA_DESCRIPTOR *
0x140631ad9  lea     rcx, CERT_INIT_SUCCESS; EventDescriptor
0x140631ae0  lea     edx, [r9+1]; unsigned int
0x140631ae4  call    ?VmEventWriteCommon@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@KPEBU_EVENT_DATA_DESCRIPTOR@@PEBI@Z; VmEventWriteCommon(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ulong,_EVENT_DATA_DESCRIPTOR const *,uint const *)
0x140631ae9  lea     rdx, [rbp+57h+var_A0]; unsigned __int8 *
0x140631aed  mov     rcx, rsi; struct _CERT_CONTEXT *
0x140631af0  call    ?GetCertHash@CertHelper@@SAJPEBU_CERT_CONTEXT@@PEAE@Z; CertHelper::GetCertHash(_CERT_CONTEXT const *,uchar *)
0x140631af5  mov     rcx, qword ptr [rbp+57h+var_A0]
0x140631af9  mov     edx, [rbp+57h+var_90]
0x140631afc  sub     rcx, [r14+3B0h]
0x140631b03  jnz     short loc_140631B1E
0x140631b05  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x140631b09  sub     rcx, [r14+3B8h]
0x140631b10  jnz     short loc_140631B1E
0x140631b12  mov     eax, [r14+3C0h]
0x140631b19  mov     ecx, edx
0x140631b1b  sub     rcx, rax
0x140631b1e  test    rcx, rcx
0x140631b21  jz      short loc_140631B42
0x140631b23  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x140631b27  lea     rcx, [r14+200h]
0x140631b2e  movups  xmmword ptr [r14+3B0h], xmm0
0x140631b36  mov     [r14+3C0h], edx
0x140631b3d  call    ?Dispatch@?$VmDelegateInterface@X$$V@Vml@@QEAAHXZ; Vml::VmDelegateInterface<void,>::Dispatch(void)
0x140631b42  test    rsi, rsi
0x140631b45  jz      short loc_140631B52
0x140631b47  mov     rdx, rsi; struct _CERT_CONTEXT *
0x140631b4a  mov     rcx, r14; this
0x140631b4d  call    ?SetCertExpirationTimer@RemoteConnectionListener@@AEAAXPEBU_CERT_CONTEXT@@@Z; RemoteConnectionListener::SetCertExpirationTimer(_CERT_CONTEXT const *)
0x140631b52  mov     edi, r13d
0x140631b55  test    edi, edi
0x140631b57  jns     short loc_140631BB8
0x140631b59  mov     ebx, edi
0x140631b5b  lea     r8, aU_1; "%%%%%u"
0x140631b62  btr     ebx, 1Ch
0x140631b66  lea     rcx, [rbp+57h+var_68]
0x140631b6a  mov     r13d, 10h
0x140631b70  mov     r9d, ebx
0x140631b73  mov     edx, r13d
0x140631b76  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140631b7b  mov     r9d, ebx
0x140631b7e  lea     r8, a0x08x; "0x%08X"
0x140631b85  mov     edx, r13d
0x140631b88  lea     rcx, [rbp+57h+var_88]
0x140631b8c  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x140631b91  lea     rax, [rbp+57h+var_88]
0x140631b95  lea     r9, [rbp+57h+var_68]
0x140631b99  mov     [rsp+100h+pvPara], rax; __int64
0x140631b9e  lea     edx, [r13-0Fh]; unsigned int
0x140631ba2  lea     rcx, CERT_CREATE_ERROR; EventDescriptor
0x140631ba9  call    ??$VmEventWrite@AEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@AEAY0BA@G2@Z; VmEventWrite<ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort (&)[16],ushort (&)[16])
0x140631bae  xor     r13d, r13d
0x140631bb1  mov     [r14+3A8h], r13
0x140631bb8  test    rsi, rsi
0x140631bbb  jz      short loc_140631BCC
0x140631bbd  mov     rcx, rsi; pCertContext
0x140631bc0  call    cs:__imp_CertFreeCertificateContext
0x140631bc7  nop     dword ptr [rax+rax+00h]
0x140631bcc  test    r15, r15
0x140631bcf  jz      short loc_140631BE2
0x140631bd1  xor     edx, edx; dwFlags
0x140631bd3  mov     rcx, r15; hCertStore
0x140631bd6  call    cs:__imp_CertCloseStore
0x140631bdd  nop     dword ptr [rax+rax+00h]
0x140631be2  test    r12, r12
0x140631be5  jz      short loc_140631BF8
0x140631be7  xor     edx, edx; dwFlags
0x140631be9  mov     rcx, r12; hCertStore
0x140631bec  call    cs:__imp_CertCloseStore
0x140631bf3  nop     dword ptr [rax+rax+00h]
0x140631bf8  lea     rcx, [rbp+57h+var_C0]; this
0x140631bfc  call    ??1VmAccessToken@Vml@@QEAA@XZ; Vml::VmAccessToken::~VmAccessToken(void)
0x140631c01  lea     rcx, [rbp+57h+var_B8]; this
0x140631c05  call    ??1VmAutoLock@Vml@@UEAA@XZ; Vml::VmAutoLock::~VmAutoLock(void)
0x140631c0a  mov     eax, edi
0x140631c0c  mov     rcx, [rbp+57h+var_48]
0x140631c10  xor     rcx, rsp; StackCookie
0x140631c13  call    __security_check_cookie
0x140631c18  add     rsp, 0C8h
0x140631c1f  pop     r15
0x140631c21  pop     r14
0x140631c23  pop     r13
0x140631c25  pop     r12
0x140631c27  pop     rdi
0x140631c28  pop     rsi
0x140631c29  pop     rbx
0x140631c2a  pop     rbp
0x140631c2b  retn
```
