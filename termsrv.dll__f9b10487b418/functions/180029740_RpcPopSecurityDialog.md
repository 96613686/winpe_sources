# RpcPopSecurityDialog

- ea: `0x180029740`
- end: `0x180029a98`
- name: `RpcPopSecurityDialog`
- size: `856`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008b40`
- `0x18000a210`
- `0x18000bad0`
- `0x18000f080`
- `0x18000f1a0`
- `0x180012480`
- `0x1800130d8`
- `0x180013150`
- `0x1800148d0`
- `0x180029740`
- `0x1800321f0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029839`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002982f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002982f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180029801`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180029801`
- `RPCRT4!RpcRevertToSelf` at `0x1800298ce`
- `RPCRT4!RpcRevertToSelf` at `0x1800298e8`
- `RPCRT4!RpcRevertToSelf` at `0x1800298ce`
- `RPCRT4!RpcRevertToSelf` at `0x1800298e8`
- `RPCRT4!RpcImpersonateClient` at `0x1800297cf`
- `RPCRT4!RpcImpersonateClient` at `0x1800297cf`

## string_xrefs

- `0x180029873`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x1800297ee`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180029768`: `RpcPopSecurityDialog`
- `0x1800299bb`: `RpcPopSecurityDialog caller is not the same as the logged user`
- `0x180029a11`: `PopSecurityDialog failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 RpcPopSecurityDialog()
{
  RPC_STATUS v0; // eax
  signed int v1; // edi
  RPC_STATUS v2; // eax
  signed int LastError; // eax
  int ClientToken; // eax
  const char *v5; // rdx
  struct IUserName *v6; // rbx
  int v7; // eax
  bool v8; // sf
  bool v9; // sf
  int InstanceOfSessionManager; // eax
  const char *v11; // rdx
  __int64 pSessionId; // [rsp+20h] [rbp-E0h] BYREF
  void *v14; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  struct IUserName *v17; // [rsp+40h] [rbp-C0h] BYREF
  struct ISessionManager *v18; // [rsp+48h] [rbp-B8h] BYREF
  struct ISessionList *v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v21[592]; // [rsp+60h] [rbp-A0h] BYREF

  v20 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  pSessionId = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v21, 0, "RpcPopSecurityDialog");
  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  if ( v1 < 0 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x in %s", (unsigned int)v1, "RpcPopSecurityDialog");
    goto LABEL_44;
  }
  v2 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)&pSessionId + 1);
  v1 = v2;
  if ( v2 > 0 )
    v1 = (unsigned __int16)v2 | 0x80070000;
  if ( v1 >= 0 )
  {
    if ( ProcessIdToSessionId(HIDWORD(pSessionId), (DWORD *)&pSessionId) )
    {
      ClientToken = CRpcUtils::GetClientToken(&v14, 1);
      v1 = ClientToken;
      if ( ClientToken >= 0 )
      {
        ClientToken = CUtils::GetInstanceOfUserName(&v17);
        v1 = ClientToken;
        if ( ClientToken >= 0 )
        {
          v6 = v17;
          ClientToken = (*(__int64 (__fastcall **)(struct IUserName *, void *, _QWORD))(*(_QWORD *)v17 + 24LL))(
                          v17,
                          v14,
                          0);
          v1 = ClientToken;
          if ( ClientToken >= 0 )
          {
            v7 = RpcRevertToSelf();
            v9 = v7 < 0;
            if ( v7 > 0 )
            {
              v7 = (unsigned __int16)v7 | 0x80070000;
              v9 = v7 < 0;
            }
            if ( !v9 )
            {
              InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v18);
              v1 = InstanceOfSessionManager;
              if ( InstanceOfSessionManager >= 0 )
              {
                InstanceOfSessionManager = CHelper::GetSessionList(&v19);
                v1 = InstanceOfSessionManager;
                if ( InstanceOfSessionManager >= 0 )
                {
                  InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, __int64 *))(*(_QWORD *)v19 + 24LL))(
                                               v19,
                                               (unsigned int)pSessionId,
                                               &v20);
                  v1 = InstanceOfSessionManager;
                  if ( InstanceOfSessionManager >= 0 )
                  {
                    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 96LL))(
                                                 v20,
                                                 &v16);
                    v1 = InstanceOfSessionManager;
                    if ( InstanceOfSessionManager >= 0 )
                    {
                      if ( (*(unsigned int (__fastcall **)(struct IUserName *, __int64))(*(_QWORD *)v6 + 32LL))(v6, v16) )
                      {
                        _DbgPrintMessage(8, "RpcPopSecurityDialog caller is not the same as the logged user");
                        goto LABEL_28;
                      }
                      InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionManager *, __int64 *))(*(_QWORD *)v18 + 48LL))(
                                                   v18,
                                                   &v15);
                      v1 = InstanceOfSessionManager;
                      if ( InstanceOfSessionManager >= 0 )
                      {
                        InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 32LL))(
                                                     v15,
                                                     (unsigned int)pSessionId);
                        v1 = InstanceOfSessionManager;
                        if ( InstanceOfSessionManager >= 0 )
                          goto LABEL_44;
                        v11 = "PopSecurityDialog failed: 0x%x in %s";
                      }
                      else
                      {
                        v11 = "GetRestrictedCalls failed: 0x%x in %s";
                      }
                    }
                    else
                    {
                      v11 = "getUserName failed: 0x%x in %s";
                    }
                  }
                  else
                  {
                    v11 = "FindSessionById failed: 0x%x in %s";
                  }
                }
                else
                {
                  v11 = "GetSessionList failed: 0x%x in %s";
                }
              }
              else
              {
                v11 = "GetInstanceOfSessionManager failed: 0x%x in %s";
              }
              _DbgPrintMessage(8, v11, (unsigned int)InstanceOfSessionManager, "RpcPopSecurityDialog", pSessionId);
              goto LABEL_44;
            }
