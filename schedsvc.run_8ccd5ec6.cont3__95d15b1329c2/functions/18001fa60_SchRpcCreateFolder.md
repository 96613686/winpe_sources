# _SchRpcCreateFolder

- ea: `0x18001fa60`
- end: `0x18001fe06`
- name: `_SchRpcCreateFolder`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001fa60`
- `0x18001fe10`
- `0x18001fe44`
- `0x180020110`
- `0x180020350`
- `0x1800204e0`
- `0x180021418`
- `0x180024730`
- `0x18002f814`
- `0x180042200`
- `0x18004f898`
- `0x18005a2bc`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fc04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fc04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fca7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fdb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fca7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fdb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fb7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fb7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fb9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fb9c`
- `RPCRT4!RpcImpersonateClient` at `0x18001fb07`
- `RPCRT4!RpcImpersonateClient` at `0x18001fb07`
- `RPCRT4!RpcRevertToSelf` at `0x18001fbc7`
- `RPCRT4!RpcRevertToSelf` at `0x18001fbe6`
- `RPCRT4!RpcRevertToSelf` at `0x18001fd6e`
- `RPCRT4!RpcRevertToSelf` at `0x18001fd91`
- `RPCRT4!RpcRevertToSelf` at `0x18001fbc7`
- `RPCRT4!RpcRevertToSelf` at `0x18001fbe6`
- `RPCRT4!RpcRevertToSelf` at `0x18001fd6e`
- `RPCRT4!RpcRevertToSelf` at `0x18001fd91`

## string_xrefs

- `0x18001fb1c`: `CreateFolder`
- `0x18001fd3c`: `RpcServer::CreateFolder`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SchRpcCreateFolder(__int64 a1, unsigned __int16 *a2, const WCHAR *a3, int a4)
{
  const unsigned __int16 *v6; // r8
  int v7; // ebx
  RPC_STATUS v8; // eax
  EventManager *v9; // rcx
  RPC_STATUS v10; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  tsched *v13; // rcx
  int v14; // r8d
  char *v15; // r9
  JobStore *v16; // rdi
  RpcServer *v17; // rcx
  int *NewDescriptor; // [rsp+28h] [rbp-2B0h]
  char v20[32]; // [rsp+0h] [rbp-2D8h] BYREF
  HANDLE v21; // [rsp+20h] [rbp-2B8h]
  PSECURITY_DESCRIPTOR *NewDescriptora; // [rsp+28h] [rbp-2B0h]
  void *TokenHandle; // [rsp+30h] [rbp-2A8h] BYREF
  int v24; // [rsp+38h] [rbp-2A0h] BYREF
  int v25; // [rsp+3Ch] [rbp-29Ch] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp-298h] BYREF
  int v27; // [rsp+48h] [rbp-290h]
  PSECURITY_DESCRIPTOR v28; // [rsp+50h] [rbp-288h] BYREF
  int v29; // [rsp+58h] [rbp-280h]
  void **pExceptionObject; // [rsp+60h] [rbp-278h] BYREF
  char v31; // [rsp+68h] [rbp-270h]
  const unsigned __int16 *v32; // [rsp+70h] [rbp-268h]
  __int64 v33; // [rsp+78h] [rbp-260h]
  __int64 v34; // [rsp+80h] [rbp-258h]
  RPC_STATUS v35; // [rsp+88h] [rbp-250h]
  __int64 v36; // [rsp+8Ch] [rbp-24Ch]
  RTL_SRWLOCK *v37; // [rsp+98h] [rbp-240h]
  unsigned __int16 v38; // [rsp+A0h] [rbp-238h] BYREF
  __int16 v39[263]; // [rsp+A2h] [rbp-236h] BYREF

  v24 = 0;
  if ( !a2 || a4 )
    goto LABEL_7;
  v38 = 0;
  memset_0(v39, 0, 0x208u);
  v7 = tsched::TaskPathCanonicalize((tsched *)&v38, a2, v6);
  if ( v7 >= 0 )
  {
    if ( !v38 || !v39[0] && v38 == 92 )
    {
LABEL_7:
      v7 = -2147024809;
      goto LABEL_8;
    }
    TokenHandle = 0;
    v8 = RpcImpersonateClient(0);
    try
    {
      v10 = v8;
      if ( v8 )
      {
        EventManager::EvtReport(
          v9,
          &IMPERSONATION_FAILURE,
          L"CreateFolder",
          v8,
          v21,
          (const struct _GUID *)NewDescriptora);
        v31 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v32 = &qword_1800A8718;
        v33 = 0;
        v34 = 0;
        v35 = v10;
        v36 = -1;
        throw (wmi::GenericException *)&pExceptionObject;
      }
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        RpcRevertToSelf();
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        RpcRevertToSelf();
        if ( v7 < 0 )
        {
          wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
          goto LABEL_8;
        }
      }
      v37 = &SRWLock;
      AcquireSRWLockExclusive(&SRWLock);
      v16 = JobStore::m_pCommonStore;
      pSecurityDescriptor = 0;
      v27 = 0;
      v7 = RpcServer::CreateRegistrationPath(v17, &v38, (struct JobSecurity *)&pSecurityDescriptor, TokenHandle);
      if ( v7 < 0 )
      {
LABEL_19:
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
        ReleaseSRWLockExclusive(&SRWLock);
        v13 = (tsched *)TokenHandle;
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        goto LABEL_8;
      }
      v7 = JobAccessCheck(TokenHandle, pSecurityDescriptor, 4u);
      if ( v7 >= 0 )
      {
        v28 = 0;
        v29 = 0;
        v7 = JobStore::GenerateJobSecurity(v16, &v38, a3, 1u, TokenHandle, &v28);
        if ( v7 < 0 )
        {
          tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v28);
          goto LABEL_19;
        }
        v7 = JobStore::RegFolderEntryCreate(v16, &v38, (const struct JobSecurity *)&v28);
        if ( v7 >= 0 )
        {
          RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v25, L"RpcServer::CreateFolder", 1);
          v7 = JobStore::CreateXmlFolder(v16, &v38, a3);
          if ( v7 >= 0 )
          {
            if ( v25 )
              RpcRevertToSelf();
            tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v28);
            tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
            ReleaseSRWLockExclusive(&SRWLock);
            wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
            v7 = 0;
            goto LABEL_8;
          }
          if ( v25 )
            RpcRevertToSelf();
        }
        tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v28);
      }
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&pSecurityDescriptor);
      ReleaseSRWLockExclusive(&SRWLock);
      wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&TokenHandle);
    }
    catch ( ... )
    {
      tsched::KnownExceptionToHResult(v13, v20, v14, v15, (unsigned __int8)&v24, NewDescriptor);
    }
  }
