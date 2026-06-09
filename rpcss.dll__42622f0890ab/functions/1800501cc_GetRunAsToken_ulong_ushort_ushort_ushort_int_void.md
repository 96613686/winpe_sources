# GetRunAsToken(ulong,ushort *,ushort *,ushort *,int,void *)

- ea: `0x1800501cc`
- end: `0x1800507b8`
- name: `?GetRunAsToken@@YAPEAXKPEAG00HPEAX@Z`
- size: `1516`
- prototype: `HANDLE __fastcall(int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, PSID pSid)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004cd64`
- `0x18006e800`

## callees

- `0x18000b310`
- `0x18000bbe8`
- `0x180034540`
- `0x1800418c0`
- `0x1800501cc`
- `0x180075e48`
- `0x18007be8c`
- `0x18007e3d4`
- `0x180081210`
- `0x180081398`
- `0x1800b27e0`
- `0x1800e834c`
- `0x1800e84b0`
- `0x1800e8728`
- `0x1800e8e80`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180050706`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x180050706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800502cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800507a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800502cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800507a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800502c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800502c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005029d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005029d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800502ad`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800502ad`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180050713`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180050713`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800506c2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800506c2`
- `KERNELBASE!LocalAlloc` at `0x1800504c8`
- `KERNELBASE!LocalAlloc` at `0x1800504c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800504db`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050613`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050621`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800504db`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050613`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180050621`
- `SspiCli!LogonUserExExW` at `0x180050584`
- `SspiCli!LogonUserExExW` at `0x180050584`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18005046c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18005047c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18005046c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18005047c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x180050412`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x180050412`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180050605`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180050605`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180050383`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180050383`

## string_xrefs

- `0x1800503cc`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18005045b`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x180050765`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x1800503c5`: `GetRunAsToken`
- `0x180050454`: `GetRunAsToken`
- `0x180050759`: `GetRunAsToken`

## pseudocode

