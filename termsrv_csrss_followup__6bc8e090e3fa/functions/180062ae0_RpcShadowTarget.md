# RpcShadowTarget

- ea: `0x180062ae0`
- end: `0x180063028`
- name: `RpcShadowTarget`
- size: `1352`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008920`
- `0x180009940`
- `0x18000ba50`
- `0x18000c2a0`
- `0x18000f610`
- `0x18000f760`
- `0x1800139c0`
- `0x180015020`
- `0x18002558c`
- `0x180033f60`
- `0x18003dea0`
- `0x18005497c`
- `0x180062ae0`
- `0x18007d9d8`
- `0x1800ce010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180062eff`
- `RPCRT4!RpcRevertToSelf` at `0x180062eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062f9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062f9d`

## string_xrefs

- `0x180062c5a`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x180062b8e`: `pConfig`
- `0x180062d8a`: `Invalid config`

## pseudocode

```c
__int64 __fastcall RpcShadowTarget(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10,
        __int64 a11)
{
  const char *v14; // r8
  int v15; // edi
  int v16; // r15d
  int v17; // eax
  int v18; // ecx
  int v19; // r14d
  int ClientToken; // eax
  struct ITSSession *v21; // rbx
  int v22; // eax
  int v23; // eax
  int v24; // edx
  int StorageForSessionObject; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  bool v30; // sf
  __int64 *v31; // rdx
  int v32; // eax
  int UserNameDomain; // [rsp+60h] [rbp-A0h]
  int TokenHandle; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v37; // [rsp+70h] [rbp-90h] BYREF
  struct ITSObjectStorage *v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  void *v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  int (__fastcall ***v43)(_QWORD, __int64 *, __int64 *); // [rsp+A0h] [rbp-60h] BYREF
  struct IRemoteConnectionManager *v44; // [rsp+A8h] [rbp-58h] BYREF
  struct ITSSession *v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  __int64 v49; // [rsp+D0h] [rbp-30h]
  _BYTE v50[592]; // [rsp+E0h] [rbp-20h] BYREF

  v49 = a3;
  v48 = a5;
  v47 = a7;
  v46 = a9;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v39 = 0;
  v38 = 0;
  v41 = 0;
  TokenHandle = 0;
  v40 = 0;
  pv = 0;
  v37 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v50, 0, "RpcShadowTarget");
  if ( !a3 )
  {
    v14 = "pConfig";
LABEL_3:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v14, "RpcShadowTarget");
    v15 = -2147024809;
    goto LABEL_51;
  }
  if ( !a5 )
  {
    v14 = "pAddress";
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v14 = "pModuleData";
    goto LABEL_3;
  }
  if ( !a11 )
  {
    v14 = "szClientName";
    goto LABEL_3;
  }
  v16 = -2147467259;
  v17 = RCMRpcPrologueEx(a2, 0x10u, 0, 0, &v45, &TokenHandle);
  v15 = v17;
  if ( v17 < 0 )
  {
    v18 = 1;
    if ( v17 != -2147022646 )
      v18 = 4;
    _DbgPrintMessage(v18, "RCMRpcPrologue failed: 0x%x", (unsigned int)v17);
    goto LABEL_41;
  }
  v19 = 1;
  ClientToken = CRpcUtils::GetClientToken(&v40, 1);
  v15 = ClientToken;
  if ( ClientToken >= 0 )
  {
    v21 = v45;
    UserNameDomain = CHelper::GetUserNameDomain(v45, (unsigned __int16 **)&pv, &v37);
    v16 = UserNameDomain;
    if ( UserNameDomain >= 0 )
    {
      v22 = CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,unsigned short *>(
              (unsigned int)&CrimsonHelper::s_instance,
              (unsigned int)EVENT_TS_SHADOW_ATTEMPT,
              a11,
              (_DWORD)pv,
              (__int64)v37);
      if ( v22 < 0 )
        _DbgPrintMessage(4, "TS_RAISE_EVENT_3 failed: 0x%x", v22);
    }
    v23 = (*(__int64 (__fastcall **)(struct ITSSession *, int (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)v21 + 104LL))(
            v21,
            &v43);
    v15 = v23;
    if ( v23 < 0 )
    {
      _DbgPrintMessage(8, "GetTerminal failed: 0x%x in %s", v23, "RpcShadowTarget");
      goto LABEL_41;
    }
    if ( (**v43)(v43, qword_1800DD390, &v42) < 0
      || (v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, unsigned int, __int64, int, __int64, int, __int64))(*(_QWORD *)v42 + 488LL))(
                  v42,
                  v49,
                  a4,
                  v48,
                  a6,
                  v47,
                  a8,
                  v46,
                  a10,
                  a11),
          v15 == -2147467263) )
    {
      if ( a4 < 0x28E8 )
      {
        _DbgPrintMessage(8, "Invalid config");
LABEL_25:
        v15 = -2147024809;
        goto LABEL_40;
      }
      if ( a6 < 0x80 )
      {
        _DbgPrintMessage(8, "Invalid address size");
        goto LABEL_25;
      }
      StorageForSessionObject = CHelper::GetStorageForSessionObject(v21, v24, &v38);
      v15 = StorageForSessionObject;
      if ( StorageForSessionObject >= 0 )
      {
        if ( (*(int (__fastcall **)(struct ITSObjectStorage *, __int64 *, __int64 *))(*(_QWORD *)v38 + 32LL))(
               v38,
               qword_1800EAA98,
               &v41) >= 0 )
        {
          v19 = 0;
          SmartPtr<ITerminal>::operator=(&v39, v41);
        }
        else
        {
          GetInstanceOfRemoteConnectionManager(&v44);
          v26 = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, struct ITSSession *, __int64 *))(*(_QWORD *)v44 + 104LL))(
                  v44,
                  v21,
                  &v39);
          v15 = v26;
          if ( v26 < 0 )
          {
            _DbgPrintMessage(
              8,
              "RCM->GetInstanceOfShadowTarget failed: 0x%x in %s",
              (unsigned int)v26,
              "RpcShadowTarget");
            goto LABEL_40;
          }
          v27 = (*(__int64 (__fastcall **)(struct ITSObjectStorage *, __int64 *, __int64))(*(_QWORD *)v38 + 24LL))(
                  v38,
                  qword_1800EAA98,
                  v39);
          v15 = v27;
          if ( v27 < 0 )
          {
            _DbgPrintMessage(8, "Storage->Add failed: 0x%x in %s", (unsigned int)v27, "RpcShadowTarget");
            goto LABEL_40;
          }
        }
        v28 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int, __int64, int, __int64, void *))(*(_QWORD *)v39 + 32LL))(
                v39,
                v49,
                v48,
                v47,
                a8,
                v46,
                a10,
                a11,
                v40);
        v15 = v28;
        if ( v28 < 0 )
          _DbgPrintMessage(8, "ShadowTarget->ShadowTargetWorker failed: 0x%x in %s", v28, "RpcShadowTarget");
        if ( v19 )
          (*(void (__fastcall **)(struct ITSObjectStorage *, __int64 *))(*(_QWORD *)v38 + 40LL))(v38, qword_1800EAA98);
        goto LABEL_40;
      }
      _DbgPrintMessage(8, "getStorage failed: 0x%x in %s", (unsigned int)StorageForSessionObject, "RpcShadowTarget");
    }
LABEL_40:
    v16 = UserNameDomain;
    goto LABEL_41;
  }
  _DbgPrintMessage(8, "CRpcUtils::GetClientToken failed: 0x%x in %s", ClientToken, "RpcShadowTarget");
LABEL_41:
  if ( TokenHandle )
  {
    v29 = RpcRevertToSelf();
    v30 = v29 < 0;
    if ( v29 > 0 )
    {
      v29 = (unsigned __int16)v29 | 0x80070000;
      v30 = v29 < 0;
    }
    if ( v30 )
    {
      _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v29);
      v15 = -2147024891;
    }
  }
  if ( v16 >= 0 )
  {
    v31 = EVENT_TS_SHADOW_SUCCEEDED;
    if ( v15 < 0 )
      v31 = EVENT_TS_SHADOW_FAILED;
    v32 = CrimsonHelper::RaiseEvent<unsigned short *,unsigned short *,unsigned short *>(
            (unsigned int)&CrimsonHelper::s_instance,
            (_DWORD)v31,
            a11,
            (_DWORD)pv,
            (__int64)v37);
    if ( v32 < 0 )
      _DbgPrintMessage(4, "TS_RAISE_EVENT_3 failed: 0x%x", v32);
  }
LABEL_51:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v37 )
    CoTaskMemFree(v37);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v50);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v40);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v41);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v38);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v39);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v42);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v44);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v45);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180062ae0  mov     [rsp-8+arg_0], rbx
0x180062ae5  push    rbp
0x180062ae6  push    rsi
0x180062ae7  push    rdi
0x180062ae8  push    r12
0x180062aea  push    r13
0x180062aec  push    r14
0x180062aee  push    r15
0x180062af0  lea     rbp, [rsp-240h]
0x180062af8  sub     rsp, 340h
0x180062aff  mov     rax, cs:__security_cookie
0x180062b06  xor     rax, rsp
0x180062b09  mov     [rbp+270h+var_40], rax
0x180062b10  mov     rax, [rbp+270h+arg_40]
0x180062b17  lea     rcx, [rbp+270h+var_290]; this
0x180062b1b  mov     rdi, [rbp+270h+arg_20]
0x180062b22  xor     r15d, r15d
0x180062b25  mov     rsi, [rbp+270h+arg_30]
0x180062b2c  mov     r14, r8
0x180062b2f  mov     r13, [rbp+270h+arg_50]
0x180062b36  mov     ebx, edx
0x180062b38  mov     [rbp+270h+var_2A0], r8
0x180062b3c  xor     edx, edx; int
0x180062b3e  lea     r8, aRpcshadowtarge; "RpcShadowTarget"
0x180062b45  mov     [rbp+270h+var_2A8], rdi
0x180062b49  mov     [rbp+270h+var_2B0], rsi
0x180062b4d  mov     r12d, r9d
0x180062b50  mov     [rbp+270h+var_2B8], rax
0x180062b54  mov     [rbp+270h+var_2C0], r15
0x180062b58  mov     [rbp+270h+var_2C8], r15
0x180062b5c  mov     [rbp+270h+var_2D0], r15
0x180062b60  mov     [rbp+270h+var_2D8], r15
0x180062b64  mov     [rbp+270h+var_2F0], r15
0x180062b68  mov     [rsp+370h+var_2F8], r15
0x180062b6d  mov     [rbp+270h+var_2E0], r15
0x180062b71  mov     [rsp+370h+var_30C], r15d
0x180062b76  mov     [rbp+270h+var_2E8], r15
0x180062b7a  mov     [rsp+370h+pv], r15
0x180062b7f  mov     [rsp+370h+var_300], r15
0x180062b84  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180062b89  test    r14, r14
0x180062b8c  jnz     short loc_180062BB7
0x180062b8e  lea     r8, aPconfig; "pConfig"
0x180062b95  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x180062b9c  mov     ecx, 8; int
0x180062ba1  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180062ba8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062bad  mov     edi, 80070057h
0x180062bb2  jmp     loc_180062F7D
0x180062bb7  test    rdi, rdi
0x180062bba  jnz     short loc_180062BC5
0x180062bbc  lea     r8, aPaddress; "pAddress"
0x180062bc3  jmp     short loc_180062B95
0x180062bc5  test    rsi, rsi
0x180062bc8  jnz     short loc_180062BD3
0x180062bca  lea     r8, aPmoduledata; "pModuleData"
0x180062bd1  jmp     short loc_180062B95
0x180062bd3  test    r13, r13
0x180062bd6  jnz     short loc_180062BE1
0x180062bd8  lea     r8, aSzclientname; "szClientName"
0x180062bdf  jmp     short loc_180062B95
0x180062be1  xor     r9d, r9d; struct ITerminal **
0x180062be4  lea     rax, [rsp+370h+var_30C]
0x180062be9  mov     [rsp+370h+TokenHandle], rax; TokenHandle
0x180062bee  xor     r8d, r8d; int
0x180062bf1  lea     rax, [rbp+270h+var_2C0]
0x180062bf5  mov     ecx, ebx; unsigned int
0x180062bf7  mov     r15d, 80004005h
0x180062bfd  mov     [rsp+370h+var_350], rax; struct ITSSession **
0x180062c02  lea     edx, [r9+10h]; unsigned int
0x180062c06  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x180062c0b  mov     esi, 8
0x180062c10  mov     edi, eax
0x180062c12  lea     ebx, [rsi-4]
0x180062c15  test    eax, eax
0x180062c17  jns     short loc_180062C38
0x180062c19  cmp     eax, 800708CAh
0x180062c1e  lea     ecx, [rsi-7]
0x180062c21  mov     r8d, eax
0x180062c24  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x180062c2b  cmovnz  ecx, ebx; int
0x180062c2e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062c33  jmp     loc_180062EF8
0x180062c38  mov     r14d, 1
0x180062c3e  lea     rcx, [rbp+270h+var_2E8]; void **
0x180062c42  mov     edx, r14d; int
0x180062c45  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x180062c4a  mov     edi, eax
0x180062c4c  test    eax, eax
0x180062c4e  jns     short loc_180062C6D
0x180062c50  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x180062c57  mov     r8d, eax
0x180062c5a  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x180062c61  mov     ecx, esi; int
0x180062c63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062c68  jmp     loc_180062EF8
0x180062c6d  mov     rbx, [rbp+270h+var_2C0]
0x180062c71  lea     r8, [rsp+370h+var_300]; unsigned __int16 **
0x180062c76  mov     rcx, rbx; struct ITSSession *
0x180062c79  lea     rdx, [rsp+370h+pv]; unsigned __int16 **
0x180062c7e  call    ?GetUserNameDomain@CHelper@@SAJPEAUITSSession@@PEAPEAG1@Z; CHelper::GetUserNameDomain(ITSSession *,ushort * *,ushort * *)
0x180062c83  mov     [rsp+370h+var_310], eax
0x180062c87  mov     r15d, eax
0x180062c8a  test    eax, eax
0x180062c8c  js      short loc_180062CCB
0x180062c8e  mov     rcx, [rsp+370h+var_300]
0x180062c93  lea     rdx, EVENT_TS_SHADOW_ATTEMPT
0x180062c9a  mov     r9, [rsp+370h+pv]
0x180062c9f  mov     r8, r13
0x180062ca2  mov     [rsp+370h+var_350], rcx
0x180062ca7  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180062cae  call    ??$RaiseEvent@PEAGPEAGPEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG11@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,ushort *>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,ushort *)
0x180062cb3  test    eax, eax
0x180062cb5  jns     short loc_180062CCB
0x180062cb7  mov     r8d, eax
0x180062cba  lea     rdx, aTsRaiseEvent3F_0; "TS_RAISE_EVENT_3 failed: 0x%x"
0x180062cc1  mov     ecx, 4; int
0x180062cc6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062ccb  mov     rax, [rbx]
0x180062cce  lea     rdx, [rbp+270h+var_2D0]
0x180062cd2  mov     rcx, rbx
0x180062cd5  mov     rax, [rax+68h]
0x180062cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062cde  mov     edi, eax
0x180062ce0  test    eax, eax
0x180062ce2  jns     short loc_180062D01
0x180062ce4  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x180062ceb  mov     r8d, eax
0x180062cee  lea     rdx, aGetterminalFai; "GetTerminal failed: 0x%x in %s"
0x180062cf5  mov     ecx, esi; int
0x180062cf7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062cfc  jmp     loc_180062EF3
0x180062d01  mov     rcx, [rbp+270h+var_2D0]
0x180062d05  lea     r8, [rbp+270h+var_2D8]
0x180062d09  lea     rdx, qword_1800DD390
0x180062d10  mov     rax, [rcx]
0x180062d13  mov     rax, [rax]
0x180062d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d1b  mov     r15d, [rbp+270h+arg_28]
0x180062d22  test    eax, eax
0x180062d24  js      short loc_180062D81
0x180062d26  mov     rcx, [rbp+270h+var_2D8]
0x180062d2a  mov     r8d, r12d
0x180062d2d  mov     edx, [rbp+270h+arg_48]
0x180062d33  mov     r9, [rbp+270h+var_2A8]
0x180062d37  mov     [rsp+370h+var_328], r13
0x180062d3c  mov     rax, [rcx]
0x180062d3f  mov     dword ptr [rsp+370h+var_330], edx
0x180062d43  mov     rdx, [rbp+270h+var_2B8]
0x180062d47  mov     [rsp+370h+var_338], rdx
0x180062d4c  mov     edx, [rbp+270h+arg_38]
0x180062d52  mov     rax, [rax+1E8h]
0x180062d59  mov     [rsp+370h+var_340], edx
0x180062d5d  mov     rdx, [rbp+270h+var_2B0]
0x180062d61  mov     [rsp+370h+TokenHandle], rdx
0x180062d66  mov     rdx, [rbp+270h+var_2A0]
0x180062d6a  mov     dword ptr [rsp+370h+var_350], r15d
0x180062d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d74  mov     edi, eax
0x180062d76  cmp     eax, 80004001h
0x180062d7b  jnz     loc_180062EEE
0x180062d81  cmp     r12d, 28E8h
0x180062d88  jnb     short loc_180062DA2
0x180062d8a  lea     rdx, aInvalidConfig; "Invalid config"
0x180062d91  mov     ecx, esi; int
0x180062d93  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062d98  mov     edi, 80070057h
0x180062d9d  jmp     loc_180062EEE
0x180062da2  cmp     r15d, 80h
0x180062da9  jnb     short loc_180062DB4
0x180062dab  lea     rdx, aInvalidAddress; "Invalid address size"
0x180062db2  jmp     short loc_180062D91
0x180062db4  lea     r8, [rsp+370h+var_2F8]; struct ITSObjectStorage **
0x180062db9  mov     rcx, rbx; struct ITSSession *
0x180062dbc  call    ?GetStorageForSessionObject@CHelper@@SAJPEAUITSSession@@HPEAPEAVITSObjectStorage@@@Z; CHelper::GetStorageForSessionObject(ITSSession *,int,ITSObjectStorage * *)
0x180062dc1  mov     edi, eax
0x180062dc3  test    eax, eax
0x180062dc5  jns     short loc_180062DE4
0x180062dc7  lea     rdx, aGetstorageFail; "getStorage failed: 0x%x in %s"
0x180062dce  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x180062dd5  mov     r8d, eax
0x180062dd8  mov     ecx, esi; int
0x180062dda  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062ddf  jmp     loc_180062EEE
0x180062de4  mov     rcx, [rsp+370h+var_2F8]
0x180062de9  lea     r15, qword_1800EAA98
0x180062df0  lea     r8, [rbp+270h+var_2E0]
0x180062df4  mov     rdx, r15
0x180062df7  mov     rax, [rcx]
0x180062dfa  mov     rax, [rax+20h]
0x180062dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e03  test    eax, eax
0x180062e05  jns     short loc_180062E60
0x180062e07  lea     rcx, [rbp+270h+var_2C8]; struct IRemoteConnectionManager **
0x180062e0b  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180062e10  mov     rcx, [rbp+270h+var_2C8]
0x180062e14  lea     r8, [rbp+270h+var_2F0]
0x180062e18  mov     rdx, rbx
0x180062e1b  mov     rax, [rcx]
0x180062e1e  mov     rax, [rax+68h]
0x180062e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e27  mov     edi, eax
0x180062e29  test    eax, eax
0x180062e2b  jns     short loc_180062E36
0x180062e2d  lea     rdx, aRcmGetinstance; "RCM->GetInstanceOfShadowTarget failed: "...
0x180062e34  jmp     short loc_180062DCE
0x180062e36  mov     rcx, [rsp+370h+var_2F8]
0x180062e3b  mov     rdx, r15
0x180062e3e  mov     r8, [rbp+270h+var_2F0]
0x180062e42  mov     rax, [rcx]
0x180062e45  mov     rax, [rax+18h]
0x180062e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e4e  mov     edi, eax
0x180062e50  test    eax, eax
0x180062e52  jns     short loc_180062E70
0x180062e54  lea     rdx, aStorageAddFail; "Storage->Add failed: 0x%x in %s"
0x180062e5b  jmp     loc_180062DCE
0x180062e60  mov     rdx, [rbp+270h+var_2E0]
0x180062e64  lea     rcx, [rbp+270h+var_2F0]
0x180062e68  xor     r14d, r14d
0x180062e6b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180062e70  mov     rcx, [rbp+270h+var_2F0]
0x180062e74  mov     r10, [rbp+270h+var_2E8]
0x180062e78  mov     edx, [rbp+270h+arg_48]
0x180062e7e  mov     r9, [rbp+270h+var_2B0]
0x180062e82  mov     rax, [rcx]
0x180062e85  mov     r8, [rbp+270h+var_2A8]
0x180062e89  mov     [rsp+370h+var_330], r10
0x180062e8e  mov     [rsp+370h+var_338], r13
0x180062e93  mov     rax, [rax+20h]
0x180062e97  mov     [rsp+370h+var_340], edx
0x180062e9b  mov     rdx, [rbp+270h+var_2B8]
0x180062e9f  mov     [rsp+370h+TokenHandle], rdx
0x180062ea4  mov     edx, [rbp+270h+arg_38]
0x180062eaa  mov     dword ptr [rsp+370h+var_350], edx
0x180062eae  mov     rdx, [rbp+270h+var_2A0]
0x180062eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062eb7  mov     edi, eax
0x180062eb9  test    eax, eax
0x180062ebb  jns     short loc_180062ED5
0x180062ebd  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x180062ec4  mov     r8d, eax
0x180062ec7  lea     rdx, aShadowtargetSh; "ShadowTarget->ShadowTargetWorker failed"...
0x180062ece  mov     ecx, esi; int
0x180062ed0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062ed5  test    r14d, r14d
0x180062ed8  jz      short loc_180062EEE
0x180062eda  mov     rcx, [rsp+370h+var_2F8]
0x180062edf  mov     rdx, r15
0x180062ee2  mov     rax, [rcx]
0x180062ee5  mov     rax, [rax+28h]
0x180062ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062eee  mov     r15d, [rsp+370h+var_310]
0x180062ef3  mov     ebx, 4
0x180062ef8  cmp     [rsp+370h+var_30C], 0
0x180062efd  jz      short loc_180062F31
0x180062eff  call    cs:__imp_RpcRevertToSelf
0x180062f06  nop     dword ptr [rax+rax+00h]
0x180062f0b  test    eax, eax
0x180062f0d  jle     short loc_180062F19
0x180062f0f  movzx   eax, ax
0x180062f12  or      eax, 80070000h
0x180062f17  test    eax, eax
0x180062f19  jns     short loc_180062F31
0x180062f1b  mov     r8d, eax
0x180062f1e  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180062f25  mov     ecx, esi; int
0x180062f27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062f2c  mov     edi, 80070005h
0x180062f31  test    r15d, r15d
0x180062f34  js      short loc_180062F7D
0x180062f36  mov     rax, [rsp+370h+var_300]
0x180062f3b  lea     r8, EVENT_TS_SHADOW_FAILED
0x180062f42  mov     r9, [rsp+370h+pv]
0x180062f47  lea     rdx, EVENT_TS_SHADOW_SUCCEEDED
0x180062f4e  test    edi, edi
0x180062f50  mov     [rsp+370h+var_350], rax
0x180062f55  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180062f5c  cmovs   rdx, r8
0x180062f60  mov     r8, r13
0x180062f63  call    ??$RaiseEvent@PEAGPEAGPEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG11@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,ushort *>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,ushort *)
0x180062f68  test    eax, eax
0x180062f6a  jns     short loc_180062F7D
0x180062f6c  mov     r8d, eax
0x180062f6f  lea     rdx, aTsRaiseEvent3F_0; "TS_RAISE_EVENT_3 failed: 0x%x"
0x180062f76  mov     ecx, ebx; int
0x180062f78  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180062f7d  mov     rcx, [rsp+370h+pv]; pv
0x180062f82  test    rcx, rcx
0x180062f85  jz      short loc_180062F93
0x180062f87  call    cs:__imp_CoTaskMemFree
0x180062f8e  nop     dword ptr [rax+rax+00h]
0x180062f93  mov     rcx, [rsp+370h+var_300]; pv
0x180062f98  test    rcx, rcx
0x180062f9b  jz      short loc_180062FA9
0x180062f9d  call    cs:__imp_CoTaskMemFree
0x180062fa4  nop     dword ptr [rax+rax+00h]
0x180062fa9  lea     rcx, [rbp+270h+var_290]; this
0x180062fad  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180062fb2  lea     rcx, [rbp+270h+var_2E8]; this
  ... truncated ...
```
