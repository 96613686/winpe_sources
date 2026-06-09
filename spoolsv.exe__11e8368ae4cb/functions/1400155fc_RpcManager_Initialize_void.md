# RpcManager::Initialize(void)

- ea: `0x1400155fc`
- end: `0x14001587b`
- name: `?Initialize@RpcManager@@SAJXZ`
- size: `639`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004f988`

## callees

- `0x140011ff8`
- `0x140014ba8`
- `0x140014e14`
- `0x1400155fc`
- `0x140015884`
- `0x140015984`
- `0x140015a40`
- `0x140023e50`
- `0x14002a344`
- `0x14002f030`
- `0x140050b5c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001585f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001585f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015869`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x14001581d`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x14001581d`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1400157f6`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x1400157f6`
- `RPCRT4!RpcStringFreeW` at `0x140015836`
- `RPCRT4!RpcStringFreeW` at `0x140015836`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x1400157cc`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x1400157cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015654`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140015654`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001569f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140015710`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001569f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140015710`

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
  dword_1400CA6A8 = NCoreLibrary::GetMaxTransportBufferSize(v1);
  qword_1400CA6C8 = (__int64)SecurityDescriptor;
  LastErrorAsFailHRNoBreak = 0;
  qword_1400CA478 = (__int64)SecurityDescriptor;
  dword_1400CA6F8 = NAsyncNotifyServer::TAsyncNotifyRPCObject::m_MaxNotificationSize;
  dword_1400CA798 = NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::m_MaxNotificationSize;
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
      qword_1400CA4A0[v5] = (__int64)v3;
    }
