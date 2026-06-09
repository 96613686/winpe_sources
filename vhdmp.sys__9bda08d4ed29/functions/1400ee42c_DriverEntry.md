# DriverEntry

- ea: `0x1400ee42c`
- end: `0x1400ee82d`
- name: `DriverEntry`
- size: `1025`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400ee010`

## callees

- `0x14001f980`
- `0x140023980`
- `0x140031e94`
- `0x140036284`
- `0x140045e10`
- `0x140049240`
- `0x14005e100`
- `0x1400cab60`
- `0x1400cc9a0`
- `0x1400ee078`
- `0x1400ee110`
- `0x1400ee1f0`
- `0x1400ee2ac`
- `0x1400ee42c`
- `0x1400ee834`
- `0x1400ee9dc`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1400ee58b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400ee58b`
- `ntoskrnl!ObfReferenceObject` at `0x1400ee802`
- `ntoskrnl!ObfReferenceObject` at `0x1400ee802`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400ee49c`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400ee49c`
- `storport!StorPortInitialize` at `0x1400ee767`
- `storport!StorPortInitialize` at `0x1400ee767`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  struct _VHD_GLOBAL_POLICY *v4; // rdx
  NTSTATUS NonGenericSecurityDescriptorFromSddlString; // ebx
  __int64 v6; // rcx
  __int64 i; // rax
  char **v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 *v14; // rax
  unsigned __int8 v15; // r8
  __int64 j; // rcx
  PDRIVER_OBJECT v17; // rcx
  _QWORD v19[32]; // [rsp+40h] [rbp-C0h] BYREF

  memset(v19, 0, 0xD0u);
  VhdmpDriverObject = DriverObject;
  McGenEventRegister_EtwRegister();
  wil_InitializeFeatureStaging();
  NonGenericSecurityDescriptorFromSddlString = ExInitializeLookasideListEx(
                                                 (PLOOKASIDE_LIST_EX)&WPP_MAIN_CB.Queue,
                                                 0,
                                                 0,
                                                 (POOL_TYPE)512,
                                                 0,
                                                 0x200u,
                                                 0x74444856u,
                                                 0);
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  VhdmpTraceBuffersInitialized = 1;
  NonGenericSecurityDescriptorFromSddlString = VhdmpiInitializeGlobalPolicyData(RegistryPath, v4);
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  for ( i = 0; i != 3; ++i )
  {
    v8 = Parsers[i];
    if ( *((_DWORD *)v8 + 9) < (unsigned int)VhdmpiMaximumTransferLength )
      VhdmpiMaximumTransferLength = *((_DWORD *)v8 + 9);
    v9 = *((unsigned int *)v8 + 12);
    if ( (unsigned int)v9 > VhdmpiMaximumSrbContextSize )
      VhdmpiMaximumSrbContextSize = *((_DWORD *)v8 + 12);
  }
  NonGenericSecurityDescriptorFromSddlString = VhdmpiCreateNonGenericSecurityDescriptorFromSddlString(
                                                 v6,
                                                 v9,
                                                 &VhdmpiVhdSecurityDescriptor);
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  NonGenericSecurityDescriptorFromSddlString = VhdmpiCreateNonGenericSecurityDescriptorFromSddlString(
                                                 v11,
                                                 v10,
                                                 &VhdmpiIsoSecurityDescriptor);
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  VhdmpiInitializeVhdScsiParser();
  VhdmpiInitializeIsoScsiParser();
  VhdmpBackingStoreHashTableLock = 0;
  v12 = 0;
  qword_14008A290 = -1;
  v13 = 0;
  do
  {
    ++v12;
    v14 = &VhdmpBackingStoreHashTable[v13];
    VhdmpBackingStoreHashTable[v13 + 1] = (__int64)&VhdmpBackingStoreHashTable[v13];
    v13 += 2;
    *v14 = (__int64)v14;
  }
  while ( v12 != 256 );
  KeInitializeSpinLock(&VhdmpSurfaceTableLock);
  NonGenericSecurityDescriptorFromSddlString = VhdmpiInitializeGlobalData();
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  memset(&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, 0, 0x200u);
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) = 16842751;
  HIWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) = -2047;
  VhdmpiEmptyISOBackingStore = (__int64)&IsoParser;
  dword_14008C840 = 2048;
  dword_14008C844 = 2048;
  qword_14008CF30 = (__int64)&qword_14008CF28;
  qword_14008CF28 = (__int64)&qword_14008CF28;
  qword_14008A2A0 = (__int64)&VhdSetList;
  VhdSetList = (__int64)&VhdSetList;
  qword_14008C838 = 1;
  qword_14008CC60 = 0;
  qword_14008CC68 = -1;
  qword_14008CA80 = 0;
  qword_14008CA88 = -1;
  qword_14008CC30 = 0;
  qword_14008CC38 = -1;
  qword_14008CA90 = 1;
  dword_14008CAA0 = 1;
  qword_14008A2A8 = 0;
  qword_14008A2B0 = -1;
  NonGenericSecurityDescriptorFromSddlString = VhdmpiInitializeThreadPool();
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  NonGenericSecurityDescriptorFromSddlString = VhdmpiInitializeSrbExtensionWorkQueues();
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  NonGenericSecurityDescriptorFromSddlString = VhdmpiInitializePrefetchEngine();
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
    goto LABEL_24;
  memset(v19, 0, 0xD0u);
  LODWORD(v19[0]) = 208;
  v19[1] = VhdmpInitialize;
  v19[3] = 0;
  v19[2] = VhdmpStartIo;
  v19[4] = VhdmpFindAdapter;
  v19[5] = VhdmpResetBus;
  v19[17] = VhdmpFreeAdapterResources;
  v19[20] = VhdmpInitializeTracing;
  v19[21] = VhdmpCleanupTracing;
  v19[15] = VhdmpAdapterControl;
  LODWORD(v19[23]) = 5;
  LODWORD(v19[8]) = 112;
  v19[9] = (unsigned int)VhdmpiSrbExtensionSize(0);
  HIDWORD(v19[8]) = 24;
  LODWORD(v19[11]) = 16842754;
  BYTE4(v19[11]) = 1;
  HIDWORD(v19[0]) = 0;
  NonGenericSecurityDescriptorFromSddlString = StorPortInitialize(DriverObject, RegistryPath, v19, 0);
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 1) )
    TraceEvents(
      "DriverEntry",
      0x2DFu,
      v15,
      1u,
      "VhdmpDriverEntry: StorPortInitialize returned 0x%08x",
      NonGenericSecurityDescriptorFromSddlString);
  if ( NonGenericSecurityDescriptorFromSddlString < 0 )
  {
LABEL_24:
    VhdmpiDriverUnload(DriverObject);
  }
  else
  {
    for ( j = 0; j != 28; ++j )
    {
      StorportIrpHandler[j] = (__int64)DriverObject->MajorFunction[j];
      DriverObject->MajorFunction[j] = (PDRIVER_DISPATCH)VhdmpFirstLevelIrpHandler;
    }
    v17 = VhdmpDriverObject;
    StorportDriverUnload = DriverObject->DriverUnload;
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)VhdmpiDriverUnload;
    ObfReferenceObject(v17);
  }
  return NonGenericSecurityDescriptorFromSddlString;
}

