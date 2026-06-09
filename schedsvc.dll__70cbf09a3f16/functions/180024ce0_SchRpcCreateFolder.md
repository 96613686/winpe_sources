# _SchRpcCreateFolder

- ea: `0x180024ce0`
- end: `0x180025037`
- name: `_SchRpcCreateFolder`
- size: `855`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, const WCHAR *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180024ce0`
- `0x180025040`
- `0x18002506c`
- `0x180025310`
- `0x180025550`
- `0x1800256d0`
- `0x1800265fc`
- `0x180039b6c`
- `0x180039d00`
- `0x180040590`
- `0x18004d50c`
- `0x18005790c`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ebd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024e60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ea3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024fef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ea3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ef1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024fef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024df7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024df7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180024e10`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180024e10`
- `RPCRT4!RpcImpersonateClient` at `0x180024d87`
- `RPCRT4!RpcImpersonateClient` at `0x180024d87`
- `RPCRT4!RpcRevertToSelf` at `0x180024e2f`
- `RPCRT4!RpcRevertToSelf` at `0x180024e48`
- `RPCRT4!RpcRevertToSelf` at `0x180024fb2`
- `RPCRT4!RpcRevertToSelf` at `0x180024fcf`
- `RPCRT4!RpcRevertToSelf` at `0x180024e2f`
- `RPCRT4!RpcRevertToSelf` at `0x180024e48`
- `RPCRT4!RpcRevertToSelf` at `0x180024fb2`
- `RPCRT4!RpcRevertToSelf` at `0x180024fcf`

## string_xrefs

- `0x180024f80`: `RpcServer::CreateFolder`
- `0x180024d96`: `CreateFolder`

## pseudocode

```c
__int64 __fastcall SchRpcCreateFolder(__int64 a1, unsigned __int16 *a2, const WCHAR *a3, int a4)
{
  const unsigned __int16 *v6; // r8
  signed int v7; // ebx
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
  signed int v24; // [rsp+38h] [rbp-2A0h] BYREF
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
        v32 = &qword_1800A4718;
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
0x180024ce0  mov     [rsp+arg_0], rbx
0x180024ce5  mov     [rsp+arg_18], rsi
0x180024cea  push    rdi
0x180024ceb  push    r14
0x180024ced  push    r15
0x180024cef  sub     rsp, 2C0h
0x180024cf6  mov     rax, cs:__security_cookie
0x180024cfd  xor     rax, rsp
0x180024d00  mov     [rsp+2D8h+var_28], rax
0x180024d08  mov     rsi, r8
0x180024d0b  mov     rbx, rdx
0x180024d0e  xor     r14d, r14d
0x180024d11  mov     [rsp+2D8h+var_2A0], r14d
0x180024d16  test    rdx, rdx
0x180024d19  jz      short loc_180024D72
0x180024d1b  test    r9d, r9d
0x180024d1e  jnz     short loc_180024D72
0x180024d20  mov     [rsp+2D8h+var_238], r14w
0x180024d29  xor     edx, edx; Val
0x180024d2b  mov     r8d, 208h; Size
0x180024d31  lea     rcx, [rsp+2D8h+var_236]; void *
0x180024d39  call    memset_0
0x180024d3e  mov     rdx, rbx; unsigned __int16 *
0x180024d41  lea     rcx, [rsp+2D8h+var_238]; this
0x180024d49  call    ?TaskPathCanonicalize@tsched@@YAJPEAGPEBG@Z; tsched::TaskPathCanonicalize(ushort *,ushort const *)
0x180024d4e  mov     ebx, eax
0x180024d50  test    eax, eax
0x180024d52  js      short loc_180024D77
0x180024d54  movzx   eax, [rsp+2D8h+var_238]
0x180024d5c  test    ax, ax
0x180024d5f  jz      short loc_180024D72
0x180024d61  cmp     [rsp+2D8h+var_236], r14w
0x180024d6a  jnz     short loc_180024D80
0x180024d6c  cmp     ax, 5Ch ; '\'
0x180024d70  jnz     short loc_180024D80
0x180024d72  mov     ebx, 80070057h
0x180024d77  mov     [rsp+2D8h+var_2A0], ebx
0x180024d7b  jmp     loc_18002500C
0x180024d80  mov     [rsp+2D8h+TokenHandle], r14
0x180024d85  xor     ecx, ecx; BindingHandle
0x180024d87  call    cs:__imp_RpcImpersonateClient
0x180024d8d  mov     ebx, eax
0x180024d8f  test    eax, eax
0x180024d91  jz      short loc_180024DF7
0x180024d93  mov     r9d, eax; unsigned int
0x180024d96  lea     r8, aCreatefolder; "CreateFolder"
0x180024d9d  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180024da4  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180024da9  mov     [rsp+2D8h+var_270], 0
0x180024dae  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180024db5  mov     [rsp+2D8h+pExceptionObject], rax
0x180024dba  lea     rax, qword_1800A4718
0x180024dc1  mov     [rsp+2D8h+var_268], rax
0x180024dc6  mov     [rsp+2D8h+var_260], r14
0x180024dcb  mov     [rsp+2D8h+var_258], r14
0x180024dd3  mov     [rsp+2D8h+var_250], ebx
0x180024dda  mov     [rsp+2D8h+var_24C], 0FFFFFFFFFFFFFFFFh
0x180024de6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180024ded  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x180024df2  call    _CxxThrowException_0
0x180024df7  call    cs:__imp_GetCurrentThread
0x180024dfd  mov     rcx, rax; ThreadHandle
0x180024e00  lea     r9, [rsp+2D8h+TokenHandle]; TokenHandle
0x180024e05  mov     edx, 8; DesiredAccess
0x180024e0a  mov     r8d, 1; OpenAsSelf
0x180024e10  call    cs:__imp_OpenThreadToken
0x180024e16  test    eax, eax
0x180024e18  jnz     short loc_180024E48
0x180024e1a  call    cs:__imp_GetLastError
0x180024e20  mov     ebx, eax
0x180024e22  test    eax, eax
0x180024e24  jle     short loc_180024E2F
0x180024e26  movzx   ebx, ax
0x180024e29  or      ebx, 80070000h
0x180024e2f  call    cs:__imp_RpcRevertToSelf
0x180024e35  test    ebx, ebx
0x180024e37  jns     short loc_180024E4E
0x180024e39  lea     rcx, [rsp+2D8h+TokenHandle]; this
0x180024e3e  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180024e43  jmp     loc_180024D77
0x180024e48  call    cs:__imp_RpcRevertToSelf
0x180024e4e  lea     r15, SRWLock
0x180024e55  mov     [rsp+2D8h+var_240], r15
0x180024e5d  mov     rcx, r15; SRWLock
0x180024e60  call    cs:__imp_AcquireSRWLockExclusive
0x180024e66  nop
0x180024e67  mov     rdi, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x180024e6e  mov     [rsp+2D8h+pSecurityDescriptor], r14
0x180024e73  mov     [rsp+2D8h+var_290], r14d
0x180024e78  mov     r9, [rsp+2D8h+TokenHandle]; void *
0x180024e7d  lea     r8, [rsp+2D8h+pSecurityDescriptor]; struct JobSecurity *
0x180024e82  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x180024e8a  call    ?CreateRegistrationPath@RpcServer@@AEAAJPEBGAEAVJobSecurity@@PEAX@Z; RpcServer::CreateRegistrationPath(ushort const *,JobSecurity &,void *)
0x180024e8f  mov     ebx, eax
0x180024e91  test    eax, eax
0x180024e93  jns     short loc_180024EC8
0x180024e95  lea     rcx, [rsp+2D8h+pSecurityDescriptor]
0x180024e9a  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024e9f  nop
0x180024ea0  mov     rcx, r15; SRWLock
0x180024ea3  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ea9  nop
0x180024eaa  mov     rcx, [rsp+2D8h+TokenHandle]; hObject
0x180024eaf  lea     rax, [rcx-1]
0x180024eb3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024eb7  ja      loc_180024D77
0x180024ebd  call    cs:__imp_CloseHandle
0x180024ec3  jmp     loc_180024D77
0x180024ec8  mov     r8d, 4; DesiredAccess
0x180024ece  mov     rdx, [rsp+2D8h+pSecurityDescriptor]; pSecurityDescriptor
0x180024ed3  mov     rcx, [rsp+2D8h+TokenHandle]; ClientToken
0x180024ed8  call    ?JobAccessCheck@@YAJPEAX0K@Z; JobAccessCheck(void *,void *,ulong)
0x180024edd  mov     ebx, eax
0x180024edf  test    eax, eax
0x180024ee1  jns     short loc_180024F07
0x180024ee3  lea     rcx, [rsp+2D8h+pSecurityDescriptor]
0x180024ee8  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024eed  nop
0x180024eee  mov     rcx, r15; SRWLock
0x180024ef1  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ef7  nop
0x180024ef8  lea     rcx, [rsp+2D8h+TokenHandle]; this
0x180024efd  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180024f02  jmp     loc_180024D77
0x180024f07  mov     [rsp+2D8h+var_288], r14
0x180024f0c  mov     [rsp+2D8h+var_280], r14d
0x180024f11  lea     rax, [rsp+2D8h+var_288]
0x180024f16  mov     [rsp+2D8h+NewDescriptor], rax; NewDescriptor
0x180024f1b  mov     rax, [rsp+2D8h+TokenHandle]
0x180024f20  mov     [rsp+2D8h+var_2B8], rax; HANDLE
0x180024f25  mov     r9b, 1; IsDirectoryObject
0x180024f28  mov     r8, rsi; StringSecurityDescriptor
0x180024f2b  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x180024f33  mov     rcx, rdi; this
0x180024f36  call    ?GenerateJobSecurity@JobStore@@QEBAJPEBG0EPEAXAEAVJobSecurity@@@Z; JobStore::GenerateJobSecurity(ushort const *,ushort const *,uchar,void *,JobSecurity &)
0x180024f3b  mov     ebx, eax
0x180024f3d  test    eax, eax
0x180024f3f  jns     short loc_180024F50
0x180024f41  lea     rcx, [rsp+2D8h+var_288]
0x180024f46  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024f4b  jmp     loc_180024E95
0x180024f50  lea     r8, [rsp+2D8h+var_288]; struct JobSecurity *
0x180024f55  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x180024f5d  mov     rcx, rdi; this
0x180024f60  call    ?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z; JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)
0x180024f65  mov     ebx, eax
0x180024f67  test    eax, eax
0x180024f69  jns     short loc_180024F7A
0x180024f6b  lea     rcx, [rsp+2D8h+var_288]
0x180024f70  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024f75  jmp     loc_180024EE3
0x180024f7a  mov     r8d, 1; int
0x180024f80  lea     rdx, aRpcserverCreat; "RpcServer::CreateFolder"
0x180024f87  lea     rcx, [rsp+2D8h+var_29C]; this
0x180024f8c  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180024f91  nop
0x180024f92  mov     r8, rsi; unsigned __int16 *
0x180024f95  lea     rdx, [rsp+2D8h+var_238]; unsigned __int16 *
0x180024f9d  mov     rcx, rdi; this
0x180024fa0  call    ?CreateXmlFolder@JobStore@@QEAAJPEBG0@Z; JobStore::CreateXmlFolder(ushort const *,ushort const *)
0x180024fa5  mov     ebx, eax
0x180024fa7  test    eax, eax
0x180024fa9  jns     short loc_180024FC8
0x180024fab  cmp     [rsp+2D8h+var_29C], 0
0x180024fb0  jz      short loc_180024FB9
0x180024fb2  call    cs:__imp_RpcRevertToSelf
0x180024fb8  nop
0x180024fb9  lea     rcx, [rsp+2D8h+var_288]
0x180024fbe  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024fc3  jmp     loc_180024EE3
0x180024fc8  cmp     [rsp+2D8h+var_29C], 0
0x180024fcd  jz      short loc_180024FD6
0x180024fcf  call    cs:__imp_RpcRevertToSelf
0x180024fd5  nop
0x180024fd6  lea     rcx, [rsp+2D8h+var_288]
0x180024fdb  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024fe0  nop
0x180024fe1  lea     rcx, [rsp+2D8h+pSecurityDescriptor]
0x180024fe6  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180024feb  nop
0x180024fec  mov     rcx, r15; SRWLock
0x180024fef  call    cs:__imp_ReleaseSRWLockExclusive
0x180024ff5  nop
0x180024ff6  lea     rcx, [rsp+2D8h+TokenHandle]; this
0x180024ffb  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180025000  mov     ebx, r14d
0x180025003  jmp     loc_180024D77
0x180025008  mov     ebx, [rsp+2D8h+var_2A0]
0x18002500c  mov     eax, ebx
0x18002500e  mov     rcx, [rsp+2D8h+var_28]
0x180025016  xor     rcx, rsp; StackCookie
0x180025019  call    __security_check_cookie
0x18002501e  lea     r11, [rsp+2D8h+var_18]
0x180025026  mov     rbx, [r11+20h]
0x18002502a  mov     rsi, [r11+38h]
0x18002502e  mov     rsp, r11
0x180025031  pop     r15
0x180025033  pop     r14
0x180025035  pop     rdi
0x180025036  retn
```
