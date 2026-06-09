# VmsPtNicBindAdapterEx

- ea: `0x140117fb0`
- end: `0x14011b456`
- name: `VmsPtNicBindAdapterEx`
- size: `13478`
- prototype: ``
- caller_count: `0`
- callee_count: `83`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x14002e0f0`
- `0x1400313cc`
- `0x1400361dc`
- `0x14003a450`
- `0x14003a95c`
- `0x14003c378`
- `0x14003cc04`
- `0x14003ef24`
- `0x140040c40`
- `0x140046d18`
- `0x140046e5c`
- `0x140046f1c`
- `0x140047204`
- `0x14004f5d8`
- `0x140065f10`
- `0x14006a330`
- `0x14006b084`
- `0x14006e100`
- `0x140076604`
- `0x14007cd4c`
- `0x14008497c`
- `0x14008823c`
- `0x140088c50`
- `0x140089de8`
- `0x14008a258`
- `0x14008c624`
- `0x14008cd0c`
- `0x14008d810`
- `0x1400a9ea0`
- `0x1400f04bc`
- `0x1400fa830`
- `0x1400fe990`
- `0x1400ff28c`
- `0x1401068b8`
- `0x140106fa8`
- `0x140117154`
- `0x140117fb0`
- `0x14011b508`
- `0x14011bb70`
- `0x14011be2c`
- `0x14011c268`
- `0x14011f0e0`
- `0x1401212bc`
- `0x140121874`
- `0x140122d20`
- `0x14012311c`
- `0x1401231bc`
- `0x140123528`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14011822d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14011859f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140118f00`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140119fae`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14011822d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14011859f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140118f00`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140119fae`
- `ntoskrnl!KeInitializeMutex` at `0x140118f42`
- `ntoskrnl!KeInitializeMutex` at `0x140118f42`
- `ntoskrnl!KeReleaseMutex` at `0x14011b29d`
- `ntoskrnl!KeReleaseMutex` at `0x14011b29d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14011b244`
- `ntoskrnl!KeWaitForSingleObject` at `0x14011b244`
- `ntoskrnl!ExFreePoolWithTag` at `0x140118bb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011afe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b001`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b1b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b1e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b26e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140118bb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011afe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b001`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b1b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b1e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011b26e`
- `ntoskrnl!ExAllocatePool2` at `0x140118e0f`
- `ntoskrnl!ExAllocatePool2` at `0x14011a3e0`
- `ntoskrnl!ExAllocatePool2` at `0x14011a470`
- `ntoskrnl!ExAllocatePool2` at `0x14011aa41`
- `ntoskrnl!ExAllocatePool2` at `0x140118e0f`
- `ntoskrnl!ExAllocatePool2` at `0x14011a3e0`
- `ntoskrnl!ExAllocatePool2` at `0x14011a470`
- `ntoskrnl!ExAllocatePool2` at `0x14011aa41`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401191ad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401191ad`
- `NDIS!NdisAllocateNetBufferPool` at `0x140119092`
- `NDIS!NdisAllocateNetBufferPool` at `0x140119092`
- `NDIS!NdisCloseAdapterEx` at `0x14011b180`
- `NDIS!NdisCloseAdapterEx` at `0x14011b2d6`
- `NDIS!NdisCloseAdapterEx` at `0x14011b180`
- `NDIS!NdisCloseAdapterEx` at `0x14011b2d6`
- `NDIS!NdisWaitEvent` at `0x14011a09b`
- `NDIS!NdisWaitEvent` at `0x14011b097`
- `NDIS!NdisWaitEvent` at `0x14011b198`
- `NDIS!NdisWaitEvent` at `0x14011b2ee`
- `NDIS!NdisWaitEvent` at `0x14011a09b`
- `NDIS!NdisWaitEvent` at `0x14011b097`
- `NDIS!NdisWaitEvent` at `0x14011b198`
- `NDIS!NdisWaitEvent` at `0x14011b2ee`
- `NDIS!NdisOpenAdapterEx` at `0x140118622`
- `NDIS!NdisOpenAdapterEx` at `0x14011a07b`
- `NDIS!NdisOpenAdapterEx` at `0x140118622`
- `NDIS!NdisOpenAdapterEx` at `0x14011a07b`
- `NDIS!NdisResetEvent` at `0x14011b16d`
- `NDIS!NdisResetEvent` at `0x14011b2c6`
- `NDIS!NdisResetEvent` at `0x14011b16d`
- `NDIS!NdisResetEvent` at `0x14011b2c6`
- `NDIS!NdisInitializeEvent` at `0x1401190fc`
- `NDIS!NdisInitializeEvent` at `0x14011910f`
- `NDIS!NdisInitializeEvent` at `0x1401190fc`
- `NDIS!NdisInitializeEvent` at `0x14011910f`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140118f86`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140119004`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140118f86`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140119004`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14011b3e6`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14011b3e6`
- `NDIS!NdisReleaseRWLock` at `0x1401182cb`
- `NDIS!NdisReleaseRWLock` at `0x140118379`
- `NDIS!NdisReleaseRWLock` at `0x14011840b`
- `NDIS!NdisReleaseRWLock` at `0x14011852d`
- `NDIS!NdisReleaseRWLock` at `0x14011855f`
- `NDIS!NdisReleaseRWLock` at `0x1401185c9`
- `NDIS!NdisReleaseRWLock` at `0x140118713`
- `NDIS!NdisReleaseRWLock` at `0x140119634`
- `NDIS!NdisReleaseRWLock` at `0x140119e62`
- `NDIS!NdisReleaseRWLock` at `0x140119f8d`
- `NDIS!NdisReleaseRWLock` at `0x14011a020`
- `NDIS!NdisReleaseRWLock` at `0x14011a1ef`
- `NDIS!NdisReleaseRWLock` at `0x14011b077`
- `NDIS!NdisReleaseRWLock` at `0x14011b14e`
- `NDIS!NdisReleaseRWLock` at `0x1401182cb`
- `NDIS!NdisReleaseRWLock` at `0x140118379`
- `NDIS!NdisReleaseRWLock` at `0x14011840b`
- `NDIS!NdisReleaseRWLock` at `0x14011852d`
- `NDIS!NdisReleaseRWLock` at `0x14011855f`
- `NDIS!NdisReleaseRWLock` at `0x1401185c9`
- `NDIS!NdisReleaseRWLock` at `0x140118713`
- `NDIS!NdisReleaseRWLock` at `0x140119634`
- `NDIS!NdisReleaseRWLock` at `0x140119e62`
- `NDIS!NdisReleaseRWLock` at `0x140119f8d`
- `NDIS!NdisReleaseRWLock` at `0x14011a020`
- `NDIS!NdisReleaseRWLock` at `0x14011a1ef`
- `NDIS!NdisReleaseRWLock` at `0x14011b077`
- `NDIS!NdisReleaseRWLock` at `0x14011b14e`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140118496`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140119ef6`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x14011ac14`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140118496`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140119ef6`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x14011ac14`

## string_xrefs

- `0x14011a150`: `memberAdapter->ProtocolHandle != NULL`
- `0x1401183ad`: `objPort->Nic->Type == VmsNicProtocol`
- `0x140118437`: `objPort->Nic->Type == VmsNicProtocol`

## pseudocode