LABEL_8:
  v24 = v7;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001fa60  mov     [rsp+arg_0], rbx
0x18001fa65  mov     [rsp+arg_18], rsi
0x18001fa6a  push    rdi
0x18001fa6b  push    r14
0x18001fa6d  push    r15
0x18001fa6f  sub     rsp, 2C0h
0x18001fa76  mov     rax, cs:__security_cookie
0x18001fa7d  xor     rax, rsp
0x18001fa80  mov     [rsp+2D8h+var_28], rax
0x18001fa88  mov     rsi, r8
0x18001fa8b  mov     rbx, rdx
0x18001fa8e  xor     r14d, r14d
0x18001fa91  mov     [rsp+2D8h+var_2A0], r14d
0x18001fa96  test    rdx, rdx
0x18001fa99  jz      short loc_18001FAF2
0x18001fa9b  test    r9d, r9d
0x18001fa9e  jnz     short loc_18001FAF2
0x18001faa0  mov     [rsp+2D8h+var_238], r14w
0x18001faa9  xor     edx, edx; Val
0x18001faab  mov     r8d, 208h; Size
0x18001fab1  lea     rcx, [rsp+2D8h+var_236]; void *
0x18001fab9  call    memset_0
0x18001fabe  mov     rdx, rbx; unsigned __int16 *
0x18001fac1  lea     rcx, [rsp+2D8h+var_238]; this
0x18001fac9  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x18001face  mov     ebx, eax
0x18001fad0  test    eax, eax
0x18001fad2  js      short loc_18001FAF7
0x18001fad4  movzx   eax, [rsp+2D8h+var_238]
0x18001fadc  test    ax, ax
0x18001fadf  jz      short loc_18001FAF2
0x18001fae1  cmp     [rsp+2D8h+var_236], r14w
0x18001faea  jnz     short loc_18001FB00
0x18001faec  cmp     ax, 5Ch ; '\'
0x18001faf0  jnz     short loc_18001FB00
0x18001faf2  mov     ebx, 80070057h
0x18001faf7  mov     [rsp+2D8h+var_2A0], ebx
0x18001fafb  jmp     loc_18001FDDA
0x18001fb00  mov     [rsp+2D8h+TokenHandle], r14
0x18001fb05  xor     ecx, ecx; BindingHandle
0x18001fb07  call    cs:__imp_RpcImpersonateClient
0x18001fb0e  nop     dword ptr [rax+rax+00h]
0x18001fb13  mov     ebx, eax
0x18001fb15  test    eax, eax
0x18001fb17  jz      short loc_18001FB7D
0x18001fb19  mov     r9d, eax; unsigned int
0x18001fb1c  lea     r8, aCreatefolder; "CreateFolder"
0x18001fb23  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18001fb2a  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18001fb2f  mov     [rsp+2D8h+var_270], 0
0x18001fb34  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001fb3b  mov     [rsp+2D8h+pExceptionObject], rax
0x18001fb40  lea     rax, qword_1800A8718
0x18001fb47  mov     [rsp+2D8h+var_268], rax
0x18001fb4c  mov     [rsp+2D8h+var_260], r14
0x18001fb51  mov     [rsp+2D8h+var_258], r14
0x18001fb59  mov     [rsp+2D8h+var_250], ebx
0x18001fb60  mov     [rsp+2D8h+var_24C], 0FFFFFFFFFFFFFFFFh
0x18001fb6c  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001fb73  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x18001fb78  call    _CxxThrowException_0
0x18001fb7d  call    cs:__imp_GetCurrentThread
0x18001fb84  nop     dword ptr [rax+rax+00h]
0x18001fb89  mov     rcx, rax; ThreadHandle
0x18001fb8c  lea     r9, [rsp+2D8h+TokenHandle]; TokenHandle
0x18001fb91  mov     edx, 8; DesiredAccess
0x18001fb96  mov     r8d, 1; OpenAsSelf
0x18001fb9c  call    cs:__imp_OpenThreadToken
0x18001fba3  nop     dword ptr [rax+rax+00h]
0x18001fba8  test    eax, eax
0x18001fbaa  jnz     short loc_18001FBE6
0x18001fbac  call    cs:__imp_GetLastError
0x18001fbb3  nop     dword ptr [rax+rax+00h]
0x18001fbb8  mov     ebx, eax
0x18001fbba  test    eax, eax
0x18001fbbc  jle     short loc_18001FBC7
0x18001fbbe  movzx   ebx, ax
0x18001fbc1  or      ebx, 80070000h
0x18001fbc7  call    cs:__imp_RpcRevertToSelf
0x18001fbce  nop     dword ptr [rax+rax+00h]
0x18001fbd3  test    ebx, ebx
0x18001fbd5  jns     short loc_18001FBF2
0x18001fbd7  lea     rcx, [rsp+2D8h+TokenHandle]; this
0x18001fbdc  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18001fbe1  jmp     loc_18001FAF7
0x18001fbe6  call    cs:__imp_RpcRevertToSelf
0x18001fbed  nop     dword ptr [rax+rax+00h]
0x18001fbf2  lea     r15, SRWLock
0x18001fbf9  mov     [rsp+2D8h+var_240], r15
0x18001fc01  mov     rcx, r15; SRWLock
0x18001fc04  call    cs:__imp_AcquireSRWLockExclusive
0x18001fc0b  nop     dword ptr [rax+rax+00h]
0x18001fc10  nop
0x18001fc11  mov     rdi, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18001fc18  mov     [rsp+2D8h+pSecurityDescriptor], r14
0x18001fc1d  mov     [rsp+2D8h+var_290], r14d
0x18001fc22  mov     r9, [rsp+2D8h+TokenHandle]; void *
0x18001fc27  lea     r8, [rsp+2D8h+pSecurityDescriptor]; struct JobSecurity *
0x18001fc2c  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x18001fc34  call    ?CreateRegistrationPath@RpcServer@@AEAAJPEBGAEAVJobSecurity@@PEAX@Z; RpcServer::CreateRegistrationPath(ushort const *,JobSecurity &,void *)
0x18001fc39  mov     ebx, eax
0x18001fc3b  test    eax, eax
0x18001fc3d  jns     short loc_18001FC7E
0x18001fc3f  lea     rcx, [rsp+2D8h+pSecurityDescriptor]
0x18001fc44  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fc49  nop
0x18001fc4a  mov     rcx, r15; SRWLock
0x18001fc4d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fc54  nop     dword ptr [rax+rax+00h]
0x18001fc59  nop
0x18001fc5a  mov     rcx, [rsp+2D8h+TokenHandle]; hObject
0x18001fc5f  lea     rax, [rcx-1]
0x18001fc63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fc67  ja      loc_18001FAF7
0x18001fc6d  call    cs:__imp_CloseHandle
0x18001fc74  nop     dword ptr [rax+rax+00h]
0x18001fc79  jmp     loc_18001FAF7
0x18001fc7e  mov     r8d, 4; DesiredAccess
0x18001fc84  mov     rdx, [rsp+2D8h+pSecurityDescriptor]; pSecurityDescriptor
0x18001fc89  mov     rcx, [rsp+2D8h+TokenHandle]; ClientToken
0x18001fc8e  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x18001fc93  mov     ebx, eax
0x18001fc95  test    eax, eax
0x18001fc97  jns     short loc_18001FCC3
0x18001fc99  lea     rcx, [rsp+2D8h+pSecurityDescriptor]
0x18001fc9e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fca3  nop
0x18001fca4  mov     rcx, r15; SRWLock
0x18001fca7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fcae  nop     dword ptr [rax+rax+00h]
0x18001fcb3  nop
0x18001fcb4  lea     rcx, [rsp+2D8h+TokenHandle]; this
0x18001fcb9  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18001fcbe  jmp     loc_18001FAF7
0x18001fcc3  mov     [rsp+2D8h+var_288], r14
0x18001fcc8  mov     [rsp+2D8h+var_280], r14d
0x18001fccd  lea     rax, [rsp+2D8h+var_288]
0x18001fcd2  mov     [rsp+2D8h+NewDescriptor], rax; NewDescriptor
0x18001fcd7  mov     rax, [rsp+2D8h+TokenHandle]
0x18001fcdc  mov     [rsp+2D8h+var_2B8], rax; HANDLE
0x18001fce1  mov     r9b, 1; IsDirectoryObject
0x18001fce4  mov     r8, rsi; StringSecurityDescriptor
0x18001fce7  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x18001fcef  mov     rcx, rdi; this
0x18001fcf2  call    ?GenerateJobSecurity@JobStore@@QEBAJPEBG0EPEAXAEAVJobSecurity@@@Z; JobStore::GenerateJobSecurity(ushort const *,ushort const *,uchar,void *,JobSecurity &)
0x18001fcf7  mov     ebx, eax
0x18001fcf9  test    eax, eax
0x18001fcfb  jns     short loc_18001FD0C
0x18001fcfd  lea     rcx, [rsp+2D8h+var_288]
0x18001fd02  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fd07  jmp     loc_18001FC3F
0x18001fd0c  lea     r8, [rsp+2D8h+var_288]; struct JobSecurity *
0x18001fd11  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x18001fd19  mov     rcx, rdi; this
0x18001fd1c  call    ?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z; JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)
0x18001fd21  mov     ebx, eax
0x18001fd23  test    eax, eax
0x18001fd25  jns     short loc_18001FD36
0x18001fd27  lea     rcx, [rsp+2D8h+var_288]
0x18001fd2c  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fd31  jmp     loc_18001FC99
0x18001fd36  mov     r8d, 1; int
0x18001fd3c  lea     rdx, aRpcserverCreat; "RpcServer::CreateFolder"
0x18001fd43  lea     rcx, [rsp+2D8h+var_29C]; this
0x18001fd48  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18001fd4d  nop
0x18001fd4e  mov     r8, rsi; unsigned __int16 *
0x18001fd51  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x18001fd59  mov     rcx, rdi; this
0x18001fd5c  call    ?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z; JobStore::CreateXmlFolder(ushort const *,ushort const *)
0x18001fd61  mov     ebx, eax
0x18001fd63  test    eax, eax
0x18001fd65  jns     short loc_18001FD8A
0x18001fd67  cmp     [rsp+2D8h+var_29C], 0
0x18001fd6c  jz      short loc_18001FD7B
0x18001fd6e  call    cs:__imp_RpcRevertToSelf
0x18001fd75  nop     dword ptr [rax+rax+00h]
0x18001fd7a  nop
0x18001fd7b  lea     rcx, [rsp+2D8h+var_288]
0x18001fd80  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fd85  jmp     loc_18001FC99
0x18001fd8a  cmp     [rsp+2D8h+var_29C], 0
0x18001fd8f  jz      short loc_18001FD9E
0x18001fd91  call    cs:__imp_RpcRevertToSelf
0x18001fd98  nop     dword ptr [rax+rax+00h]
0x18001fd9d  nop
0x18001fd9e  lea     rcx, [rsp+2D8h+var_288]
0x18001fda3  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fda8  nop
0x18001fda9  lea     rcx, [rsp+2D8h+pSecurityDescriptor]
0x18001fdae  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001fdb3  nop
0x18001fdb4  mov     rcx, r15; SRWLock
0x18001fdb7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fdbe  nop     dword ptr [rax+rax+00h]
0x18001fdc3  nop
0x18001fdc4  lea     rcx, [rsp+2D8h+TokenHandle]; this
0x18001fdc9  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18001fdce  mov     ebx, r14d
0x18001fdd1  jmp     loc_18001FAF7
0x18001fdd6  mov     ebx, [rsp+2D8h+var_2A0]
0x18001fdda  mov     eax, ebx
0x18001fddc  mov     rcx, [rsp+2D8h+var_28]
0x18001fde4  xor     rcx, rsp; StackCookie
0x18001fde7  call    __security_check_cookie
0x18001fdec  lea     r11, [rsp+2D8h+var_18]
0x18001fdf4  mov     rbx, [r11+20h]
0x18001fdf8  mov     rsi, [r11+38h]
0x18001fdfc  mov     rsp, r11
0x18001fdff  pop     r15
0x18001fe01  pop     r14
0x18001fe03  pop     rdi
0x18001fe04  retn
```
