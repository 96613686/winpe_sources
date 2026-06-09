# CVdsService::InitializeThread(void *)

- ea: `0x140009e70`
- end: `0x14000a05d`
- name: `?InitializeThread@CVdsService@@CAKPEAX@Z`
- size: `493`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140009e70`
- `0x14000a070`
- `0x14000a870`
- `0x14000a9c4`
- `0x14000ae70`
- `0x14000b5bc`
- `0x1400168c8`
- `0x1400171e8`
- `0x140017ca8`
- `0x14001ae08`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140009ecb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000a031`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140009ecb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000a031`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009ee8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000a044`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009ee8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000a044`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140009e97`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140009e97`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000a017`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14000a017`
- `vdsutil!VdsTraceEx` at `0x140009eb8`
- `vdsutil!VdsTraceEx` at `0x140009f36`
- `vdsutil!VdsTraceEx` at `0x140009eb8`
- `vdsutil!VdsTraceEx` at `0x140009f36`
- `vdsutil!?Initialize@CVdsPnPNotificationBase@@QEAAKXZ` at `0x140009f94`
- `vdsutil!?Initialize@CVdsPnPNotificationBase@@QEAAKXZ` at `0x140009f94`
- `vdsutil!?Initialize@CVdsAsyncObjectBase@@SAKXZ` at `0x140009f7f`
- `vdsutil!?Initialize@CVdsAsyncObjectBase@@SAKXZ` at `0x140009f7f`
- `vdsutil!AcquireRundownProtection` at `0x140009f1e`
- `vdsutil!AcquireRundownProtection` at `0x140009f1e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140009e8c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140009e8c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009ef4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a050`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009ef4`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000a050`
- `vdsutil!IsWinPE` at `0x140009f0b`
- `vdsutil!IsWinPE` at `0x140009f0b`
- `vdsutil!ReleaseRundownProtection` at `0x140009edd`
- `vdsutil!ReleaseRundownProtection` at `0x14000a03e`
- `vdsutil!ReleaseRundownProtection` at `0x140009edd`
- `vdsutil!ReleaseRundownProtection` at `0x14000a03e`

## string_xrefs

- `0x140009e79`: `CVdsService::InitializeThread()`
- `0x14000a010`: `fveapi.dll`
- `0x140009ead`: `CVdsService::InitializeThread: CoInitializeEx failed: %lX`
- `0x140009f2b`: `CVdsService::InitializeThread exiting due to shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::InitializeThread(PVOID Parameter)
{
  HRESULT v1; // eax
  char v2; // bp
  char v3; // si
  CVdsCallbackObject *v5; // rcx
  _BYTE v6[56]; // [rsp+20h] [rbp-38h] BYREF
  CVdsCallbackObject *v7; // [rsp+68h] [rbp+10h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v6, 0x5Eu, "CVdsService::InitializeThread()");
  v1 = CoInitializeEx(0, 0);
  if ( v1 >= 0 )
  {
    v2 = 1;
    CVdsService::m_bIsWinPE = IsWinPE();
    v3 = AcquireRundownProtection(&g_RundownRef);
    if ( v3 )
    {
      v7 = 0;
      ATL::CComObject<CVdsCallbackObject>::CreateInstance(&v7);
      CVdsService::m_pCallbackObject = v7;
      if ( v7 )
      {
        (*(void (__fastcall **)(CVdsCallbackObject *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( !CVdsCallbackObject::Initialize(v5)
          && !(unsigned int)CVdsAsyncObjectBase::Initialize()
          && !CVdsPnPNotificationBase::Initialize((CVdsPnPNotificationBase *)&CVdsService::m_PnPNotificationManager) )
        {
          CVdsService::InitializeNetworkShareConstants();
          if ( (int)CVdsService::LoadAndInitializeProviders(
                      VDS_PT_SOFTWARE,
                      (struct CRtlList *)CVdsService::m_lstSoftwareProviders,
                      0) >= 0 )
          {
            CVdsService::LoadAndInitializeProviders(
              VDS_PT_HARDWARE,
              (struct CRtlList *)CVdsService::m_lstHardwareProviders,
              &CVdsService::m_pVdsHardwareProviderList);
            CVdsService::LoadAndInitializeProviders(
              VDS_PT_VIRTUALDISK,
              (struct CRtlList *)CVdsService::m_lstVirtualDiskProviders,
              0);
            if ( !(unsigned int)CVdsService::AssignDisksToProviders(0) )
            {
              CVdsService::DumpUnallocatedDisks();
              CVdsService::LoadHbaPorts();
              CVdsService::LoadSasPorts();
              CVdsService::LoadIscsiInitiator();
              CVdsService::m_hFVEModule = LoadLibraryW(L"fveapi.dll");
              _InterlockedExchange(&CVdsService::m_lVdsStatus, 2);
              SetEvent(CVdsService::m_hProvidersLoadedEvent);
              ReleaseRundownProtection(&g_RundownRef);
              CoUninitialize();
              CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v6);
              return 0;
            }
          }
        }
      }
    }
    else
    {
      VdsTraceEx(94, 3, "CVdsService::InitializeThread exiting due to shutdown");
    }
  }
  else
  {
    v2 = 0;
    v3 = 0;
    VdsTraceEx(94, 0, "CVdsService::InitializeThread: CoInitializeEx failed: %lX", v1);
  }
  _InterlockedExchange(&CVdsService::m_lVdsStatus, 3);
  SetEvent(CVdsService::m_hProvidersLoadedEvent);
  if ( v3 )
    ReleaseRundownProtection(&g_RundownRef);
  if ( v2 )
    CoUninitialize();
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v6);
  return 1;
}

```

## disassembly

```asm
0x140009e70  push    rbx
0x140009e72  push    rbp
0x140009e73  push    rsi
0x140009e74  push    rdi
0x140009e75  sub     rsp, 38h
0x140009e79  lea     r8, aCvdsserviceIni_0; "CVdsService::InitializeThread()"
0x140009e80  mov     edi, 5Eh ; '^'
0x140009e85  mov     edx, edi
0x140009e87  lea     rcx, [rsp+58h+var_38]
0x140009e8c  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140009e92  nop
0x140009e93  xor     edx, edx; dwCoInit
0x140009e95  xor     ecx, ecx; pvReserved
0x140009e97  call    cs:__imp_CoInitializeEx
0x140009e9d  lea     ebx, [rdi-5Bh]
0x140009ea0  test    eax, eax
0x140009ea2  jns     short loc_140009F08
0x140009ea4  xor     bpl, bpl
0x140009ea7  xor     sil, sil
0x140009eaa  mov     r9d, eax
0x140009ead  lea     r8, aCvdsserviceIni_6; "CVdsService::InitializeThread: CoInitia"...
0x140009eb4  xor     edx, edx
0x140009eb6  mov     ecx, edi
0x140009eb8  call    cs:__imp_VdsTraceEx
0x140009ebe  xchg    ebx, cs:?m_lVdsStatus@CVdsService@@0JA; long CVdsService::m_lVdsStatus
0x140009ec4  mov     rcx, cs:?m_hProvidersLoadedEvent@CVdsService@@0PEAXEA; hEvent
0x140009ecb  call    cs:__imp_SetEvent
0x140009ed1  test    sil, sil
0x140009ed4  jz      short loc_140009EE3
0x140009ed6  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140009edd  call    cs:__imp_ReleaseRundownProtection
0x140009ee3  test    bpl, bpl
0x140009ee6  jz      short loc_140009EEF
0x140009ee8  call    cs:__imp_CoUninitialize
0x140009eee  nop
0x140009eef  lea     rcx, [rsp+58h+var_38]
0x140009ef4  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009efa  mov     eax, 1
0x140009eff  add     rsp, 38h
0x140009f03  pop     rdi
0x140009f04  pop     rsi
0x140009f05  pop     rbp
0x140009f06  pop     rbx
0x140009f07  retn
0x140009f08  mov     bpl, 1
0x140009f0b  call    cs:__imp_IsWinPE
0x140009f11  mov     cs:?m_bIsWinPE@CVdsService@@0HA, eax; int CVdsService::m_bIsWinPE
0x140009f17  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140009f1e  call    cs:__imp_AcquireRundownProtection
0x140009f24  mov     sil, al
0x140009f27  test    al, al
0x140009f29  jnz     short loc_140009F3E
0x140009f2b  lea     r8, aCvdsserviceIni_1; "CVdsService::InitializeThread exiting d"...
0x140009f32  mov     edx, ebx
0x140009f34  mov     ecx, edi
0x140009f36  call    cs:__imp_VdsTraceEx
0x140009f3c  jmp     short loc_140009EBE
0x140009f3e  mov     [rsp+58h+arg_8], 0
0x140009f47  lea     rcx, [rsp+58h+arg_8]
0x140009f4c  call    ?CreateInstance@?$CComObject@VCVdsCallbackObject@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CVdsCallbackObject>::CreateInstance(ATL::CComObject<CVdsCallbackObject> * *)
0x140009f51  mov     rcx, [rsp+58h+arg_8]
0x140009f56  mov     cs:?m_pCallbackObject@CVdsService@@0PEAVCVdsCallbackObject@@EA, rcx; CVdsCallbackObject * CVdsService::m_pCallbackObject
0x140009f5d  test    rcx, rcx
0x140009f60  jz      loc_140009EBE
0x140009f66  mov     rax, [rcx]
0x140009f69  mov     rax, [rax+8]
0x140009f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f72  call    ?Initialize@CVdsCallbackObject@@QEAAKXZ; CVdsCallbackObject::Initialize(void)
0x140009f77  test    eax, eax
0x140009f79  jnz     loc_140009EBE
0x140009f7f  call    cs:__imp_?Initialize@CVdsAsyncObjectBase@@SAKXZ; CVdsAsyncObjectBase::Initialize(void)
0x140009f85  test    eax, eax
0x140009f87  jnz     loc_140009EBE
0x140009f8d  lea     rcx, ?m_PnPNotificationManager@CVdsService@@2VCVdsPnPNotificationManager@@A; CVdsPnPNotificationManager CVdsService::m_PnPNotificationManager
0x140009f94  call    cs:__imp_?Initialize@CVdsPnPNotificationBase@@QEAAKXZ; CVdsPnPNotificationBase::Initialize(void)
0x140009f9a  test    eax, eax
0x140009f9c  jnz     loc_140009EBE
0x140009fa2  call    ?InitializeNetworkShareConstants@CVdsService@@CAXXZ; CVdsService::InitializeNetworkShareConstants(void)
0x140009fa7  xor     r8d, r8d; struct _VDSSVC_PROVIDER_LIST **
0x140009faa  lea     rdx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; struct CRtlList *
0x140009fb1  lea     ecx, [r8+1]; enum _VDS_PROVIDER_TYPE
0x140009fb5  call    ?LoadAndInitializeProviders@CVdsService@@CAJW4_VDS_PROVIDER_TYPE@@AEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z; CVdsService::LoadAndInitializeProviders(_VDS_PROVIDER_TYPE,CRtlList &,_VDSSVC_PROVIDER_LIST * *)
0x140009fba  test    eax, eax
0x140009fbc  js      loc_140009EBE
0x140009fc2  lea     r8, ?m_pVdsHardwareProviderList@CVdsService@@0PEAU_VDSSVC_PROVIDER_LIST@@EA; struct _VDSSVC_PROVIDER_LIST **
0x140009fc9  lea     rdx, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; struct CRtlList *
0x140009fd0  mov     edi, 2
0x140009fd5  mov     ecx, edi; enum _VDS_PROVIDER_TYPE
0x140009fd7  call    ?LoadAndInitializeProviders@CVdsService@@CAJW4_VDS_PROVIDER_TYPE@@AEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z; CVdsService::LoadAndInitializeProviders(_VDS_PROVIDER_TYPE,CRtlList &,_VDSSVC_PROVIDER_LIST * *)
0x140009fdc  xor     r8d, r8d; struct _VDSSVC_PROVIDER_LIST **
0x140009fdf  lea     rdx, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; struct CRtlList *
0x140009fe6  mov     ecx, ebx; enum _VDS_PROVIDER_TYPE
0x140009fe8  call    ?LoadAndInitializeProviders@CVdsService@@CAJW4_VDS_PROVIDER_TYPE@@AEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z; CVdsService::LoadAndInitializeProviders(_VDS_PROVIDER_TYPE,CRtlList &,_VDSSVC_PROVIDER_LIST * *)
0x140009fed  xor     ecx, ecx; int
0x140009fef  call    ?AssignDisksToProviders@CVdsService@@CAKH@Z; CVdsService::AssignDisksToProviders(int)
0x140009ff4  test    eax, eax
0x140009ff6  jnz     loc_140009EBE
0x140009ffc  call    ?DumpUnallocatedDisks@CVdsService@@SAXXZ; CVdsService::DumpUnallocatedDisks(void)
0x14000a001  call    ?LoadHbaPorts@CVdsService@@CAJXZ; CVdsService::LoadHbaPorts(void)
0x14000a006  call    ?LoadSasPorts@CVdsService@@CAJXZ; CVdsService::LoadSasPorts(void)
0x14000a00b  call    ?LoadIscsiInitiator@CVdsService@@CAJXZ; CVdsService::LoadIscsiInitiator(void)
0x14000a010  lea     rcx, LibFileName; "fveapi.dll"
0x14000a017  call    cs:__imp_LoadLibraryW
0x14000a01d  mov     cs:?m_hFVEModule@CVdsService@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CVdsService::m_hFVEModule
0x14000a024  xchg    edi, cs:?m_lVdsStatus@CVdsService@@0JA; long CVdsService::m_lVdsStatus
0x14000a02a  mov     rcx, cs:?m_hProvidersLoadedEvent@CVdsService@@0PEAXEA; hEvent
0x14000a031  call    cs:__imp_SetEvent
0x14000a037  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14000a03e  call    cs:__imp_ReleaseRundownProtection
0x14000a044  call    cs:__imp_CoUninitialize
0x14000a04a  nop
0x14000a04b  lea     rcx, [rsp+58h+var_38]
0x14000a050  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000a056  xor     eax, eax
0x14000a058  jmp     loc_140009EFF
```