```

## disassembly

```asm
0x1400ee42c  push    rbp
0x1400ee42e  push    rbx
0x1400ee42f  push    rsi
0x1400ee430  push    rdi
0x1400ee431  push    r12
0x1400ee433  push    r13
0x1400ee435  push    r15
0x1400ee437  lea     rbp, [rsp-10h]
0x1400ee43c  sub     rsp, 110h
0x1400ee443  mov     rsi, rdx
0x1400ee446  mov     rdi, rcx
0x1400ee449  xor     edx, edx; Val
0x1400ee44b  lea     rcx, [rsp+140h+var_100]; void *
0x1400ee450  mov     r8d, 0D0h; Size
0x1400ee456  call    memset
0x1400ee45b  mov     cs:VhdmpDriverObject, rdi
0x1400ee462  call    McGenEventRegister_EtwRegister
0x1400ee467  call    wil_InitializeFeatureStaging
0x1400ee46c  xor     eax, eax
0x1400ee46e  lea     rcx, WPP_MAIN_CB.Queue; Lookaside
0x1400ee475  mov     [rsp+140h+Depth], ax; Depth
0x1400ee47a  xor     r8d, r8d; Free
0x1400ee47d  mov     eax, 200h
0x1400ee482  mov     [rsp+140h+Tag], 74444856h; Tag
0x1400ee48a  mov     [rsp+140h+Size], rax; Size
0x1400ee48f  mov     r9d, eax; PoolType
0x1400ee492  xor     edx, edx; Allocate
0x1400ee494  mov     [rsp+140h+Flags], 0; Flags
0x1400ee49c  call    cs:__imp_ExInitializeLookasideListEx
0x1400ee4a3  nop     dword ptr [rax+rax+00h]
0x1400ee4a8  mov     ebx, eax
0x1400ee4aa  test    eax, eax
0x1400ee4ac  js      loc_1400EE810
0x1400ee4b2  mov     r15d, 1
0x1400ee4b8  mov     rcx, rsi; StringIn
0x1400ee4bb  mov     cs:?VhdmpTraceBuffersInitialized@@3EA, r15b; uchar VhdmpTraceBuffersInitialized
0x1400ee4c2  call    ?VhdmpiInitializeGlobalPolicyData@@YAJPEAU_UNICODE_STRING@@PEAU_VHD_GLOBAL_POLICY@@@Z; VhdmpiInitializeGlobalPolicyData(_UNICODE_STRING *,_VHD_GLOBAL_POLICY *)
0x1400ee4c7  mov     ebx, eax
0x1400ee4c9  test    eax, eax
0x1400ee4cb  js      loc_1400EE810
0x1400ee4d1  xor     eax, eax
0x1400ee4d3  lea     r13, cs:140000000h
0x1400ee4da  mov     r8, ds:rva Parsers[r13+rax*8]
0x1400ee4e2  mov     edx, [r8+24h]
0x1400ee4e6  cmp     edx, cs:VhdmpiMaximumTransferLength
0x1400ee4ec  jnb     short loc_1400EE4F4
0x1400ee4ee  mov     cs:VhdmpiMaximumTransferLength, edx
0x1400ee4f4  mov     edx, [r8+30h]
0x1400ee4f8  cmp     edx, cs:VhdmpiMaximumSrbContextSize
0x1400ee4fe  jbe     short loc_1400EE506
0x1400ee500  mov     cs:VhdmpiMaximumSrbContextSize, edx
0x1400ee506  add     rax, r15
0x1400ee509  cmp     rax, 3
0x1400ee50d  jnz     short loc_1400EE4DA
0x1400ee50f  lea     r8, ?VhdmpiVhdSecurityDescriptor@@3PEAXEA; void * VhdmpiVhdSecurityDescriptor
0x1400ee516  call    VhdmpiCreateNonGenericSecurityDescriptorFromSddlString
0x1400ee51b  mov     ebx, eax
0x1400ee51d  test    eax, eax
0x1400ee51f  js      loc_1400EE810
0x1400ee525  lea     r8, ?VhdmpiIsoSecurityDescriptor@@3PEAXEA; void * VhdmpiIsoSecurityDescriptor
0x1400ee52c  call    VhdmpiCreateNonGenericSecurityDescriptorFromSddlString
0x1400ee531  mov     ebx, eax
0x1400ee533  test    eax, eax
0x1400ee535  js      loc_1400EE810
0x1400ee53b  call    VhdmpiInitializeVhdScsiParser
0x1400ee540  call    VhdmpiInitializeIsoScsiParser
0x1400ee545  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400ee549  mov     cs:VhdmpBackingStoreHashTableLock, 0
0x1400ee554  xor     edx, edx
0x1400ee556  mov     cs:qword_14008A290, r12
0x1400ee55d  xor     ecx, ecx
0x1400ee55f  lea     rax, rva VhdmpBackingStoreHashTable[r13]
0x1400ee566  add     rdx, r15
0x1400ee569  add     rax, rcx
0x1400ee56c  mov     [rcx+r13+8D318h], rax
0x1400ee574  add     rcx, 10h
0x1400ee578  mov     [rax], rax
0x1400ee57b  cmp     rdx, 100h
0x1400ee582  jnz     short loc_1400EE55F
0x1400ee584  lea     rcx, ?VhdmpSurfaceTableLock@@3_KA; SpinLock
0x1400ee58b  call    cs:__imp_KeInitializeSpinLock
0x1400ee592  nop     dword ptr [rax+rax+00h]
0x1400ee597  call    VhdmpiInitializeGlobalData
0x1400ee59c  mov     ebx, eax
0x1400ee59e  test    eax, eax
0x1400ee5a0  js      loc_1400EE810
0x1400ee5a6  xor     edx, edx; Val
0x1400ee5a8  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; void *
0x1400ee5af  mov     r8d, 200h; Size
0x1400ee5b5  call    memset
0x1400ee5ba  mov     eax, 0F801h
0x1400ee5bf  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, 100FFFFh
0x1400ee5c9  mov     word ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink+6, ax
0x1400ee5d0  lea     rax, IsoParser
0x1400ee5d7  mov     cs:VhdmpiEmptyISOBackingStore, rax
0x1400ee5de  mov     eax, 800h
0x1400ee5e3  mov     cs:dword_14008C840, eax
0x1400ee5e9  mov     cs:dword_14008C844, eax
0x1400ee5ef  lea     rax, qword_14008CF28
0x1400ee5f6  mov     cs:qword_14008CF30, rax
0x1400ee5fd  mov     cs:qword_14008CF28, rax
0x1400ee604  lea     rax, VhdSetList
0x1400ee60b  mov     cs:qword_14008A2A0, rax
0x1400ee612  mov     cs:VhdSetList, rax
0x1400ee619  mov     cs:qword_14008C838, r15
0x1400ee620  mov     cs:qword_14008CC60, 0
0x1400ee62b  mov     cs:qword_14008CC68, r12
0x1400ee632  mov     cs:qword_14008CA80, 0
0x1400ee63d  mov     cs:qword_14008CA88, r12
0x1400ee644  mov     cs:qword_14008CC30, 0
0x1400ee64f  mov     cs:qword_14008CC38, r12
0x1400ee656  mov     cs:qword_14008CA90, r15
0x1400ee65d  mov     cs:dword_14008CAA0, r15d
0x1400ee664  mov     cs:qword_14008A2A8, 0
0x1400ee66f  mov     cs:qword_14008A2B0, r12
0x1400ee676  call    VhdmpiInitializeThreadPool
0x1400ee67b  mov     ebx, eax
0x1400ee67d  test    eax, eax
0x1400ee67f  js      loc_1400EE810
0x1400ee685  call    VhdmpiInitializeSrbExtensionWorkQueues
0x1400ee68a  mov     ebx, eax
0x1400ee68c  test    eax, eax
0x1400ee68e  js      loc_1400EE810
0x1400ee694  call    ?VhdmpiInitializePrefetchEngine@@YAJXZ; VhdmpiInitializePrefetchEngine(void)
0x1400ee699  mov     ebx, eax
0x1400ee69b  test    eax, eax
0x1400ee69d  js      loc_1400EE810
0x1400ee6a3  mov     ebx, 0D0h
0x1400ee6a8  lea     rcx, [rsp+140h+var_100]; void *
0x1400ee6ad  mov     r8d, ebx; Size
0x1400ee6b0  xor     edx, edx; Val
0x1400ee6b2  call    memset
0x1400ee6b7  lea     rax, VhdmpInitialize
0x1400ee6be  mov     [rsp+140h+var_100], ebx
0x1400ee6c2  mov     [rsp+140h+var_F8], rax
0x1400ee6c7  xor     ecx, ecx
0x1400ee6c9  lea     rax, VhdmpStartIo
0x1400ee6d0  mov     [rsp+140h+var_E8], 0
0x1400ee6d9  mov     [rsp+140h+var_F0], rax
0x1400ee6de  lea     rax, VhdmpFindAdapter
0x1400ee6e5  mov     [rsp+140h+var_E0], rax
0x1400ee6ea  lea     rax, ?VhdmpResetBus@@YAEPEAXK@Z; VhdmpResetBus(void *,ulong)
0x1400ee6f1  mov     [rsp+140h+var_D8], rax
0x1400ee6f6  lea     rax, VhdmpFreeAdapterResources
0x1400ee6fd  mov     [rbp+40h+var_78], rax
0x1400ee701  lea     rax, ?VhdmpInitializeTracing@@YAXPEAX0@Z; VhdmpInitializeTracing(void *,void *)
0x1400ee708  mov     [rbp+40h+var_60], rax
0x1400ee70c  lea     rax, ?VhdmpCleanupTracing@@YAXPEAX@Z; VhdmpCleanupTracing(void *)
0x1400ee713  mov     [rbp+40h+var_58], rax
0x1400ee717  lea     rax, ?VhdmpAdapterControl@@YA?AW4_SCSI_ADAPTER_CONTROL_STATUS@@PEAXW4_SCSI_ADAPTER_CONTROL_TYPE@@0@Z; VhdmpAdapterControl(void *,_SCSI_ADAPTER_CONTROL_TYPE,void *)
0x1400ee71e  mov     [rbp+40h+var_88], rax
0x1400ee722  mov     [rbp+40h+var_48], 5
0x1400ee729  mov     [rbp+40h+var_C0], 70h ; 'p'
0x1400ee730  call    VhdmpiSrbExtensionSize
0x1400ee735  mov     rcx, rdi
0x1400ee738  mov     [rbp+40h+var_B8], eax
0x1400ee73b  xor     r9d, r9d
0x1400ee73e  mov     [rbp+40h+var_BC], 18h
0x1400ee745  lea     r8, [rsp+140h+var_100]
0x1400ee74a  mov     [rbp+40h+var_B4], 0
0x1400ee751  mov     rdx, rsi
0x1400ee754  mov     [rbp+40h+var_A8], 1010002h
0x1400ee75b  mov     [rbp+40h+var_A4], r15b
0x1400ee75f  mov     [rsp+140h+var_FC], 0
0x1400ee767  call    cs:__imp_StorPortInitialize
0x1400ee76e  nop     dword ptr [rax+rax+00h]
0x1400ee773  mov     ebx, eax
0x1400ee775  mov     r8d, 4
0x1400ee77b  mov     eax, cs:dword_1400876D0
0x1400ee781  cmp     eax, r8d
0x1400ee784  jbe     short loc_1400EE7BD
0x1400ee786  mov     rdx, r15
0x1400ee789  lea     rcx, dword_1400876D0
0x1400ee790  call    _tlgKeywordOn
0x1400ee795  test    al, al
0x1400ee797  jz      short loc_1400EE7BD
0x1400ee799  lea     rax, aVhdmpdriverent; "VhdmpDriverEntry: StorPortInitialize re"...
0x1400ee7a0  mov     dword ptr [rsp+140h+Size], ebx; char
0x1400ee7a4  mov     edx, 2DFh; int
0x1400ee7a9  mov     qword ptr [rsp+140h+Flags], rax; char *
0x1400ee7ae  mov     r9d, r15d; int
0x1400ee7b1  lea     rcx, aDriverentry; "DriverEntry"
0x1400ee7b8  call    TraceEvents
0x1400ee7bd  test    ebx, ebx
0x1400ee7bf  js      short loc_1400EE810
0x1400ee7c1  xor     ecx, ecx
0x1400ee7c3  mov     rax, [rdi+rcx*8+70h]
0x1400ee7c8  mov     rva StorportIrpHandler[r13+rcx*8], rax
0x1400ee7d0  lea     rax, ?VhdmpFirstLevelIrpHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VhdmpFirstLevelIrpHandler(_DEVICE_OBJECT *,_IRP *)
0x1400ee7d7  mov     [rdi+rcx*8+70h], rax
0x1400ee7dc  add     rcx, r15
0x1400ee7df  cmp     rcx, 1Ch
0x1400ee7e3  jnz     short loc_1400EE7C3
0x1400ee7e5  mov     rax, [rdi+68h]
0x1400ee7e9  mov     rcx, cs:VhdmpDriverObject; Object
0x1400ee7f0  mov     cs:?StorportDriverUnload@@3P6AXPEAU_DRIVER_OBJECT@@@ZEA, rax; void (*StorportDriverUnload)(_DRIVER_OBJECT *)
0x1400ee7f7  lea     rax, ?VhdmpiDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; VhdmpiDriverUnload(_DRIVER_OBJECT *)
0x1400ee7fe  mov     [rdi+68h], rax
0x1400ee802  call    cs:__imp_ObfReferenceObject
0x1400ee809  nop     dword ptr [rax+rax+00h]
0x1400ee80e  jmp     short loc_1400EE818
0x1400ee810  mov     rcx, rdi; struct _DRIVER_OBJECT *
0x1400ee813  call    ?VhdmpiDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; VhdmpiDriverUnload(_DRIVER_OBJECT *)
0x1400ee818  mov     eax, ebx
0x1400ee81a  add     rsp, 110h
0x1400ee821  pop     r15
0x1400ee823  pop     r13
0x1400ee825  pop     r12
0x1400ee827  pop     rdi
0x1400ee828  pop     rsi
0x1400ee829  pop     rbx
0x1400ee82a  pop     rbp
0x1400ee82b  retn
```