LABEL_13:
    hMem = 0;
  }
  NAsyncNotifyServer::TAsyncNotifyRPCObject::TAsyncNotifyRPCObject((NAsyncNotifyServer::TAsyncNotifyRPCObject *)v13);
  if ( LastErrorAsFailHRNoBreak >= 0 )
    LastErrorAsFailHRNoBreak = NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyRPCObject,_IRPCAsyncNotify_v1_0_epv_t>::InitializeInterfaceTemplates(
                                 v13,
                                 qword_1400CA6D0,
                                 qword_1400CA720);
  NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::TAsyncNotifyChannelRPCObject((NAsyncNotifyServer::TAsyncNotifyChannelRPCObject *)v12);
  if ( LastErrorAsFailHRNoBreak >= 0 )
    NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyChannelRPCObject,_IRPCAsyncNotifyChannel_v1_0_epv_t>::InitializeInterfaceTemplates(
      v12,
      qword_1400CA770,
      qword_1400CA7C0);
  v11 = 0;
  v10 = &TRemoteWinspool::`vftable';
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    NDPS_RPCLibrary::TRPCRemoteObject<TRemoteWinspool,_IRemoteWinspool_v1_0_epv_t>::InitializeInterfaceTemplates(
      &v10,
      qword_1400CA810,
      qword_1400CA860);
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
0x1400155fc  push    rbp
0x1400155fe  push    rbx
0x1400155ff  lea     rbp, [rsp-28h]
0x140015604  sub     rsp, 128h
0x14001560b  cmp     cs:?g_bTestMode@@3HA, 0; int g_bTestMode
0x140015612  jz      short loc_140015684
0x140015614  lea     rax, [rbp+30h+arg_0]
0x140015618  mov     [rbp+30h+arg_0], 4
0x14001561f  mov     [rsp+130h+pcbData], rax; pcbData
0x140015624  lea     r8, aIdletimeout; "IdleTimeout"
0x14001562b  lea     rax, ?m_timeout@RpcManager@@0KA; ulong RpcManager::m_timeout
0x140015632  mov     r9d, 18h; dwFlags
0x140015638  mov     [rsp+130h+pvData], rax; pvData
0x14001563d  lea     rdx, szPrintKey; "System\\CurrentControlSet\\Control\\Pri"...
0x140015644  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001564b  mov     [rsp+130h+pdwType], 0; pdwType
0x140015654  call    cs:__imp_RegGetValueW
0x14001565a  test    eax, eax
0x14001565c  jnz     short loc_14001567A
0x14001565e  lea     rdx, aEnteringDemand; "Entering demand-start mode because test"...
0x140015665  lea     rcx, aRpcmanagerInit; "RpcManager::Initialize"
0x14001566c  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140015671  mov     cs:?m_enabled@DemandStart@@2_NA, 1; bool DemandStart::m_enabled
0x140015678  jmp     short loc_140015684
0x14001567a  mov     cs:?m_timeout@RpcManager@@0KA, 258h; ulong RpcManager::m_timeout
0x140015684  xor     ebx, ebx
0x140015686  mov     [rbp+30h+SecurityDescriptor], 0
0x14001568e  xor     r9d, r9d; SecurityDescriptorSize
0x140015691  lea     r8, [rbp+30h+SecurityDescriptor]; SecurityDescriptor
0x140015695  lea     rcx, StringSecurityDescriptor; "D:(A;;0x100003;;;BU)(A;;0x1201bb;;;WD)("...
0x14001569c  lea     edx, [rbx+1]; StringSDRevision
0x14001569f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400156a5  test    eax, eax
0x1400156a7  jnz     short loc_1400156B0
0x1400156a9  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400156ae  mov     ebx, eax
0x1400156b0  test    ebx, ebx
0x1400156b2  js      loc_140015743
0x1400156b8  call    ?GetMaxTransportBufferSize@NCoreLibrary@@YAKXZ; NCoreLibrary::GetMaxTransportBufferSize(void)
0x1400156bd  mov     cs:dword_1400CA6A8, eax
0x1400156c3  lea     r8, [rbp+30h+hMem]; SecurityDescriptor
0x1400156c7  mov     rax, [rbp+30h+SecurityDescriptor]
0x1400156cb  lea     rcx, aDA0x100003BuA0_0; "D:(A;;0x100003;;;BU)(A;;0x1201bb;;;WD)("...
0x1400156d2  mov     cs:qword_1400CA6C8, rax
0x1400156d9  xor     ebx, ebx
0x1400156db  mov     cs:qword_1400CA478, rax
0x1400156e2  xor     r9d, r9d; SecurityDescriptorSize
0x1400156e5  mov     eax, cs:?m_MaxNotificationSize@TAsyncNotifyRPCObject@NAsyncNotifyServer@@0JA; long NAsyncNotifyServer::TAsyncNotifyRPCObject::m_MaxNotificationSize
0x1400156eb  mov     cs:dword_1400CA6F8, eax
0x1400156f1  mov     eax, cs:?m_MaxNotificationSize@TAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@0JA; long NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::m_MaxNotificationSize
0x1400156f7  lea     edx, [rbx+1]; StringSDRevision
0x1400156fa  mov     cs:dword_1400CA798, eax
0x140015700  mov     [rbp+30h+SecurityDescriptor], 0
0x140015708  mov     [rbp+30h+hMem], 0
0x140015710  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140015716  test    eax, eax
0x140015718  jnz     short loc_140015721
0x14001571a  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14001571f  mov     ebx, eax
0x140015721  test    ebx, ebx
0x140015723  js      short loc_14001574B
0x140015725  mov     rax, [rbp+30h+hMem]
0x140015729  xor     edx, edx
0x14001572b  lea     rcx, [rdx+rdx*4]
0x14001572f  inc     rdx
0x140015732  lea     r8, qword_1400CA4A0
0x140015739  mov     [r8+rcx*8], rax
0x14001573d  cmp     rdx, 2
0x140015741  jnz     short loc_14001572B
0x140015743  mov     [rbp+30h+hMem], 0
0x14001574b  lea     rcx, [rbp+30h+var_70]; this
0x14001574f  call    ??0TAsyncNotifyRPCObject@NAsyncNotifyServer@@QEAA@XZ; NAsyncNotifyServer::TAsyncNotifyRPCObject::TAsyncNotifyRPCObject(void)
0x140015754  test    ebx, ebx
0x140015756  js      short loc_140015771
0x140015758  lea     r8, qword_1400CA720
0x14001575f  lea     rdx, qword_1400CA6D0
0x140015766  lea     rcx, [rbp+30h+var_70]
0x14001576a  call    ?InitializeInterfaceTemplates@?$TRPCRemoteObject@VTAsyncNotifyRPCObject@NAsyncNotifyServer@@U_IRPCAsyncNotify_v1_0_epv_t@@@NDPS_RPCLibrary@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@0@Z; NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyRPCObject,_IRPCAsyncNotify_v1_0_epv_t>::InitializeInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,RPC_INTERFACE_TEMPLATEW *)
0x14001576f  mov     ebx, eax
0x140015771  lea     rcx, [rsp+130h+var_D0]; this
0x140015776  call    ??0TAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@QEAA@XZ; NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::TAsyncNotifyChannelRPCObject(void)
0x14001577b  test    ebx, ebx
0x14001577d  js      short loc_140015797
0x14001577f  lea     r8, qword_1400CA7C0
0x140015786  lea     rdx, qword_1400CA770
0x14001578d  lea     rcx, [rsp+130h+var_D0]
0x140015792  call    ?InitializeInterfaceTemplates@?$TRPCRemoteObject@VTAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@U_IRPCAsyncNotifyChannel_v1_0_epv_t@@@NDPS_RPCLibrary@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@0@Z; NDPS_RPCLibrary::TRPCRemoteObject<NAsyncNotifyServer::TAsyncNotifyChannelRPCObject,_IRPCAsyncNotifyChannel_v1_0_epv_t>::InitializeInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,RPC_INTERFACE_TEMPLATEW *)
0x140015797  mov     [rsp+130h+var_E8], 0
0x14001579f  lea     rax, ??_7TRemoteWinspool@@6B@; const TRemoteWinspool::`vftable'
0x1400157a6  mov     [rsp+130h+var_F0], rax
0x1400157ab  test    ebx, ebx
0x1400157ad  js      short loc_1400157E1
0x1400157af  lea     r8, qword_1400CA860
0x1400157b6  lea     rdx, qword_1400CA810
0x1400157bd  lea     rcx, [rsp+130h+var_F0]
0x1400157c2  call    ?InitializeInterfaceTemplates@?$TRPCRemoteObject@VTRemoteWinspool@@U_IRemoteWinspool_v1_0_epv_t@@@NDPS_RPCLibrary@@QEAAJPEAURPC_INTERFACE_TEMPLATEW@@0@Z; NDPS_RPCLibrary::TRPCRemoteObject<TRemoteWinspool,_IRemoteWinspool_v1_0_epv_t>::InitializeInterfaceTemplates(RPC_INTERFACE_TEMPLATEW *,RPC_INTERFACE_TEMPLATEW *)
0x1400157c7  mov     ecx, 8000h; ThreadStackSize
0x1400157cc  call    cs:__imp_RpcMgmtSetServerStackSize
0x1400157d2  mov     ebx, eax
0x1400157d4  test    eax, eax
0x1400157d6  jle     short loc_1400157E1
0x1400157d8  movzx   ebx, ax
0x1400157db  or      ebx, 80070000h
0x1400157e1  mov     [rbp+30h+PrincName], 0
0x1400157e9  test    ebx, ebx
0x1400157eb  js      short loc_140015832
0x1400157ed  lea     rdx, [rbp+30h+PrincName]; PrincName
0x1400157f1  mov     ecx, 9; AuthnSvc
0x1400157f6  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x1400157fc  mov     ebx, eax
0x1400157fe  test    eax, eax
0x140015800  jle     short loc_14001580B
0x140015802  movzx   ebx, ax
0x140015805  or      ebx, 80070000h
0x14001580b  test    ebx, ebx
0x14001580d  js      short loc_140015832
0x14001580f  mov     rcx, [rbp+30h+PrincName]; ServerPrincName
0x140015813  xor     r9d, r9d; Arg
0x140015816  xor     r8d, r8d; GetKeyFn
0x140015819  lea     edx, [r9+9]; AuthnSvc
0x14001581d  call    cs:__imp_RpcServerRegisterAuthInfoW
0x140015823  mov     ebx, eax
0x140015825  test    eax, eax
0x140015827  jle     short loc_140015832
0x140015829  movzx   ebx, ax
0x14001582c  or      ebx, 80070000h
0x140015832  lea     rcx, [rbp+30h+PrincName]; String
0x140015836  call    cs:__imp_RpcStringFreeW
0x14001583c  lea     rax, ??_7TRPCRunDownRemoteObject@NDPS_RPCLibrary@@6B@; const NDPS_RPCLibrary::TRPCRunDownRemoteObject::`vftable'
0x140015843  lea     rcx, [rsp+130h+var_D0]; this
0x140015848  mov     [rsp+130h+var_F0], rax
0x14001584d  call    ??1TAsyncNotifyChannelRPCObject@NAsyncNotifyServer@@UEAA@XZ; NAsyncNotifyServer::TAsyncNotifyChannelRPCObject::~TAsyncNotifyChannelRPCObject(void)
0x140015852  lea     rcx, [rbp+30h+var_70]; this
0x140015856  call    ??1TAsyncNotifyRPCObject@NAsyncNotifyServer@@UEAA@XZ; NAsyncNotifyServer::TAsyncNotifyRPCObject::~TAsyncNotifyRPCObject(void)
0x14001585b  mov     rcx, [rbp+30h+hMem]; hMem
0x14001585f  call    cs:__imp_LocalFree
0x140015865  mov     rcx, [rbp+30h+SecurityDescriptor]; hMem
0x140015869  call    cs:__imp_LocalFree
0x14001586f  mov     eax, ebx
0x140015871  add     rsp, 128h
0x140015878  pop     rbx
0x140015879  pop     rbp
0x14001587a  retn
```