LABEL_27:
            _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v7);
LABEL_28:
            v1 = -2147024891;
            goto LABEL_44;
          }
          v5 = "ptrRequestorUserName->Initialize failed: 0x%x in %s";
        }
        else
        {
          v5 = "CUtils::GetInstanceOfUserName failed: 0x%x in %s";
        }
      }
      else
      {
        v5 = "CRpcUtils::GetClientToken failed: 0x%x in %s";
      }
      _DbgPrintMessage(8, v5, (unsigned int)ClientToken, "RpcPopSecurityDialog", pSessionId);
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "Failed to get session id");
    }
  }
  else
  {
    _DbgPrintMessage(8, "I_RpcBindingInqLocalClientPID failed: 0x%x in %s", (unsigned int)v1, "RpcPopSecurityDialog");
  }
  v7 = RpcRevertToSelf();
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = v7 < 0;
  }
  if ( v8 )
    goto LABEL_27;
LABEL_44:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v21);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v14);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v15);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v16);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v17);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v18);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v19);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v20);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180029740  push    rbp
0x180029742  push    rbx
0x180029743  push    rdi
0x180029744  push    r14
0x180029746  push    r15
0x180029748  lea     rbp, [rsp-1C0h]
0x180029750  sub     rsp, 2C0h
0x180029757  mov     rax, cs:__security_cookie
0x18002975e  xor     rax, rsp
0x180029761  mov     [rbp+1E0h+var_30], rax
0x180029768  lea     r14, aRpcpopsecurity; "RpcPopSecurityDialog"
0x18002976f  mov     [rsp+2E0h+var_288], 0
0x180029778  mov     r8, r14; char *
0x18002977b  mov     [rsp+2E0h+var_290], 0
0x180029784  xor     edx, edx; int
0x180029786  mov     [rsp+2E0h+var_298], 0
0x18002978f  lea     rcx, [rsp+2E0h+var_280]; this
0x180029794  mov     [rsp+2E0h+var_2A0], 0
0x18002979d  mov     [rsp+2E0h+var_2A8], 0
0x1800297a6  mov     [rsp+2E0h+var_2B0], 0
0x1800297af  mov     [rsp+2E0h+var_2B8], 0
0x1800297b8  mov     [rsp+2E0h+pSessionId], 0
0x1800297c0  mov     [rsp+2E0h+Pid], 0
0x1800297c8  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x1800297cd  xor     ecx, ecx; BindingHandle
0x1800297cf  call    cs:__imp_RpcImpersonateClient
0x1800297d5  mov     edi, eax
0x1800297d7  mov     r15d, 80070000h
0x1800297dd  test    eax, eax
0x1800297df  jle     short loc_1800297E7
0x1800297e1  movzx   edi, ax
0x1800297e4  or      edi, r15d
0x1800297e7  test    edi, edi
0x1800297e9  jns     short loc_1800297FA
0x1800297eb  mov     r8d, edi
0x1800297ee  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x1800297f5  jmp     loc_180029A1B
0x1800297fa  lea     rdx, [rsp+2E0h+Pid]; Pid
0x1800297ff  xor     ecx, ecx; Binding
0x180029801  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180029807  mov     edi, eax
0x180029809  test    eax, eax
0x18002980b  jle     short loc_180029813
0x18002980d  movzx   edi, ax
0x180029810  or      edi, r15d
0x180029813  test    edi, edi
0x180029815  jns     short loc_180029826
0x180029817  mov     r8d, edi
0x18002981a  lea     rdx, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID failed: 0"...
0x180029821  jmp     loc_1800298C1
0x180029826  mov     ecx, [rsp+2E0h+Pid]; dwProcessId
0x18002982a  lea     rdx, [rsp+2E0h+pSessionId]; pSessionId
0x18002982f  call    cs:__imp_ProcessIdToSessionId
0x180029835  test    eax, eax
0x180029837  jnz     short loc_18002985E
0x180029839  call    cs:__imp_GetLastError
0x18002983f  mov     edi, eax
0x180029841  test    eax, eax
0x180029843  jle     short loc_18002984B
0x180029845  movzx   edi, ax
0x180029848  or      edi, r15d
0x18002984b  lea     rdx, aFailedToGetSes_3; "Failed to get session id"
0x180029852  mov     ecx, 8; int
0x180029857  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002985c  jmp     short loc_1800298CE
0x18002985e  mov     edx, 1; int
0x180029863  lea     rcx, [rsp+2E0h+var_2B8]; void **
0x180029868  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x18002986d  mov     edi, eax
0x18002986f  test    eax, eax
0x180029871  jns     short loc_18002987C
0x180029873  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18002987a  jmp     short loc_1800298BE
0x18002987c  lea     rcx, [rsp+2E0h+var_2A0]; struct IUserName **
0x180029881  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x180029886  mov     edi, eax
0x180029888  test    eax, eax
0x18002988a  jns     short loc_180029895
0x18002988c  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x180029893  jmp     short loc_1800298BE
0x180029895  mov     rbx, [rsp+2E0h+var_2A0]
0x18002989a  xor     r8d, r8d
0x18002989d  mov     rdx, [rsp+2E0h+var_2B8]
0x1800298a2  mov     rcx, rbx
0x1800298a5  mov     rax, [rbx]
0x1800298a8  mov     rax, [rax+18h]
0x1800298ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298b1  mov     edi, eax
0x1800298b3  test    eax, eax
0x1800298b5  jns     short loc_1800298E8
0x1800298b7  lea     rdx, aPtrrequestorus; "ptrRequestorUserName->Initialize failed"...
0x1800298be  mov     r8d, eax
0x1800298c1  mov     r9, r14
0x1800298c4  mov     ecx, 8; int
0x1800298c9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800298ce  call    cs:__imp_RpcRevertToSelf
0x1800298d4  test    eax, eax
0x1800298d6  jle     short loc_1800298E0
0x1800298d8  movzx   eax, ax
0x1800298db  or      eax, r15d
0x1800298de  test    eax, eax
0x1800298e0  jns     loc_180029A28
0x1800298e6  jmp     short loc_1800298FC
0x1800298e8  call    cs:__imp_RpcRevertToSelf
0x1800298ee  test    eax, eax
0x1800298f0  jle     short loc_1800298FA
0x1800298f2  movzx   eax, ax
0x1800298f5  or      eax, r15d
0x1800298f8  test    eax, eax
0x1800298fa  jns     short loc_18002991A
0x1800298fc  mov     r8d, eax
0x1800298ff  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180029906  mov     ecx, 8; int
0x18002990b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029910  mov     edi, 80070005h
0x180029915  jmp     loc_180029A28
0x18002991a  lea     rcx, [rsp+2E0h+var_298]; struct ISessionManager **
0x18002991f  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x180029924  mov     edi, eax
0x180029926  test    eax, eax
0x180029928  jns     short loc_180029936
0x18002992a  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x180029931  jmp     loc_180029A18
0x180029936  lea     rcx, [rsp+2E0h+var_290]; struct ISessionList **
0x18002993b  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180029940  mov     edi, eax
0x180029942  test    eax, eax
0x180029944  jns     short loc_180029952
0x180029946  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x18002994d  jmp     loc_180029A18
0x180029952  mov     rcx, [rsp+2E0h+var_290]
0x180029957  lea     r8, [rsp+2E0h+var_288]
0x18002995c  mov     edx, [rsp+2E0h+pSessionId]
0x180029960  mov     rax, [rcx]
0x180029963  mov     rax, [rax+18h]
0x180029967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002996c  mov     edi, eax
0x18002996e  test    eax, eax
0x180029970  jns     short loc_18002997E
0x180029972  lea     rdx, aFindsessionbyi_0; "FindSessionById failed: 0x%x in %s"
0x180029979  jmp     loc_180029A18
0x18002997e  mov     rcx, [rsp+2E0h+var_288]
0x180029983  lea     rdx, [rsp+2E0h+var_2A8]
0x180029988  mov     rax, [rcx]
0x18002998b  mov     rax, [rax+60h]
0x18002998f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029994  mov     edi, eax
0x180029996  test    eax, eax
0x180029998  jns     short loc_1800299A3
0x18002999a  lea     rdx, aGetusernameFai_0; "getUserName failed: 0x%x in %s"
0x1800299a1  jmp     short loc_180029A18
0x1800299a3  mov     rax, [rbx]
0x1800299a6  mov     rcx, rbx
0x1800299a9  mov     rdx, [rsp+2E0h+var_2A8]
0x1800299ae  mov     rax, [rax+20h]
0x1800299b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299b7  test    eax, eax
0x1800299b9  jz      short loc_1800299D1
0x1800299bb  lea     rdx, aRpcpopsecurity_0; "RpcPopSecurityDialog caller is not the "...
0x1800299c2  mov     ecx, 8; int
0x1800299c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800299cc  jmp     loc_180029910
0x1800299d1  mov     rcx, [rsp+2E0h+var_298]
0x1800299d6  lea     rdx, [rsp+2E0h+var_2B0]
0x1800299db  mov     rax, [rcx]
0x1800299de  mov     rax, [rax+30h]
0x1800299e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299e7  mov     edi, eax
0x1800299e9  test    eax, eax
0x1800299eb  jns     short loc_1800299F6
0x1800299ed  lea     rdx, aGetrestrictedc; "GetRestrictedCalls failed: 0x%x in %s"
0x1800299f4  jmp     short loc_180029A18
0x1800299f6  mov     rcx, [rsp+2E0h+var_2B0]
0x1800299fb  mov     edx, [rsp+2E0h+pSessionId]
0x1800299ff  mov     rax, [rcx]
0x180029a02  mov     rax, [rax+20h]
0x180029a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a0b  mov     edi, eax
0x180029a0d  test    eax, eax
0x180029a0f  jns     short loc_180029A28
0x180029a11  lea     rdx, aPopsecuritydia; "PopSecurityDialog failed: 0x%x in %s"
0x180029a18  mov     r8d, eax
0x180029a1b  mov     r9, r14
0x180029a1e  mov     ecx, 8; int
0x180029a23  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029a28  lea     rcx, [rsp+2E0h+var_280]; this
0x180029a2d  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180029a32  lea     rcx, [rsp+2E0h+var_2B8]; this
0x180029a37  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180029a3c  lea     rcx, [rsp+2E0h+var_2B0]; void *
0x180029a41  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180029a46  lea     rcx, [rsp+2E0h+var_2A8]; void *
0x180029a4b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180029a50  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x180029a55  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180029a5a  lea     rcx, [rsp+2E0h+var_298]; void *
0x180029a5f  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180029a64  lea     rcx, [rsp+2E0h+var_290]; void *
0x180029a69  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180029a6e  lea     rcx, [rsp+2E0h+var_288]; void *
0x180029a73  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180029a78  mov     eax, edi
0x180029a7a  mov     rcx, [rbp+1E0h+var_30]
0x180029a81  xor     rcx, rsp; StackCookie
0x180029a84  call    __security_check_cookie
0x180029a89  add     rsp, 2C0h
0x180029a90  pop     r15
0x180029a92  pop     r14
0x180029a94  pop     rdi
0x180029a95  pop     rbx
0x180029a96  pop     rbp
0x180029a97  retn
```
