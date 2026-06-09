# VidKmIfCreate

- ea: `0x14008bad0`
- end: `0x14008be8e`
- name: `VidKmIfCreate`
- size: `958`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140082cd0`

## callees

- `0x140021db0`
- `0x14002f724`
- `0x14008bad0`

## import_xrefs

- `winhvr!WinHvPostMessage2` at `0x14008bd5e`
- `winhvr!WinHvSetEndOfMessage2` at `0x14008bd50`
- `winhvr!WinHvGetSintEventFlagsPhysicalPage` at `0x14008bd42`
- `winhvr!WinHvSetPortProperty` at `0x14008bd34`
- `winhvr!WinHvGetPortProperty` at `0x14008bd26`
- `winhvr!WinHvSignalEventWithSchedulerAssist` at `0x14008bd18`
- `winhvr!WinHvSignalEvent` at `0x14008bd0a`
- `winhvr!WinHvDisconnectPort` at `0x14008bcfc`
- `winhvr!WinHvConnectPort` at `0x14008bcee`
- `winhvr!WinHvDeletePort` at `0x14008bce0`
- `winhvr!WinHvCreatePort` at `0x14008bccb`
- `winhvr!WinHvGetVpRegisters` at `0x14008bcb5`
- `winhvr!WinHvLookupPortId` at `0x14008bca0`
- `winhvr!WinHvFreePortId` at `0x14008bc92`
- `winhvr!WinHvAllocatePortId` at `0x14008bc84`
- `winhvr!WinHvNtProcessorToVpIndex` at `0x14008bc79`
- `winhvr!WinHvGetNextQueuedPort` at `0x14008bc6e`
- `winhvr!WinHvSetEndOfMessage` at `0x14008bc63`
- `winhvr!WinHvGetSintMessagePhysicalPage` at `0x14008bc58`
- `winhvr!WinHvSetSint` at `0x14008bc4d`
- `winhvr!WinHvFreePartitionSintIndex` at `0x14008bc42`
- `winhvr!WinHvAllocatePartitionSintIndex` at `0x14008bc37`

## string_xrefs

- `0x14008bde7`: `VidKmIfCreate`
- `0x14008be6e`: `VidKmIfCreate`

## pseudocode

```c
__int64 __fastcall VidKmIfCreate(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v6; // [rsp+20h] [rbp-E0h] BYREF
  int *v7; // [rsp+28h] [rbp-D8h]
  GUID *v8; // [rsp+30h] [rbp-D0h]
  __int64 v9; // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall *v10)(); // [rsp+40h] [rbp-C0h]
  __int64 v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v13; // [rsp+54h] [rbp-ACh]
  int v14; // [rsp+5Ch] [rbp-A4h]
  __int64 (__fastcall *v15)(); // [rsp+60h] [rbp-A0h]
  __int64 (__fastcall *v16)(); // [rsp+68h] [rbp-98h]
  void *v17; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v18)(int, int, int, int, __int64); // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v19)(); // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v20)(int, int, int, int, int); // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v21)(); // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v22)(int, int, int, int, __int64, __int64, __int64); // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v23)(); // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v24)(); // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v25)(int, int, int, int, __int64); // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v26)(int, int, int, int, __int64, int, __int64, __int64); // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v27)(int, int, int, int, __int64, __int64, __int64); // [rsp+C0h] [rbp-40h]
  __int64 (__fastcall *v28)(); // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v29)(); // [rsp+D0h] [rbp-30h]
  __int64 (__fastcall *v30)(char *, unsigned __int64, __int64, __int64, int, unsigned int, char, _QWORD *, __int64, _QWORD *); // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v31)(); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v32)(); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v33)(int, int, int, int, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall *v34)(); // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v35)(); // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v36)(); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v37)(); // [rsp+110h] [rbp+10h]
  __int64 v38; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v39)(); // [rsp+120h] [rbp+20h]
  __int64 (__fastcall *v40)(int, int, int, int, size_t, __int64); // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v41)(int, int, int, int, int, char); // [rsp+130h] [rbp+30h]
  __int64 (__fastcall *v42)(); // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v43)(); // [rsp+140h] [rbp+40h]
  __int64 v44; // [rsp+148h] [rbp+48h]
  __int64 v45; // [rsp+150h] [rbp+50h]
  __int64 v46; // [rsp+158h] [rbp+58h]
  __int64 v47; // [rsp+160h] [rbp+60h]
  __int64 v48; // [rsp+168h] [rbp+68h]
  __int64 v49; // [rsp+170h] [rbp+70h]
  __int64 v50; // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v51)(_QWORD, _QWORD); // [rsp+180h] [rbp+80h]
  __int64 (*v52)(void); // [rsp+188h] [rbp+88h]
  __int64 v53; // [rsp+190h] [rbp+90h]
  __int64 (__fastcall *v54)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+198h] [rbp+98h]
  __int64 (__fastcall *v55)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD); // [rsp+1A0h] [rbp+A0h]
  __int64 (__fastcall *v56)(_QWORD, _QWORD); // [rsp+1A8h] [rbp+A8h]
  __int64 (__fastcall *v57)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD); // [rsp+1B0h] [rbp+B0h]
  __int64 (__fastcall *v58)(_QWORD, _QWORD); // [rsp+1B8h] [rbp+B8h]
  __int64 v59; // [rsp+1C0h] [rbp+C0h]
  __int64 v60; // [rsp+1C8h] [rbp+C8h]
  __int64 (__fastcall *v61)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v62)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+1D8h] [rbp+D8h]
  __int64 v63; // [rsp+1E0h] [rbp+E0h]
  __int64 v64; // [rsp+1E8h] [rbp+E8h]
  __int64 v65; // [rsp+1F0h] [rbp+F0h]
  __int64 (__fastcall *v66)(int, int, int, int, char, __int64, __int64); // [rsp+1F8h] [rbp+F8h]
  __int64 (__fastcall *v67)(); // [rsp+200h] [rbp+100h]

  v12 = 65976;
  v13 = 0;
  v14 = 0;
  v38 = 0;
  v15 = VidKmIfInterfaceReference;
  v16 = VidKmIfInterfaceDereference;
  v17 = &VidKmIfGetPartitionInformation;
  v18 = VidKmIfCreateMbSpecifyParentGpas;
  v19 = VidKmIfSetMbClientContext;
  v20 = VidKmIfSetMbClientNotifications;
  v21 = VidKmIfDestroyMb;
  v22 = VidKmIfGpaLockAcquire;
  v23 = VsmmCryptpDataAlignmentGetAesCbc;
  v24 = VidKmIfGpaLockCancel;
  v25 = VidKmIfGpaLockRelease;
  v26 = VidKmIfGetNumaNodeMap;
  v27 = VidKmIfCreateMbGpaRange;
  v28 = VidKmIfDestroyGpaRange;
  v29 = VidKmIfGetVaBackingProcess;
  v30 = VsmmVaGpaRangeKmifCreate;
  v31 = VsmmPhuKmifItemRegister;
  v32 = VsmmPhuKmifItemUnregister;
  v33 = VsmmPhuKmifItemLookup;
  v34 = VsmmPhuKmifItemMarkReady;
  v35 = VsmmPhuKmifItemMarkUnready;
  v36 = VsmmPhuKmifPersistGpaRange;
  v37 = VsmmPhuKmifPersistMemoryBlock;
  v39 = VidKmIfRegisterSynicEventCallback;
  v40 = VsmmPhuKmifItemGetData;
  v41 = VsmmPhuKmifItemSetData;
  v42 = VidKmifAttachDevice;
  v43 = VidKmifDetachDevice;
  v44 = WinHvAllocatePartitionSintIndex;
  v45 = WinHvFreePartitionSintIndex;
  v46 = WinHvSetSint;
  v47 = WinHvGetSintMessagePhysicalPage;
  v48 = WinHvSetEndOfMessage;
  v49 = WinHvGetNextQueuedPort;
  v50 = WinHvNtProcessorToVpIndex;
  v51 = WinHvAllocatePortId;
  v52 = WinHvFreePortId;
  v53 = WinHvLookupPortId;
  v54 = WinHvGetVpRegisters;
  v55 = WinHvCreatePort;
  v56 = WinHvDeletePort;
  v57 = WinHvConnectPort;
  v58 = WinHvDisconnectPort;
  v59 = WinHvSignalEvent;
  v60 = WinHvSignalEventWithSchedulerAssist;
  v61 = WinHvGetPortProperty;
  v62 = WinHvSetPortProperty;
  v63 = WinHvGetSintEventFlagsPhysicalPage;
  v64 = WinHvSetEndOfMessage2;
  v65 = WinHvPostMessage2;
  v66 = VidKmIfCreateMbSpecifyParentGpas2;
  v67 = VidKmIfDestroyGpaRange2;
  v7 = &v12;
  v8 = &GUID_VID_VSMM_INTERFACE;
  v6 = 48;
  v9 = 0;
  v11 = 0;
  v10 = VidUndockedKmEvtProcessQueryInterfaceRequest;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1824))(
         WdfDriverGlobals,
         a1,
         &v6);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v7 = &v12;
    v12 = 17433000;
    v8 = &GUID_VID_VSMM_INTERFACE_AH2025;
    v6 = 48;
    v9 = 0;
    v11 = 0;
    v10 = VidUndockedKmEvtProcessQueryInterfaceRequest;
    v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1824))(
           WdfDriverGlobals,
           a1,
           &v6);
    v3 = v4;
    if ( v4 >= 0 )
      return 0;
    else
      VidTraceErrorStatusInternal0(
        "VidKmIfCreate",
        "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c",
        489,
        (unsigned int)v4);
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VidKmIfCreate",
      "onecore\\vm\\vid\\sys\\driver\\vidkminterface.c",
      460,
      (unsigned int)v2);
  }
  return v3;
}