```c
__int64 __fastcall VmsPtNicBindAdapterEx(__int64 a1, void *a2, __int64 a3)
{
  __int64 v4; // rdi
  __int64 v5; // r15
  unsigned __int64 v6; // r13
  unsigned __int8 v7; // r12
  unsigned __int16 v8; // si
  __int64 v9; // r9
  char v10; // bl
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  __int64 *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  int v18; // edx
  __int64 v19; // rax
  int v20; // edx
  NTSTATUS v21; // eax
  int v22; // edx
  int v23; // r8d
  NDIS_STATUS v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // r15d
  __int64 v28; // r8
  __int64 v29; // rdx
  int v30; // r8d
  __int64 *v31; // rsi
  __int64 *v32; // r11
  __int64 *v33; // r10
  PVOID v34; // r8
  PVOID v35; // rdx
  __int64 *v36; // r10
  __int64 *v37; // r8
  __int64 *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r10
  __int64 v42; // r11
  __int64 v43; // r8
  __int64 *v44; // rsi
  __int64 *v45; // r10
  __int64 *v46; // r8
  __int64 *v47; // rdx
  unsigned int v48; // eax
  const UNICODE_STRING *v49; // rsi
  unsigned int v50; // r15d
  __int64 Pool2; // rax
  int v52; // edx
  NDIS_HANDLE NetBufferListPool; // rax
  int v54; // edx
  NDIS_HANDLE v55; // rax
  int v56; // edx
  NDIS_HANDLE NetBufferPool; // rax
  int v58; // edx
  int v59; // edx
  __int64 v60; // rcx
  int WorkItem; // eax
  int v62; // edx
  int v63; // eax
  int v64; // edx
  int v65; // eax
  int v66; // edx
  int v67; // eax
  int v68; // edx
  int v69; // eax
  int v70; // edx
  int v71; // eax
  int v72; // edx
  int v73; // eax
  int v74; // edx
  int v75; // eax
  int v76; // edx
  int v77; // eax
  int v78; // edx
  int v79; // eax
  int v80; // edx
  int v81; // eax
  int v82; // edx
  int v83; // eax
  int v84; // edx
  int v85; // eax
  int v86; // edx
  int v87; // eax
  int v88; // edx
  int v89; // eax
  int v90; // edx
  int v91; // eax
  int v92; // edx
  int v93; // eax
  int v94; // edx
  int v95; // eax
  int v96; // edx
  int v97; // eax
  int v98; // edx
  char v99; // r11
  unsigned __int64 v100; // rcx
  __int64 DefaultSwitchConfig; // r12
  __int64 v102; // rax
  _DWORD *v103; // r15
  char v104; // al
  int v105; // edx
  int v106; // eax
  __int64 v107; // rax
  __int64 v108; // rax
  _WORD *v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rcx
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rdx
  _OWORD *v115; // rax
  _OWORD *v116; // rcx
  __int128 v117; // xmm1
  __int64 v118; // rdx
  NTSTATUS v119; // eax
  int v120; // edx
  int v121; // r8d
  PVOID *v122; // r15
  NDIS_STATUS v123; // eax
  int v124; // edx
  int v125; // r8d
  int v126; // edx
  PVOID v127; // rcx
  __int64 v128; // rcx
  BOOL v129; // r12d
  __int64 v130; // rcx
  unsigned __int8 v131; // r15
  unsigned int v132; // r15d
  _DWORD *v133; // r15
  unsigned int v134; // eax
  __int64 v135; // rax
  int v136; // edx
  __int64 v137; // rax
  char v138; // cl
  int v139; // edx
  __int64 v140; // rax
  __int64 *v141; // rsi
  __int64 *v142; // r8
  __int64 *v143; // rdx
  __int64 *v144; // rcx
  bool v145; // zf
  _BYTE *v146; // r15
  unsigned int v147; // eax
  char v148; // al
  unsigned int v149; // esi
  unsigned __int64 v150; // rax
  int v151; // edx
  int v152; // ecx
  int v153; // r8d
  _QWORD *v154; // r12
  void *v155; // r9
  unsigned int v156; // edx
  unsigned int v157; // eax
  unsigned int v158; // r15d
  __int64 v159; // rcx
  int v160; // esi
  unsigned __int64 v161; // rax
  void *v162; // rcx
  NTSTATUS v163; // eax
  int v164; // edx
  int v165; // r8d
  PVOID v166; // r15
  int v167; // eax
  int v168; // edx
  int v169; // r8d
  __int64 v170; // r9
  __int64 v171; // rdx
  __int64 v172; // rdx
  __int64 v173; // r8
  int v174; // edx
  int v175; // r8d
  int v176; // r9d
  __int64 v177; // rdx
  __int64 v178; // r9
  __int64 v179; // r10
  __int64 v180; // rdx
  __int64 v181; // r8
  int v182; // r8d
  int v183; // r9d
  __int64 v184; // rdx
  char v185; // bl
  int v186; // edx
  PVOID v187; // rcx
  char v188; // al
  __int64 v189; // rcx
  void *v190; // rcx
  _QWORD *v191; // rax
  __int64 v192; // rcx
  int v193; // eax
  int NdisBindingHandle; // [rsp+20h] [rbp-E0h]
  int NdisBindingHandlea; // [rsp+20h] [rbp-E0h]
  PNDIS_HANDLE NdisBindingHandled; // [rsp+20h] [rbp-E0h]
  int NdisBindingHandleb; // [rsp+20h] [rbp-E0h]
  int NdisBindingHandlee; // [rsp+20h] [rbp-E0h]
  int NdisBindingHandlec; // [rsp+20h] [rbp-E0h]
  int v201; // [rsp+30h] [rbp-D0h]
  __int64 v202; // [rsp+30h] [rbp-D0h]
  unsigned int v203; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v204; // [rsp+70h] [rbp-90h]
  unsigned int SwitchUnsafe; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v206; // [rsp+78h] [rbp-88h] BYREF
  BOOL v207; // [rsp+80h] [rbp-80h]
  char v208; // [rsp+84h] [rbp-7Ch]
  PNDIS_HANDLE v209; // [rsp+88h] [rbp-78h] BYREF
  char v210; // [rsp+90h] [rbp-70h]
  struct _LOCK_STATE_EX v211; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v212; // [rsp+98h] [rbp-68h]
  char v213; // [rsp+A0h] [rbp-60h]
  char v214; // [rsp+A1h] [rbp-5Fh] BYREF
  char v215; // [rsp+A2h] [rbp-5Eh]
  BOOL v216; // [rsp+A4h] [rbp-5Ch] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+A8h] [rbp-58h] BYREF
  struct _LOCK_STATE_EX v218; // [rsp+ACh] [rbp-54h] BYREF
  struct _LOCK_STATE_EX v219; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v220; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v221; // [rsp+C0h] [rbp-40h] BYREF
  int v222; // [rsp+C4h] [rbp-3Ch] BYREF
  NDIS_HANDLE BindContext; // [rsp+C8h] [rbp-38h]
  PVOID v224; // [rsp+D0h] [rbp-30h] BYREF
  UNICODE_STRING SourceString; // [rsp+D8h] [rbp-28h] BYREF
  PVOID v226; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v227; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F8h] [rbp-8h] BYREF
  struct _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+108h] [rbp+8h] BYREF
  int v230; // [rsp+140h] [rbp+40h]
  PVOID P; // [rsp+148h] [rbp+48h]
  GUID v232; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v233[2]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v234[2]; // [rsp+170h] [rbp+70h] BYREF
  GUID v235; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v236[2]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE Parameters[20]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v238[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v239; // [rsp+1D8h] [rbp+D8h] BYREF
  GUID InterfaceGuid; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v241[26]; // [rsp+200h] [rbp+100h] BYREF
  int v242; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int16 v243; // [rsp+2D4h] [rbp+1D4h]
  _BYTE v244[256]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v245[256]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v246[256]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v247[256]; // [rsp+5E0h] [rbp+4E0h] BYREF

  BindContext = a2;
  SwitchUnsafe = -1073741823;
  v206 = 0;
  memset(v236, 0, 28);
  v222 = 0;
  v242 = 0;
  v243 = 0;
  v4 = 0;
  memset(&OpenParameters, 0, 52);
  v224 = 0;
  v226 = 0;
  memset(v238, 0, 12);
  memset(Parameters, 0, sizeof(Parameters));
  v239 = 0;
  memset(v241, 0, sizeof(v241));
  v215 = 0;
  v212 = 0;
  v5 = 0;
  *(_QWORD *)&v232.Data1 = 0;
  v6 = 0;
  v220 = 0;
  v221 = 0;
  P = 0;
  v7 = 0;
  v227 = 0;
  v8 = 0;
  v209 = 0;
  v210 = 0;
  v207 = 0;
  LOWORD(v216) = 0;
  v213 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  InterfaceGuid = 0;
  LockState.Flags = 0;
  *(_WORD *)&v218.OldIrql = 0;
  v218.Flags = 0;
  *(_WORD *)&v219.OldIrql = 0;
  v219.Flags = 0;
  *(_WORD *)&v211.OldIrql = 0;
  v211.Flags = 0;
  memset(v244, 0, 0xFEu);
  *(_QWORD *)&DestinationString.Length = 16646144;
  DestinationString.Buffer = (wchar_t *)v244;
  memset(v245, 0, 0xFEu);
  *(_QWORD *)&SourceString.Length = 16646144;
  SourceString.Buffer = (wchar_t *)v245;
  memset(v246, 0, 0xFEu);
  v233[0] = 16646144;
  v233[1] = v246;
  memset(v247, 0, 0xFEu);
  v234[0] = 16646144;
  v234[1] = v247;
  LOBYTE(v9) = 1;
  VmsWppTraceInitializeContextEx(&v227, 1, 1, v9);
  v10 = 0;
  VmsWppTraceApi(
    (unsigned int)&v227,
    (unsigned int)"VmsPtNicBindAdapterEx",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\pt\\vmspt.c",
    1237,
    4,
    0,
    0,
    1,
    0);
  v14 = WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids;
  if ( *(_DWORD *)(a3 + 32) )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_d(
      VmsIfrLog,
      v11,
      20,
      14,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      *(_DWORD *)(a3 + 32));
    SwitchUnsafe = -1073741811;
    v10 = 5;
LABEL_92:
    v8 = v207;
    goto LABEL_93;
  }
  if ( *(_WORD *)a3 != 1158 || (LODWORD(v14) = 312, *(_WORD *)(a3 + 2) < 0x138u) )
  {
    WPP_RECORDER_SF_HHH((_DWORD)v14, v11, v12, v13, NdisBindingHandle, *(_BYTE *)a3, *(_BYTE *)a3, *(_BYTE *)a3);
    SwitchUnsafe = -1073741811;
    v10 = 10;
    goto LABEL_93;
  }
  VmsIfrInfoParamInputNdisBindParameters(&v227, a3);
  VmsNetworkIndication = 21;
  VmsReadReloadableParameters();
  RtlCopyUnicodeString(&DestinationString, *(PCUNICODE_STRING *)(a3 + 16));
  VmsUtilStrMakeRegistryCompliant(&DestinationString);
  SwitchUnsafe = VmsUtilUpcaseUnicodeString(&SourceString, &DestinationString);
  if ( SwitchUnsafe )
  {
    v10 = 11;
    goto LABEL_93;
  }
  v230 = VmsPtNicPvtReadConnectionInfo(&SourceString, &v224, &v226, 0);
  if ( v230 )
  {
    v204 = 0;
  }
  else
  {
    SwitchUnsafe = VmsUtilUpcaseUnicodeString(v233, v224);
    if ( SwitchUnsafe )
    {
      v10 = 12;
      goto LABEL_93;
    }
    VmsUtilLockShared(v15, &LockState, 0);
    SwitchUnsafe = VmsOmFindSwitchUnsafe(v233, &v220);
    NdisReleaseRWLock(VmsOmObjectListLock, &LockState);
    v6 = v220;
    if ( SwitchUnsafe )
      goto LABEL_12;
    v7 = VmsPtCheckIsEmbeddedTeamingEnabled(0, v220);
    v204 = v7;
  }
  if ( *(_BYTE *)(a3 + 1) <= 3u
    || (v16 = *(_QWORD *)(a3 + 272)) == 0
    || (v17 = *(_DWORD *)(v16 + 32), v208 = 1, (v17 & 0x40) == 0) )
  {
    v208 = 0;
  }
  if ( !v7 )
  {
LABEL_131:
    v49 = *(const UNICODE_STRING **)(a3 + 8);
    v50 = v49->MaximumLength + VmsCacheLineSizeInBytes + 5505;
    Pool2 = ExAllocatePool2(64, v50, 1349743446);
    v52 = 0;
    if ( !Pool2 )
    {
      LOBYTE(v52) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v52, 20, 23, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v50);
      SwitchUnsafe = -1073741670;
      v10 = 55;
LABEL_91:
      v5 = v212;
      goto LABEL_92;
    }
    v4 = -(__int64)(unsigned int)VmsCacheLineSizeInBytes & (Pool2 + (unsigned int)VmsCacheLineSizeInBytes - 1LL);
    *(_QWORD *)(v4 + 0x58) = Pool2;
    if ( v7 )
    {
      *(_DWORD *)(v4 + 2520) = 2621824;
      *(_BYTE *)(v4 + 2401) = 1;
      *(_DWORD *)(v4 + 1500) = 2;
    }
    *(_BYTE *)(v4 + 3312) = 0;
    *(_BYTE *)(v4 + 3314) = 1;
    *(_DWORD *)(v4 + 3368) = 1;
    VmsPtNicMuxInitQosOffload(v4);
    *(_DWORD *)(v4 + 296) = 2;
    *(_DWORD *)(v4 + 2440) = *(_DWORD *)(a3 + 160);
    *(_QWORD *)(v4 + 2432) = *(_QWORD *)(a3 + 168);
    *(_QWORD *)(v4 + 128) = v4 + 5504;
    *(_WORD *)(v4 + 122) = v49->MaximumLength;
    *(_WORD *)(v4 + 120) = v49->Length;
    RtlCopyUnicodeString((PUNICODE_STRING)(v4 + 120), v49);
    *(_QWORD *)(v4 + 1408) = v4 + 1400;
    *(_QWORD *)(v4 + 1400) = v4 + 1400;
    *(_QWORD *)(v4 + 1472) = v4 + 1464;
    *(_QWORD *)(v4 + 1464) = v4 + 1464;
    *(_QWORD *)(v4 + 1488) = v4 + 1480;
    *(_QWORD *)(v4 + 1480) = v4 + 1480;
    KeInitializeMutex((PRKMUTEX)(v4 + 5200), 0xFFFFu);
    *(_DWORD *)Parameters = 1311104;
    Parameters[13] = 0;
    *(_WORD *)&Parameters[14] = 0;
    *(_DWORD *)&Parameters[16] = 0;
    *(_DWORD *)&Parameters[4] = 15204608;
    strcpy(&Parameters[8], "VsNC");
    NetBufferListPool = NdisAllocateNetBufferListPool(VmsProtocolHandle, (PNET_BUFFER_LIST_POOL_PARAMETERS)Parameters);
    *(_QWORD *)(v4 + 168) = NetBufferListPool;
    if ( !NetBufferListPool )
    {
      LOBYTE(v54) = 2;
      WPP_RECORDER_SF_qq(
        VmsIfrLog,
        v54,
        20,
        24,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (char)VmsProtocolHandle,
        (char)Parameters);
      SwitchUnsafe = -1073741670;
      v10 = 60;
      goto LABEL_91;
    }
    Parameters[5] = 1;
    strcpy(&Parameters[6], "(");
    v55 = NdisAllocateNetBufferListPool(VmsProtocolHandle, (PNET_BUFFER_LIST_POOL_PARAMETERS)Parameters);
    *(_QWORD *)(v4 + 176) = v55;
    if ( !v55 )
    {
      LOBYTE(v56) = 2;
      WPP_RECORDER_SF_qq(
        VmsIfrLog,
        v56,
        20,
        25,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (char)VmsProtocolHandle,
        (char)Parameters);
      SwitchUnsafe = -1073741670;
      v10 = 65;
      goto LABEL_91;
    }
    v239 = 0x434E735600100180uLL;
    NetBufferPool = NdisAllocateNetBufferPool(VmsProtocolHandle, (PNET_BUFFER_POOL_PARAMETERS)&v239);
    *(_QWORD *)(v4 + 184) = NetBufferPool;
    if ( !NetBufferPool )
    {
      LOBYTE(v58) = 2;
      WPP_RECORDER_SF_qq(
        VmsIfrLog,
        v58,
        20,
        26,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (char)VmsProtocolHandle,
        (char)Parameters);
      SwitchUnsafe = -1073741670;
      v10 = 70;
      goto LABEL_91;
    }
    NdisInitializeEvent((PNDIS_EVENT)(v4 + 144));
    NdisInitializeEvent((PNDIS_EVENT)(v4 + 3400));
    *(_DWORD *)(v4 + 100) = 1;
    *(_BYTE *)(v4 + 104) = 1;
    SwitchUnsafe = VmsOmNicCreate(&SourceString, &DestinationString, 0, (__int64)&v206);
    if ( SwitchUnsafe )
    {
      v10 = 105;
      goto LABEL_91;
    }
    *(_QWORD *)v4 = v206;
    *(_QWORD *)(v206 + 3312) = v4;
    *(_QWORD *)(v206 + 3320) = VmsPtNicPvtContextCleanup;
    *(_DWORD *)(v206 + 1872) = 2;
    *(_BYTE *)(v206 + 1896) = v7;
    RtlInitUnicodeString((PUNICODE_STRING)(v206 + 1288), L"Microsoft Default External Interface");
    v60 = v206;
    if ( !*(_QWORD *)(v206 + 2096) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v59,
        19,
        27,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (__int64)"objNic->NvIoWorkerQueue != NULL");
      v60 = v206;
      if ( !*(_QWORD *)(v206 + 2096) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v60 = v206;
      }
    }
    WorkItem = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v60 + 2096), 23, v4 + 1608);
    SwitchUnsafe = WorkItem;
    if ( WorkItem < 0 )
    {
      LOBYTE(v62) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v62, 20, 28, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, WorkItem);
      v10 = 75;
      goto LABEL_91;
    }
    v63 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 18, v4 + 1616);
    SwitchUnsafe = v63;
    if ( v63 < 0 )
    {
      LOBYTE(v64) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v64, 20, 29, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v63);
      v10 = 80;
      goto LABEL_91;
    }
    v65 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 31, v4 + 2472);
    SwitchUnsafe = v65;
    if ( v65 < 0 )
    {
      LOBYTE(v66) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v66, 20, 30, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v65);
      v10 = 85;
      goto LABEL_91;
    }
    v67 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 19, v4 + 1624);
    SwitchUnsafe = v67;
    if ( v67 < 0 )
    {
      LOBYTE(v68) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v68, 20, 31, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v67);
      v10 = 90;
      goto LABEL_91;
    }
    v69 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 25, v4 + 5152);
    SwitchUnsafe = v69;
    if ( v69 < 0 )
    {
      LOBYTE(v70) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v70, 20, 32, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v69);
      v10 = 91;
      goto LABEL_91;
    }
    v71 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 26, v4 + 5168);
    SwitchUnsafe = v71;
    if ( v71 < 0 )
    {
      LOBYTE(v72) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v72, 20, 33, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v71);
      v10 = 92;
      goto LABEL_91;
    }
    v73 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 27, v4 + 5184);
    SwitchUnsafe = v73;
    if ( v73 < 0 )
    {
      LOBYTE(v74) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v74, 20, 34, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v73);
      v10 = 93;
      goto LABEL_91;
    }
    v75 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 16, v4 + 496);
    SwitchUnsafe = v75;
    if ( v75 < 0 )
    {
      LOBYTE(v76) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v76, 20, 35, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v75);
      v10 = 95;
      goto LABEL_91;
    }
    v77 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 17, v4 + 392);
    SwitchUnsafe = v77;
    if ( v77 < 0 )
    {
      LOBYTE(v78) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v78, 20, 36, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v77);
      v10 = 100;
      goto LABEL_91;
    }
    VmsOmObjectLockExclusive(v206, &v211, 0);
    *(_DWORD *)(v4 + 5280) = 0;
    *(_DWORD *)(v4 + 5296) = 0;
    *(_DWORD *)(v4 + 5312) = 0;
    *(_QWORD *)(v4 + 5328) = v4 + 5320;
    *(_QWORD *)(v4 + 5320) = v4 + 5320;
    *(_QWORD *)(v4 + 5352) = v4 + 5344;
    *(_QWORD *)(v4 + 5344) = v4 + 5344;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
    v79 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 20, v4 + 5272);
    SwitchUnsafe = v79;
    if ( v79 < 0 )
    {
      LOBYTE(v80) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v80, 20, 37, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v79);
      v10 = 101;
      goto LABEL_91;
    }
    v81 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 21, v4 + 5288);
    SwitchUnsafe = v81;
    if ( v81 < 0 )
    {
      LOBYTE(v82) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v82, 20, 38, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v81);
      v10 = 102;
      goto LABEL_91;
    }
    v83 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 22, v4 + 5304);
    SwitchUnsafe = v83;
    if ( v83 < 0 )
    {
      LOBYTE(v84) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v84, 20, 39, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v83);
      v10 = 103;
      goto LABEL_91;
    }
    v85 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 28, v4 + 5336);
    SwitchUnsafe = v85;
    if ( v85 < 0 )
    {
      LOBYTE(v86) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v86, 20, 40, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v85);
      v10 = 104;
      goto LABEL_91;
    }
    v87 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 29, v4 + 5360);
    SwitchUnsafe = v87;
    if ( v87 < 0 )
    {
      LOBYTE(v88) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v88, 20, 41, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v87);
      v10 = 106;
      goto LABEL_91;
    }
    v89 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 24, v4 + 5264);
    SwitchUnsafe = v89;
    if ( v89 < 0 )
    {
      LOBYTE(v90) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v90, 20, 42, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v89);
      v10 = 107;
      goto LABEL_91;
    }
    v91 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 37, v4 + 768);
    SwitchUnsafe = v91;
    if ( v91 < 0 )
    {
      LOBYTE(v92) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v92, 20, 43, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v91);
      v10 = 108;
      goto LABEL_91;
    }
    v93 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 37, v4 + 5368);
    SwitchUnsafe = v93;
    if ( v93 < 0 )
    {
      LOBYTE(v94) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v94, 20, 44, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v93);
      v10 = 109;
      goto LABEL_91;
    }
    v95 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 39, v4 + 808);
    SwitchUnsafe = v95;
    if ( v95 < 0 )
    {
      LOBYTE(v96) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v96, 20, 45, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v95);
      v10 = 110;
      goto LABEL_91;
    }
    v97 = NvIoAllocateWorkItem(*(PNPAGED_LOOKASIDE_LIST *)(v206 + 2096), 40, v4 + 776);
    v99 = 0;
    SwitchUnsafe = v97;
    if ( v97 < 0 )
    {
      LOBYTE(v98) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v98, 20, 46, (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids, v97);
      v10 = 111;
      goto LABEL_91;
    }
    v100 = *(_QWORD *)(a3 + 48);
    LODWORD(DefaultSwitchConfig) = 0;
    v220 = v100;
    if ( v100 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v100 = *(_QWORD *)(a3 + 40);
      v220 = v100;
    }
    *(_QWORD *)(v4 + 1544) = v100;
    *(_QWORD *)(v4 + 1552) = *(_QWORD *)(a3 + 40);
    v102 = *(_QWORD *)(a3 + 256);
    if ( !v102 )
    {
LABEL_206:
      v107 = *(_QWORD *)(a3 + 272);
      if ( v107 )
      {
        *(_OWORD *)(v4 + 504) = *(_OWORD *)v107;
        *(_OWORD *)(v4 + 520) = *(_OWORD *)(v107 + 16);
        *(_OWORD *)(v4 + 536) = *(_OWORD *)(v107 + 32);
        *(_OWORD *)(v4 + 552) = *(_OWORD *)(v107 + 48);
        *(_OWORD *)(v4 + 568) = *(_OWORD *)(v107 + 64);
        *(_OWORD *)(v4 + 584) = *(_OWORD *)(v107 + 80);
        *(_OWORD *)(v4 + 600) = *(_OWORD *)(v107 + 96);
        *(_OWORD *)(v4 + 616) = *(_OWORD *)(v107 + 112);
        *(_DWORD *)(v4 + 632) = *(_DWORD *)(v107 + 128);
      }
      v108 = *(_QWORD *)(a3 + 288);
      if ( v108 && (v109 = *(_WORD **)(v108 + 48)) != 0 && *v109 >= 2u )
      {
        *(_DWORD *)(v206 + 4764) = *(_BYTE *)(a3 + 280) != 0 ? 3 : 1;
        v110 = *(_QWORD *)(a3 + 288);
        v111 = v206;
        *(_OWORD *)(v206 + 4768) = *(_OWORD *)v110;
        *(_OWORD *)(v111 + 4784) = *(_OWORD *)(v110 + 16);
        *(_OWORD *)(v111 + 4800) = *(_OWORD *)(v110 + 32);
        *(_QWORD *)(v111 + 4816) = *(_QWORD *)(v110 + 48);
      }
      else
      {
        *(_DWORD *)(v206 + 4764) = 0;
        v112 = v206;
        *(_OWORD *)(v206 + 4768) = 0;
        *(_OWORD *)(v112 + 4784) = 0;
        *(_OWORD *)(v112 + 4800) = 0;
        *(_QWORD *)(v112 + 4816) = 0;
      }
      v113 = *(_QWORD *)(a3 + 296);
      if ( v113 )
      {
        *(_QWORD *)(v4 + 784) = *(_QWORD *)v113;
        *(_DWORD *)(v4 + 792) = *(_DWORD *)(v113 + 8);
      }
      if ( *(_QWORD *)(a3 + 304) )
      {
        DefaultSwitchConfig = VmsIovGetDefaultSwitchConfig();
        if ( DefaultSwitchConfig )
        {
          VmsOmObjectLockExclusive(v206, &v211, 0);
          v114 = 4;
          v115 = (_OWORD *)(v4 + 816);
          v116 = (_OWORD *)DefaultSwitchConfig;
          do
          {
            *v115 = *v116;
            v115[1] = v116[1];
            v115[2] = v116[2];
            v115[3] = v116[3];
            v115[4] = v116[4];
            v115[5] = v116[5];
            v115[6] = v116[6];
            v117 = v116[7];
            v116 += 8;
            v115[7] = v117;
            v115 += 8;
            --v114;
          }
          while ( v114 );
          *v115 = *v116;
          v115[1] = v116[1];
          v115[2] = v116[2];
          *(_OWORD *)((char *)v115 + 44) = *(_OWORD *)((char *)v116 + 44);
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
          v99 = 0;
        }
      }
      v214 = v99;
      VmsIovIsIovSupported(
        *(_QWORD *)(a3 + 272),
        *(_QWORD *)(a3 + 296),
        DefaultSwitchConfig,
        v4 + 305,
        v4 + 1513,
        v4 + 306,
        (__int64)&v214,
        (__int64)&v216);
      LOBYTE(v118) = v214;
      VmsPtNicPvtUpdateVportBasedVmqParameters(v4, v118);
      *(_DWORD *)(v206 + 3356) = *(_DWORD *)(a3 + 36);
      *(_DWORD *)(v206 + 1844) = *(_DWORD *)(a3 + 36);
      v119 = ConvertInterfaceLuidToGuid((const NET_LUID *)(a3 + 168), &InterfaceGuid);
      SwitchUnsafe = v119;
      if ( v119 )
      {
        WPP_RECORDER_SF_Id(
          VmsIfrLog,
          v120,
          v121,
          47,
          (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
          *(_QWORD *)(a3 + 168),
          v119);
        v10 = 110;
LABEL_222:
        v7 = v204;
        goto LABEL_91;
      }
      VmsOmObjectLockExclusive(v206, &v211, 0);
      v232 = InterfaceGuid;
      SwitchUnsafe = VmsPtNicMuxCreateNewMemberAdapter(v206, a3, &v232, &v209);
      if ( SwitchUnsafe )
      {
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
        v10 = 120;
        goto LABEL_222;
      }
      RtlCopyUnicodeString((PUNICODE_STRING)v209 + 136, &SourceString);
      v7 = v204;
      if ( v204 )
      {
        *((_WORD *)v209 + 8) = 1;
        *(_QWORD *)(v4 + 3392) = 0;
      }
      else
      {
        *((_WORD *)v209 + 8) = 0;
        *(_QWORD *)(v4 + 3392) = v209;
      }
      VmsPtNicSetMemberState(v4, *((unsigned __int16 *)v209 + 8), 1);
      VmsPtNicSetMemberState(v4, *((unsigned __int16 *)v209 + 8), 2);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
      OpenParameters.AdapterName = *(PNDIS_STRING *)(a3 + 16);
      OpenParameters.MediumArray = (PNDIS_MEDIUM)&dword_1401FA25C;
      *(_QWORD *)&OpenParameters.FrameTypeArraySize = 0;
      OpenParameters.FrameTypeArray = 0;
      v122 = (PVOID *)(v4 + 112);
      OpenParameters.SelectedMediumIndex = (PUINT)&v222;
      *(_QWORD *)&OpenParameters.Header.Type = 3670407;
      *(_QWORD *)&OpenParameters.MediumArraySize = 1;
      v123 = NdisOpenAdapterEx(VmsProtocolHandle, v209, &OpenParameters, BindContext, (PNDIS_HANDLE)(v4 + 112));
      SwitchUnsafe = v123;
      if ( v123 == 259 )
      {
        NdisWaitEvent((PNDIS_EVENT)(v4 + 144), 0);
        v123 = *(_DWORD *)(v4 + 136);
        SwitchUnsafe = v123;
      }
      if ( v123 )
      {
        WPP_RECORDER_SF_qqqqd(
          VmsIfrLog,
          v124,
          v125,
          48,
          (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
          (char)VmsProtocolHandle,
          (char)v209,
          (char)&OpenParameters,
          (char)BindContext,
          v123);
        *v122 = 0;
        v10 = 125;
        goto LABEL_91;
      }
      v209[18] = *(PVOID *)(a3 + 24);
      SwitchUnsafe = VmsPtNicPvtUpdateFriendlyName(v209, &SourceString, *v122);
      if ( SwitchUnsafe )
      {
        v10 = -126;
        goto LABEL_91;
      }
      v127 = *v122;
      *v209 = *v122;
      if ( !v127 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v126,
          19,
          49,
          (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
          (__int64)"memberAdapter->ProtocolHandle != NULL");
        if ( !*v209 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( v204 && (unsigned int)VmsPtNicConnectNicIndexEx(v206, 1, v209) )
      {
        v10 = -121;
        goto LABEL_91;
      }
      VmsOmObjectLockExclusive(v206, &v211, 0);
      if ( !v204 )
        VmsPtNicSetMemberState(v4, *((unsigned __int16 *)v209 + 8), 3);
      ++*(_DWORD *)(v4 + 2464);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
      *(_DWORD *)(v4 + 96) = *(_DWORD *)(a3 + 72);
      v128 = v206;
      *(_DWORD *)(v206 + 3336) = *(_DWORD *)(a3 + 106);
      *(_WORD *)(v128 + 3340) = *(_WORD *)(a3 + 110);
      *(_DWORD *)(v128 + 1838) = *(_DWORD *)(a3 + 106);
      *(_WORD *)(v128 + 1842) = *(_WORD *)(a3 + 110);
      v129 = v204 != 0;
      v213 = 1;
      v216 = v129;
      SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 0, 16843009, v129, 0, 0, 0, (__int64)&v242, 6, 0, 0, 0, 0);
      if ( SwitchUnsafe )
      {
        v10 = -116;
        goto LABEL_222;
      }
      v130 = v206;
      *(_DWORD *)(v206 + 2104) = v242;
      *(_WORD *)(v130 + 2108) = v243;
      *(_DWORD *)(v130 + 1832) = v242;
      *(_WORD *)(v130 + 1836) = v243;
      VmsPtUpdateMemberAdapterInfoFromBind(v209, a3);
      VmsPtInitializeMemberAdapterNdisQos(v209);
      v131 = v204;
      if ( !v204 )
      {
        VmsPtPvtInitializePtNicNdisQosSettings(v4);
        *(_DWORD *)(v206 + 3360) = 0;
        SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 1, 65806, 0, 0, 0, 0, v206 + 3360, 4, 0, 0, 0, 0);
        if ( SwitchUnsafe )
        {
          v10 = -106;
          v7 = 0;
          goto LABEL_91;
        }
      }
      SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 0, 66819, v129, -1, 1, 0, 0, 0, 0, (__int64)&v221, 0, 0);
      if ( SwitchUnsafe == -1073676266 )
      {
        v132 = v221;
        P = (PVOID)ExAllocatePool2(64, v221, 1146123094);
        if ( P )
        {
          v203 = v132;
          v133 = P;
          SwitchUnsafe = VmsPtPvtProcessPrivateOid(
                           v206,
                           0,
                           66819,
                           v129,
                           -1,
                           1,
                           0,
                           (__int64)P,
                           v203,
                           0,
                           (__int64)&v221,
                           0,
                           0);
          if ( !SwitchUnsafe )
          {
            v134 = v133[4];
            if ( v134 )
            {
              v135 = ExAllocatePool2(64, v134, 1146123094);
              v136 = 0;
              *(_QWORD *)(v4 + 2456) = v135;
              if ( v135 )
              {
                *(_BYTE *)(v4 + 2444) = *((_BYTE *)v133 + 8);
                *(_DWORD *)(v4 + 2448) = v133[4];
                if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
                  WPP_RECORDER_SF_(
                    WPP_GLOBAL_Control->DeviceExtension,
                    0,
                    22,
                    50,
                    (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids);
                memmove(*(void **)(v4 + 2456), (char *)v133 + (unsigned int)v133[3], (unsigned int)v133[4]);
              }
              else
              {
                LOBYTE(v136) = 2;
                WPP_RECORDER_SF_ld(
                  VmsIfrLog,
                  v136,
                  20,
                  51,
                  (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
                  v133[4],
                  SwitchUnsafe);
              }
            }
          }
        }
        v131 = v204;
      }
      v137 = *(_QWORD *)(a3 + 144);
      if ( v137 )
      {
        *(_OWORD *)(v4 + 1516) = *(_OWORD *)v137;
        *(_DWORD *)(v4 + 1532) = *(_DWORD *)(v137 + 16);
      }
      VmsPtPvtInitializeRss(v209);
      VmsPtNicPvtDisableIncompatOffloads(v206, v129);
      v138 = 0;
      v139 = 1;
      if ( v131 )
      {
        *(_DWORD *)(v4 + 3004) = 1;
        *(_DWORD *)(v4 + 3008) = 2;
        *(_DWORD *)(v4 + 3012) = 14;
        *(_DWORD *)(v4 + 3016) = 1;
        *(_DWORD *)(v4 + 3020) = 2;
        *(_DWORD *)(v4 + 3024) = 14;
      }
      if ( *(_QWORD *)(a3 + 224) )
      {
        *(_QWORD *)((char *)&v236[1] + 4) = 0;
        LODWORD(v236[0]) = 1835432;
        *(_QWORD *)((char *)v236 + 4) = 0x200000001LL;
        *(_QWORD *)((char *)v236 + 12) = 14;
        if ( !(unsigned int)VmsPtPvtProcessPrivateOid(v206, 1, 16843018, v129, 0, 0, 0, (__int64)v236, 28, 0, 0, 0, 0) )
        {
          *(_BYTE *)(v4 + 192) = 1;
          if ( v204 )
          {
            *((_DWORD *)v209 + 475) = 1;
            *((_DWORD *)v209 + 476) = 2;
            *((_DWORD *)v209 + 477) = 14;
          }
        }
        DWORD1(v236[0]) = 0;
        LODWORD(v236[1]) = 1;
        *(_QWORD *)((char *)&v236[1] + 4) = 0xE00000002LL;
        v131 = v204;
        if ( !(unsigned int)VmsPtPvtProcessPrivateOid(v206, 1, 16843018, v216, 0, 0, 0, (__int64)v236, 28, 0, 0, 0, 0) )
        {
          *(_BYTE *)(v4 + 192) = 1;
          if ( v204 )
          {
            *((_DWORD *)v209 + 478) = 1;
            *((_DWORD *)v209 + 479) = 2;
            *((_DWORD *)v209 + 480) = 14;
          }
        }
        VmsPtNicUpdateCurrentOffloadCache(v206, *(_QWORD *)(a3 + 224));
        v129 = v216;
        v138 = 0;
      }
      v140 = *(_QWORD *)(a3 + 224);
      if ( v140 )
      {
        *(_OWORD *)(v4 + 1572) = *(_OWORD *)(v140 + 112);
        *(_OWORD *)(v4 + 1588) = *(_OWORD *)(v140 + 128);
      }
      if ( (*(_DWORD *)(a3 + 216) & 0x200) != 0 )
        *(_BYTE *)(v206 + 3556) = 1;
      if ( v208 )
      {
        SwitchUnsafe = VmsPtNicCreateDefaultNicSwitchOnMemberAdapter(v209, a3);
      }
      else
      {
        if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 2) == 0 )
          goto LABEL_292;
        v141 = &VmsEmptyString;
        if ( v206 && v6 )
          v142 = *(__int64 **)(v6 + 624);
        else
          v142 = &VmsEmptyString;
        if ( v206 && v6 )
          v143 = *(__int64 **)(v6 + 80);
        else
          v143 = &VmsEmptyString;
        if ( v209 )
          v144 = (__int64 *)v209[307];
        else
          v144 = &VmsEmptyString;
        if ( v209 )
          v141 = (__int64 *)v209[273];
        McTemplateK0tqzzzzq_EtwWriteTransfer(
          (_DWORD)v144,
          (unsigned int)VMS_NIC_SWITCH_NOT_SUPPORTED_ON_FIRST_MEMBER,
          (_DWORD)v142,
          v131,
          0,
          (__int64)v141,
          (__int64)v144,
          (__int64)v143,
          (__int64)v142,
          SwitchUnsafe);
      }
      v138 = 0;
LABEL_292:
      if ( *(_QWORD *)(a3 + 272) )
      {
        VmsVmmqInitialize(v209 + 465, a3);
        v138 = 0;
      }
      v145 = v131 == 0;
      v146 = (_BYTE *)(v4 + 305);
      if ( !v145 )
      {
        *((_DWORD *)v209 + 50) = 65551;
        if ( !*v146 || !*(_DWORD *)(v6 + 8568) )
          *((_DWORD *)v209 + 50) |= 0x20u;
        v147 = VmsPtPvtProcessPrivateOid(v206, 1, 65806, v129, 0, 0, 0, (__int64)(v209 + 25), 4, 4, 0, 0, 0);
        v138 = 0;
        SwitchUnsafe = v147;
        if ( v147 )
        {
          v10 = -101;
          goto LABEL_222;
        }
      }
      if ( *v146 )
      {
        SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 0, 66144, v129, 0, 0, 0, (__int64)v238, 12, 0, 0, 0, 0);
        if ( SwitchUnsafe )
        {
          v10 = -96;
          goto LABEL_222;
        }
        *(_QWORD *)(v4 + 1388) = *(_QWORD *)((char *)v238 + 4);
        v209[462] = *(PVOID *)((char *)v238 + 4);
        v138 = 0;
      }
      v148 = *(_BYTE *)(v4 + 304);
      v208 = 0;
      if ( v148 )
      {
        if ( *(_BYTE *)(v4 + 306) )
        {
          if ( !*(_QWORD *)(a3 + 256) )
          {
            WPP_RECORDER_SF_s(
              VmsIfrLog,
              v139,
              19,
              52,
              (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
              (__int64)"BindParams->ReceiveFilterCapabilities");
            if ( !*(_QWORD *)(a3 + 256) )
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          v138 = *(_BYTE *)(v4 + 304);
          *(_DWORD *)(v4 + 428) = *(_DWORD *)(v4 + 1432);
          v148 = v138;
        }
        else
        {
          v138 = v148;
        }
      }
      v7 = v204;
      if ( v204 && *(_BYTE *)(v4 + 306) == 1 )
      {
        v149 = *(_DWORD *)(v4 + 1348) + *(_DWORD *)(v4 + 1432);
      }
      else
      {
        if ( !*v146 && !*(_BYTE *)(v4 + 1513) )
        {
          if ( v148 )
          {
            v149 = *(_DWORD *)(v4 + 428);
            if ( v149 )
              goto LABEL_326;
            *(_BYTE *)(v4 + 304) = 0;
            *(_BYTE *)(v4 + 1496) = 0;
          }
          else
          {
            v149 = 0;
          }
LABEL_322:
          if ( !*v146 && !*(_BYTE *)(v4 + 1513) )
          {
            if ( !v204 )
              VmsPDIsPDSupported(v4, 0);
            goto LABEL_337;
          }
LABEL_326:
          v150 = ExAllocatePool2(64, 8LL * v149, 1349743446);
          v154 = (_QWORD *)(v4 + 1424);
          v155 = (void *)v150;
          *(_QWORD *)(v4 + 1424) = v150;
          if ( !v150 )
          {
            SwitchUnsafe = -1073741801;
            WPP_RECORDER_SF_P(v152, v151, v153, 53, NdisBindingHandleb, 8 * v149);
            v10 = -91;
            goto LABEL_222;
          }
          *(_DWORD *)(v4 + 1420) = v149;
          if ( v149 )
          {
            v156 = 0;
            if ( v149 < 2 || v150 <= (unsigned __int64)v154 && v150 + 8LL * (v149 - 1) >= (unsigned __int64)v154 )
              goto LABEL_444;
            v157 = v149 & 0xFFFFFFFE;
            do
            {
              v156 += 2;
              v158 = v156;
            }
            while ( v156 < v157 );
            memset(v155, 0, 16 * ((unsigned __int64)v157 >> 1));
            v156 = v158;
            if ( v158 < v149 )
            {
LABEL_444:
              do
              {
                v159 = v156++;
                *(_QWORD *)(*v154 + 8 * v159) = 0;
              }
              while ( v156 < v149 );
            }
          }
          v7 = v204;
LABEL_337:
          v160 = 0;
          VmsPtRssInitialize(v206);
          SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 0, -100597503, v216, 0, 0, 0, (__int64)v241, 208, 0, 0, 0, 0);
          *(_BYTE *)(v4 + 2400) = 0;
          if ( SwitchUnsafe )
          {
            *(_QWORD *)(v4 + 1560) = v220;
            SwitchUnsafe = 0;
          }
          else if ( BYTE1(v241[0]) >= 2u && WORD1(v241[0]) >= 0xCCu && (v241[25] & 1) != 0 )
          {
            *(_QWORD *)(v4 + 1560) = v220;
          }
          else
          {
            v160 = 1;
            *(_BYTE *)(v4 + 2401) = 1;
            v161 = v220;
            if ( (unsigned __int64)(v241[8] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
              v161 = v241[8];
            v162 = *(void **)(v4 + 112);
            *(_QWORD *)(v4 + 1560) = v161;
            SwitchUnsafe = VmsPtPvtDetectTeamingProvider(v162);
            if ( SwitchUnsafe )
            {
              v10 = -86;
              goto LABEL_91;
            }
            if ( !v215 )
            {
              *(_BYTE *)(v4 + 2400) = 1;
              v160 = 2;
            }
          }
          v163 = ConvertInterfaceLuidToGuid((const NET_LUID *)(a3 + 168), (GUID *)(v4 + 2416));
          SwitchUnsafe = v163;
          if ( v163 )
          {
            WPP_RECORDER_SF_Id(
              VmsIfrLog,
              v164,
              v165,
              54,
              (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
              *(_QWORD *)(a3 + 168),
              v163);
            v10 = -81;
            goto LABEL_91;
          }
          *(_OWORD *)(v206 + 1816) = *(_OWORD *)(v4 + 2416);
          *(_QWORD *)(v206 + 3176) = VmsPtNicPvtPacketForward;
          *(_QWORD *)(v206 + 3168) = &VmsPtNicPvtPacketRouted;
          *(_QWORD *)(v206 + 3200) = VmsPtNicPvtLinkStateChanged;
          *(_QWORD *)(v206 + 3272) = VmsPtNicPvtUpdateNdisStack;
          *(_QWORD *)(v206 + 3256) = 0;
          *(_QWORD *)(v206 + 3264) = VmsPtNicPvtDeliverPDBuffers;
          *(_QWORD *)(v206 + 3240) = VmsPtNicPvtAllowRef;
          *(_DWORD *)(v206 + 68) = 1;
          if ( v7 )
          {
            VmsPtNicMuxTaskOffloadInit(v4 + 2780, v209 + 108);
            VmsPtNicMuxTaskOffloadInit(v4 + 2560, (char *)v209 + 644);
          }
          if ( !v230 )
          {
            v166 = v226;
            v167 = VmsOmNicConnect(&DestinationString, v224, v226);
            SwitchUnsafe = v167;
            if ( v167 < 0 )
            {
              WPP_RECORDER_SF_ZZZd(
                VmsIfrLog,
                v168,
                v169,
                55,
                (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
                (__int64)&DestinationString,
                (__int64)v224,
                (__int64)v166,
                v167);
              v10 = -77;
              goto LABEL_91;
            }
          }
          if ( v7 )
          {
            *((_DWORD *)v209 + 48) = 2;
            v170 = v206;
            if ( *(_DWORD *)(v206 + 1880) != 1 )
            {
LABEL_361:
              v171 = *(_QWORD *)(v170 + 1888);
              v202 = (v171 + 72) & -(__int64)(v171 != 0);
              VmsEtwTraceNicTeamConfiguration(
                v170 + 72,
                v202,
                v171 != 0 ? v171 + 616 : 0,
                v160,
                v170 + 72,
                v170 + 616,
                v202,
                (v171 + 616) & -(__int64)(v171 != 0));
              if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
                WPP_RECORDER_SF_id(
                  WPP_GLOBAL_Control->DeviceExtension,
                  0,
                  8,
                  56,
                  (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
                  v4,
                  SwitchUnsafe);
              goto LABEL_91;
            }
            VmsPtNicMuxCalculateProtocolNicTaskOffloadCapsChange(v206);
            SwitchUnsafe = VmsPtNicMUXNotifyConnectToExtStack(v209);
            if ( SwitchUnsafe )
            {
              v10 = -76;
              goto LABEL_91;
            }
          }
          v170 = v206;
          goto LABEL_361;
        }
        v149 = *(_DWORD *)(v4 + 1356) - 1;
      }
      if ( v138 )
        goto LABEL_326;
      goto LABEL_322;
    }
    *(_OWORD *)(v4 + 412) = *(_OWORD *)v102;
    *(_OWORD *)(v4 + 428) = *(_OWORD *)(v102 + 16);
    *(_OWORD *)(v4 + 444) = *(_OWORD *)(v102 + 32);
    *(_OWORD *)(v4 + 460) = *(_OWORD *)(v102 + 48);
    *(_OWORD *)(v4 + 476) = *(_OWORD *)(v102 + 64);
    *(_DWORD *)(v4 + 492) = *(_DWORD *)(v102 + 80);
    v103 = *(_DWORD **)(a3 + 256);
    if ( (v103[2] & 1) != 0
      && (v103[3] & 1) != 0
      && (v103[5] & 2) != 0
      && (v103[6] & 1) != 0
      && (v103[7] & 1) != 0
      && (v103[8] & 1) != 0 )
    {
      if ( v100 < 0x2540BE400LL )
      {
        v104 = VmsVmqUserConfig;
        *(_BYTE *)(v4 + 304) = VmsVmqUserConfig;
        if ( !v104 )
          goto LABEL_205;
      }
      else
      {
        *(_BYTE *)(v4 + 304) = 1;
      }
      if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(*(_QWORD *)v4, 0) )
      {
        *(_BYTE *)(v4 + 2401) = 1;
        *(_BYTE *)(v4 + 1496) = 1;
LABEL_204:
        *(_DWORD *)(v4 + 1500) = 2;
        goto LABEL_205;
      }
      if ( (v103[5] & 8) == 0 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v105,
          19,
          273,
          (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
          (__int64)"(ReceiveFilterCaps->SupportedQueueProperties & NDIS_RECEIVE_FILTER_DYNAMIC_PROCESSOR_AFFINITY_CHANGE_SUPPORTED) != 0");
        if ( (v103[5] & 8) == 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      *(_DWORD *)(v4 + 1500) = 0;
      *(_BYTE *)(v4 + 1496) = 1;
      v106 = v103[5];
      if ( (v106 & 0x40) != 0 )
      {
        *(_DWORD *)(v4 + 1500) = 1;
      }
      else if ( (v106 & 0x80u) != 0 )
      {
        goto LABEL_204;
      }
    }
LABEL_205:
    LOBYTE(v201) = *(_BYTE *)(v4 + 304);
    NdisBindingHandled = (PNDIS_HANDLE)((*(_QWORD *)v4 + 616LL) & -(__int64)(*(_QWORD *)v4 != 0));
    VmsEtwTraceVmqCaps(
      *(_QWORD *)v4 + 616,
      -*(_DWORD *)v4,
      (_DWORD)NdisBindingHandled,
      *(_QWORD *)v4 != 0 ? *(_DWORD *)v4 + 72 : 0,
      (__int64)NdisBindingHandled,
      v220,
      v201,
      *(_BYTE *)(v4 + 1496),
      *(_DWORD *)(v4 + 1500),
      (__int64)v103);
    v99 = 0;
    goto LABEL_206;
  }
  SwitchUnsafe = VmsUtilUpcaseUnicodeString(v234, v226);
  if ( SwitchUnsafe )
  {
    v10 = 13;
    goto LABEL_93;
  }
  VmsOmObjectLockShared(v6, &v218, 0);
  SwitchUnsafe = VmsOmpFindPortInListUnsafe(v6 + 1416, v234, &v232);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), &v218);
  v5 = *(_QWORD *)&v232.Data1;
  if ( SwitchUnsafe )
  {
LABEL_12:
    SwitchUnsafe = -1073741772;
    goto LABEL_93;
  }
  v212 = *(_QWORD *)&v232.Data1;
  VmsOmObjectLockShared(*(_QWORD *)&v232.Data1, &v219, 0);
  v19 = *(_QWORD *)(v5 + 1256);
  if ( v19 )
  {
    if ( *(_DWORD *)(v19 + 1872) != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v18,
        19,
        16,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (__int64)"objPort->Nic->Type == VmsNicProtocol");
      if ( *(_DWORD *)(*(_QWORD *)(v5 + 1256) + 1872LL) != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v210 = 1;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 56), &v219);
  if ( v210 != 1 )
    goto LABEL_131;
  if ( *(_DWORD *)(*(_QWORD *)(v5 + 1256) + 1872LL) != 2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v20,
      19,
      17,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"objPort->Nic->Type == VmsNicProtocol");
    if ( *(_DWORD *)(*(_QWORD *)(v5 + 1256) + 1872LL) != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v206 = *(_QWORD *)(v5 + 1256);
  v4 = *(_QWORD *)(v206 + 3312);
  v21 = ConvertInterfaceLuidToGuid((const NET_LUID *)(a3 + 168), &InterfaceGuid);
  SwitchUnsafe = v21;
  if ( v21 )
  {
    WPP_RECORDER_SF_Id(
      VmsIfrLog,
      v22,
      v23,
      18,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      *(_QWORD *)(a3 + 168),
      v21);
    v10 = 14;
    goto LABEL_92;
  }
  VmsOmObjectLockExclusive(v206, &v211, 0);
  v235 = InterfaceGuid;
  SwitchUnsafe = VmsPtNicMuxCreateNewMemberAdapter(v206, a3, &v235, &v209);
  if ( SwitchUnsafe )
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
    v10 = 15;
    goto LABEL_92;
  }
  SwitchUnsafe = VmsPtPvtAllocateNicIndex(v206, &v216);
  if ( SwitchUnsafe )
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
    v8 = v216;
    v10 = 25;
    SwitchUnsafe = -1073741670;
    goto LABEL_93;
  }
  v8 = v216;
  v207 = v216;
  *((_WORD *)v209 + 8) = v216;
  RtlCopyUnicodeString((PUNICODE_STRING)v209 + 136, &SourceString);
  VmsPtNicSetMemberState(v4, v8, 2);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
  OpenParameters.AdapterName = *(PNDIS_STRING *)(a3 + 16);
  OpenParameters.MediumArray = (PNDIS_MEDIUM)&dword_1401FA25C;
  *(_QWORD *)&OpenParameters.FrameTypeArraySize = 0;
  OpenParameters.FrameTypeArray = 0;
  OpenParameters.SelectedMediumIndex = (PUINT)&v222;
  *(_QWORD *)&OpenParameters.Header.Type = 3670407;
  *(_QWORD *)&OpenParameters.MediumArraySize = 1;
  v24 = NdisOpenAdapterEx(VmsProtocolHandle, v209, &OpenParameters, BindContext, v209);
  SwitchUnsafe = v24;
  if ( v24 )
  {
    WPP_RECORDER_SF_qqqqd(
      VmsIfrLog,
      v25,
      v26,
      19,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (char)VmsProtocolHandle,
      (char)v209,
      (char)&OpenParameters,
      (char)BindContext,
      v24);
    v10 = 20;
    goto LABEL_92;
  }
  v209[18] = *(PVOID *)(a3 + 24);
  SwitchUnsafe = VmsPtNicPvtUpdateFriendlyName(v209, &SourceString, *v209);
  if ( SwitchUnsafe )
  {
    v10 = 30;
    goto LABEL_93;
  }
  v27 = v8;
  if ( (unsigned int)VmsPtNicConnectNicIndexEx(v206, v8, v209) )
  {
    v10 = 35;
LABEL_43:
    v5 = v212;
    goto LABEL_93;
  }
  VmsOmObjectLockExclusive(v206, &v211, 0);
  *((_DWORD *)v209 + 48) = 2;
  ++*(_DWORD *)(v4 + 2464);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
  v213 = 1;
  VmsPtUpdateMemberAdapterInfoFromBind(v209, a3);
  VmsPtInitializeMemberAdapterNdisQos(v209);
  VmsPtPvtInitializeRss(v209);
  VmsPtNicPvtDisableIncompatOffloads(v206, v8);
  LOBYTE(v28) = *(_BYTE *)(v6 + 9192);
  VmsRscApplyOffloadSettings(v206, v8, v28);
  if ( *(_QWORD *)(a3 + 224) )
  {
    *(_QWORD *)((char *)&v236[1] + 4) = 0;
    *(_QWORD *)&v236[0] = 0x1001C01A8LL;
    DWORD2(v236[0]) = 2;
    *(_QWORD *)((char *)v236 + 12) = 14;
    if ( !(unsigned int)VmsPtPvtProcessPrivateOid(v206, 1, 16843018, v8, 0, 0, 0, (__int64)v236, 28, 0, 0, 0, 0) )
    {
      *((_DWORD *)v209 + 475) = 1;
      *((_DWORD *)v209 + 476) = 2;
      *((_DWORD *)v209 + 477) = 14;
    }
    DWORD1(v236[0]) = 0;
    LODWORD(v236[1]) = 1;
    *(_QWORD *)((char *)&v236[1] + 4) = 0xE00000002LL;
    if ( !(unsigned int)VmsPtPvtProcessPrivateOid(v206, 1, 16843018, v8, 0, 0, 0, (__int64)v236, 28, 0, 0, 0, 0) )
    {
      *((_DWORD *)v209 + 478) = 1;
      *((_DWORD *)v209 + 479) = 2;
      *((_DWORD *)v209 + 480) = 14;
    }
    LOBYTE(v29) = 13;
    if ( (unsigned __int8)VmsOmObjectPrepareForConfigStore(v206, v29, 1) == 1 )
    {
      v7 = v204;
      v8 = v207;
      if ( (unsigned int)VmsOmNicStoreConfig(v206, (const UNICODE_STRING *)v209 + 136, 13) )
      {
        v10 = 36;
        goto LABEL_43;
      }
    }
    else
    {
      v7 = v204;
      v8 = v207;
    }
  }
  *((_DWORD *)v209 + 50) = 65551;
  if ( !*(_BYTE *)(v4 + 305) || !*(_DWORD *)(v6 + 8568) )
    *((_DWORD *)v209 + 50) |= 0x20u;
  SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 1, 65806, v27, 0, 0, 0, (__int64)(v209 + 25), 4, 4, 0, 0, 0);
  if ( SwitchUnsafe )
  {
    v10 = 40;
    goto LABEL_43;
  }
  if ( *(_BYTE *)(v4 + 305) )
  {
    SwitchUnsafe = VmsPtPvtProcessPrivateOid(v206, 0, 66144, v27, 0, 0, 0, (__int64)v238, 12, 0, 0, 0, 0);
    if ( SwitchUnsafe )
    {
      v10 = 45;
      goto LABEL_43;
    }
    v209[462] = *(PVOID *)((char *)v238 + 4);
  }
  VmsPtNicMuxCalculateProtocolNicTaskOffloadCapsChange(v206);
  if ( !*(_BYTE *)(v4 + 1514) )
  {
    if ( v208 )
    {
      WPP_RECORDER_SF_Z_guid_Dqqd(
        *((unsigned __int16 *)v209 + 8),
        (_DWORD)v209 + 2176,
        v30,
        22,
        NdisBindingHandlea,
        (__int64)(v209 + 272),
        (__int64)&InterfaceGuid,
        *((_WORD *)v209 + 8),
        v206,
        v6,
        SwitchUnsafe);
      if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 4) != 0 )
      {
        v44 = &VmsEmptyString;
        if ( v206 )
          v45 = *(__int64 **)(v6 + 624);
        else
          v45 = &VmsEmptyString;
        if ( v206 )
          v46 = *(__int64 **)(v6 + 80);
        else
          v46 = &VmsEmptyString;
        if ( v209 )
          v47 = (__int64 *)v209[307];
        else
          v47 = &VmsEmptyString;
        if ( v209 )
          v44 = (__int64 *)v209[273];
        McTemplateK0tqzzzzq_EtwWriteTransfer(
          v209 != 0 ? v27 : 0,
          (unsigned int)VMS_EMBEDDED_TEAMING_TEAM_NIC_SWITCH_ASSYMETRIC_CONFIGURATION,
          (_DWORD)v46,
          v7,
          v209 != 0 ? v27 : 0,
          (__int64)v44,
          (__int64)v47,
          (__int64)v46,
          (__int64)v45,
          SwitchUnsafe);
      }
    }
    goto LABEL_127;
  }
  if ( !v208 )
  {
    SwitchUnsafe = -1073741637;
    WPP_RECORDER_SF_Z_guid_Dqqd(
      *((unsigned __int16 *)v209 + 8),
      (_DWORD)v209 + 2176,
      -1073741637,
      20,
      NdisBindingHandlea,
      (__int64)(v209 + 272),
      (__int64)&InterfaceGuid,
      *((_WORD *)v209 + 8),
      v206,
      v6,
      187);
    v31 = &VmsEmptyString;
    if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 4) != 0 )
    {
      v32 = v206 ? *(__int64 **)(v6 + 624) : &VmsEmptyString;
      v33 = v206 ? *(__int64 **)(v6 + 80) : &VmsEmptyString;
      v34 = v209 ? v209[307] : &VmsEmptyString;
      v35 = v209 ? v209[273] : &VmsEmptyString;
      McTemplateK0tqzzzzq_EtwWriteTransfer(
        v209 != 0 ? v27 : 0,
        (unsigned int)VMS_NIC_SWITCH_NOT_SUPPORTED_ON_SECONDARY_MEMBER,
        (_DWORD)v34,
        v7,
        v209 != 0 ? v27 : 0,
        (__int64)v35,
        (__int64)v34,
        (__int64)v33,
        (__int64)v32,
        SwitchUnsafe);
      if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 4) != 0 )
      {
        if ( v206 )
          v36 = *(__int64 **)(v6 + 624);
        else
          v36 = &VmsEmptyString;
        if ( v206 )
          v37 = *(__int64 **)(v6 + 80);
        else
          v37 = &VmsEmptyString;
        if ( v209 )
          v38 = (__int64 *)v209[307];
        else
          v38 = &VmsEmptyString;
        if ( v209 )
          v31 = (__int64 *)v209[273];
        McTemplateK0tqzzzzq_EtwWriteTransfer(
          v209 != 0 ? v27 : 0,
          (unsigned int)VMS_EMBEDDED_TEAMING_TEAM_NIC_SWITCH_ASSYMETRIC_CONFIGURATION,
          (_DWORD)v37,
          v7,
          v209 != 0 ? v27 : 0,
          (__int64)v31,
          (__int64)v38,
          (__int64)v37,
          (__int64)v36,
          SwitchUnsafe);
      }
    }
    v10 = 46;
    goto LABEL_91;
  }
  SwitchUnsafe = VmsPtNicCreateDefaultNicSwitchOnMemberAdapter(v209, a3);
  if ( SwitchUnsafe )
  {
    v10 = 47;
    goto LABEL_43;
  }
  if ( *(_DWORD *)(v6 + 8916) != 1 )
  {
    if ( !*(_BYTE *)(v6 + 8904) || !(unsigned __int8)VmsPDIsPDSupported(v4, 0) || !*(_QWORD *)(v6 + 4264) )
      goto LABEL_127;
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_I(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        22,
        21,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        v206);
    v43 = 1;
    goto LABEL_112;
  }
  if ( (int)VmsPDSetupPDAccess(v206, v206, v8) < 0 )
  {
    v43 = 0;
LABEL_112:
    VmsPDSwitchDataPathMode(v6, v206, v43);
  }
LABEL_127:
  if ( *(_QWORD *)(a3 + 272) )
    VmsVmmqInitialize(v209 + 465, a3);
  VmsPtNicMuxAggregateNicSwitchCaps(v206);
  v48 = VmsPtNicMUXNotifyConnectToExtStack(v209);
  v5 = v212;
  v8 = v207;
  SwitchUnsafe = v48;
  if ( v48 )
    v10 = 50;
LABEL_93:
  v39 = v206;
  if ( v206 )
  {
    v5 = *(_QWORD *)(v206 + 1984);
    v6 = *(_QWORD *)(v206 + 1888);
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    v39 = v206;
  }
  v40 = 0;
  if ( SwitchUnsafe )
  {
    if ( v6 )
    {
      v178 = v6 + 616;
      v179 = v6 + 72;
    }
    else
    {
      v178 = 0;
      v179 = 0;
    }
    if ( v5 )
    {
      v180 = v5 + 616;
      v181 = v5 + 72;
    }
    else
    {
      v180 = 0;
      v181 = 0;
    }
    if ( v39 )
    {
      v40 = v39 + 616;
      v39 += 72;
    }
    VmsEtwTraceNicError(
      (unsigned int)VM_PROTOCOL_BIND_FAILED,
      v180,
      v181,
      (unsigned int)&SwitchUnsafe,
      v10,
      v39,
      v40,
      v181,
      v180,
      v179,
      v178);
    v184 = 0;
    if ( v206 )
      v184 = v206 + 616;
    WPP_RECORDER_SF_qqqqqZd(
      v206,
      v184,
      v182,
      v183,
      NdisBindingHandlec,
      (char)BindContext,
      a3,
      v206,
      v5,
      v6,
      v184,
      SwitchUnsafe);
  }
  else
  {
    if ( v6 )
    {
      v41 = v6 + 616;
      v42 = v6 + 72;
    }
    else
    {
      v41 = 0;
      v42 = 0;
    }
    if ( v5 )
    {
      v172 = v5 + 616;
      v173 = v5 + 72;
    }
    else
    {
      v172 = 0;
      v173 = 0;
    }
    VmsEtwTraceNicSuccess(
      (unsigned int)VM_PROTOCOL_BIND_SUCCEEDED,
      v172,
      v173,
      v39 + 72,
      v39 + 616,
      v173,
      v172,
      v42,
      v41);
    WPP_RECORDER_SF_qZqq(v206, v174, v175, v176, NdisBindingHandlee, v206, v206 + 616, v5, v6);
  }
  if ( v224 )
    ExFreePoolWithTag(v224, 0);
  if ( v226 )
    ExFreePoolWithTag(v226, 0);
  if ( !SwitchUnsafe )
  {
    if ( !v7 )
    {
      v192 = v206;
      goto LABEL_439;
    }
    if ( *(_DWORD *)(v4 + 4LL * *((unsigned __int16 *)v209 + 8) + 1632) != 3 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v177,
        19,
        60,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (__int64)"VmsPtNicIsMemberConnected(ptNicExt, memberAdapter->MemberIndex)");
      if ( *(_DWORD *)(v4 + 4LL * *((unsigned __int16 *)v209 + 8) + 1632) != 3 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    VmsPtNicMuxConsolidateProtocolNicNdisQosSettings(v206);
    VmsPtNicMuxUpdateHwQosOnNewMember(v209);
    v188 = v210;
    goto LABEL_434;
  }
  if ( v7 )
  {
    if ( v209 )
    {
      VmsOmObjectLockExclusive(v206, &v211, 0);
      VmsPtNicSetMemberState(v4, *((unsigned __int16 *)v209 + 8), 4);
      *((_DWORD *)v209 + 48) = 6;
      v185 = *((_BYTE *)v209 + 3688);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
      if ( v185 )
        NdisWaitEvent((PNDIS_EVENT)(v209 + 269), 0xBB8u);
      if ( !v210 )
        v8 = 1;
      if ( v8 )
      {
        if ( *(_QWORD *)(v4 + 8LL * v8 + 1888) )
          VmsPtNicDisconnectNicIndexEx(v206, v8);
        VmsPtPvtCleanupNicIndex(v206, v8);
      }
      VmsOmObjectLockExclusive(v206, &v211, 0);
      if ( *(_DWORD *)(v4 + 4LL * v8 + 1632) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v186,
          19,
          59,
          (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
          (__int64)"VmsPtNicGetMemberState(ptNicExt, memberIndex) == VmsMemberNicStateFree");
        if ( *(_DWORD *)(v4 + 4LL * v8 + 1632) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( v213 )
        --*(_DWORD *)(v4 + 2464);
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v206 + 56), &v211);
      if ( *v209 )
      {
        NdisResetEvent((PNDIS_EVENT)(v4 + 144));
        if ( NdisCloseAdapterEx(*v209) == 259 )
          NdisWaitEvent((PNDIS_EVENT)(v4 + 144), 0);
      }
      v187 = v209[248];
      if ( v187 )
      {
        ExFreePoolWithTag(v187, 0);
        v209[248] = 0;
      }
      NvIoFreeWorkItem(v209 + 464);
      ExFreePoolWithTag(v209, 0);
    }
    v188 = v210;
    if ( !v210 )
    {
      if ( !v4 )
        goto LABEL_425;
      goto LABEL_413;
    }
LABEL_434:
    v192 = v206;
    goto LABEL_435;
  }
  if ( !v4 )
    goto LABEL_425;
  v189 = *(_QWORD *)(v4 + 3392);
  if ( v189 )
    NvIoFreeWorkItem(v189 + 3712);
LABEL_413:
  if ( *(_QWORD *)(v4 + 112) )
  {
    KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
    VmsVmqDoVmqOperation(v206, 0, 2);
    v190 = *(void **)(v4 + 1424);
    if ( v190 )
    {
      ExFreePoolWithTag(v190, 0);
      *(_QWORD *)(v4 + 1424) = 0;
      *(_DWORD *)(v4 + 1420) = 0;
    }
    VmsIovDeleteMacFilters(v206, 0);
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
    if ( *(_BYTE *)(v4 + 1514) )
      VmsPtNicDeleteDefaultNicSwitch(v4, 0);
    NdisResetEvent((PNDIS_EVENT)(v4 + 144));
    if ( NdisCloseAdapterEx(*(NDIS_HANDLE *)(v4 + 112)) == 259 )
      NdisWaitEvent((PNDIS_EVENT)(v4 + 144), 0);
    v191 = *(_QWORD **)(v4 + 3392);
    *(_QWORD *)(v4 + 112) = 0;
    if ( v191 )
      *v191 = 0;
  }
  if ( v206 )
    VmsPtPvtRemovePtNicNdisQosSettings(v4);
  else
    VmsPtNicPvtContextCleanup(0, v4);
LABEL_425:
  v192 = v206;
  if ( v206 )
  {
    VmsOmNicDelete(v206);
    v192 = v206;
  }
  if ( v7 )
  {
    v188 = v210;
LABEL_435:
    if ( v192 && !v188 )
      goto LABEL_440;
    goto LABEL_441;
  }
LABEL_439:
  if ( v192 )
  {
LABEL_440:
    LOBYTE(v177) = 7;
    VmsOmpObjectDereference(v192, v177);
  }
LABEL_441:
  v193 = NdisConvertNdisStatusToNtStatus(SwitchUnsafe);
  VmsWppTraceApi(
    (unsigned int)&v227,
    (unsigned int)"VmsPtNicBindAdapterEx",
    (unsigned int)"onecore\\vm\\dv\\net\\nvsp\\driver\\pt\\vmspt.c",
    3827,
    4,
    v193,
    1,
    0,
    0);
  return SwitchUnsafe;
}

```

