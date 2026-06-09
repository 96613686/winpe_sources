# RpcManager::Initialize(void)

- ea: `0x140016830`
- end: `0x140016ae6`
- name: `?Initialize@RpcManager@@SAJXZ`
- size: `694`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140054600`

## callees

- `0x140013160`
- `0x140015e84`
- `0x140016120`
- `0x140016830`
- `0x140016aec`
- `0x140016bf4`
- `0x140016cb8`
- `0x140025e40`
- `0x14002c84c`
- `0x140031720`
- `0x14005593c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016abd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016acd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016abd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016acd`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x140016a6f`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x140016a6f`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x140016a42`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x140016a42`
- `RPCRT4!RpcStringFreeW` at `0x140016a8e`
- `RPCRT4!RpcStringFreeW` at `0x140016a8e`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x140016a12`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x140016a12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016888`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016888`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400168d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140016950`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400168d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140016950`

## pseudocode

```c
__int64 RpcManager::Initialize(void)
{
  signed int LastErrorAsFailHRNoBreak; // ebx
  NCoreLibrary *v1; // rcx
  NCoreLibrary *v2; // rcx
  PSECURITY_DESCRIPTOR v3; // rax
  __int64 i; // rdx
  __int64 v5; // rcx
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  RPC_STATUS v8; // eax
  void **v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h]
  _BYTE v12[96]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[112]; // [rsp+C0h] [rbp-40h] BYREF
  DWORD pcbData; // [rsp+140h] [rbp+40h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+148h] [rbp+48h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+150h] [rbp+50h] BYREF
  RPC_WSTR PrincName; // [rsp+158h] [rbp+58h] BYREF

  if ( g_bTestMode )
  {
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Print",
           L"IdleTimeout",
           0x18u,
           0,
           &RpcManager::m_timeout,
           &pcbData) )
    {
      RpcManager::m_timeout = 600;
    }
    else
    {
      SpoolerServiceTelemetry::WriteDbgTraceInfo(
        "RpcManager::Initialize",
        L"Entering demand-start mode because test mode is enabled");
      DemandStart::m_enabled = 1;
    }
  }
  LastErrorAsFailHRNoBreak = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;0x100003;;;BU)(A;;0x1201bb;;;WD)(A;;0x1201bb;;;AN)(A;;0x1201bb;;;AC)(A;;0x1201bb;;;S-1-15-3-1024-4044835"
           "139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422)(A;;FA;;;CO)(A;;FA;;;SY)(A;;FA"
           ";;;BA)(A;;FA;;;S-1-5-99-216390572-1995538116-3857911515-2404958512-2623887229)S:(ML;;;;;S-1-16-0)",
          1u,
          &SecurityDescriptor,
          0) )
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v1);
  if ( LastErrorAsFailHRNoBreak < 0 )
    goto LABEL_13;
  dword_1400D16A8 = NCoreLibrary::GetMaxTransportBufferSize(v1);
  qword_1400D16C8 = (__int64)SecurityDescriptor;
  LastErrorAsFailHRNoBreak = 0;
  qword_1400D1478 = (__int64)SecurityDescriptor;
  dword_1400D16F8 = NAsyncNotifyServer::TAsyncNotifyRPCObject::m_MaxNotificationSize;
  dword_1400D1798 = NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::m_MaxNotificationSize;
  SecurityDescriptor = 0;
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;0x100003;;;BU)(A;;0x1201bb;;;WD)(A;;0x1201bb;;;AN)(A;;FA;;;CO)(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;S-1-5-99-"
           "216390572-1995538116-3857911515-2404958512-2623887229)S:(ML;;;;;S-1-16-0)",
          1u,
          &hMem,
          0) )
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v2);
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v3 = hMem;
    for ( i = 0; i != 2; ++i )
    {
      v5 = 5 * i;
      qword_1400D14A0[v5] = (__int64)v3;
    }
LABEL_13:
    hMem = 0;
  }
  NAsyncNotifyServer::TAsyncNotifyRPCObject::TAsyncNotifyRPCObject((NAsyncNotifyServer::TAsyncNotifyRPCObject *)v13);
  if ( LastErrorAsFailHRNoBreak >= 0 )
    LastErrorAsFailHRNoBreak = NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyRPCObject,_IRPCAsyncNotify_v1_0_epv_t>::InitializeInterfaceTemplates(
                                 v13,
                                 qword_1400D16D0,
                                 qword_1400D1720);
  NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::TAsyncNotifyChannelRPCObject((NAsyncNotifyServer::TAsyncNotifyChannelRPCObject *)v12);
  if ( LastErrorAsFailHRNoBreak >= 0 )
    NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyChannelRPCObject,_IRPCAsyncNotifyChannel_v1_0_epv_t>::InitializeInterfaceTemplates(
      v12,
      qword_1400D1770,
      qword_1400D17C0);
  v11 = 0;
  v10 = &TRemoteWinspool::`vftable';
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    NDPS_RPCLibrary::TRPCRemoteObject<TRemoteWinspool,_IRemoteWinspool_v1_0_epv_t>::InitializeInterfaceTemplates(
      &v10,
      qword_1400D1810,
      qword_1400D1860);
    v6 = RpcMgmtSetServerStackSize(0x8000u);
    LastErrorAsFailHRNoBreak = v6;
    if ( v6 > 0 )
      LastErrorAsFailHRNoBreak = (unsigned __int16)v6 | 0x80070000;
  }
  PrincName = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v7 = RpcServerInqDefaultPrincNameW(9u, &PrincName);
    LastErrorAsFailHRNoBreak = v7;
    if ( v7 > 0 )
      LastErrorAsFailHRNoBreak = (unsigned __int16)v7 | 0x80070000;
    if ( LastErrorAsFailHRNoBreak >= 0 )
    {
      v8 = RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0);
      LastErrorAsFailHRNoBreak = v8;
      if ( v8 > 0 )
        LastErrorAsFailHRNoBreak = (unsigned __int16)v8 | 0x80070000;
    }
  }
  RpcStringFreeW(&PrincName);
  v10 = &NDPS_RPCLibrary::TRPCRunDownRemoteObject::`vftable';
  NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::~TAsyncNotifyChannelRPCObject((NAsyncNotifyServer::TAsyncNotifyChannelRPCObject *)v12);
  NAsyncNotifyServer::TAsyncNotifyRPCObject::~TAsyncNotifyRPCObject((NAsyncNotifyServer::TAsyncNotifyRPCObject *)v13);
  LocalFree(hMem);
  LocalFree(SecurityDescriptor);
  return (unsigned int)LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x140016830  push    rbp
0x140016832  push    rbx
0x140016833  lea     rbp, [rsp-28h]
0x140016838  sub     rsp, 128h
0x14001683f  cmp     cs:?g_bTestMode@@3HA, 0; int g_bTestMode
0x140016846  jz      short loc_1400168BE
0x140016848  lea     rax, [rbp+30h+arg_0]
0x14001684c  mov     [rbp+30h+arg_0], 4
0x140016853  mov     [rsp+130h+pcbData], rax; pcbData
0x140016858  lea     r8, aIdletimeout; "IdleTimeout"
0x14001685f  lea     rax, ?m_timeout@RpcManager@@0KA; ulong RpcManager::m_timeout
0x140016866  mov     r9d, 18h; dwFlags
0x14001686c  mov     [rsp+130h+pvData], rax; pvData
0x140016871  lea     rdx, szPrintKey; "System\\CurrentControlSet\\Control\\Pri"...
0x140016878  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001687f  mov     [rsp+130h+pdwType], 0; pdwType
0x140016888  call    cs:__imp_RegGetValueW
0x14001688f  nop     dword ptr [rax+rax+00h]
0x140016894  test    eax, eax
0x140016896  jnz     short loc_1400168B4
0x140016898  lea     rdx, aEnteringDemand; "Entering demand-start mode because test"...
0x14001689f  lea     rcx, aRpcmanagerInit; "RpcManager::Initialize"
0x1400168a6  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400168ab  mov     cs:?m_enabled@DemandStart@@2_NA, 1; bool DemandStart::m_enabled
0x1400168b2  jmp     short loc_1400168BE
0x1400168b4  mov     cs:?m_timeout@RpcManager@@0KA, 258h; ulong RpcManager::m_timeout
0x1400168be  xor     ebx, ebx
0x1400168c0  mov     [rbp+30h+SecurityDescriptor], 0
0x1400168c8  xor     r9d, r9d; SecurityDescriptorSize
0x1400168cb  lea     r8, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x1400168cf  lea     rcx, StringSecurityDescriptor; "D:(A;;0x100003;;;BU)(A;;0x1201bb;;;WD)("...
0x1400168d6  lea     edx, [rbx+1]; StringSDRevision
0x1400168d9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400168e0  nop     dword ptr [rax+rax+00h]
0x1400168e5  test    eax, eax
0x1400168e7  jnz     short loc_1400168F0
0x1400168e9  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400168ee  mov     ebx, eax
0x1400168f0  test    ebx, ebx
0x1400168f2  js      loc_140016989
0x1400168f8  call    ?GetMaxTransportBufferSize@NCoreLibrary@@YAKXZ; NCoreLibrary::GetMaxTransportBufferSize(void)
0x1400168fd  mov     cs:dword_1400D16A8, eax
0x140016903  lea     r8, [rbp+30h+hMem]; SecurityDescriptor
0x140016907  mov     rax, [rbp+30h+SecurityDescriptor]
0x14001690b  lea     rcx, aDA0x100003BuA0_0; "D:(A;;0x100003;;;BU)(A;;0x1201bb;;;WD)("...
0x140016912  mov     cs:qword_1400D16C8, rax
0x140016919  xor     ebx, ebx
0x14001691b  mov     cs:qword_1400D1478, rax
0x140016922  xor     r9d, r9d; SecurityDescriptorSize
0x140016925  mov     eax, cs:?m_MaxNotificationSize@TAsyncNotifyRPCObject@NAsyncNotifyServer@@0JA; long NAsyncNotifyServer::TAsyncNotifyRPCObject::m_MaxNotificationSize
0x14001692b  mov     cs:dword_1400D16F8, eax
0x140016931  mov     eax, cs:?m_MaxNotificationSize@TAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@0JA; long NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::m_MaxNotificationSize
0x140016937  lea     edx, [rbx+1]; StringSDRevision
0x14001693a  mov     cs:dword_1400D1798, eax
0x140016940  mov     [rbp+30h+SecurityDescriptor], 0
0x140016948  mov     [rbp+30h+hMem], 0
0x140016950  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140016957  nop     dword ptr [rax+rax+00h]
0x14001695c  test    eax, eax
0x14001695e  jnz     short loc_140016967
0x140016960  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140016965  mov     ebx, eax
0x140016967  test    ebx, ebx
0x140016969  js      short loc_140016991
0x14001696b  mov     rax, [rbp+30h+hMem]
0x14001696f  xor     edx, edx
0x140016971  lea     rcx, [rdx+rdx*4]
0x140016975  inc     rdx
0x140016978  lea     r8, qword_1400D14A0
0x14001697f  mov     [r8+rcx*8], rax
0x140016983  cmp     rdx, 2
0x140016987  jnz     short loc_140016971
0x140016989  mov     [rbp+30h+hMem], 0
0x140016991  lea     rcx, [rbp+30h+var_70]; this
0x140016995  call    ??0TAsyncNotifyRPCObject@NAsyncNotifyServer@@QEAA@XZ; NAsyncNotifyServer::TAsyncNotifyRPCObject::TAsyncNotifyRPCObject(void)
0x14001699a  test    ebx, ebx
0x14001699c  js      short loc_1400169B7
0x14001699e  lea     r8, qword_1400D1720
0x1400169a5  lea     rdx, qword_1400D16D0
0x1400169ac  lea     rcx, [rbp+30h+var_70]
0x1400169b0  call    ?InitializeInterfaceTemplates@?$TRPCRemoteObject@VTAsyncNotifyRPCObject@NAsyncNotifyServer@@U_IRPCAsyncNotify_v1_0_epv_t@@@NDPS_RPCLibrary@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@0@Z; NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyRPCObject,_IRPCAsyncNotify_v1_0_epv_t>::InitializeInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,RPC_INTERFACE_TEMPLATEW *)
0x1400169b5  mov     ebx, eax
0x1400169b7  lea     rcx, [rsp+130h+var_D0]; this
0x1400169bc  call    ??0TAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@QEAA@XZ; NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::TAsyncNotifyChannelRPCObject(void)
0x1400169c1  test    ebx, ebx
0x1400169c3  js      short loc_1400169DD
0x1400169c5  lea     r8, qword_1400D17C0
0x1400169cc  lea     rdx, qword_1400D1770
0x1400169d3  lea     rcx, [rsp+130h+var_D0]
0x1400169d8  call    ?InitializeInterfaceTemplates@?$TRPCRemoteObject@VTAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@U_IRPCAsyncNotifyChannel_v1_0_epv_t@@@NDPS_RPCLibrary@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@0@Z; NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyChannelRPCObject,_IRPCAsyncNotifyChannel_v1_0_epv_t>::InitializeInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,RPC_INTERFACE_TEMPLATEW *)
0x1400169dd  mov     [rsp+130h+var_E8], 0
0x1400169e5  lea     rax, ??_7TRemoteWinspool@@6B@; const TRemoteWinspool::`vftable'
0x1400169ec  mov     [rsp+130h+var_F0], rax
0x1400169f1  test    ebx, ebx
0x1400169f3  js      short loc_140016A2D
0x1400169f5  lea     r8, qword_1400D1860
0x1400169fc  lea     rdx, qword_1400D1810
0x140016a03  lea     rcx, [rsp+130h+var_F0]
0x140016a08  call    ?InitializeInterfaceTemplates@?$TRPCRemoteObject@VTRemoteWinspool@@U_IRemoteWinspool_v1_0_epv_t@@@NDPS_RPCLibrary@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@0@Z; NDPS_RPCLibrary::TRPCRemoteObject<TRemoteWinspool,_IRemoteWinspool_v1_0_epv_t>::InitializeInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,RPC_INTERFACE_TEMPLATEW *)
0x140016a0d  mov     ecx, 8000h; ThreadStackSize
0x140016a12  call    cs:__imp_RpcMgmtSetServerStackSize
0x140016a19  nop     dword ptr [rax+rax+00h]
0x140016a1e  mov     ebx, eax
0x140016a20  test    eax, eax
0x140016a22  jle     short loc_140016A2D
0x140016a24  movzx   ebx, ax
0x140016a27  or      ebx, 80070000h
0x140016a2d  mov     [rbp+30h+PrincName], 0
0x140016a35  test    ebx, ebx
0x140016a37  js      short loc_140016A8A
0x140016a39  lea     rdx, [rbp+30h+PrincName]; PrincName
0x140016a3d  mov     ecx, 9; AuthnSvc
0x140016a42  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x140016a49  nop     dword ptr [rax+rax+00h]
0x140016a4e  mov     ebx, eax
0x140016a50  test    eax, eax
0x140016a52  jle     short loc_140016A5D
0x140016a54  movzx   ebx, ax
0x140016a57  or      ebx, 80070000h
0x140016a5d  test    ebx, ebx
0x140016a5f  js      short loc_140016A8A
0x140016a61  mov     rcx, [rbp+30h+PrincName]; ServerPrincName
0x140016a65  xor     r9d, r9d; Arg
0x140016a68  xor     r8d, r8d; GetKeyFn
0x140016a6b  lea     edx, [r9+9]; AuthnSvc
0x140016a6f  call    cs:__imp_RpcServerRegisterAuthInfoW
0x140016a76  nop     dword ptr [rax+rax+00h]
0x140016a7b  mov     ebx, eax
0x140016a7d  test    eax, eax
0x140016a7f  jle     short loc_140016A8A
0x140016a81  movzx   ebx, ax
0x140016a84  or      ebx, 80070000h
0x140016a8a  lea     rcx, [rbp+30h+PrincName]; String
0x140016a8e  call    cs:__imp_RpcStringFreeW
0x140016a95  nop     dword ptr [rax+rax+00h]
0x140016a9a  lea     rax, ??_7TRPCRunDownRemoteObject@NDPS_RPCLibrary@@6B@; const NDPS_RPCLibrary::TRPCRunDownRemoteObject::`vftable'
0x140016aa1  lea     rcx, [rsp+130h+var_D0]; this
0x140016aa6  mov     [rsp+130h+var_F0], rax
0x140016aab  call    ??1TAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@UEAA@XZ; NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::~TAsyncNotifyChannelRPCObject(void)
0x140016ab0  lea     rcx, [rbp+30h+var_70]; this
0x140016ab4  call    ??1TAsyncNotifyRPCObject@NAsyncNotifyServer@@UEAA@XZ; NAsyncNotifyServer::TAsyncNotifyRPCObject::~TAsyncNotifyRPCObject(void)
0x140016ab9  mov     rcx, [rbp+30h+hMem]; hMem
0x140016abd  call    cs:__imp_LocalFree
0x140016ac4  nop     dword ptr [rax+rax+00h]
0x140016ac9  mov     rcx, [rbp+30h+SecurityDescriptor]; hMem
0x140016acd  call    cs:__imp_LocalFree
0x140016ad4  nop     dword ptr [rax+rax+00h]
0x140016ad9  mov     eax, ebx
0x140016adb  add     rsp, 128h
0x140016ae2  pop     rbx
0x140016ae3  pop     rbp
0x140016ae4  retn
```
