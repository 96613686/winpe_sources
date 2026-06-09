# RpcPopSecurityDialog

- ea: `0x18002ad60`
- end: `0x18002b0dd`
- name: `RpcPopSecurityDialog`
- size: `893`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008110`
- `0x180009940`
- `0x18000ba50`
- `0x18000f610`
- `0x18000f760`
- `0x180012c90`
- `0x180013948`
- `0x1800139c0`
- `0x180015020`
- `0x18002ad60`
- `0x180033f60`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae6b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002ae5b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002ae5b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002ae27`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002ae27`
- `RPCRT4!RpcRevertToSelf` at `0x18002af06`
- `RPCRT4!RpcRevertToSelf` at `0x18002af26`
- `RPCRT4!RpcRevertToSelf` at `0x18002af06`
- `RPCRT4!RpcRevertToSelf` at `0x18002af26`
- `RPCRT4!RpcImpersonateClient` at `0x18002adef`
- `RPCRT4!RpcImpersonateClient` at `0x18002adef`

## string_xrefs

- `0x18002aeab`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18002ae14`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x18002ad88`: `RpcPopSecurityDialog`
- `0x18002afff`: `RpcPopSecurityDialog caller is not the same as the logged user`
- `0x18002b055`: `PopSecurityDialog failed: 0x%x in %s`

## pseudocode

```c
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
0x18002ad60  push    rbp
0x18002ad62  push    rbx
0x18002ad63  push    rdi
0x18002ad64  push    r14
0x18002ad66  push    r15
0x18002ad68  lea     rbp, [rsp-1C0h]
0x18002ad70  sub     rsp, 2C0h
0x18002ad77  mov     rax, cs:__security_cookie
0x18002ad7e  xor     rax, rsp
0x18002ad81  mov     [rbp+1E0h+var_30], rax
0x18002ad88  lea     r14, aRpcpopsecurity; "RpcPopSecurityDialog"
0x18002ad8f  mov     [rsp+2E0h+var_288], 0
0x18002ad98  mov     r8, r14; char *
0x18002ad9b  mov     [rsp+2E0h+var_290], 0
0x18002ada4  xor     edx, edx; int
0x18002ada6  mov     [rsp+2E0h+var_298], 0
0x18002adaf  lea     rcx, [rsp+2E0h+var_280]; this
0x18002adb4  mov     [rsp+2E0h+var_2A0], 0
0x18002adbd  mov     [rsp+2E0h+var_2A8], 0
0x18002adc6  mov     [rsp+2E0h+var_2B0], 0
0x18002adcf  mov     [rsp+2E0h+var_2B8], 0
0x18002add8  mov     [rsp+2E0h+pSessionId], 0
0x18002ade0  mov     [rsp+2E0h+Pid], 0
0x18002ade8  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18002aded  xor     ecx, ecx; BindingHandle
0x18002adef  call    cs:__imp_RpcImpersonateClient
0x18002adf6  nop     dword ptr [rax+rax+00h]
0x18002adfb  mov     edi, eax
0x18002adfd  mov     r15d, 80070000h
0x18002ae03  test    eax, eax
0x18002ae05  jle     short loc_18002AE0D
0x18002ae07  movzx   edi, ax
0x18002ae0a  or      edi, r15d
0x18002ae0d  test    edi, edi
0x18002ae0f  jns     short loc_18002AE20
0x18002ae11  mov     r8d, edi
0x18002ae14  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x18002ae1b  jmp     loc_18002B05F
0x18002ae20  lea     rdx, [rsp+2E0h+Pid]; Pid
0x18002ae25  xor     ecx, ecx; Binding
0x18002ae27  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002ae2e  nop     dword ptr [rax+rax+00h]
0x18002ae33  mov     edi, eax
0x18002ae35  test    eax, eax
0x18002ae37  jle     short loc_18002AE3F
0x18002ae39  movzx   edi, ax
0x18002ae3c  or      edi, r15d
0x18002ae3f  test    edi, edi
0x18002ae41  jns     short loc_18002AE52
0x18002ae43  mov     r8d, edi
0x18002ae46  lea     rdx, aIRpcbindinginq; "I_RpcBindingInqLocalClientPID failed: 0"...
0x18002ae4d  jmp     loc_18002AEF9
0x18002ae52  mov     ecx, [rsp+2E0h+Pid]; dwProcessId
0x18002ae56  lea     rdx, [rsp+2E0h+pSessionId]; pSessionId
0x18002ae5b  call    cs:__imp_ProcessIdToSessionId
0x18002ae62  nop     dword ptr [rax+rax+00h]
0x18002ae67  test    eax, eax
0x18002ae69  jnz     short loc_18002AE96
0x18002ae6b  call    cs:__imp_GetLastError
0x18002ae72  nop     dword ptr [rax+rax+00h]
0x18002ae77  mov     edi, eax
0x18002ae79  test    eax, eax
0x18002ae7b  jle     short loc_18002AE83
0x18002ae7d  movzx   edi, ax
0x18002ae80  or      edi, r15d
0x18002ae83  lea     rdx, aFailedToGetSes_3; "Failed to get session id"
0x18002ae8a  mov     ecx, 8; int
0x18002ae8f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ae94  jmp     short loc_18002AF06
0x18002ae96  mov     edx, 1; int
0x18002ae9b  lea     rcx, [rsp+2E0h+var_2B8]; void **
0x18002aea0  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x18002aea5  mov     edi, eax
0x18002aea7  test    eax, eax
0x18002aea9  jns     short loc_18002AEB4
0x18002aeab  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18002aeb2  jmp     short loc_18002AEF6
0x18002aeb4  lea     rcx, [rsp+2E0h+var_2A0]; struct IUserName **
0x18002aeb9  call    ?GetInstanceOfUserName@CUtils@@SAJPEAPEAUIUserName@@@Z; CUtils::GetInstanceOfUserName(IUserName * *)
0x18002aebe  mov     edi, eax
0x18002aec0  test    eax, eax
0x18002aec2  jns     short loc_18002AECD
0x18002aec4  lea     rdx, aCutilsGetinsta; "CUtils::GetInstanceOfUserName failed: 0"...
0x18002aecb  jmp     short loc_18002AEF6
0x18002aecd  mov     rbx, [rsp+2E0h+var_2A0]
0x18002aed2  xor     r8d, r8d
0x18002aed5  mov     rdx, [rsp+2E0h+var_2B8]
0x18002aeda  mov     rcx, rbx
0x18002aedd  mov     rax, [rbx]
0x18002aee0  mov     rax, [rax+18h]
0x18002aee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aee9  mov     edi, eax
0x18002aeeb  test    eax, eax
0x18002aeed  jns     short loc_18002AF26
0x18002aeef  lea     rdx, aPtrrequestorus; "ptrRequestorUserName->Initialize failed"...
0x18002aef6  mov     r8d, eax
0x18002aef9  mov     r9, r14
0x18002aefc  mov     ecx, 8; int
0x18002af01  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002af06  call    cs:__imp_RpcRevertToSelf
0x18002af0d  nop     dword ptr [rax+rax+00h]
0x18002af12  test    eax, eax
0x18002af14  jle     short loc_18002AF1E
0x18002af16  movzx   eax, ax
0x18002af19  or      eax, r15d
0x18002af1c  test    eax, eax
0x18002af1e  jns     loc_18002B06C
0x18002af24  jmp     short loc_18002AF40
0x18002af26  call    cs:__imp_RpcRevertToSelf
0x18002af2d  nop     dword ptr [rax+rax+00h]
0x18002af32  test    eax, eax
0x18002af34  jle     short loc_18002AF3E
0x18002af36  movzx   eax, ax
0x18002af39  or      eax, r15d
0x18002af3c  test    eax, eax
0x18002af3e  jns     short loc_18002AF5E
0x18002af40  mov     r8d, eax
0x18002af43  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18002af4a  mov     ecx, 8; int
0x18002af4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002af54  mov     edi, 80070005h
0x18002af59  jmp     loc_18002B06C
0x18002af5e  lea     rcx, [rsp+2E0h+var_298]; struct ISessionManager **
0x18002af63  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x18002af68  mov     edi, eax
0x18002af6a  test    eax, eax
0x18002af6c  jns     short loc_18002AF7A
0x18002af6e  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x18002af75  jmp     loc_18002B05C
0x18002af7a  lea     rcx, [rsp+2E0h+var_290]; struct ISessionList **
0x18002af7f  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x18002af84  mov     edi, eax
0x18002af86  test    eax, eax
0x18002af88  jns     short loc_18002AF96
0x18002af8a  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x18002af91  jmp     loc_18002B05C
0x18002af96  mov     rcx, [rsp+2E0h+var_290]
0x18002af9b  lea     r8, [rsp+2E0h+var_288]
0x18002afa0  mov     edx, [rsp+2E0h+pSessionId]
0x18002afa4  mov     rax, [rcx]
0x18002afa7  mov     rax, [rax+18h]
0x18002afab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afb0  mov     edi, eax
0x18002afb2  test    eax, eax
0x18002afb4  jns     short loc_18002AFC2
0x18002afb6  lea     rdx, aFindsessionbyi_0; "FindSessionById failed: 0x%x in %s"
0x18002afbd  jmp     loc_18002B05C
0x18002afc2  mov     rcx, [rsp+2E0h+var_288]
0x18002afc7  lea     rdx, [rsp+2E0h+var_2A8]
0x18002afcc  mov     rax, [rcx]
0x18002afcf  mov     rax, [rax+60h]
0x18002afd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afd8  mov     edi, eax
0x18002afda  test    eax, eax
0x18002afdc  jns     short loc_18002AFE7
0x18002afde  lea     rdx, aGetusernameFai_0; "getUserName failed: 0x%x in %s"
0x18002afe5  jmp     short loc_18002B05C
0x18002afe7  mov     rax, [rbx]
0x18002afea  mov     rcx, rbx
0x18002afed  mov     rdx, [rsp+2E0h+var_2A8]
0x18002aff2  mov     rax, [rax+20h]
0x18002aff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002affb  test    eax, eax
0x18002affd  jz      short loc_18002B015
0x18002afff  lea     rdx, aRpcpopsecurity_0; "RpcPopSecurityDialog caller is not the "...
0x18002b006  mov     ecx, 8; int
0x18002b00b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b010  jmp     loc_18002AF54
0x18002b015  mov     rcx, [rsp+2E0h+var_298]
0x18002b01a  lea     rdx, [rsp+2E0h+var_2B0]
0x18002b01f  mov     rax, [rcx]
0x18002b022  mov     rax, [rax+30h]
0x18002b026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b02b  mov     edi, eax
0x18002b02d  test    eax, eax
0x18002b02f  jns     short loc_18002B03A
0x18002b031  lea     rdx, aGetrestrictedc; "GetRestrictedCalls failed: 0x%x in %s"
0x18002b038  jmp     short loc_18002B05C
0x18002b03a  mov     rcx, [rsp+2E0h+var_2B0]
0x18002b03f  mov     edx, [rsp+2E0h+pSessionId]
0x18002b043  mov     rax, [rcx]
0x18002b046  mov     rax, [rax+20h]
0x18002b04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b04f  mov     edi, eax
0x18002b051  test    eax, eax
0x18002b053  jns     short loc_18002B06C
0x18002b055  lea     rdx, aPopsecuritydia; "PopSecurityDialog failed: 0x%x in %s"
0x18002b05c  mov     r8d, eax
0x18002b05f  mov     r9, r14
0x18002b062  mov     ecx, 8; int
0x18002b067  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002b06c  lea     rcx, [rsp+2E0h+var_280]; this
0x18002b071  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18002b076  lea     rcx, [rsp+2E0h+var_2B8]; this
0x18002b07b  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18002b080  lea     rcx, [rsp+2E0h+var_2B0]; void *
0x18002b085  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002b08a  lea     rcx, [rsp+2E0h+var_2A8]; void *
0x18002b08f  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002b094  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x18002b099  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002b09e  lea     rcx, [rsp+2E0h+var_298]; void *
0x18002b0a3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002b0a8  lea     rcx, [rsp+2E0h+var_290]; void *
0x18002b0ad  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002b0b2  lea     rcx, [rsp+2E0h+var_288]; void *
0x18002b0b7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002b0bc  mov     eax, edi
0x18002b0be  mov     rcx, [rbp+1E0h+var_30]
0x18002b0c5  xor     rcx, rsp; StackCookie
0x18002b0c8  call    __security_check_cookie
0x18002b0cd  add     rsp, 2C0h
0x18002b0d4  pop     r15
0x18002b0d6  pop     r14
0x18002b0d8  pop     rdi
0x18002b0d9  pop     rbx
0x18002b0da  pop     rbp
0x18002b0db  retn
```