```c
HANDLE __fastcall GetRunAsToken(
        int a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        PSID pSid)
{
  void *LogonSid; // rdi
  const unsigned __int16 *v7; // rsi
  const unsigned __int16 *v8; // r14
  DWORD CurrentProcessId; // eax
  HANDLE v11; // rbx
  int v13; // r13d
  unsigned int v14; // r10d
  __int64 v15; // rax
  NTSTATUS v16; // r8d
  NTSTATUS v17; // r8d
  _DWORD *v18; // rax
  void *v19; // rbx
  DWORD v20; // r15d
  PWSTR Buffer; // r8
  DWORD LastError; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  PLSA_UNICODE_STRING v27; // rcx
  __int64 Length; // rdx
  PWSTR v29; // rax
  unsigned int ActivationFailureLoggingLevel; // eax
  int v31; // ebx
  HANDLE *p_hObject; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+38h] [rbp-C8h]
  ULONGLONG RegHandle; // [rsp+60h] [rbp-A0h] BYREF
  PLSA_UNICODE_STRING PrivateData; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+98h] [rbp-68h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v43; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v44[24]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v45[48]; // [rsp+120h] [rbp+20h] BYREF

  LogonSid = 0;
  v40 = a2;
  LODWORD(TokenHandle) = a1;
  PolicyHandle = 0;
  v7 = a4;
  PrivateData = 0;
  hObject = 0;
  v8 = a3;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyName = 0;
  if ( !a2 )
    return 0;
  if ( !gSidService )
    return 0;
  if ( !gSidLocal )
    return 0;
  LODWORD(RegHandle) = 0;
  if ( (int)IsLocalSystemAccount(a3, a4, (int *)&RegHandle) < 0 )
    return 0;
  if ( (_DWORD)RegHandle )
  {
    if ( !a5 )
    {
      TokenHandle = 0;
      CurrentProcessId = GetCurrentProcessId();
      v11 = OpenProcess(0x1FFFFFu, 0, CurrentProcessId);
      OpenProcessToken(v11, 0xF01FFu, &TokenHandle);
      CloseHandle(v11);
      return TokenHandle;
    }
    return 0;
  }
  LODWORD(RegHandle) = 0;
  if ( (int)IsLowPrivilegeServiceAccount(v8, v7, (int *)&RegHandle) < 0 )
    return 0;
  v13 = RegHandle;
  if ( !(_DWORD)RegHandle )
  {
    StringCchCopyW(v45, 0x2Cu, L"SCM:");
    StringCchCatW(v45, v14, a2);
    v15 = -1;
    do
      ++v15;
    while ( v45[v15] );
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    KeyName.Length = 2 * (v15 + 1);
    KeyName.MaximumLength = 88;
    KeyName.Buffer = v45;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = LsaOpenPolicy(0, &ObjectAttributes, 4u, &PolicyHandle);
    if ( v16 < 0 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
          (unsigned int)"GetRunAsToken",
          848,
          0,
          (__int64)L"%!STATUS!",
          v16);
      return 0;
    }
    v17 = LsaRetrievePrivateData(PolicyHandle, &KeyName, &PrivateData);
    if ( v17 < 0 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
          (unsigned int)"GetRunAsToken",
          855,
          0,
          (__int64)L"%!STATUS!",
          v17);
      LsaClose(PolicyHandle);
      return 0;
    }
    LsaClose(PolicyHandle);
    if ( PrivateData )
    {
      PrivateData->Length = PrivateData->MaximumLength - 2;
      goto LABEL_27;
    }
    return 0;
  }
  if ( !pSid )
  {
    v19 = 0;
    goto LABEL_33;
  }
LABEL_27:
  LogonSid = CreateLogonSid();
  if ( !LogonSid )
    return 0;
  v18 = LocalAlloc(0x40u, 16LL * ((unsigned int)(pSid != 0) + 2) + 24);
  v19 = v18;
  if ( !v18 )
  {
    LocalFree(LogonSid);
    return 0;
  }
  *v18 = (pSid != 0) + 3;
  v18[4] = -1073741817;
  *((_QWORD *)v18 + 1) = LogonSid;
  *((_QWORD *)v18 + 3) = gSidLocal;
  v18[8] = 7;
  *((_QWORD *)v18 + 5) = gSidService;
  v18[12] = 7;
  if ( pSid )
  {
    *((_QWORD *)v18 + 7) = pSid;
    v18[16] = 15;
    v18[4] = -1073741809;
  }
LABEL_33:
  v20 = 0;
  if ( PrivateData )
    Buffer = PrivateData->Buffer;
  else
    Buffer = 0;
  HIDWORD(v33) = 0;
  p_hObject = &hObject;
  LODWORD(RegHandle) = LogonUserExExW(v7, v8, Buffer, (unsigned int)(v13 != 0) + 4);
  if ( !(_DWORD)RegHandle )
  {
    LastError = GetLastError();
    v26 = dword_18014E4B8;
    v20 = LastError;
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
      ComTraceMessageT<unsigned short *,unsigned short *,int,unsigned long>(
        v26,
        v23,
        v24,
        v25,
        0,
        (__int64)v8,
        (__int64)v7,
        (v13 != 0) + 4,
        v20);
  }
  v27 = PrivateData;
  if ( PrivateData )
  {
    Length = PrivateData->Length;
    v29 = PrivateData->Buffer;
    if ( PrivateData->Length )
    {
      do
      {
        *(_BYTE *)v29 = 0;
        v29 = (PWSTR)((char *)v29 + 1);
        --Length;
      }
      while ( Length );
      v27 = PrivateData;
    }
    LsaFreeMemory(v27);
  }
  if ( LogonSid )
    LocalFree(LogonSid);
  if ( v19 )
    LocalFree(v19);
  if ( !(_DWORD)RegHandle )
  {
    ActivationFailureLoggingLevel = GetActivationFailureLoggingLevel();
    if ( ActivationFailureLoggingLevel != 2
      && (ActivationFailureLoggingLevel == 1 || ((unsigned __int16)TokenHandle & 0x4000) == 0) )
    {
      RegHandle = 0;
      v42 = 0;
      v43 = 0;
      StringCchPrintfW(v44, 0x14u, L"%lu", v20);
      *(_QWORD *)&v42 = v44;
      if ( !v8 )
        v8 = ResourceStrings::Unavailable();
      *((_QWORD *)&v42 + 1) = v8;
      if ( !v7 )
        v7 = ResourceStrings::Unavailable();
      *((_QWORD *)&v43 + 1) = v40;
      *(_QWORD *)&v43 = v7;
      EventRegister(&S_olemsg_DCOM, 0, 0, &RegHandle);
      if ( !RegHandle
        || (LODWORD(v33) = 0,
            LOWORD(p_hObject) = 4,
            v31 = EvtIntReportEventAndSourceAsync(RegHandle, L"DCOM", 1, 0, 10004, 0, p_hObject, v33, &v42, 0),
            EventUnregister(RegHandle),
            !v31) )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          LODWORD(p_hObject) = GetLastError();
          ComTraceMessageT<unsigned __int64,unsigned long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\security.cxx",
            (unsigned int)"GetRunAsToken",
            1021,
            0,
            (__int64)L"Either log registration or event reporting failed, log handle:0X%I64X, error: 0X%X",
            RegHandle,
            p_hObject);
        }
      }
    }
    return 0;
  }
  if ( !pSid || (int)AdjustRunAsTokenDefaultDacl(hObject, pSid) >= 0 )
    return hObject;
  CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1800501cc  mov     [rsp-8+arg_0], rbx
0x1800501d1  push    rbp
0x1800501d2  push    rsi
0x1800501d3  push    rdi
0x1800501d4  push    r12
0x1800501d6  push    r13
0x1800501d8  push    r14
0x1800501da  push    r15
0x1800501dc  lea     rbp, [rsp-90h]
0x1800501e4  sub     rsp, 190h
0x1800501eb  mov     rax, cs:__security_cookie
0x1800501f2  xor     rax, rsp
0x1800501f5  mov     [rbp+0C0h+var_40], rax
0x1800501fc  mov     r12, [rbp+0C0h+pSid]
0x180050203  xor     edi, edi
0x180050205  xorps   xmm0, xmm0
0x180050208  mov     [rbp+0C0h+var_128], rdx
0x18005020c  mov     rax, r12
0x18005020f  mov     dword ptr [rsp+1C0h+TokenHandle], ecx
0x180050213  neg     rax
0x180050216  mov     [rsp+1C0h+PolicyHandle], rdi
0x18005021b  mov     rsi, r9
0x18005021e  mov     [rsp+1C0h+PrivateData], rdi
0x180050223  sbb     r15d, r15d
0x180050226  mov     [rbp+0C0h+hObject], rdi
0x18005022a  neg     r15d
0x18005022d  mov     r14, r8
0x180050230  add     r15d, 3
0x180050234  mov     rbx, rdx
0x180050237  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x18005023b  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x18005023f  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180050243  movups  xmmword ptr [rbp+0C0h+KeyName.Length], xmm0
0x180050247  test    rdx, rdx
0x18005024a  jz      loc_1800503D8
0x180050250  cmp     cs:?gSidService@@3PEAXEA, rdi; void * gSidService
0x180050257  jz      loc_1800503D8
0x18005025d  cmp     cs:?gSidLocal@@3PEAXEA, rdi; void * gSidLocal
0x180050264  jz      loc_1800503D8
0x18005026a  lea     r8, [rsp+1C0h+RegHandle]; int *
0x18005026f  mov     dword ptr [rsp+1C0h+RegHandle], edi
0x180050273  mov     rdx, r9; unsigned __int16 *
0x180050276  mov     rcx, r14; unsigned __int16 *
0x180050279  call    ?IsLocalSystemAccount@@YAJPEBG0PEAH@Z; IsLocalSystemAccount(ushort const *,ushort const *,int *)
0x18005027e  test    eax, eax
0x180050280  js      loc_1800503D8
0x180050286  cmp     dword ptr [rsp+1C0h+RegHandle], edi
0x18005028a  jz      short loc_1800502DC
0x18005028c  cmp     [rbp+0C0h+arg_20], edi
0x180050292  jnz     loc_1800503D8
0x180050298  mov     [rsp+1C0h+TokenHandle], rdi
0x18005029d  call    cs:__imp_GetCurrentProcessId
0x1800502a3  xor     edx, edx; bInheritHandle
0x1800502a5  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800502aa  mov     r8d, eax; dwProcessId
0x1800502ad  call    cs:__imp_OpenProcess
0x1800502b3  lea     r8, [rsp+1C0h+TokenHandle]; TokenHandle
0x1800502b8  mov     edx, 0F01FFh; DesiredAccess
0x1800502bd  mov     rcx, rax; ProcessHandle
0x1800502c0  mov     rbx, rax
0x1800502c3  call    cs:__imp_OpenProcessToken
0x1800502c9  mov     rcx, rbx; hObject
0x1800502cc  call    cs:__imp_CloseHandle
0x1800502d2  mov     rax, [rsp+1C0h+TokenHandle]
0x1800502d7  jmp     loc_1800503DA
0x1800502dc  lea     r8, [rsp+1C0h+RegHandle]; int *
0x1800502e1  mov     dword ptr [rsp+1C0h+RegHandle], edi
0x1800502e5  mov     rdx, rsi; unsigned __int16 *
0x1800502e8  mov     rcx, r14; unsigned __int16 *
0x1800502eb  call    ?IsLowPrivilegeServiceAccount@@YAJPEBG0PEAH@Z; IsLowPrivilegeServiceAccount(ushort const *,ushort const *,int *)
0x1800502f0  test    eax, eax
0x1800502f2  js      loc_1800503D8
0x1800502f8  mov     r13d, dword ptr [rsp+1C0h+RegHandle]
0x1800502fd  test    r13d, r13d
0x180050300  jnz     loc_18005049D
0x180050306  lea     r10d, [r13+2Ch]
0x18005030a  mov     edx, r10d; unsigned __int64
0x18005030d  lea     r8, aScm; "SCM:"
0x180050314  lea     rcx, [rbp+0C0h+var_A0]; unsigned __int16 *
0x180050318  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005031d  mov     r8, rbx; unsigned __int16 *
0x180050320  lea     rcx, [rbp+0C0h+var_A0]; unsigned __int16 *
0x180050324  mov     edx, r10d; unsigned __int64
0x180050327  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005032c  lea     rcx, [rbp+0C0h+var_A0]
0x180050330  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050334  inc     rax
0x180050337  cmp     [rcx+rax*2], di
0x18005033b  jnz     short loc_180050334
0x18005033d  inc     ax
0x180050340  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x180050347  add     ax, ax
0x18005034a  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], rdi
0x18005034e  mov     [rbp+0C0h+KeyName.Length], ax
0x180050352  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180050357  mov     eax, 58h ; 'X'
0x18005035c  mov     [rbp+0C0h+ObjectAttributes.Attributes], edi
0x18005035f  mov     [rbp+0C0h+KeyName.MaximumLength], ax
0x180050363  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x180050367  lea     rax, [rbp+0C0h+var_A0]
0x18005036b  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rdi
0x18005036f  xorps   xmm0, xmm0
0x180050372  mov     [rbp+0C0h+KeyName.Buffer], rax
0x180050376  mov     r8d, 4; DesiredAccess
0x18005037c  xor     ecx, ecx; SystemName
0x18005037e  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180050383  call    cs:__imp_LsaOpenPolicy
0x180050389  mov     r8d, eax
0x18005038c  test    eax, eax
0x18005038e  jns     short loc_180050404
0x180050390  mov     ecx, cs:dword_18014E4B8
0x180050396  test    ecx, ecx
0x180050398  jnz     short loc_1800503AB
0x18005039a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800503a0  jz      short loc_1800503D8
0x1800503a2  call    IsWppLevelEnabled
0x1800503a7  test    al, al
0x1800503a9  jz      short loc_1800503D8
0x1800503ab  mov     dword ptr [rsp+1C0h+var_198], r8d
0x1800503b0  lea     rax, aStatus; "%!STATUS!"
0x1800503b7  mov     r8d, 350h
0x1800503bd  mov     [rsp+1C0h+var_1A0], rax
0x1800503c2  xor     r9d, r9d
0x1800503c5  lea     rdx, aGetrunastoken; "GetRunAsToken"
0x1800503cc  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800503d3  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800503d8  xor     eax, eax
0x1800503da  mov     rcx, [rbp+0C0h+var_40]
0x1800503e1  xor     rcx, rsp; StackCookie
0x1800503e4  call    __security_check_cookie
0x1800503e9  mov     rbx, [rsp+1C0h+arg_0]
0x1800503f1  add     rsp, 190h
0x1800503f8  pop     r15
0x1800503fa  pop     r14
0x1800503fc  pop     r13
0x1800503fe  pop     r12
0x180050400  pop     rdi
0x180050401  pop     rsi
0x180050402  pop     rbp
0x180050403  retn
0x180050404  mov     rcx, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x180050409  lea     r8, [rsp+1C0h+PrivateData]; PrivateData
0x18005040e  lea     rdx, [rbp+0C0h+KeyName]; KeyName
0x180050412  call    cs:__imp_LsaRetrievePrivateData
0x180050418  mov     r8d, eax
0x18005041b  test    eax, eax
0x18005041d  jns     short loc_180050477
0x18005041f  mov     ecx, cs:dword_18014E4B8
0x180050425  test    ecx, ecx
0x180050427  jnz     short loc_18005043A
0x180050429  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18005042f  jz      short loc_180050467
0x180050431  call    IsWppLevelEnabled
0x180050436  test    al, al
0x180050438  jz      short loc_180050467
0x18005043a  mov     dword ptr [rsp+1C0h+var_198], r8d
0x18005043f  lea     rax, aStatus; "%!STATUS!"
0x180050446  mov     r8d, 357h
0x18005044c  mov     [rsp+1C0h+var_1A0], rax
0x180050451  xor     r9d, r9d
0x180050454  lea     rdx, aGetrunastoken; "GetRunAsToken"
0x18005045b  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180050462  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180050467  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x18005046c  call    cs:__imp_LsaClose
0x180050472  jmp     loc_1800503D8
0x180050477  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x18005047c  call    cs:__imp_LsaClose
0x180050482  mov     rcx, [rsp+1C0h+PrivateData]
0x180050487  test    rcx, rcx
0x18005048a  jz      loc_1800503D8
0x180050490  movzx   eax, word ptr [rcx+2]
0x180050494  sub     ax, 2
0x180050498  mov     [rcx], ax
0x18005049b  jmp     short loc_1800504A6
0x18005049d  test    r12, r12
0x1800504a0  jz      loc_18005052E
0x1800504a6  call    ?CreateLogonSid@@YAPEAXXZ; CreateLogonSid(void)
0x1800504ab  mov     rdi, rax
0x1800504ae  test    rax, rax
0x1800504b1  jz      loc_1800503D8
0x1800504b7  lea     edx, [r15-1]
0x1800504bb  mov     ecx, 40h ; '@'; uFlags
0x1800504c0  shl     rdx, 4
0x1800504c4  add     rdx, 18h; uBytes
0x1800504c8  call    cs:__imp_LocalAlloc
0x1800504ce  xor     edx, edx
0x1800504d0  mov     rbx, rax
0x1800504d3  test    rax, rax
0x1800504d6  jnz     short loc_1800504E6
0x1800504d8  mov     rcx, rdi; hMem
0x1800504db  call    cs:__imp_LocalFree
0x1800504e1  jmp     loc_1800503D8
0x1800504e6  mov     [rax], r15d
0x1800504e9  mov     ecx, 7
0x1800504ee  mov     dword ptr [rax+10h], 0C0000007h
0x1800504f5  mov     [rax+8], rdi
0x1800504f9  mov     rax, cs:?gSidLocal@@3PEAXEA; void * gSidLocal
0x180050500  mov     [rbx+18h], rax
0x180050504  mov     [rbx+20h], ecx
0x180050507  mov     rax, cs:?gSidService@@3PEAXEA; void * gSidService
0x18005050e  mov     [rbx+28h], rax
0x180050512  mov     [rbx+30h], ecx
0x180050515  test    r12, r12
0x180050518  jz      short loc_180050533
0x18005051a  mov     [rbx+38h], r12
0x18005051e  mov     dword ptr [rbx+40h], 0Fh
0x180050525  mov     dword ptr [rbx+10h], 0C000000Fh
0x18005052c  jmp     short loc_180050533
0x18005052e  mov     rbx, rdi
0x180050531  xor     edx, edx
0x180050533  mov     eax, r13d
0x180050536  mov     r15d, edx
0x180050539  neg     eax
0x18005053b  mov     rax, [rsp+1C0h+PrivateData]
0x180050540  sbb     r9d, r9d
0x180050543  neg     r9d
0x180050546  add     r9d, 4
0x18005054a  test    rax, rax
0x18005054d  jz      short loc_180050555
0x18005054f  mov     r8, [rax+8]
0x180050553  jmp     short loc_180050558
0x180050555  mov     r8, rdx
0x180050558  mov     [rsp+1C0h+var_170], rdx
0x18005055d  lea     rax, [rbp+0C0h+hObject]
0x180050561  mov     [rsp+1C0h+var_178], rdx
0x180050566  mov     rcx, rsi
0x180050569  mov     [rsp+1C0h+var_180], rdx
0x18005056e  mov     [rsp+1C0h+var_188], rdx
0x180050573  mov     [rsp+1C0h+var_190], rax
0x180050578  mov     [rsp+1C0h+var_198], rbx
0x18005057d  mov     dword ptr [rsp+1C0h+var_1A0], edx
0x180050581  mov     rdx, r14
0x180050584  call    cs:__imp_LogonUserExExW
0x18005058a  mov     dword ptr [rsp+1C0h+RegHandle], eax
0x18005058e  test    eax, eax
0x180050590  jnz     short loc_1800505D8
0x180050592  call    cs:__imp_GetLastError
0x180050598  mov     ecx, cs:dword_18014E4B8
0x18005059e  mov     r15d, eax
0x1800505a1  test    ecx, ecx
0x1800505a3  jnz     short loc_1800505B6
0x1800505a5  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800505ab  jz      short loc_1800505D8
0x1800505ad  call    IsWppLevelEnabled
0x1800505b2  test    al, al
0x1800505b4  jz      short loc_1800505D8
0x1800505b6  mov     dword ptr [rsp+1C0h+var_180], r15d
0x1800505bb  neg     r13d
0x1800505be  sbb     eax, eax
0x1800505c0  neg     eax
0x1800505c2  add     eax, 4
0x1800505c5  mov     dword ptr [rsp+1C0h+var_188], eax
0x1800505c9  mov     [rsp+1C0h+var_190], rsi
0x1800505ce  mov     [rsp+1C0h+var_198], r14
0x1800505d3  call    ??$ComTraceMessageT@PEAGPEAGHK@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3HK@Z; ComTraceMessageT<ushort *,ushort *,int,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,int,ulong)
0x1800505d8  mov     rcx, [rsp+1C0h+PrivateData]
0x1800505dd  xor     r13d, r13d
0x1800505e0  test    rcx, rcx
0x1800505e3  jz      short loc_18005060B
0x1800505e5  movzx   edx, word ptr [rcx]
0x1800505e8  mov     rax, [rcx+8]
0x1800505ec  test    rdx, rdx
0x1800505ef  jz      short loc_180050605
0x1800505f1  lea     ecx, [r13+1]
0x1800505f5  mov     [rax], r13b
0x1800505f8  add     rax, rcx
0x1800505fb  sub     rdx, rcx
0x1800505fe  jnz     short loc_1800505F5
0x180050600  mov     rcx, [rsp+1C0h+PrivateData]; Buffer
0x180050605  call    cs:__imp_LsaFreeMemory
0x18005060b  test    rdi, rdi
0x18005060e  jz      short loc_180050619
0x180050610  mov     rcx, rdi; hMem
0x180050613  call    cs:__imp_LocalFree
0x180050619  test    rbx, rbx
0x18005061c  jz      short loc_180050627
0x18005061e  mov     rcx, rbx; hMem
0x180050621  call    cs:__imp_LocalFree
0x180050627  cmp     dword ptr [rsp+1C0h+RegHandle], r13d
0x18005062c  jnz     loc_180050788
0x180050632  call    ?GetActivationFailureLoggingLevel@@YAKXZ; GetActivationFailureLoggingLevel(void)
0x180050637  cmp     eax, 2
0x18005063a  jz      loc_1800503D8
0x180050640  mov     ebx, 1
0x180050645  cmp     eax, ebx
0x180050647  jz      short loc_180050657
0x180050649  test    dword ptr [rsp+1C0h+TokenHandle], 4000h
0x180050651  jnz     loc_1800503D8
0x180050657  xorps   xmm0, xmm0
0x18005065a  mov     [rsp+1C0h+RegHandle], r13
0x18005065f  mov     r9d, r15d
0x180050662  lea     r8, aLu; "%lu"
0x180050669  mov     edx, 14h; unsigned __int64
0x18005066e  lea     rcx, [rbp+0C0h+var_D0]; unsigned __int16 *
0x180050672  movups  [rbp+0C0h+var_F0], xmm0
0x180050676  movups  [rbp+0C0h+var_E0], xmm0
0x18005067a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005067f  lea     rax, [rbp+0C0h+var_D0]
0x180050683  mov     qword ptr [rbp+0C0h+var_F0], rax
  ... truncated ...
```
