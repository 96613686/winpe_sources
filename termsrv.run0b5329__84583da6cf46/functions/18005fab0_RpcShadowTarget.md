# RpcShadowTarget

- ea: `0x18005fab0`
- end: `0x18005ffe5`
- name: `RpcShadowTarget`
- size: `1333`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800092f0`
- `0x18000a210`
- `0x18000bad0`
- `0x18000c2f0`
- `0x18000f080`
- `0x18000f1a0`
- `0x180013150`
- `0x1800148d0`
- `0x1800241f0`
- `0x1800321f0`
- `0x18003bd20`
- `0x180052248`
- `0x18005fab0`
- `0x18007a328`
- `0x1800c8010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18005fecf`
- `RPCRT4!RpcRevertToSelf` at `0x18005fecf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ff51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ff61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ff51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ff61`

## string_xrefs

- `0x18005fc2a`: `CRpcUtils::GetClientToken failed: 0x%x in %s`
- `0x18005fb5e`: `pConfig`
- `0x18005fd5a`: `Invalid config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    if ( (**v43)(v43, qword_1800D7370, &v42) < 0
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
               qword_1800E4A48,
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
                  qword_1800E4A48,
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
          (*(void (__fastcall **)(struct ITSObjectStorage *, __int64 *))(*(_QWORD *)v38 + 40LL))(v38, qword_1800E4A48);
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
0x18005fab0  mov     [rsp-8+arg_0], rbx
0x18005fab5  push    rbp
0x18005fab6  push    rsi
0x18005fab7  push    rdi
0x18005fab8  push    r12
0x18005faba  push    r13
0x18005fabc  push    r14
0x18005fabe  push    r15
0x18005fac0  lea     rbp, [rsp-240h]
0x18005fac8  sub     rsp, 340h
0x18005facf  mov     rax, cs:__security_cookie
0x18005fad6  xor     rax, rsp
0x18005fad9  mov     [rbp+270h+var_40], rax
0x18005fae0  mov     rax, [rbp+270h+arg_40]
0x18005fae7  lea     rcx, [rbp+270h+var_290]; this
0x18005faeb  mov     rdi, [rbp+270h+arg_20]
0x18005faf2  xor     r15d, r15d
0x18005faf5  mov     rsi, [rbp+270h+arg_30]
0x18005fafc  mov     r14, r8
0x18005faff  mov     r13, [rbp+270h+arg_50]
0x18005fb06  mov     ebx, edx
0x18005fb08  mov     [rbp+270h+var_2A0], r8
0x18005fb0c  xor     edx, edx; int
0x18005fb0e  lea     r8, aRpcshadowtarge; "RpcShadowTarget"
0x18005fb15  mov     [rbp+270h+var_2A8], rdi
0x18005fb19  mov     [rbp+270h+var_2B0], rsi
0x18005fb1d  mov     r12d, r9d
0x18005fb20  mov     [rbp+270h+var_2B8], rax
0x18005fb24  mov     [rbp+270h+var_2C0], r15
0x18005fb28  mov     [rbp+270h+var_2C8], r15
0x18005fb2c  mov     [rbp+270h+var_2D0], r15
0x18005fb30  mov     [rbp+270h+var_2D8], r15
0x18005fb34  mov     [rbp+270h+var_2F0], r15
0x18005fb38  mov     [rsp+370h+var_2F8], r15
0x18005fb3d  mov     [rbp+270h+var_2E0], r15
0x18005fb41  mov     [rsp+370h+var_30C], r15d
0x18005fb46  mov     [rbp+270h+var_2E8], r15
0x18005fb4a  mov     [rsp+370h+pv], r15
0x18005fb4f  mov     [rsp+370h+var_300], r15
0x18005fb54  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005fb59  test    r14, r14
0x18005fb5c  jnz     short loc_18005FB87
0x18005fb5e  lea     r8, aPconfig; "pConfig"
0x18005fb65  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x18005fb6c  mov     ecx, 8; int
0x18005fb71  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005fb78  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fb7d  mov     edi, 80070057h
0x18005fb82  jmp     loc_18005FF47
0x18005fb87  test    rdi, rdi
0x18005fb8a  jnz     short loc_18005FB95
0x18005fb8c  lea     r8, aPaddress; "pAddress"
0x18005fb93  jmp     short loc_18005FB65
0x18005fb95  test    rsi, rsi
0x18005fb98  jnz     short loc_18005FBA3
0x18005fb9a  lea     r8, aPmoduledata; "pModuleData"
0x18005fba1  jmp     short loc_18005FB65
0x18005fba3  test    r13, r13
0x18005fba6  jnz     short loc_18005FBB1
0x18005fba8  lea     r8, aSzclientname; "szClientName"
0x18005fbaf  jmp     short loc_18005FB65
0x18005fbb1  xor     r9d, r9d; struct ITerminal **
0x18005fbb4  lea     rax, [rsp+370h+var_30C]
0x18005fbb9  mov     [rsp+370h+TokenHandle], rax; TokenHandle
0x18005fbbe  xor     r8d, r8d; int
0x18005fbc1  lea     rax, [rbp+270h+var_2C0]
0x18005fbc5  mov     ecx, ebx; unsigned int
0x18005fbc7  mov     r15d, 80004005h
0x18005fbcd  mov     [rsp+370h+var_350], rax; struct ITSSession **
0x18005fbd2  lea     edx, [r9+10h]; unsigned int
0x18005fbd6  call    ?RCMRpcPrologueEx@@YAJKKHPEAPEAUITerminal@@PEAPEAUITSSession@@PEAH@Z; RCMRpcPrologueEx(ulong,ulong,int,ITerminal * *,ITSSession * *,int *)
0x18005fbdb  mov     esi, 8
0x18005fbe0  mov     edi, eax
0x18005fbe2  lea     ebx, [rsi-4]
0x18005fbe5  test    eax, eax
0x18005fbe7  jns     short loc_18005FC08
0x18005fbe9  cmp     eax, 800708CAh
0x18005fbee  lea     ecx, [rsi-7]
0x18005fbf1  mov     r8d, eax
0x18005fbf4  lea     rdx, aRcmrpcprologue; "RCMRpcPrologue failed: 0x%x"
0x18005fbfb  cmovnz  ecx, ebx; int
0x18005fbfe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fc03  jmp     loc_18005FEC8
0x18005fc08  mov     r14d, 1
0x18005fc0e  lea     rcx, [rbp+270h+var_2E8]; void **
0x18005fc12  mov     edx, r14d; int
0x18005fc15  call    ?GetClientToken@CRpcUtils@@SAJPEAPEAXH@Z; CRpcUtils::GetClientToken(void * *,int)
0x18005fc1a  mov     edi, eax
0x18005fc1c  test    eax, eax
0x18005fc1e  jns     short loc_18005FC3D
0x18005fc20  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x18005fc27  mov     r8d, eax
0x18005fc2a  lea     rdx, aCrpcutilsGetcl_0; "CRpcUtils::GetClientToken failed: 0x%x "...
0x18005fc31  mov     ecx, esi; int
0x18005fc33  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fc38  jmp     loc_18005FEC8
0x18005fc3d  mov     rbx, [rbp+270h+var_2C0]
0x18005fc41  lea     r8, [rsp+370h+var_300]; unsigned __int16 **
0x18005fc46  mov     rcx, rbx; struct ITSSession *
0x18005fc49  lea     rdx, [rsp+370h+pv]; unsigned __int16 **
0x18005fc4e  call    ?GetUserNameDomain@CHelper@@SAJPEAUITSSession@@PEAPEAG1@Z; CHelper::GetUserNameDomain(ITSSession *,ushort * *,ushort * *)
0x18005fc53  mov     [rsp+370h+var_310], eax
0x18005fc57  mov     r15d, eax
0x18005fc5a  test    eax, eax
0x18005fc5c  js      short loc_18005FC9B
0x18005fc5e  mov     rcx, [rsp+370h+var_300]
0x18005fc63  lea     rdx, EVENT_TS_SHADOW_ATTEMPT
0x18005fc6a  mov     r9, [rsp+370h+pv]
0x18005fc6f  mov     r8, r13
0x18005fc72  mov     [rsp+370h+var_350], rcx
0x18005fc77  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18005fc7e  call    ??$RaiseEvent@PEAGPEAGPEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG11@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,ushort *>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,ushort *)
0x18005fc83  test    eax, eax
0x18005fc85  jns     short loc_18005FC9B
0x18005fc87  mov     r8d, eax
0x18005fc8a  lea     rdx, aTsRaiseEvent3F_0; "TS_RAISE_EVENT_3 failed: 0x%x"
0x18005fc91  mov     ecx, 4; int
0x18005fc96  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fc9b  mov     rax, [rbx]
0x18005fc9e  lea     rdx, [rbp+270h+var_2D0]
0x18005fca2  mov     rcx, rbx
0x18005fca5  mov     rax, [rax+68h]
0x18005fca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcae  mov     edi, eax
0x18005fcb0  test    eax, eax
0x18005fcb2  jns     short loc_18005FCD1
0x18005fcb4  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x18005fcbb  mov     r8d, eax
0x18005fcbe  lea     rdx, aGetterminalFai; "GetTerminal failed: 0x%x in %s"
0x18005fcc5  mov     ecx, esi; int
0x18005fcc7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fccc  jmp     loc_18005FEC3
0x18005fcd1  mov     rcx, [rbp+270h+var_2D0]
0x18005fcd5  lea     r8, [rbp+270h+var_2D8]
0x18005fcd9  lea     rdx, qword_1800D7370
0x18005fce0  mov     rax, [rcx]
0x18005fce3  mov     rax, [rax]
0x18005fce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fceb  mov     r15d, [rbp+270h+arg_28]
0x18005fcf2  test    eax, eax
0x18005fcf4  js      short loc_18005FD51
0x18005fcf6  mov     rcx, [rbp+270h+var_2D8]
0x18005fcfa  mov     r8d, r12d
0x18005fcfd  mov     edx, [rbp+270h+arg_48]
0x18005fd03  mov     r9, [rbp+270h+var_2A8]
0x18005fd07  mov     [rsp+370h+var_328], r13
0x18005fd0c  mov     rax, [rcx]
0x18005fd0f  mov     dword ptr [rsp+370h+var_330], edx
0x18005fd13  mov     rdx, [rbp+270h+var_2B8]
0x18005fd17  mov     [rsp+370h+var_338], rdx
0x18005fd1c  mov     edx, [rbp+270h+arg_38]
0x18005fd22  mov     rax, [rax+1E8h]
0x18005fd29  mov     [rsp+370h+var_340], edx
0x18005fd2d  mov     rdx, [rbp+270h+var_2B0]
0x18005fd31  mov     [rsp+370h+TokenHandle], rdx
0x18005fd36  mov     rdx, [rbp+270h+var_2A0]
0x18005fd3a  mov     dword ptr [rsp+370h+var_350], r15d
0x18005fd3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd44  mov     edi, eax
0x18005fd46  cmp     eax, 80004001h
0x18005fd4b  jnz     loc_18005FEBE
0x18005fd51  cmp     r12d, 28E8h
0x18005fd58  jnb     short loc_18005FD72
0x18005fd5a  lea     rdx, aInvalidConfig; "Invalid config"
0x18005fd61  mov     ecx, esi; int
0x18005fd63  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fd68  mov     edi, 80070057h
0x18005fd6d  jmp     loc_18005FEBE
0x18005fd72  cmp     r15d, 80h
0x18005fd79  jnb     short loc_18005FD84
0x18005fd7b  lea     rdx, aInvalidAddress; "Invalid address size"
0x18005fd82  jmp     short loc_18005FD61
0x18005fd84  lea     r8, [rsp+370h+var_2F8]; struct ITSObjectStorage **
0x18005fd89  mov     rcx, rbx; struct ITSSession *
0x18005fd8c  call    ?GetStorageForSessionObject@CHelper@@SAJPEAUITSSession@@HPEAPEAVITSObjectStorage@@@Z; CHelper::GetStorageForSessionObject(ITSSession *,int,ITSObjectStorage * *)
0x18005fd91  mov     edi, eax
0x18005fd93  test    eax, eax
0x18005fd95  jns     short loc_18005FDB4
0x18005fd97  lea     rdx, aGetstorageFail; "getStorage failed: 0x%x in %s"
0x18005fd9e  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x18005fda5  mov     r8d, eax
0x18005fda8  mov     ecx, esi; int
0x18005fdaa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fdaf  jmp     loc_18005FEBE
0x18005fdb4  mov     rcx, [rsp+370h+var_2F8]
0x18005fdb9  lea     r15, qword_1800E4A48
0x18005fdc0  lea     r8, [rbp+270h+var_2E0]
0x18005fdc4  mov     rdx, r15
0x18005fdc7  mov     rax, [rcx]
0x18005fdca  mov     rax, [rax+20h]
0x18005fdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdd3  test    eax, eax
0x18005fdd5  jns     short loc_18005FE30
0x18005fdd7  lea     rcx, [rbp+270h+var_2C8]; struct IRemoteConnectionManager **
0x18005fddb  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x18005fde0  mov     rcx, [rbp+270h+var_2C8]
0x18005fde4  lea     r8, [rbp+270h+var_2F0]
0x18005fde8  mov     rdx, rbx
0x18005fdeb  mov     rax, [rcx]
0x18005fdee  mov     rax, [rax+68h]
0x18005fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdf7  mov     edi, eax
0x18005fdf9  test    eax, eax
0x18005fdfb  jns     short loc_18005FE06
0x18005fdfd  lea     rdx, aRcmGetinstance; "RCM->GetInstanceOfShadowTarget failed: "...
0x18005fe04  jmp     short loc_18005FD9E
0x18005fe06  mov     rcx, [rsp+370h+var_2F8]
0x18005fe0b  mov     rdx, r15
0x18005fe0e  mov     r8, [rbp+270h+var_2F0]
0x18005fe12  mov     rax, [rcx]
0x18005fe15  mov     rax, [rax+18h]
0x18005fe19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe1e  mov     edi, eax
0x18005fe20  test    eax, eax
0x18005fe22  jns     short loc_18005FE40
0x18005fe24  lea     rdx, aStorageAddFail; "Storage->Add failed: 0x%x in %s"
0x18005fe2b  jmp     loc_18005FD9E
0x18005fe30  mov     rdx, [rbp+270h+var_2E0]
0x18005fe34  lea     rcx, [rbp+270h+var_2F0]
0x18005fe38  xor     r14d, r14d
0x18005fe3b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18005fe40  mov     rcx, [rbp+270h+var_2F0]
0x18005fe44  mov     r10, [rbp+270h+var_2E8]
0x18005fe48  mov     edx, [rbp+270h+arg_48]
0x18005fe4e  mov     r9, [rbp+270h+var_2B0]
0x18005fe52  mov     rax, [rcx]
0x18005fe55  mov     r8, [rbp+270h+var_2A8]
0x18005fe59  mov     [rsp+370h+var_330], r10
0x18005fe5e  mov     [rsp+370h+var_338], r13
0x18005fe63  mov     rax, [rax+20h]
0x18005fe67  mov     [rsp+370h+var_340], edx
0x18005fe6b  mov     rdx, [rbp+270h+var_2B8]
0x18005fe6f  mov     [rsp+370h+TokenHandle], rdx
0x18005fe74  mov     edx, [rbp+270h+arg_38]
0x18005fe7a  mov     dword ptr [rsp+370h+var_350], edx
0x18005fe7e  mov     rdx, [rbp+270h+var_2A0]
0x18005fe82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe87  mov     edi, eax
0x18005fe89  test    eax, eax
0x18005fe8b  jns     short loc_18005FEA5
0x18005fe8d  lea     r9, aRpcshadowtarge; "RpcShadowTarget"
0x18005fe94  mov     r8d, eax
0x18005fe97  lea     rdx, aShadowtargetSh; "ShadowTarget->ShadowTargetWorker failed"...
0x18005fe9e  mov     ecx, esi; int
0x18005fea0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fea5  test    r14d, r14d
0x18005fea8  jz      short loc_18005FEBE
0x18005feaa  mov     rcx, [rsp+370h+var_2F8]
0x18005feaf  mov     rdx, r15
0x18005feb2  mov     rax, [rcx]
0x18005feb5  mov     rax, [rax+28h]
0x18005feb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005febe  mov     r15d, [rsp+370h+var_310]
0x18005fec3  mov     ebx, 4
0x18005fec8  cmp     [rsp+370h+var_30C], 0
0x18005fecd  jz      short loc_18005FEFB
0x18005fecf  call    cs:__imp_RpcRevertToSelf
0x18005fed5  test    eax, eax
0x18005fed7  jle     short loc_18005FEE3
0x18005fed9  movzx   eax, ax
0x18005fedc  or      eax, 80070000h
0x18005fee1  test    eax, eax
0x18005fee3  jns     short loc_18005FEFB
0x18005fee5  mov     r8d, eax
0x18005fee8  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18005feef  mov     ecx, esi; int
0x18005fef1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005fef6  mov     edi, 80070005h
0x18005fefb  test    r15d, r15d
0x18005fefe  js      short loc_18005FF47
0x18005ff00  mov     rax, [rsp+370h+var_300]
0x18005ff05  lea     r8, EVENT_TS_SHADOW_FAILED
0x18005ff0c  mov     r9, [rsp+370h+pv]
0x18005ff11  lea     rdx, EVENT_TS_SHADOW_SUCCEEDED
0x18005ff18  test    edi, edi
0x18005ff1a  mov     [rsp+370h+var_350], rax
0x18005ff1f  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18005ff26  cmovs   rdx, r8
0x18005ff2a  mov     r8, r13
0x18005ff2d  call    ??$RaiseEvent@PEAGPEAGPEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG11@Z; CrimsonHelper::RaiseEvent<ushort *,ushort *,ushort *>(_EVENT_DESCRIPTOR const &,ushort *,ushort *,ushort *)
0x18005ff32  test    eax, eax
0x18005ff34  jns     short loc_18005FF47
0x18005ff36  mov     r8d, eax
0x18005ff39  lea     rdx, aTsRaiseEvent3F_0; "TS_RAISE_EVENT_3 failed: 0x%x"
0x18005ff40  mov     ecx, ebx; int
0x18005ff42  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005ff47  mov     rcx, [rsp+370h+pv]; pv
0x18005ff4c  test    rcx, rcx
0x18005ff4f  jz      short loc_18005FF57
0x18005ff51  call    cs:__imp_CoTaskMemFree
0x18005ff57  mov     rcx, [rsp+370h+var_300]; pv
0x18005ff5c  test    rcx, rcx
0x18005ff5f  jz      short loc_18005FF67
0x18005ff61  call    cs:__imp_CoTaskMemFree
0x18005ff67  lea     rcx, [rbp+270h+var_290]; this
0x18005ff6b  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18005ff70  lea     rcx, [rbp+270h+var_2E8]; this
0x18005ff74  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18005ff79  lea     rcx, [rbp+270h+var_2E0]; void *
0x18005ff7d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
  ... truncated ...
```