## disassembly

```asm
0x140117fb0  mov     [rsp-8+arg_0], rbx
0x140117fb5  push    rbp
0x140117fb6  push    rsi
0x140117fb7  push    rdi
0x140117fb8  push    r12
0x140117fba  push    r13
0x140117fbc  push    r14
0x140117fbe  push    r15
0x140117fc0  lea     rbp, [rsp-5F0h]
0x140117fc8  sub     rsp, 6F0h
0x140117fcf  mov     rax, cs:__security_cookie
0x140117fd6  xor     rax, rsp
0x140117fd9  mov     [rbp+620h+var_40], rax
0x140117fe0  xorps   xmm0, xmm0
0x140117fe3  mov     [rbp+620h+BindContext], rdx
0x140117fe7  xor     eax, eax
0x140117fe9  mov     [rsp+720h+var_6AC], 0C0000001h
0x140117ff1  xor     ebx, ebx
0x140117ff3  mov     [rbp+620h+OpenParameters.FrameTypeArraySize], eax
0x140117ff6  mov     r14, r8
0x140117ff9  mov     [rsp+720h+var_6A8], rbx
0x140117ffe  movups  [rbp+620h+var_590], xmm0
0x140118005  xor     edx, edx; Val
0x140118007  mov     [rbp+620h+var_65C], ebx
0x14011800a  mov     r8d, 0D0h; Size
0x140118010  mov     [rbp+620h+var_450], eax
0x140118016  lea     rcx, [rbp+620h+var_520]; void *
0x14011801d  mov     [rbp+620h+var_44C], ax
0x140118024  movups  [rbp+620h+var_590+0Ch], xmm0
0x14011802b  mov     edi, ebx
0x14011802d  mov     [rbp+620h+var_560], eax
0x140118033  movups  xmmword ptr [rbp+620h+OpenParameters.Header.Type], xmm0
0x140118037  mov     [rbp+620h+var_650], rbx
0x14011803b  movups  xmmword ptr [rbp+620h+OpenParameters.MediumArray], xmm0
0x14011803f  mov     [rbp+620h+var_638], rbx
0x140118043  movups  xmmword ptr [rbp+620h+OpenParameters.SelectedMediumIndex], xmm0
0x140118047  mov     [rbp+620h+var_558], rax
0x14011804e  movups  xmmword ptr [rbp+620h+Parameters.Header.Type], xmm0
0x140118055  mov     [rbp+620h+var_550], eax
0x14011805b  movups  [rbp+620h+var_548], xmm0
0x140118062  call    memset
0x140118067  xor     eax, eax
0x140118069  mov     [rbp+620h+var_67E], bl
0x14011806c  xorps   xmm0, xmm0
0x14011806f  mov     [rbp+620h+var_688], rbx
0x140118073  mov     r15d, ebx
0x140118076  mov     qword ptr [rbp+620h+var_5D0], rbx
0x14011807a  mov     r13d, ebx
0x14011807d  mov     [rbp+620h+var_668], rbx
0x140118081  mov     [rbp+620h+var_660], ebx
0x140118084  lea     rcx, [rbp+620h+var_440]; void *
0x14011808b  mov     [rbp+620h+P], rbx
0x14011808f  mov     r12b, bl
0x140118092  mov     [rbp+620h+var_630], rbx
0x140118096  mov     esi, ebx
0x140118098  mov     [rbp+620h+var_698], rbx
0x14011809c  xor     edx, edx; Val
0x14011809e  mov     [rbp+620h+var_690], bl
0x1401180a1  mov     [rbp+620h+var_6A0], ebx
0x1401180a4  mov     word ptr [rbp+620h+var_67C], bx
0x1401180a8  mov     [rbp+620h+var_680], bl
0x1401180ab  mov     ebx, 0FEh
0x1401180b0  mov     r8d, ebx; Size
0x1401180b3  mov     word ptr [rbp+620h+LockState.OldIrql], ax
0x1401180b7  movups  xmmword ptr [rbp+620h+InterfaceGuid.Data1], xmm0
0x1401180be  mov     [rbp+620h+LockState.Flags], al
0x1401180c1  mov     word ptr [rbp+620h+var_674.OldIrql], ax
0x1401180c5  mov     [rbp+620h+var_674.Flags], al
0x1401180c8  mov     word ptr [rbp+620h+var_670.OldIrql], ax
0x1401180cc  mov     [rbp+620h+var_670.Flags], al
0x1401180cf  mov     word ptr [rbp+620h+var_68C.OldIrql], ax
0x1401180d3  mov     [rbp+620h+var_68C.Flags], al
0x1401180d6  call    memset
0x1401180db  lea     rax, [rbp+620h+var_440]
0x1401180e2  mov     qword ptr [rbp+620h+DestinationString.Length], 0FE0000h
0x1401180ea  mov     r8d, ebx; Size
0x1401180ed  mov     [rbp+620h+DestinationString.Buffer], rax
0x1401180f1  xor     edx, edx; Val
0x1401180f3  lea     rcx, [rbp+620h+var_340]; void *
0x1401180fa  call    memset
0x1401180ff  lea     rax, [rbp+620h+var_340]
0x140118106  mov     qword ptr [rbp+620h+SourceString.Length], 0FE0000h
0x14011810e  mov     r8d, ebx; Size
0x140118111  mov     [rbp+620h+SourceString.Buffer], rax
0x140118115  xor     edx, edx; Val
0x140118117  lea     rcx, [rbp+620h+var_240]; void *
0x14011811e  call    memset
0x140118123  lea     rax, [rbp+620h+var_240]
0x14011812a  mov     [rbp+620h+var_5C0], 0FE0000h
0x140118132  mov     r8d, ebx; Size
0x140118135  mov     [rbp+620h+var_5B8], rax
0x140118139  xor     edx, edx; Val
0x14011813b  lea     rcx, [rbp+620h+var_140]; void *
0x140118142  call    memset
0x140118147  lea     rax, [rbp+620h+var_140]
0x14011814e  mov     [rbp+620h+var_5B0], 0FE0000h
0x140118156  mov     [rbp+620h+var_5A8], rax
0x14011815a  lea     rcx, [rbp+620h+var_630]
0x14011815e  lea     eax, [r13+1]
0x140118162  mov     r9b, al
0x140118165  mov     r8d, eax
0x140118168  mov     edx, eax
0x14011816a  call    VmsWppTraceInitializeContextEx
0x14011816f  xor     ebx, ebx
0x140118171  lea     r8, aOnecoreVmDvNet_12; "onecore\\vm\\dv\\net\\nvsp\\driver\\pt"...
0x140118178  mov     byte ptr [rsp+720h+var_6E0], bl
0x14011817c  lea     rdx, aVmsptnicbindad; "VmsPtNicBindAdapterEx"
0x140118183  mov     byte ptr [rsp+720h+var_6E8], 1
0x140118188  lea     rcx, [rbp+620h+var_630]
0x14011818c  mov     byte ptr [rsp+720h+var_6F0], bl
0x140118190  mov     r9d, 4D5h
0x140118196  mov     dword ptr [rsp+720h+var_6F8], ebx
0x14011819a  mov     byte ptr [rsp+720h+NdisBindingHandle], 4
0x14011819f  call    VmsWppTraceApi
0x1401181a4  mov     eax, [r14+20h]
0x1401181a8  lea     rcx, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x1401181af  test    eax, eax
0x1401181b1  jz      short loc_1401181E3
0x1401181b3  mov     dword ptr [rsp+720h+var_6F8], eax
0x1401181b7  lea     r9d, [r13+0Eh]
0x1401181bb  mov     [rsp+720h+NdisBindingHandle], rcx
0x1401181c0  lea     r8d, [r13+14h]
0x1401181c4  mov     rcx, cs:VmsIfrLog
0x1401181cb  mov     dl, 2
0x1401181cd  call    WPP_RECORDER_SF_d
0x1401181d2  mov     [rsp+720h+var_6AC], 0C000000Dh
0x1401181da  lea     ebx, [r13+5]
0x1401181de  jmp     loc_140118B8B
0x1401181e3  movzx   eax, byte ptr [r14]
0x1401181e7  cmp     al, 86h
0x1401181e9  jnz     loc_14011AE7C
0x1401181ef  cmp     byte ptr [r14+1], 4
0x1401181f4  jnz     loc_14011AE7C
0x1401181fa  mov     ecx, 138h
0x1401181ff  cmp     [r14+2], cx
0x140118204  jb      loc_14011AE7C
0x14011820a  mov     rdx, r14
0x14011820d  lea     rcx, [rbp+620h+var_630]
0x140118211  call    VmsIfrInfoParamInputNdisBindParameters
0x140118216  mov     cs:VmsNetworkIndication, 15h
0x140118220  call    VmsReadReloadableParameters
0x140118225  mov     rdx, [r14+10h]; SourceString
0x140118229  lea     rcx, [rbp+620h+DestinationString]; DestinationString
0x14011822d  call    cs:__imp_RtlCopyUnicodeString
0x140118234  nop     dword ptr [rax+rax+00h]
0x140118239  lea     rcx, [rbp+620h+DestinationString]
0x14011823d  call    VmsUtilStrMakeRegistryCompliant
0x140118242  lea     rdx, [rbp+620h+DestinationString]
0x140118246  lea     rcx, [rbp+620h+SourceString]
0x14011824a  call    VmsUtilUpcaseUnicodeString
0x14011824f  mov     [rsp+720h+var_6AC], eax
0x140118253  test    eax, eax
0x140118255  jz      short loc_140118261
0x140118257  mov     ebx, 0Bh
0x14011825c  jmp     loc_140118B8E
0x140118261  xor     r9d, r9d
0x140118264  lea     r8, [rbp+620h+var_638]
0x140118268  lea     rdx, [rbp+620h+var_650]
0x14011826c  lea     rcx, [rbp+620h+SourceString]
0x140118270  call    VmsPtNicPvtReadConnectionInfo
0x140118275  xor     ecx, ecx
0x140118277  mov     [rbp+620h+var_5E0], eax
0x14011827a  test    eax, eax
0x14011827c  jz      short loc_140118284
0x14011827e  mov     [rsp+720h+var_6B0], cl
0x140118282  jmp     short loc_140118301
0x140118284  mov     rdx, [rbp+620h+var_650]
0x140118288  lea     rcx, [rbp+620h+var_5C0]
0x14011828c  call    VmsUtilUpcaseUnicodeString
0x140118291  mov     [rsp+720h+var_6AC], eax
0x140118295  test    eax, eax
0x140118297  jz      short loc_1401182A3
0x140118299  mov     ebx, 0Ch
0x14011829e  jmp     loc_140118B8E
0x1401182a3  xor     r8d, r8d
0x1401182a6  lea     rdx, [rbp+620h+LockState]
0x1401182aa  call    VmsUtilLockShared
0x1401182af  lea     rdx, [rbp+620h+var_668]
0x1401182b3  lea     rcx, [rbp+620h+var_5C0]
0x1401182b7  call    VmsOmFindSwitchUnsafe
0x1401182bc  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1401182c3  lea     rdx, [rbp+620h+LockState]; LockState
0x1401182c7  mov     [rsp+720h+var_6AC], eax
0x1401182cb  call    cs:__imp_NdisReleaseRWLock
0x1401182d2  nop     dword ptr [rax+rax+00h]
0x1401182d7  mov     r13, [rbp+620h+var_668]
0x1401182db  cmp     [rsp+720h+var_6AC], ebx
0x1401182df  jz      short loc_1401182EE
0x1401182e1  mov     [rsp+720h+var_6AC], 0C0000034h
0x1401182e9  jmp     loc_140118B8E
0x1401182ee  mov     rdx, r13
0x1401182f1  xor     ecx, ecx
0x1401182f3  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1401182f8  mov     r12b, al
0x1401182fb  mov     [rsp+720h+var_6B0], al
0x1401182ff  xor     ecx, ecx
0x140118301  cmp     byte ptr [r14+1], 3
0x140118306  jbe     short loc_14011831F
0x140118308  mov     rax, [r14+110h]
0x14011830f  test    rax, rax
0x140118312  jz      short loc_14011831F
0x140118314  mov     eax, [rax+20h]
0x140118317  mov     [rbp+620h+var_69C], 1
0x14011831b  test    al, 40h
0x14011831d  jnz     short loc_140118322
0x14011831f  mov     [rbp+620h+var_69C], cl
0x140118322  test    r12b, r12b
0x140118325  jz      loc_140118DE8
0x14011832b  mov     rdx, [rbp+620h+var_638]
0x14011832f  lea     rcx, [rbp+620h+var_5B0]
0x140118333  call    VmsUtilUpcaseUnicodeString
0x140118338  mov     [rsp+720h+var_6AC], eax
0x14011833c  test    eax, eax
0x14011833e  jz      short loc_14011834A
0x140118340  mov     ebx, 0Dh
0x140118345  jmp     loc_140118B8E
0x14011834a  xor     r8d, r8d
0x14011834d  lea     rdx, [rbp+620h+var_674]
0x140118351  mov     rcx, r13
0x140118354  call    VmsOmObjectLockShared
0x140118359  lea     rcx, [r13+588h]
0x140118360  lea     r8, [rbp+620h+var_5D0]
0x140118364  lea     rdx, [rbp+620h+var_5B0]
0x140118368  call    VmsOmpFindPortInListUnsafe
0x14011836d  mov     [rsp+720h+var_6AC], eax
0x140118371  lea     rdx, [rbp+620h+var_674]; LockState
0x140118375  mov     rcx, [r13+38h]; Lock
0x140118379  call    cs:__imp_NdisReleaseRWLock
0x140118380  nop     dword ptr [rax+rax+00h]
0x140118385  mov     r15, qword ptr [rbp+620h+var_5D0]
0x140118389  cmp     [rsp+720h+var_6AC], ebx
0x14011838d  jnz     loc_1401182E1
0x140118393  xor     r8d, r8d
0x140118396  mov     [rbp+620h+var_688], r15
0x14011839a  lea     rdx, [rbp+620h+var_670]
0x14011839e  mov     rcx, r15
0x1401183a1  call    VmsOmObjectLockShared
0x1401183a6  mov     rax, [r15+4E8h]
0x1401183ad  lea     rcx, aObjportNicType; "objPort->Nic->Type == VmsNicProtocol"
0x1401183b4  mov     esi, 2
0x1401183b9  test    rax, rax
0x1401183bc  jz      short loc_140118403
0x1401183be  cmp     [rax+750h], esi
0x1401183c4  jz      short loc_1401183FF
0x1401183c6  mov     [rsp+720h+var_6F8], rcx
0x1401183cb  lea     rax, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x1401183d2  mov     rcx, cs:VmsIfrLog
0x1401183d9  lea     r9d, [rsi+0Eh]
0x1401183dd  lea     r8d, [rsi+11h]
0x1401183e1  mov     [rsp+720h+NdisBindingHandle], rax
0x1401183e6  call    WPP_RECORDER_SF_s
0x1401183eb  mov     rax, [r15+4E8h]
0x1401183f2  cmp     [rax+750h], esi
0x1401183f8  jz      short loc_1401183FF
0x1401183fa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objPort->Nic->Type == VmsNicProtocol")
0x1401183ff  mov     [rbp+620h+var_690], 1
0x140118403  mov     rcx, [r15+38h]; Lock
0x140118407  lea     rdx, [rbp+620h+var_670]; LockState
0x14011840b  call    cs:__imp_NdisReleaseRWLock
0x140118412  nop     dword ptr [rax+rax+00h]
0x140118417  cmp     [rbp+620h+var_690], 1
0x14011841b  jnz     loc_140118DE8
0x140118421  mov     rax, [r15+4E8h]
0x140118428  cmp     [rax+750h], esi
0x14011842e  jz      short loc_140118472
0x140118430  mov     rcx, cs:VmsIfrLog
0x140118437  lea     rax, aObjportNicType; "objPort->Nic->Type == VmsNicProtocol"
0x14011843e  mov     [rsp+720h+var_6F8], rax
0x140118443  mov     r9d, 11h
0x140118449  lea     rax, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x140118450  mov     [rsp+720h+NdisBindingHandle], rax
0x140118455  lea     r8d, [r9+2]
0x140118459  call    WPP_RECORDER_SF_s
0x14011845e  mov     rax, [r15+4E8h]
0x140118465  cmp     [rax+750h], esi
0x14011846b  jz      short loc_140118472
0x14011846d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objPort->Nic->Type == VmsNicProtocol")
0x140118472  mov     rax, [r15+4E8h]
0x140118479  lea     rsi, [r14+0A8h]
0x140118480  mov     [rsp+720h+var_6A8], rax
0x140118485  lea     rdx, [rbp+620h+InterfaceGuid]; InterfaceGuid
0x14011848c  mov     rcx, rsi; InterfaceLuid
0x14011848f  mov     rdi, [rax+0CF0h]
0x140118496  call    cs:__imp_ConvertInterfaceLuidToGuid
0x14011849d  nop     dword ptr [rax+rax+00h]
0x1401184a2  mov     [rsp+720h+var_6AC], eax
0x1401184a6  test    eax, eax
0x1401184a8  jz      short loc_1401184DE
0x1401184aa  mov     rcx, cs:VmsIfrLog
0x1401184b1  mov     r9d, 12h
0x1401184b7  mov     dword ptr [rsp+720h+var_6F0], eax
0x1401184bb  mov     rax, [rsi]
0x1401184be  mov     [rsp+720h+var_6F8], rax
0x1401184c3  lea     rax, WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids
0x1401184ca  mov     [rsp+720h+NdisBindingHandle], rax
0x1401184cf  call    WPP_RECORDER_SF_Id
0x1401184d4  mov     ebx, 0Eh
0x1401184d9  jmp     loc_140118B8B
0x1401184de  mov     rcx, [rsp+720h+var_6A8]
0x1401184e3  lea     rdx, [rbp+620h+var_68C]
  ... truncated ...
```
