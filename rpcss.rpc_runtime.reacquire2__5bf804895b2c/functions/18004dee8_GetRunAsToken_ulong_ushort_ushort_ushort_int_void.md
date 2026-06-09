# GetRunAsToken(ulong,ushort *,ushort *,ushort *,int,void *)

- ea: `0x18004dee8`
- end: `0x18004e54d`
- name: `?GetRunAsToken@@YAPEAXKPEAG00HPEAX@Z`
- size: `1637`
- prototype: `void *(unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e578`
- `0x180073020`

## callees

- `0x18001037c`
- `0x180011db0`
- `0x180034260`
- `0x18004b524`
- `0x18004dee8`
- `0x18007a604`
- `0x180080864`
- `0x18008172c`
- `0x1800855d8`
- `0x1800857e0`
- `0x1800b7ac0`
- `0x1800efa0c`
- `0x1800efb88`
- `0x1800efe5c`
- `0x1800f061c`

## import_xrefs

- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18004e483`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x18004e483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e4d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004dffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e530`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004dfeb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004dfeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004dfb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004dfb9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004dfcf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004dfcf`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18004e496`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18004e496`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18004e439`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18004e439`
- `KERNELBASE!LocalAlloc` at `0x18004e215`
- `KERNELBASE!LocalAlloc` at `0x18004e215`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e22e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e37e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e392`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e22e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e37e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18004e392`
- `SspiCli!LogonUserExExW` at `0x18004e2dd`
- `SspiCli!LogonUserExExW` at `0x18004e2dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004e1ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004e1c3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004e1ad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18004e1c3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18004e14d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18004e14d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004e36a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18004e36a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004e0b7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18004e0b7`

## string_xrefs

- `0x18004e106`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004e19c`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004e4f4`: `onecore\com\combase\rpcss\olescm\security.cxx`
- `0x18004e0ff`: `GetRunAsToken`
- `0x18004e195`: `GetRunAsToken`
- `0x18004e4e8`: `GetRunAsToken`

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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
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
    v26 = dword_1801574B8;
    v20 = LastError;
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x18004dee8  mov     [rsp-8+arg_0], rbx
0x18004deed  push    rbp
0x18004deee  push    rsi
0x18004deef  push    rdi
0x18004def0  push    r12
0x18004def2  push    r13
0x18004def4  push    r14
0x18004def6  push    r15
0x18004def8  lea     rbp, [rsp-90h]
0x18004df00  sub     rsp, 190h
0x18004df07  mov     rax, cs:__security_cookie
0x18004df0e  xor     rax, rsp
0x18004df11  mov     [rbp+0C0h+var_40], rax
0x18004df18  mov     r12, [rbp+0C0h+pSid]
0x18004df1f  xor     edi, edi
0x18004df21  xorps   xmm0, xmm0
0x18004df24  mov     [rbp+0C0h+var_128], rdx
0x18004df28  mov     rax, r12
0x18004df2b  mov     dword ptr [rsp+1C0h+TokenHandle], ecx
0x18004df2f  neg     rax
0x18004df32  mov     [rsp+1C0h+PolicyHandle], rdi
0x18004df37  mov     rsi, r9
0x18004df3a  mov     [rsp+1C0h+PrivateData], rdi
0x18004df3f  sbb     r15d, r15d
0x18004df42  mov     [rbp+0C0h+hObject], rdi
0x18004df46  neg     r15d
0x18004df49  mov     r14, r8
0x18004df4c  add     r15d, 3
0x18004df50  mov     rbx, rdx
0x18004df53  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm0
0x18004df57  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm0
0x18004df5b  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004df5f  movups  xmmword ptr [rbp+0C0h+KeyName.Length], xmm0
0x18004df63  test    rdx, rdx
0x18004df66  jz      loc_18004E112
0x18004df6c  cmp     cs:?gSidService@@3PEAXEA, rdi; void * gSidService
0x18004df73  jz      loc_18004E112
0x18004df79  cmp     cs:?gSidLocal@@3PEAXEA, rdi; void * gSidLocal
0x18004df80  jz      loc_18004E112
0x18004df86  lea     r8, [rsp+1C0h+RegHandle]; int *
0x18004df8b  mov     dword ptr [rsp+1C0h+RegHandle], edi
0x18004df8f  mov     rdx, r9; unsigned __int16 *
0x18004df92  mov     rcx, r14; unsigned __int16 *
0x18004df95  call    ?IsLocalSystemAccount@@YAJPEBG0PEAH@Z; IsLocalSystemAccount(ushort const *,ushort const *,int *)
0x18004df9a  test    eax, eax
0x18004df9c  js      loc_18004E112
0x18004dfa2  cmp     dword ptr [rsp+1C0h+RegHandle], edi
0x18004dfa6  jz      short loc_18004E010
0x18004dfa8  cmp     [rbp+0C0h+arg_20], edi
0x18004dfae  jnz     loc_18004E112
0x18004dfb4  mov     [rsp+1C0h+TokenHandle], rdi
0x18004dfb9  call    cs:__imp_GetCurrentProcessId
0x18004dfc0  nop     dword ptr [rax+rax+00h]
0x18004dfc5  xor     edx, edx; bInheritHandle
0x18004dfc7  mov     ecx, 1FFFFFh; dwDesiredAccess
0x18004dfcc  mov     r8d, eax; dwProcessId
0x18004dfcf  call    cs:__imp_OpenProcess
0x18004dfd6  nop     dword ptr [rax+rax+00h]
0x18004dfdb  lea     r8, [rsp+1C0h+TokenHandle]; TokenHandle
0x18004dfe0  mov     edx, 0F01FFh; DesiredAccess
0x18004dfe5  mov     rcx, rax; ProcessHandle
0x18004dfe8  mov     rbx, rax
0x18004dfeb  call    cs:__imp_OpenProcessToken
0x18004dff2  nop     dword ptr [rax+rax+00h]
0x18004dff7  mov     rcx, rbx; hObject
0x18004dffa  call    cs:__imp_CloseHandle
0x18004e001  nop     dword ptr [rax+rax+00h]
0x18004e006  mov     rax, [rsp+1C0h+TokenHandle]
0x18004e00b  jmp     loc_18004E114
0x18004e010  lea     r8, [rsp+1C0h+RegHandle]; int *
0x18004e015  mov     dword ptr [rsp+1C0h+RegHandle], edi
0x18004e019  mov     rdx, rsi; unsigned __int16 *
0x18004e01c  mov     rcx, r14; unsigned __int16 *
0x18004e01f  call    ?IsLowPrivilegeServiceAccount@@YAJPEBG0PEAH@Z; IsLowPrivilegeServiceAccount(ushort const *,ushort const *,int *)
0x18004e024  test    eax, eax
0x18004e026  js      loc_18004E112
0x18004e02c  mov     r13d, dword ptr [rsp+1C0h+RegHandle]
0x18004e031  test    r13d, r13d
0x18004e034  jnz     loc_18004E1EA
0x18004e03a  lea     r10d, [r13+2Ch]
0x18004e03e  mov     edx, r10d; unsigned __int64
0x18004e041  lea     r8, aScm; "SCM:"
0x18004e048  lea     rcx, [rbp+0C0h+var_A0]; unsigned __int16 *
0x18004e04c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004e051  mov     r8, rbx; unsigned __int16 *
0x18004e054  lea     rcx, [rbp+0C0h+var_A0]; unsigned __int16 *
0x18004e058  mov     edx, r10d; unsigned __int64
0x18004e05b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e060  lea     rcx, [rbp+0C0h+var_A0]
0x18004e064  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e068  inc     rax
0x18004e06b  cmp     [rcx+rax*2], di
0x18004e06f  jnz     short loc_18004E068
0x18004e071  inc     ax
0x18004e074  mov     [rbp+0C0h+ObjectAttributes.Length], 30h ; '0'
0x18004e07b  add     ax, ax
0x18004e07e  mov     [rbp+0C0h+ObjectAttributes.RootDirectory], rdi
0x18004e082  mov     [rbp+0C0h+KeyName.Length], ax
0x18004e086  lea     r9, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x18004e08b  mov     eax, 58h ; 'X'
0x18004e090  mov     [rbp+0C0h+ObjectAttributes.Attributes], edi
0x18004e093  mov     [rbp+0C0h+KeyName.MaximumLength], ax
0x18004e097  lea     rdx, [rbp+0C0h+ObjectAttributes]; ObjectAttributes
0x18004e09b  lea     rax, [rbp+0C0h+var_A0]
0x18004e09f  mov     [rbp+0C0h+ObjectAttributes.ObjectName], rdi
0x18004e0a3  xorps   xmm0, xmm0
0x18004e0a6  mov     [rbp+0C0h+KeyName.Buffer], rax
0x18004e0aa  mov     r8d, 4; DesiredAccess
0x18004e0b0  xor     ecx, ecx; SystemName
0x18004e0b2  movdqu  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004e0b7  call    cs:__imp_LsaOpenPolicy
0x18004e0be  nop     dword ptr [rax+rax+00h]
0x18004e0c3  mov     r8d, eax
0x18004e0c6  test    eax, eax
0x18004e0c8  jns     short loc_18004E13F
0x18004e0ca  mov     ecx, cs:dword_1801574B8
0x18004e0d0  test    ecx, ecx
0x18004e0d2  jnz     short loc_18004E0E5
0x18004e0d4  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18004e0da  jz      short loc_18004E112
0x18004e0dc  call    IsWppLevelEnabled
0x18004e0e1  test    al, al
0x18004e0e3  jz      short loc_18004E112
0x18004e0e5  mov     dword ptr [rsp+1C0h+var_198], r8d
0x18004e0ea  lea     rax, aStatus; "%!STATUS!"
0x18004e0f1  mov     r8d, 350h
0x18004e0f7  mov     [rsp+1C0h+var_1A0], rax
0x18004e0fc  xor     r9d, r9d
0x18004e0ff  lea     rdx, aGetrunastoken; "GetRunAsToken"
0x18004e106  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004e10d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18004e112  xor     eax, eax
0x18004e114  mov     rcx, [rbp+0C0h+var_40]
0x18004e11b  xor     rcx, rsp; StackCookie
0x18004e11e  call    __security_check_cookie
0x18004e123  mov     rbx, [rsp+1C0h+arg_0]
0x18004e12b  add     rsp, 190h
0x18004e132  pop     r15
0x18004e134  pop     r14
0x18004e136  pop     r13
0x18004e138  pop     r12
0x18004e13a  pop     rdi
0x18004e13b  pop     rsi
0x18004e13c  pop     rbp
0x18004e13d  retn
0x18004e13f  mov     rcx, [rsp+1C0h+PolicyHandle]; PolicyHandle
0x18004e144  lea     r8, [rsp+1C0h+PrivateData]; PrivateData
0x18004e149  lea     rdx, [rbp+0C0h+KeyName]; KeyName
0x18004e14d  call    cs:__imp_LsaRetrievePrivateData
0x18004e154  nop     dword ptr [rax+rax+00h]
0x18004e159  mov     r8d, eax
0x18004e15c  test    eax, eax
0x18004e15e  jns     short loc_18004E1BE
0x18004e160  mov     ecx, cs:dword_1801574B8
0x18004e166  test    ecx, ecx
0x18004e168  jnz     short loc_18004E17B
0x18004e16a  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18004e170  jz      short loc_18004E1A8
0x18004e172  call    IsWppLevelEnabled
0x18004e177  test    al, al
0x18004e179  jz      short loc_18004E1A8
0x18004e17b  mov     dword ptr [rsp+1C0h+var_198], r8d
0x18004e180  lea     rax, aStatus; "%!STATUS!"
0x18004e187  mov     r8d, 357h
0x18004e18d  mov     [rsp+1C0h+var_1A0], rax
0x18004e192  xor     r9d, r9d
0x18004e195  lea     rdx, aGetrunastoken; "GetRunAsToken"
0x18004e19c  lea     rcx, aOnecoreComComb_86; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18004e1a3  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18004e1a8  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x18004e1ad  call    cs:__imp_LsaClose
0x18004e1b4  nop     dword ptr [rax+rax+00h]
0x18004e1b9  jmp     loc_18004E112
0x18004e1be  mov     rcx, [rsp+1C0h+PolicyHandle]; ObjectHandle
0x18004e1c3  call    cs:__imp_LsaClose
0x18004e1ca  nop     dword ptr [rax+rax+00h]
0x18004e1cf  mov     rcx, [rsp+1C0h+PrivateData]
0x18004e1d4  test    rcx, rcx
0x18004e1d7  jz      loc_18004E112
0x18004e1dd  movzx   eax, word ptr [rcx+2]
0x18004e1e1  sub     ax, 2
0x18004e1e5  mov     [rcx], ax
0x18004e1e8  jmp     short loc_18004E1F3
0x18004e1ea  test    r12, r12
0x18004e1ed  jz      loc_18004E287
0x18004e1f3  call    ?CreateLogonSid@@YAPEAXXZ; CreateLogonSid(void)
0x18004e1f8  mov     rdi, rax
0x18004e1fb  test    rax, rax
0x18004e1fe  jz      loc_18004E112
0x18004e204  lea     edx, [r15-1]
0x18004e208  mov     ecx, 40h ; '@'; uFlags
0x18004e20d  shl     rdx, 4
0x18004e211  add     rdx, 18h; uBytes
0x18004e215  call    cs:__imp_LocalAlloc
0x18004e21c  nop     dword ptr [rax+rax+00h]
0x18004e221  xor     edx, edx
0x18004e223  mov     rbx, rax
0x18004e226  test    rax, rax
0x18004e229  jnz     short loc_18004E23F
0x18004e22b  mov     rcx, rdi; hMem
0x18004e22e  call    cs:__imp_LocalFree
0x18004e235  nop     dword ptr [rax+rax+00h]
0x18004e23a  jmp     loc_18004E112
0x18004e23f  mov     [rax], r15d
0x18004e242  mov     ecx, 7
0x18004e247  mov     dword ptr [rax+10h], 0C0000007h
0x18004e24e  mov     [rax+8], rdi
0x18004e252  mov     rax, cs:?gSidLocal@@3PEAXEA; void * gSidLocal
0x18004e259  mov     [rbx+18h], rax
0x18004e25d  mov     [rbx+20h], ecx
0x18004e260  mov     rax, cs:?gSidService@@3PEAXEA; void * gSidService
0x18004e267  mov     [rbx+28h], rax
0x18004e26b  mov     [rbx+30h], ecx
0x18004e26e  test    r12, r12
0x18004e271  jz      short loc_18004E28C
0x18004e273  mov     [rbx+38h], r12
0x18004e277  mov     dword ptr [rbx+40h], 0Fh
0x18004e27e  mov     dword ptr [rbx+10h], 0C000000Fh
0x18004e285  jmp     short loc_18004E28C
0x18004e287  mov     rbx, rdi
0x18004e28a  xor     edx, edx
0x18004e28c  mov     eax, r13d
0x18004e28f  mov     r15d, edx
0x18004e292  neg     eax
0x18004e294  mov     rax, [rsp+1C0h+PrivateData]
0x18004e299  sbb     r9d, r9d
0x18004e29c  neg     r9d
0x18004e29f  add     r9d, 4
0x18004e2a3  test    rax, rax
0x18004e2a6  jz      short loc_18004E2AE
0x18004e2a8  mov     r8, [rax+8]
0x18004e2ac  jmp     short loc_18004E2B1
0x18004e2ae  mov     r8, rdx
0x18004e2b1  mov     [rsp+1C0h+var_170], rdx
0x18004e2b6  lea     rax, [rbp+0C0h+hObject]
0x18004e2ba  mov     [rsp+1C0h+var_178], rdx
0x18004e2bf  mov     rcx, rsi
0x18004e2c2  mov     [rsp+1C0h+var_180], rdx
0x18004e2c7  mov     [rsp+1C0h+var_188], rdx
0x18004e2cc  mov     [rsp+1C0h+var_190], rax
0x18004e2d1  mov     [rsp+1C0h+var_198], rbx
0x18004e2d6  mov     dword ptr [rsp+1C0h+var_1A0], edx
0x18004e2da  mov     rdx, r14
0x18004e2dd  call    cs:__imp_LogonUserExExW
0x18004e2e4  nop     dword ptr [rax+rax+00h]
0x18004e2e9  mov     dword ptr [rsp+1C0h+RegHandle], eax
0x18004e2ed  test    eax, eax
0x18004e2ef  jnz     short loc_18004E33D
0x18004e2f1  call    cs:__imp_GetLastError
0x18004e2f8  nop     dword ptr [rax+rax+00h]
0x18004e2fd  mov     ecx, cs:dword_1801574B8
0x18004e303  mov     r15d, eax
0x18004e306  test    ecx, ecx
0x18004e308  jnz     short loc_18004E31B
0x18004e30a  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18004e310  jz      short loc_18004E33D
0x18004e312  call    IsWppLevelEnabled
0x18004e317  test    al, al
0x18004e319  jz      short loc_18004E33D
0x18004e31b  mov     dword ptr [rsp+1C0h+var_180], r15d
0x18004e320  neg     r13d
0x18004e323  sbb     eax, eax
0x18004e325  neg     eax
0x18004e327  add     eax, 4
0x18004e32a  mov     dword ptr [rsp+1C0h+var_188], eax
0x18004e32e  mov     [rsp+1C0h+var_190], rsi
0x18004e333  mov     [rsp+1C0h+var_198], r14
0x18004e338  call    ??$ComTraceMessageT@PEAGPEAGHK@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3HK@Z; ComTraceMessageT<ushort *,ushort *,int,ulong>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,int,ulong)
0x18004e33d  mov     rcx, [rsp+1C0h+PrivateData]
0x18004e342  xor     r13d, r13d
0x18004e345  test    rcx, rcx
0x18004e348  jz      short loc_18004E376
0x18004e34a  movzx   edx, word ptr [rcx]
0x18004e34d  mov     rax, [rcx+8]
0x18004e351  test    rdx, rdx
0x18004e354  jz      short loc_18004E36A
0x18004e356  lea     ecx, [r13+1]
0x18004e35a  mov     [rax], r13b
0x18004e35d  add     rax, rcx
0x18004e360  sub     rdx, rcx
0x18004e363  jnz     short loc_18004E35A
0x18004e365  mov     rcx, [rsp+1C0h+PrivateData]; Buffer
0x18004e36a  call    cs:__imp_LsaFreeMemory
0x18004e371  nop     dword ptr [rax+rax+00h]
0x18004e376  test    rdi, rdi
0x18004e379  jz      short loc_18004E38A
0x18004e37b  mov     rcx, rdi; hMem
0x18004e37e  call    cs:__imp_LocalFree
0x18004e385  nop     dword ptr [rax+rax+00h]
0x18004e38a  test    rbx, rbx
0x18004e38d  jz      short loc_18004E39E
0x18004e38f  mov     rcx, rbx; hMem
0x18004e392  call    cs:__imp_LocalFree
0x18004e399  nop     dword ptr [rax+rax+00h]
0x18004e39e  cmp     dword ptr [rsp+1C0h+RegHandle], r13d
0x18004e3a3  jnz     loc_18004E517
0x18004e3a9  call    ?GetActivationFailureLoggingLevel@@YAKXZ; GetActivationFailureLoggingLevel(void)
0x18004e3ae  cmp     eax, 2
0x18004e3b1  jz      loc_18004E112
0x18004e3b7  mov     ebx, 1
  ... truncated ...
```
