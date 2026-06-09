# VidKmIfCreate

- ea: `0x14008a720`
- end: `0x14008aade`
- name: `VidKmIfCreate`
- size: `958`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140081e00`

## callees

- `0x1400217a0`
- `0x14002f524`
- `0x14008a720`

## import_xrefs

- `winhvr!WinHvPostMessage2` at `0x14008a9ae`
- `winhvr!WinHvSetEndOfMessage2` at `0x14008a9a0`
- `winhvr!WinHvGetSintEventFlagsPhysicalPage` at `0x14008a992`
- `winhvr!WinHvSetPortProperty` at `0x14008a984`
- `winhvr!WinHvGetPortProperty` at `0x14008a976`
- `winhvr!WinHvSignalEventWithSchedulerAssist` at `0x14008a968`
- `winhvr!WinHvSignalEvent` at `0x14008a95a`
- `winhvr!WinHvDisconnectPort` at `0x14008a94c`
- `winhvr!WinHvConnectPort` at `0x14008a93e`
- `winhvr!WinHvDeletePort` at `0x14008a930`
- `winhvr!WinHvCreatePort` at `0x14008a91b`
- `winhvr!WinHvGetVpRegisters` at `0x14008a905`
- `winhvr!WinHvLookupPortId` at `0x14008a8f0`
- `winhvr!WinHvFreePortId` at `0x14008a8e2`
- `winhvr!WinHvAllocatePortId` at `0x14008a8d4`
- `winhvr!WinHvNtProcessorToVpIndex` at `0x14008a8c9`
- `winhvr!WinHvGetNextQueuedPort` at `0x14008a8be`
- `winhvr!WinHvSetEndOfMessage` at `0x14008a8b3`
- `winhvr!WinHvGetSintMessagePhysicalPage` at `0x14008a8a8`
- `winhvr!WinHvSetSint` at `0x14008a89d`
- `winhvr!WinHvFreePartitionSintIndex` at `0x14008a892`
- `winhvr!WinHvAllocatePartitionSintIndex` at `0x14008a887`

## string_xrefs

- `0x14008aa37`: `VidKmIfCreate`
- `0x14008aabe`: `VidKmIfCreate`

## pseudocode

```c
__int64 __fastcall VidKmIfCreate(__int64 a1)
{
  int v2; // ebx
  __int64 v4; // [rsp+20h] [rbp-E0h] BYREF
  int *v5; // [rsp+28h] [rbp-D8h]
  GUID *v6; // [rsp+30h] [rbp-D0h]
  __int64 v7; // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall *v8)(); // [rsp+40h] [rbp-C0h]
  __int64 v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+54h] [rbp-ACh]
  int v12; // [rsp+5Ch] [rbp-A4h]
  __int64 (__fastcall *v13)(); // [rsp+60h] [rbp-A0h]
  __int64 (__fastcall *v14)(); // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v15)(__int64, __int64, _QWORD *, size_t); // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v16)(int, int, int, int, __int64); // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v17)(); // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v18)(int, int, int, int, int); // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v19)(); // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v20)(__int64, __int64, int, char, __int64, __int64, __int64); // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v21)(); // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v22)(); // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v23)(__int64, __int64, __int64, unsigned int, unsigned __int64); // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v24)(int, int, int, int, __int64, int, __int64, __int64); // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v25)(int, int, int, int, __int64, __int64, __int64); // [rsp+C0h] [rbp-40h]
  __int64 (__fastcall *v26)(); // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v27)(); // [rsp+D0h] [rbp-30h]
  __int64 (__fastcall *v28)(char *, __int64, __int64, __int64, int, int, char, _QWORD *, __int64, _QWORD *); // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v29)(); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v30)(); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v31)(int, int, int, int, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v32)(); // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v33)(); // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v34)(); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v35)(); // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v37)(); // [rsp+120h] [rbp+20h]
  __int64 (__fastcall *v38)(__int64, __int64, __int64, void *, size_t, unsigned int *); // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v39)(int, int, int, int, int, char); // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v40)(); // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v41)(); // [rsp+140h] [rbp+40h]
  __int64 (__fastcall *v42)(_QWORD, _QWORD, _QWORD); // [rsp+148h] [rbp+48h]
  __int64 v43; // [rsp+150h] [rbp+50h]
  __int64 v44; // [rsp+158h] [rbp+58h]
  __int64 v45; // [rsp+160h] [rbp+60h]
  __int64 v46; // [rsp+168h] [rbp+68h]
  __int64 v47; // [rsp+170h] [rbp+70h]
  __int64 v48; // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v49)(_QWORD, _QWORD); // [rsp+180h] [rbp+80h]
  __int64 (*v50)(void); // [rsp+188h] [rbp+88h]
  __int64 v51; // [rsp+190h] [rbp+90h]
  __int64 (__fastcall *v52)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+198h] [rbp+98h]
  __int64 (__fastcall *v53)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD); // [rsp+1A0h] [rbp+A0h]
  __int64 (__fastcall *v54)(_QWORD, _QWORD); // [rsp+1A8h] [rbp+A8h]
  __int64 (__fastcall *v55)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD); // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v56)(_QWORD, _QWORD); // [rsp+1B8h] [rbp+B8h]
  __int64 v57; // [rsp+1C0h] [rbp+C0h]
  __int64 v58; // [rsp+1C8h] [rbp+C8h]
  __int64 (__fastcall *v59)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v60)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+1D8h] [rbp+D8h]
  __int64 v61; // [rsp+1E0h] [rbp+E0h]
  __int64 v62; // [rsp+1E8h] [rbp+E8h]
  __int64 v63; // [rsp+1F0h] [rbp+F0h]
  __int64 (__fastcall *v64)(int, int, int, int, char, __int64, __int64); // [rsp+1F8h] [rbp+F8h]
  __int64 (__fastcall *v65)(); // [rsp+200h] [rbp+100h]

  v10 = 65976;
  v11 = 0;
  v12 = 0;
  v36 = 0;
  v13 = VidKmIfInterfaceReference;
  v14 = VidKmIfInterfaceDereference;
  v15 = VidKmIfGetPartitionInformation;
  v16 = VidKmIfCreateMbSpecifyParentGpas;
  v17 = VidKmIfSetMbClientContext;
  v18 = VidKmIfSetMbClientNotifications;
  v19 = VidKmIfDestroyMb;
  v20 = VidKmIfGpaLockAcquire;
  v21 = VsmmCryptpDataAlignmentGetAesCbc;
  v22 = VidKmIfGpaLockCancel;
  v23 = VidKmIfGpaLockRelease;
  v24 = VidKmIfGetNumaNodeMap;
  v25 = VidKmIfCreateMbGpaRange;
  v26 = VidKmIfDestroyGpaRange;
  v27 = VidKmIfGetVaBackingProcess;
  v28 = VsmmVaGpaRangeKmifCreate;
  v29 = VsmmPhuKmifItemRegister;
  v30 = VsmmPhuKmifItemUnregister;
  v31 = VsmmPhuKmifItemLookup;
  v32 = VsmmPhuKmifItemMarkReady;
  v33 = VsmmPhuKmifItemMarkUnready;
  v34 = VsmmPhuKmifPersistGpaRange;
  v35 = VsmmPhuKmifPersistMemoryBlock;
  v37 = VidKmIfRegisterSynicEventCallback;
  v38 = VsmmPhuKmifItemGetData;
  v39 = VsmmPhuKmifItemSetData;
  v40 = VidKmifAttachDevice;
  v41 = VidKmifDetachDevice;
  v42 = WinHvAllocatePartitionSintIndex;
  v43 = WinHvFreePartitionSintIndex;
  v44 = WinHvSetSint;
  v45 = WinHvGetSintMessagePhysicalPage;
  v46 = WinHvSetEndOfMessage;
  v47 = WinHvGetNextQueuedPort;
  v48 = WinHvNtProcessorToVpIndex;
  v49 = WinHvAllocatePortId;
  v50 = WinHvFreePortId;
  v51 = WinHvLookupPortId;
  v52 = WinHvGetVpRegisters;
  v53 = WinHvCreatePort;
  v54 = WinHvDeletePort;
  v55 = WinHvConnectPort;
  v56 = WinHvDisconnectPort;
  v57 = WinHvSignalEvent;
  v58 = WinHvSignalEventWithSchedulerAssist;
  v59 = WinHvGetPortProperty;
  v60 = WinHvSetPortProperty;
  v61 = WinHvGetSintEventFlagsPhysicalPage;
  v62 = WinHvSetEndOfMessage2;
  v63 = WinHvPostMessage2;
  v64 = VidKmIfCreateMbSpecifyParentGpas2;
  v65 = VidKmIfDestroyGpaRange2;
  v5 = &v10;
  v6 = &GUID_VID_VSMM_INTERFACE;
  v4 = 48;
  v7 = 0;
  v9 = 0;
  v8 = VidUndockedKmEvtProcessQueryInterfaceRequest;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1824))(
         WdfDriverGlobals,
         a1,
         &v4);
  if ( v2 >= 0 )
  {
    v5 = &v10;
    v10 = 17433000;
    v6 = &GUID_VID_VSMM_INTERFACE_AH2025;
    v4 = 48;
    v7 = 0;
    v9 = 0;
    v8 = VidUndockedKmEvtProcessQueryInterfaceRequest;
    v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1824))(
           WdfDriverGlobals,
           a1,
           &v4);
    if ( v2 >= 0 )
      return 0;
    else
      VidTraceErrorStatusInternal0("VidKmIfCreate", "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c", 489);
  }
  else
  {
    VidTraceErrorStatusInternal0("VidKmIfCreate", "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c", 460);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14008a720  push    rbp
0x14008a722  push    rbx
0x14008a723  push    rdi
0x14008a724  push    r15
0x14008a726  lea     rbp, [rsp-118h]
0x14008a72e  sub     rsp, 218h
0x14008a735  xor     eax, eax
0x14008a737  mov     [rsp+230h+var_1E0], 101B8h
0x14008a73f  mov     [rsp+230h+var_1DC], rax
0x14008a744  mov     rdi, rcx
0x14008a747  mov     [rsp+230h+var_1D4], eax
0x14008a74b  mov     [rbp+130h+var_118], rax
0x14008a74f  lea     rax, VidKmIfInterfaceReference
0x14008a756  mov     [rsp+230h+var_1D0], rax
0x14008a75b  lea     rax, VidKmIfInterfaceDereference
0x14008a762  mov     [rsp+230h+var_1C8], rax
0x14008a767  lea     rax, VidKmIfGetPartitionInformation
0x14008a76e  mov     [rsp+230h+var_1C0], rax
0x14008a773  lea     rax, VidKmIfCreateMbSpecifyParentGpas
0x14008a77a  mov     [rsp+230h+var_1B8], rax
0x14008a77f  lea     rax, VidKmIfSetMbClientContext
0x14008a786  mov     [rbp+130h+var_1B0], rax
0x14008a78a  lea     rax, VidKmIfSetMbClientNotifications
0x14008a791  mov     [rbp+130h+var_1A8], rax
0x14008a795  lea     rax, VidKmIfDestroyMb
0x14008a79c  mov     [rbp+130h+var_1A0], rax
0x14008a7a0  lea     rax, VidKmIfGpaLockAcquire
0x14008a7a7  mov     [rbp+130h+var_198], rax
0x14008a7ab  lea     rax, VsmmCryptpDataAlignmentGetAesCbc
0x14008a7b2  mov     [rbp+130h+var_190], rax
0x14008a7b6  lea     rax, VidKmIfGpaLockCancel
0x14008a7bd  mov     [rbp+130h+var_188], rax
0x14008a7c1  lea     rax, VidKmIfGpaLockRelease
0x14008a7c8  mov     [rbp+130h+var_180], rax
0x14008a7cc  lea     rax, VidKmIfGetNumaNodeMap
0x14008a7d3  mov     [rbp+130h+var_178], rax
0x14008a7d7  lea     rax, VidKmIfCreateMbGpaRange
0x14008a7de  mov     [rbp+130h+var_170], rax
0x14008a7e2  lea     rax, VidKmIfDestroyGpaRange
0x14008a7e9  mov     [rbp+130h+var_168], rax
0x14008a7ed  lea     rax, VidKmIfGetVaBackingProcess
0x14008a7f4  mov     [rbp+130h+var_160], rax
0x14008a7f8  lea     rax, VsmmVaGpaRangeKmifCreate
0x14008a7ff  mov     [rbp+130h+var_158], rax
0x14008a803  lea     rax, VsmmPhuKmifItemRegister
0x14008a80a  mov     [rbp+130h+var_150], rax
0x14008a80e  lea     rax, VsmmPhuKmifItemUnregister
0x14008a815  mov     [rbp+130h+var_148], rax
0x14008a819  lea     rax, VsmmPhuKmifItemLookup
0x14008a820  mov     [rbp+130h+var_140], rax
0x14008a824  lea     rax, VsmmPhuKmifItemMarkReady
0x14008a82b  mov     [rbp+130h+var_138], rax
0x14008a82f  lea     rax, VsmmPhuKmifItemMarkUnready
0x14008a836  mov     [rbp+130h+var_130], rax
0x14008a83a  lea     rax, VsmmPhuKmifPersistGpaRange
0x14008a841  mov     [rbp+130h+var_128], rax
0x14008a845  lea     rax, VsmmPhuKmifPersistMemoryBlock
0x14008a84c  mov     [rbp+130h+var_120], rax
0x14008a850  lea     rax, VidKmIfRegisterSynicEventCallback
0x14008a857  mov     [rbp+130h+var_110], rax
0x14008a85b  lea     rax, VsmmPhuKmifItemGetData
0x14008a862  mov     [rbp+130h+var_108], rax
0x14008a866  lea     rax, VsmmPhuKmifItemSetData
0x14008a86d  mov     [rbp+130h+var_100], rax
0x14008a871  lea     rax, VidKmifAttachDevice
0x14008a878  mov     [rbp+130h+var_F8], rax
0x14008a87c  lea     rax, VidKmifDetachDevice
0x14008a883  mov     [rbp+130h+var_F0], rax
0x14008a887  mov     rax, cs:__imp_WinHvAllocatePartitionSintIndex
0x14008a88e  mov     [rbp+130h+var_E8], rax
0x14008a892  mov     rax, cs:__imp_WinHvFreePartitionSintIndex
0x14008a899  mov     [rbp+130h+var_E0], rax
0x14008a89d  mov     rax, cs:__imp_WinHvSetSint
0x14008a8a4  mov     [rbp+130h+var_D8], rax
0x14008a8a8  mov     rax, cs:__imp_WinHvGetSintMessagePhysicalPage
0x14008a8af  mov     [rbp+130h+var_D0], rax
0x14008a8b3  mov     rax, cs:__imp_WinHvSetEndOfMessage
0x14008a8ba  mov     [rbp+130h+var_C8], rax
0x14008a8be  mov     rax, cs:__imp_WinHvGetNextQueuedPort
0x14008a8c5  mov     [rbp+130h+var_C0], rax
0x14008a8c9  mov     rax, cs:__imp_WinHvNtProcessorToVpIndex
0x14008a8d0  mov     [rbp+130h+var_B8], rax
0x14008a8d4  mov     rax, cs:__imp_WinHvAllocatePortId
0x14008a8db  mov     [rbp+130h+var_B0], rax
0x14008a8e2  mov     rax, cs:__imp_WinHvFreePortId
0x14008a8e9  mov     [rbp+130h+var_A8], rax
0x14008a8f0  mov     rax, cs:__imp_WinHvLookupPortId
0x14008a8f7  mov     [rbp+130h+var_A0], rax
0x14008a8fe  lea     r15, VidUndockedKmEvtProcessQueryInterfaceRequest
0x14008a905  mov     rax, cs:__imp_WinHvGetVpRegisters
0x14008a90c  lea     r8, [rsp+230h+var_210]
0x14008a911  mov     [rbp+130h+var_98], rax
0x14008a918  mov     rdx, rcx
0x14008a91b  mov     rax, cs:__imp_WinHvCreatePort
0x14008a922  mov     rcx, cs:WdfDriverGlobals
0x14008a929  mov     [rbp+130h+var_90], rax
0x14008a930  mov     rax, cs:__imp_WinHvDeletePort
0x14008a937  mov     [rbp+130h+var_88], rax
0x14008a93e  mov     rax, cs:__imp_WinHvConnectPort
0x14008a945  mov     [rbp+130h+var_80], rax
0x14008a94c  mov     rax, cs:__imp_WinHvDisconnectPort
0x14008a953  mov     [rbp+130h+var_78], rax
0x14008a95a  mov     rax, cs:__imp_WinHvSignalEvent
0x14008a961  mov     [rbp+130h+var_70], rax
0x14008a968  mov     rax, cs:__imp_WinHvSignalEventWithSchedulerAssist
0x14008a96f  mov     [rbp+130h+var_68], rax
0x14008a976  mov     rax, cs:__imp_WinHvGetPortProperty
0x14008a97d  mov     [rbp+130h+var_60], rax
0x14008a984  mov     rax, cs:__imp_WinHvSetPortProperty
0x14008a98b  mov     [rbp+130h+var_58], rax
0x14008a992  mov     rax, cs:__imp_WinHvGetSintEventFlagsPhysicalPage
0x14008a999  mov     [rbp+130h+var_50], rax
0x14008a9a0  mov     rax, cs:__imp_WinHvSetEndOfMessage2
0x14008a9a7  mov     [rbp+130h+var_48], rax
0x14008a9ae  mov     rax, cs:__imp_WinHvPostMessage2
0x14008a9b5  mov     [rbp+130h+var_40], rax
0x14008a9bc  lea     rax, VidKmIfCreateMbSpecifyParentGpas2
0x14008a9c3  mov     [rbp+130h+var_38], rax
0x14008a9ca  lea     rax, VidKmIfDestroyGpaRange2
0x14008a9d1  mov     [rbp+130h+var_30], rax
0x14008a9d8  lea     rax, [rsp+230h+var_1E0]
0x14008a9dd  mov     [rsp+230h+var_208], rax
0x14008a9e2  lea     rax, GUID_VID_VSMM_INTERFACE
0x14008a9e9  mov     [rsp+230h+var_200], rax
0x14008a9ee  mov     rax, cs:WdfFunctions_01015
0x14008a9f5  mov     [rsp+230h+var_210], 30h ; '0'
0x14008a9fe  mov     [rsp+230h+var_1F8], 0
0x14008aa07  mov     [rsp+230h+var_1E8], 0
0x14008aa10  mov     [rsp+230h+var_1F0], r15
0x14008aa15  mov     rax, [rax+720h]
0x14008aa1c  call    _guard_dispatch_icall
0x14008aa21  mov     ebx, eax
0x14008aa23  test    eax, eax
0x14008aa25  jns     short loc_14008AA48
0x14008aa27  mov     r9d, eax
0x14008aa2a  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008aa31  mov     r8d, 1CCh
0x14008aa37  lea     rcx, aVidkmifcreate; "VidKmIfCreate"
0x14008aa3e  call    VidTraceErrorStatusInternal0
0x14008aa43  jmp     loc_14008AACE
0x14008aa48  mov     rcx, cs:WdfDriverGlobals
0x14008aa4f  lea     rax, [rsp+230h+var_1E0]
0x14008aa54  mov     [rsp+230h+var_208], rax
0x14008aa59  lea     r8, [rsp+230h+var_210]
0x14008aa5e  lea     rax, GUID_VID_VSMM_INTERFACE_AH2025
0x14008aa65  mov     [rsp+230h+var_1E0], 10A01A8h
0x14008aa6d  mov     [rsp+230h+var_200], rax
0x14008aa72  mov     rdx, rdi
0x14008aa75  mov     rax, cs:WdfFunctions_01015
0x14008aa7c  mov     [rsp+230h+var_210], 30h ; '0'
0x14008aa85  mov     [rsp+230h+var_1F8], 0
0x14008aa8e  mov     [rsp+230h+var_1E8], 0
0x14008aa97  mov     [rsp+230h+var_1F0], r15
0x14008aa9c  mov     rax, [rax+720h]
0x14008aaa3  call    _guard_dispatch_icall
0x14008aaa8  mov     ebx, eax
0x14008aaaa  test    eax, eax
0x14008aaac  jns     short loc_14008AACC
0x14008aaae  mov     r9d, eax
0x14008aab1  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008aab8  mov     r8d, 1E9h
0x14008aabe  lea     rcx, aVidkmifcreate; "VidKmIfCreate"
0x14008aac5  call    VidTraceErrorStatusInternal0
0x14008aaca  jmp     short loc_14008AACE
0x14008aacc  xor     ebx, ebx
0x14008aace  mov     eax, ebx
0x14008aad0  add     rsp, 218h
0x14008aad7  pop     r15
0x14008aad9  pop     rdi
0x14008aada  pop     rbx
0x14008aadb  pop     rbp
0x14008aadc  retn
```