```

## disassembly

```asm
0x14008bad0  push    rbp
0x14008bad2  push    rbx
0x14008bad3  push    rdi
0x14008bad4  push    r15
0x14008bad6  lea     rbp, [rsp-118h]
0x14008bade  sub     rsp, 218h
0x14008bae5  xor     eax, eax
0x14008bae7  mov     [rsp+230h+var_1E0], 101B8h
0x14008baef  mov     [rsp+230h+var_1DC], rax
0x14008baf4  mov     rdi, rcx
0x14008baf7  mov     [rsp+230h+var_1D4], eax
0x14008bafb  mov     [rbp+130h+var_118], rax
0x14008baff  lea     rax, VidKmIfInterfaceReference
0x14008bb06  mov     [rsp+230h+var_1D0], rax
0x14008bb0b  lea     rax, VidKmIfInterfaceDereference
0x14008bb12  mov     [rsp+230h+var_1C8], rax
0x14008bb17  lea     rax, VidKmIfGetPartitionInformation
0x14008bb1e  mov     [rsp+230h+var_1C0], rax
0x14008bb23  lea     rax, VidKmIfCreateMbSpecifyParentGpas
0x14008bb2a  mov     [rsp+230h+var_1B8], rax
0x14008bb2f  lea     rax, VidKmIfSetMbClientContext
0x14008bb36  mov     [rbp+130h+var_1B0], rax
0x14008bb3a  lea     rax, VidKmIfSetMbClientNotifications
0x14008bb41  mov     [rbp+130h+var_1A8], rax
0x14008bb45  lea     rax, VidKmIfDestroyMb
0x14008bb4c  mov     [rbp+130h+var_1A0], rax
0x14008bb50  lea     rax, VidKmIfGpaLockAcquire
0x14008bb57  mov     [rbp+130h+var_198], rax
0x14008bb5b  lea     rax, VsmmCryptpDataAlignmentGetAesCbc
0x14008bb62  mov     [rbp+130h+var_190], rax
0x14008bb66  lea     rax, VidKmIfGpaLockCancel
0x14008bb6d  mov     [rbp+130h+var_188], rax
0x14008bb71  lea     rax, VidKmIfGpaLockRelease
0x14008bb78  mov     [rbp+130h+var_180], rax
0x14008bb7c  lea     rax, VidKmIfGetNumaNodeMap
0x14008bb83  mov     [rbp+130h+var_178], rax
0x14008bb87  lea     rax, VidKmIfCreateMbGpaRange
0x14008bb8e  mov     [rbp+130h+var_170], rax
0x14008bb92  lea     rax, VidKmIfDestroyGpaRange
0x14008bb99  mov     [rbp+130h+var_168], rax
0x14008bb9d  lea     rax, VidKmIfGetVaBackingProcess
0x14008bba4  mov     [rbp+130h+var_160], rax
0x14008bba8  lea     rax, VsmmVaGpaRangeKmifCreate
0x14008bbaf  mov     [rbp+130h+var_158], rax
0x14008bbb3  lea     rax, VsmmPhuKmifItemRegister
0x14008bbba  mov     [rbp+130h+var_150], rax
0x14008bbbe  lea     rax, VsmmPhuKmifItemUnregister
0x14008bbc5  mov     [rbp+130h+var_148], rax
0x14008bbc9  lea     rax, VsmmPhuKmifItemLookup
0x14008bbd0  mov     [rbp+130h+var_140], rax
0x14008bbd4  lea     rax, VsmmPhuKmifItemMarkReady
0x14008bbdb  mov     [rbp+130h+var_138], rax
0x14008bbdf  lea     rax, VsmmPhuKmifItemMarkUnready
0x14008bbe6  mov     [rbp+130h+var_130], rax
0x14008bbea  lea     rax, VsmmPhuKmifPersistGpaRange
0x14008bbf1  mov     [rbp+130h+var_128], rax
0x14008bbf5  lea     rax, VsmmPhuKmifPersistMemoryBlock
0x14008bbfc  mov     [rbp+130h+var_120], rax
0x14008bc00  lea     rax, VidKmIfRegisterSynicEventCallback
0x14008bc07  mov     [rbp+130h+var_110], rax
0x14008bc0b  lea     rax, VsmmPhuKmifItemGetData
0x14008bc12  mov     [rbp+130h+var_108], rax
0x14008bc16  lea     rax, VsmmPhuKmifItemSetData
0x14008bc1d  mov     [rbp+130h+var_100], rax
0x14008bc21  lea     rax, VidKmifAttachDevice
0x14008bc28  mov     [rbp+130h+var_F8], rax
0x14008bc2c  lea     rax, VidKmifDetachDevice
0x14008bc33  mov     [rbp+130h+var_F0], rax
0x14008bc37  mov     rax, cs:__imp_WinHvAllocatePartitionSintIndex
0x14008bc3e  mov     [rbp+130h+var_E8], rax
0x14008bc42  mov     rax, cs:__imp_WinHvFreePartitionSintIndex
0x14008bc49  mov     [rbp+130h+var_E0], rax
0x14008bc4d  mov     rax, cs:__imp_WinHvSetSint
0x14008bc54  mov     [rbp+130h+var_D8], rax
0x14008bc58  mov     rax, cs:__imp_WinHvGetSintMessagePhysicalPage
0x14008bc5f  mov     [rbp+130h+var_D0], rax
0x14008bc63  mov     rax, cs:__imp_WinHvSetEndOfMessage
0x14008bc6a  mov     [rbp+130h+var_C8], rax
0x14008bc6e  mov     rax, cs:__imp_WinHvGetNextQueuedPort
0x14008bc75  mov     [rbp+130h+var_C0], rax
0x14008bc79  mov     rax, cs:__imp_WinHvNtProcessorToVpIndex
0x14008bc80  mov     [rbp+130h+var_B8], rax
0x14008bc84  mov     rax, cs:__imp_WinHvAllocatePortId
0x14008bc8b  mov     [rbp+130h+var_B0], rax
0x14008bc92  mov     rax, cs:__imp_WinHvFreePortId
0x14008bc99  mov     [rbp+130h+var_A8], rax
0x14008bca0  mov     rax, cs:__imp_WinHvLookupPortId
0x14008bca7  mov     [rbp+130h+var_A0], rax
0x14008bcae  lea     r15, VidUndockedKmEvtProcessQueryInterfaceRequest
0x14008bcb5  mov     rax, cs:__imp_WinHvGetVpRegisters
0x14008bcbc  lea     r8, [rsp+230h+var_210]
0x14008bcc1  mov     [rbp+130h+var_98], rax
0x14008bcc8  mov     rdx, rcx
0x14008bccb  mov     rax, cs:__imp_WinHvCreatePort
0x14008bcd2  mov     rcx, cs:WdfDriverGlobals
0x14008bcd9  mov     [rbp+130h+var_90], rax
0x14008bce0  mov     rax, cs:__imp_WinHvDeletePort
0x14008bce7  mov     [rbp+130h+var_88], rax
0x14008bcee  mov     rax, cs:__imp_WinHvConnectPort
0x14008bcf5  mov     [rbp+130h+var_80], rax
0x14008bcfc  mov     rax, cs:__imp_WinHvDisconnectPort
0x14008bd03  mov     [rbp+130h+var_78], rax
0x14008bd0a  mov     rax, cs:__imp_WinHvSignalEvent
0x14008bd11  mov     [rbp+130h+var_70], rax
0x14008bd18  mov     rax, cs:__imp_WinHvSignalEventWithSchedulerAssist
0x14008bd1f  mov     [rbp+130h+var_68], rax
0x14008bd26  mov     rax, cs:__imp_WinHvGetPortProperty
0x14008bd2d  mov     [rbp+130h+var_60], rax
0x14008bd34  mov     rax, cs:__imp_WinHvSetPortProperty
0x14008bd3b  mov     [rbp+130h+var_58], rax
0x14008bd42  mov     rax, cs:__imp_WinHvGetSintEventFlagsPhysicalPage
0x14008bd49  mov     [rbp+130h+var_50], rax
0x14008bd50  mov     rax, cs:__imp_WinHvSetEndOfMessage2
0x14008bd57  mov     [rbp+130h+var_48], rax
0x14008bd5e  mov     rax, cs:__imp_WinHvPostMessage2
0x14008bd65  mov     [rbp+130h+var_40], rax
0x14008bd6c  lea     rax, VidKmIfCreateMbSpecifyParentGpas2
0x14008bd73  mov     [rbp+130h+var_38], rax
0x14008bd7a  lea     rax, VidKmIfDestroyGpaRange2
0x14008bd81  mov     [rbp+130h+var_30], rax
0x14008bd88  lea     rax, [rsp+230h+var_1E0]
0x14008bd8d  mov     [rsp+230h+var_208], rax
0x14008bd92  lea     rax, GUID_VID_VSMM_INTERFACE
0x14008bd99  mov     [rsp+230h+var_200], rax
0x14008bd9e  mov     rax, cs:WdfFunctions_01015
0x14008bda5  mov     [rsp+230h+var_210], 30h ; '0'
0x14008bdae  mov     [rsp+230h+var_1F8], 0
0x14008bdb7  mov     [rsp+230h+var_1E8], 0
0x14008bdc0  mov     [rsp+230h+var_1F0], r15
0x14008bdc5  mov     rax, [rax+720h]
0x14008bdcc  call    _guard_dispatch_icall
0x14008bdd1  mov     ebx, eax
0x14008bdd3  test    eax, eax
0x14008bdd5  jns     short loc_14008BDF8
0x14008bdd7  mov     r9d, eax
0x14008bdda  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008bde1  mov     r8d, 1CCh
0x14008bde7  lea     rcx, aVidkmifcreate; "VidKmIfCreate"
0x14008bdee  call    VidTraceErrorStatusInternal0
0x14008bdf3  jmp     loc_14008BE7E
0x14008bdf8  mov     rcx, cs:WdfDriverGlobals
0x14008bdff  lea     rax, [rsp+230h+var_1E0]
0x14008be04  mov     [rsp+230h+var_208], rax
0x14008be09  lea     r8, [rsp+230h+var_210]
0x14008be0e  lea     rax, GUID_VID_VSMM_INTERFACE_AH2025
0x14008be15  mov     [rsp+230h+var_1E0], 10A01A8h
0x14008be1d  mov     [rsp+230h+var_200], rax
0x14008be22  mov     rdx, rdi
0x14008be25  mov     rax, cs:WdfFunctions_01015
0x14008be2c  mov     [rsp+230h+var_210], 30h ; '0'
0x14008be35  mov     [rsp+230h+var_1F8], 0
0x14008be3e  mov     [rsp+230h+var_1E8], 0
0x14008be47  mov     [rsp+230h+var_1F0], r15
0x14008be4c  mov     rax, [rax+720h]
0x14008be53  call    _guard_dispatch_icall
0x14008be58  mov     ebx, eax
0x14008be5a  test    eax, eax
0x14008be5c  jns     short loc_14008BE7C
0x14008be5e  mov     r9d, eax
0x14008be61  lea     rdx, aOnecoreVmVidSy_36; "onecore\\vm\\vid\\sys\\driver\\vidkmint"...
0x14008be68  mov     r8d, 1E9h
0x14008be6e  lea     rcx, aVidkmifcreate; "VidKmIfCreate"
0x14008be75  call    VidTraceErrorStatusInternal0
0x14008be7a  jmp     short loc_14008BE7E
0x14008be7c  xor     ebx, ebx
0x14008be7e  mov     eax, ebx
0x14008be80  add     rsp, 218h
0x14008be87  pop     r15
0x14008be89  pop     rdi
0x14008be8a  pop     rbx
0x14008be8b  pop     rbp
0x14008be8c  retn
```
