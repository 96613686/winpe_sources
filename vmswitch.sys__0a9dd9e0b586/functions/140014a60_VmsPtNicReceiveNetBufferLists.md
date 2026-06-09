# VmsPtNicReceiveNetBufferLists

- ea: `0x140014a60`
- end: `0x140016ab8`
- name: `VmsPtNicReceiveNetBufferLists`
- size: `8280`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140010aa8`
- `0x140011270`
- `0x140012980`
- `0x140012d90`
- `0x140014330`
- `0x1400143ac`
- `0x1400147e0`
- `0x14001484c`
- `0x140014988`
- `0x140014a60`
- `0x140017a7c`
- `0x140017ca8`
- `0x14001d520`
- `0x14001e598`
- `0x1400211c0`
- `0x140022ff0`
- `0x140025be0`
- `0x140025d10`
- `0x140027a64`
- `0x14002ca0c`
- `0x1400313cc`
- `0x140031f84`
- `0x140034860`
- `0x14003c378`
- `0x140046e5c`
- `0x140046f1c`
- `0x14004d37c`
- `0x140055494`
- `0x14005c170`
- `0x14005fc3c`
- `0x140064e34`
- `0x14006b4dc`
- `0x1400763ec`
- `0x14008497c`
- `0x1400f2adc`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140014b9e`
- `ntoskrnl!KeBugCheckEx` at `0x140014f65`
- `ntoskrnl!KeBugCheckEx` at `0x140014b9e`
- `ntoskrnl!KeBugCheckEx` at `0x140014f65`
- `ntoskrnl!KeSetEvent` at `0x1400169b9`
- `ntoskrnl!KeSetEvent` at `0x1400169b9`
- `ntoskrnl!KeInsertQueueDpc` at `0x14001577f`
- `ntoskrnl!KeInsertQueueDpc` at `0x14001577f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014e93`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014e93`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400151b4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400151b4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014b22`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014b3b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014b7f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014c35`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014cce`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014f0b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014f46`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140015213`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400161dc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400162d4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400166dd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014b22`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014b3b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014b7f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014c35`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014cce`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014f0b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014f46`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140015213`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400161dc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400162d4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400166dd`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014b06`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014b06`
- `NDIS!NdisReturnNetBufferLists` at `0x140016a6c`
- `NDIS!NdisReturnNetBufferLists` at `0x140016a6c`
- `NDIS!NdisAcquireRWLockRead` at `0x140015d66`
- `NDIS!NdisAcquireRWLockRead` at `0x140015f5a`
- `NDIS!NdisAcquireRWLockRead` at `0x140015d66`
- `NDIS!NdisAcquireRWLockRead` at `0x140015f5a`
- `NDIS!NdisReleaseRWLock` at `0x140014cfc`
- `NDIS!NdisReleaseRWLock` at `0x140015a43`
- `NDIS!NdisReleaseRWLock` at `0x140015cca`
- `NDIS!NdisReleaseRWLock` at `0x140015d97`
- `NDIS!NdisReleaseRWLock` at `0x140015f85`
- `NDIS!NdisReleaseRWLock` at `0x140014cfc`
- `NDIS!NdisReleaseRWLock` at `0x140015a43`
- `NDIS!NdisReleaseRWLock` at `0x140015cca`
- `NDIS!NdisReleaseRWLock` at `0x140015d97`
- `NDIS!NdisReleaseRWLock` at `0x140015f85`
- `HAL!KeQueryPerformanceCounter` at `0x14001646b`
- `HAL!KeQueryPerformanceCounter` at `0x14001646b`

## string_xrefs

- `0x14001677f`: `ProtocolNic->Type == VmsNicProtocol`

## pseudocode

```c
int __fastcall VmsPtNicReceiveNetBufferLists(__int64 a1, __int64 a2, unsigned __int16 a3, int a4, __int16 a5)
{
  unsigned __int8 *v5; // rbp
  __int64 v6; // r12
  __int64 v8; // rsi
  struct _NET_BUFFER_LIST *v9; // rdi
  char v10; // bl
  ULONG CurrentProcessorNumber; // eax
  int v12; // edx
  ULONG_PTR v13; // rbx
  __int64 v14; // rdi
  ULONG_PTR v15; // rdi
  ULONG v16; // eax
  __int64 v17; // rax
  int v18; // r14d
  char v19; // r15
  __int64 v20; // rbx
  __int64 NicHeaderAtIndex; // rdi
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rcx
  unsigned int v25; // ecx
  __int64 v26; // rdx
  __int64 v27; // r8
  char v28; // di
  __int64 v29; // r11
  __int64 v30; // rbx
  bool v31; // r12
  __int64 v32; // rsi
  char v33; // r14
  __int16 v34; // r13
  __int64 v35; // rcx
  __int16 v36; // bx
  const char *v37; // rdx
  char v38; // di
  int v39; // eax
  __int64 v40; // r12
  struct _KDPC *v41; // r14
  char v42; // di
  char v43; // al
  __int64 v44; // r13
  int v45; // r15d
  const char *v46; // rdx
  __int64 v47; // rax
  __int64 *v48; // rsi
  unsigned __int64 v49; // r14
  void *v50; // rdx
  char v51; // si
  unsigned int v52; // r8d
  __int64 v53; // rax
  ULONG v54; // eax
  int v55; // edx
  ULONG_PTR v56; // rbx
  __int64 v57; // rdi
  ULONG v58; // eax
  __int64 v59; // rbx
  __int64 v60; // rcx
  __int64 v61; // rax
  int DuplicateNblsCopyData; // eax
  __int64 v63; // r9
  unsigned int v64; // ebx
  int v65; // r9d
  _QWORD *v66; // rax
  _QWORD *v67; // rcx
  char v68; // al
  char v69; // cl
  unsigned int v70; // eax
  int v71; // eax
  PVOID v72; // rax
  __int64 v73; // rbx
  ULONG v74; // eax
  __int64 v75; // rdi
  char v76; // al
  int v77; // r10d
  unsigned int v78; // ecx
  int v79; // ebx
  unsigned int v80; // eax
  __int64 v81; // rax
  int v82; // eax
  __int64 **v83; // rcx
  unsigned __int8 *v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rsi
  _QWORD *v88; // rdi
  __int64 v89; // r14
  __int64 v90; // rcx
  __int64 v91; // rax
  int NetBufferListContext; // r9d
  __int64 v93; // r9
  int v94; // r10d
  unsigned int v95; // ecx
  int v96; // ebx
  unsigned int v97; // eax
  __int64 v98; // r11
  int ProcessorIndexForEntry; // eax
  __int64 NblGroup; // rax
  bool v101; // zf
  __int64 **v102; // rcx
  unsigned __int8 *v103; // rax
  unsigned __int64 v104; // rdi
  __int64 v105; // r9
  unsigned __int8 v106; // cl
  char v107; // cl
  __int64 v108; // rbx
  int v109; // eax
  struct _KDPC *v110; // rcx
  __int64 v111; // rcx
  const char *v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rdx
  __int64 v123; // rax
  __int64 v124; // r8
  unsigned int v125; // ecx
  unsigned int v126; // eax
  unsigned int v127; // ecx
  unsigned int v128; // eax
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // rdx
  __int64 v132; // r9
  int v133; // r8d
  void *v134; // rcx
  char v135; // al
  int v136; // r9d
  __int64 v137; // rax
  char v138; // al
  int v139; // ecx
  __int64 v140; // rdx
  __int64 v141; // rax
  int v142; // r9d
  __int64 v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  int v146; // r8d
  char v147; // r9
  __int64 v148; // rax
  __int64 v149; // rax
  char v150; // r14
  struct _NDIS_RW_LOCK_EX *v151; // rcx
  char v152; // cl
  char v153; // al
  unsigned int v154; // ecx
  unsigned int v155; // eax
  __int64 v156; // rcx
  __int64 v157; // rax
  unsigned int v158; // ecx
  unsigned int v159; // eax
  __int64 v160; // rdx
  __int64 v161; // r9
  char ShouldDropLoopBackPacket; // al
  int v163; // r9d
  __int64 v164; // rax
  unsigned int v165; // ecx
  unsigned int v166; // eax
  int v167; // edx
  __int64 v168; // rsi
  unsigned __int64 v169; // rdi
  __int64 v170; // rbx
  __int64 v171; // rdx
  unsigned int v172; // eax
  char *v173; // rcx
  int v174; // edx
  __int64 v175; // rax
  char v176; // bl
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v178; // rcx
  __int64 v179; // rdx
  LARGE_INTEGER *v180; // rcx
  unsigned __int8 v181; // r8
  char v182; // al
  __int64 v183; // r13
  __int64 v184; // rax
  char v185; // al
  __int64 v186; // rax
  __int64 v187; // rax
  LARGE_INTEGER v188; // rdx
  LARGE_INTEGER v189; // rcx
  LARGE_INTEGER *v190; // rbx
  char *v191; // rcx
  const char *v192; // rax
  __int64 v193; // rcx
  __int64 v194; // rcx
  int v195; // ebx
  _SLIST_HEADER *Alignment; // rax
  __int64 v197; // r15
  __int64 v198; // rdi
  __int64 v199; // rax
  __int64 v200; // rax
  __int64 v201; // rax
  int v202; // edx
  NDIS_HANDLE *v203; // rcx
  char BugCheckParameter4; // [rsp+20h] [rbp-80h]
  int v206; // [rsp+28h] [rbp-78h]
  char v207; // [rsp+A0h] [rbp+0h] BYREF
  void *retaddr; // [rsp+238h] [rbp+198h]

  v5 = (unsigned __int8 *)((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL);
  v6 = 0;
  *((_QWORD *)v5 + 7) = a2;
  *((_QWORD *)v5 + 10) = a1;
  *((_QWORD *)v5 + 16) = a2;
  v8 = a2;
  *((_QWORD *)v5 + 8) = 0;
  *((_QWORD *)v5 + 17) = 0;
  *((_DWORD *)v5 + 30) = 0;
  *((_DWORD *)v5 + 9) = 0;
  v9 = 0;
  *((_QWORD *)v5 + 19) = 0;
  *((_WORD *)v5 + 4) = 0;
  v5[10] = 0;
  *((_DWORD *)v5 + 4) = a4;
  memset((void *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 192), 0, 0x80u);
  *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 0;
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x32) = 0;
  if ( (a5 & 1) != 0 || (v10 = 0, KeGetCurrentIrql() == 2) )
    v10 = 1;
  *v5 = v10;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = KeGetCurrentProcessorNumberEx(0);
  if ( v10 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v13 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1 )
      goto LABEL_8;
    v14 = CurrentProcessorNumber >> 6;
    if ( (unsigned int)v14 >= 0x40 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v12,
        19,
        10,
        (__int64)WPP_1993566a47c33aa75355351056e61473_Traceguids,
        (__int64)"(*SetIndex < VMS_CPU_SET_ARRAY_COUNT)");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( !_bittest64(&VmsKnownProcessors[v14], v13 & 0x3F) )
    {
LABEL_8:
      v15 = v13;
      goto LABEL_9;
    }
    v15 = v13;
    v190 = (LARGE_INTEGER *)((char *)VmsPlanCpuTable + 5440 * v13);
    if ( !v190 )
    {
LABEL_9:
      v16 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v15, v16, 0, 0);
    }
    if ( v190[146].QuadPart )
    {
      LOBYTE(v190[161].LowPart) = 1;
    }
    else
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v178 = v190[144];
      v190[146] = PerformanceCounter;
      v179 = *(_QWORD *)(v178.QuadPart + 13104);
      BYTE2(v190[150].u.LowPart) = 0;
      LOBYTE(v190[150].LowPart) = v179 != 0;
      v180 = v190 + 145;
      if ( !v179 || (v181 = 1, v180->QuadPart != v179) )
        v181 = 0;
      BYTE1(v190[150].LowPart) = v181;
      v180->QuadPart = v179;
      if ( v179 && !v181 )
      {
        v188.QuadPart = HIWORD(v190[150].QuadPart);
        v189 = v190[155];
        HIWORD(v190[150].QuadPart) = 1;
        v190[148] = PerformanceCounter;
        if ( v189.QuadPart <= (unsigned __int64)v188.QuadPart )
          v189 = v188;
        v190[147] = PerformanceCounter;
        ++v190[153].QuadPart;
        v190[155] = v189;
        v190[149].QuadPart = 0;
        BYTE4(v190[150].QuadPart) = -1;
      }
      HIWORD(v190[150].QuadPart) += v181;
    }
    v8 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
    v9 = *(struct _NET_BUFFER_LIST **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
  }
  v182 = VmsDiagnosticFlags;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = 0;
  v183 = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = 0;
  v176 = 0;
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = 0;
  if ( (v182 & 1) != 0 )
  {
    if ( v8 )
    {
      v186 = *(_QWORD *)(v8 + 288);
      if ( v186 )
      {
        v187 = *(_QWORD *)(v186 + 16);
        if ( v187 )
        {
          *(_QWORD *)(v187 + 176) = "VmsPtNicReceiveNetBufferLists";
          *(_DWORD *)(v187 + 184) = 8642;
          *(_QWORD *)(v187 + 168) = retaddr;
        }
      }
    }
  }
  v184 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50);
  if ( v184 )
  {
    v183 = *(_QWORD *)(v184 + 8);
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = v183;
  }
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = *(_QWORD *)(v183 + 3312);
  v185 = g_VmsSkuInfo;
  if ( (g_VmsSkuInfo & 1) == 0
    || (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 1) = 0, (v185 & 2) != 0) )
  {
    if ( *(_DWORD *)(v183 + 1872) != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        0,
        19,
        292,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (__int64)"ProtocolNic->Type == VmsNicProtocol");
      if ( *(_DWORD *)(v183 + 1872) != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v137 = *(_QWORD *)(v183 + 1888);
    if ( v137 )
      v138 = *(_BYTE *)(v137 + 8912);
    else
      v138 = *(_BYTE *)(v183 + 1896);
    *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 1) = v138;
  }
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 0;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = a5 & 2;
  v139 = *v5 | 4;
  if ( (a5 & 0x800) == 0 )
    v139 = *v5;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C) = v139;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v183 + 56), (PLOCK_STATE_EX)(v5 + 8), 0);
  v141 = *(_QWORD *)(v183 + 1888);
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v141;
  if ( !v141 )
    goto LABEL_252;
  if ( *(_DWORD *)(v141 + 68) == 2 )
    goto LABEL_252;
  if ( *(_DWORD *)(v141 + 4272) != 3 )
    goto LABEL_252;
  LOBYTE(v140) = 12;
  VmsOmpObjectReference(v141, v140);
  v175 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
  v176 = 1;
  if ( *(_BYTE *)(v175 + 104) == 1 )
    goto LABEL_252;
  if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 1) )
  {
    v17 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50);
    if ( !v17 || *(_DWORD *)(v17 + 192) == 4 )
    {
      v18 = *(unsigned __int16 *)(v17 + 16);
      goto LABEL_14;
    }
LABEL_252:
    LOWORD(v18) = 0;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v183 + 56), (PLOCK_STATE_EX)(v5 + 8));
    if ( !*(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) )
    {
      LOBYTE(v142) = 1;
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v8;
      v9 = (struct _NET_BUFFER_LIST *)v8;
      VmsPktReportDroppedPacketEx(v183, v8, 2, v142, -1073676271, -536862707);
    }
    if ( v176 )
      goto LABEL_49;
    goto LABEL_50;
  }
  if ( !*(_BYTE *)(v175 + 2400) )
  {
    LOWORD(v18) = 1;
    *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) = 1;
    goto LABEL_16;
  }
  v18 = a3;
LABEL_14:
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) = v18;
  if ( (unsigned __int16)v18 > 0x3Fu )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v174,
      19,
      228,
      (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
      (__int64)"NicIndex <= VMS_LBFO_SUPPORTED_TEAM_NICS");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
LABEL_16:
  v19 = 0;
  if ( *(_DWORD *)(v183 + 1872) == 2 && (_WORD)v18 )
  {
    v59 = *(_QWORD *)(v183 + 3312);
    if ( !v59 || (unsigned __int16)v18 > 0x3Fu )
    {
LABEL_243:
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v183 + 56), (PLOCK_STATE_EX)(v5 + 8));
      if ( !*(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) )
      {
        LOBYTE(v136) = 1;
        *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v8;
        v9 = (struct _NET_BUFFER_LIST *)v8;
        VmsPktReportDroppedPacketEx(v183, v8, 2, v136, -1073676271, -536862706);
      }
      goto LABEL_49;
    }
    _mm_lfence();
    v20 = *(_QWORD *)(v59 + 8LL * (unsigned __int16)v18 + 1888);
  }
  else
  {
    v20 = v183 + 1232;
  }
  if ( !v20 || *(_DWORD *)(v20 + 16) != 2 )
    goto LABEL_243;
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = 0;
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
  NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v183, (unsigned __int16)v18);
  if ( NicHeaderAtIndex )
    _InterlockedAdd64(
      (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                + *(_QWORD *)(NicHeaderAtIndex + 24)
                                + 16),
      *(int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10));
  v22 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70);
  v23 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
  v24 = *(_QWORD *)(v22 + 9000);
  if ( v24 && (*(_BYTE *)(v24 + 204) & 2) != 0 )
  {
    if ( !*(_BYTE *)(v23 + 304) || !*(_BYTE *)(v23 + 306) )
    {
      VmsTmReceiveNetBufferLists(v24, v8, (unsigned __int16)v18);
LABEL_406:
      v23 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
      goto LABEL_23;
    }
    if ( *(_WORD *)(v8 + 258) )
    {
      if ( (unsigned int)VmsPtNicMUXGetAggregateVMQId((unsigned __int16)v18, *(unsigned __int16 *)(v8 + 258), v5 + 120) )
        *(_WORD *)(v8 + 258) = 0;
      else
        *(_WORD *)(v8 + 258) = *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x78);
      *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 1;
      goto LABEL_406;
    }
  }
LABEL_23:
  v25 = *(unsigned __int16 *)(v8 + 258);
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v25;
  if ( v25 && (v26 = *(_QWORD *)(v23 + 1424)) != 0 )
  {
    if ( !*(_BYTE *)(v23 + 2400)
      || v25 <= *(_DWORD *)(v20 + 624)
      && (v25 = *(_DWORD *)(*(_QWORD *)(v20 + 616) + 8LL * (v25 - 1)),
          (*(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v25) != 0) )
    {
      v6 = *(_QWORD *)(v26 + 8LL * (v25 - 1));
LABEL_27:
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = v6;
    }
  }
  else
  {
    if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 1) )
    {
      v67 = *(_QWORD **)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) + 1928LL);
    }
    else
    {
      v66 = (_QWORD *)(v23 + 1480);
      v67 = (_QWORD *)*v66;
      if ( (_QWORD *)*v66 == v66 )
      {
        *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 0;
        goto LABEL_33;
      }
    }
    if ( v67 )
    {
      v6 = v67[7];
      goto LABEL_27;
    }
  }
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 0;
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 48) != 1 || (*(_DWORD *)(v6 + 52) & 0x20) != 0 )
    {
      v6 = 0;
    }
    else
    {
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v6 + 216)
                                                        + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)));
      *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 3) = 1;
    }
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = v6;
  }
LABEL_33:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v183 + 56), (PLOCK_STATE_EX)(v5 + 8));
  v28 = *(_BYTE *)(v22 + 9176);
  v29 = 0;
  if ( v6 )
  {
    v149 = *(_QWORD *)(v6 + 8);
    v32 = *(_QWORD *)(v6 + 40);
    v150 = 0;
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = v149;
    v151 = *(struct _NDIS_RW_LOCK_EX **)(v32 + 56);
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = *(_QWORD *)(v149 + 640);
    v30 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
    v31 = (v30 & 3) == 3;
    NdisAcquireRWLockRead(v151, (PLOCK_STATE_EX)v5 + 16, 0);
    if ( *(_DWORD *)(v32 + 1880) == 1 )
      v150 = *(_BYTE *)(*(_QWORD *)(v32 + 1984) + 6364LL);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v32 + 56), (PLOCK_STATE_EX)v5 + 16);
    v29 = 0;
    if ( !*(_BYTE *)(v32 + 3954) || (v152 = 1, !v150) )
      v152 = 0;
    if ( !*(_BYTE *)(v32 + 3955) || (v153 = 1, !v150) )
      v153 = 0;
    if ( v28 && v152 )
    {
      v33 = 1;
    }
    else
    {
      v33 = 0;
      if ( !v28 )
      {
LABEL_280:
        v28 = 0;
        goto LABEL_35;
      }
    }
    if ( v153 )
    {
      v28 = 1;
      goto LABEL_35;
    }
    goto LABEL_280;
  }
  v30 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
  v31 = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = 0;
  v32 = 0;
  v33 = v28;
LABEL_35:
  if ( *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) || !v33 && !v28 )
  {
LABEL_36:
    v34 = 0;
    if ( !*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) )
      goto LABEL_37;
    goto LABEL_209;
  }
  if ( v31 || !*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) )
  {
    *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = VmsPtNicPvtRscCoalesceNbls(
                                                                              v183,
                                                                              v5 + 128,
                                                                              *(unsigned int *)(((unsigned __int64)&v207
                                                                                               & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                              + 0x34));
    v29 = 0;
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = *(_QWORD *)(((unsigned __int64)&v207
                                                                                       & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                      + 0x80);
    goto LABEL_36;
  }
LABEL_209:
  v121 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68);
  v34 = *(_WORD *)(v121 + 1282);
  if ( !v31 )
  {
    v193 = 0;
    if ( *(_QWORD *)(v121 + 624) )
      v193 = v121 + 176;
    if ( *(_DWORD *)(v121 + 1328) != *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) )
      _InterlockedAdd64(
        (volatile signed __int64 *)(v193 + 96),
        *(unsigned int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10));
  }
  LOBYTE(v27) = *v5;
  VmsOmObjectLockShared(v32, v5 + 8, v27);
  if ( *(_BYTE *)(v32 + 5496) )
  {
    v123 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
    if ( *(_BYTE *)(v123 + 56) )
      v124 = *(unsigned __int16 *)(v123 + 58);
    else
      v124 = 4789;
    LOBYTE(v122) = !v31;
    VmsNblGenerateToeplitzRssHash(
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38),
      v122,
      v124,
      v32 + 5496);
    v19 = (v30 & 1) != 0 && (v30 & 2) == 0;
  }
  else
  {
    v19 = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 2);
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v32 + 56), (PLOCK_STATE_EX)(v5 + 8));
  v29 = 0;
LABEL_37:
  v35 = *(unsigned int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34);
  v36 = *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x62);
  v37 = *(const char **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68);
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) = v31;
  v38 = v33 & 1 | (2 * (v28 & 1));
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = ((unsigned __int64)&v207
                                                                         & 0xFFFFFFFFFFFFFFC0uLL)
                                                                        + 200;
  v39 = VmsExecutionMode;
  v40 = 5440 * v35;
  v41 = (struct _KDPC *)((char *)VmsPlanCpuTable + 5440 * v35 + 576);
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) = 8 * v38;
  v42 = *v5;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) = 0;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = 0;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) = v35;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x134) = v39;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = v37;
  *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFA) = v34;
  *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8) = v36;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 5440 * v35;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = v41;
  if ( (v39 & 6) == 0
    && (v42 && LODWORD(v41[4].ProcessorHistory)
     || (LOBYTE(v35) = v42,
         v68 = VmsVrssCheckWatchdog(v35),
         v37 = *(const char **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68),
         v29 = 0,
         v68)) )
  {
    v43 = 1;
  }
  else
  {
    v43 = 0;
    if ( !v19 )
    {
      v44 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90);
      goto LABEL_40;
    }
  }
  v44 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90);
  v69 = (4 * v43) | *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 0xFB;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118) = v44;
  *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130) = *(_DWORD *)(((unsigned __int64)&v207
                                                                                     & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                    + 0xC);
  v70 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C) & 0xFFFFFFFE;
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) = v69;
  *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128) = v70;
  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108) = VmsPtPvtRssReceiveProcessNblGroup;
  if ( v19 )
  {
    v71 = *((_DWORD *)v37 + 173);
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100) = v37;
    *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) = v69 & 0xFC | 1;
    *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x12C) = v71;
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x110) = 0;
    *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x132) = v42;
    *(_WORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8) = v36;
    v72 = ExAllocateFromNPagedLookasideList(&stru_1401FA0C0);
    v29 = 0;
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) = v72;
    if ( v72 )
    {
      memset(v72, 0, 0x408u);
      v29 = 0;
    }
    else
    {
      *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) &= 0xFCu;
    }
  }
LABEL_40:
  *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 2) = 1;
  if ( !*(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) )
  {
    v87 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
    v88 = v5 + 136;
    if ( !v87 )
      goto LABEL_167;
    while ( 1 )
    {
      v89 = *(_QWORD *)v87;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v89 )
        {
          v115 = *(_QWORD *)(v89 + 288);
          if ( v115 )
          {
            v116 = *(_QWORD *)(v115 + 16);
            if ( v116 )
            {
              v37 = "VmsPtNicReceiveNetBufferLists";
              *(_DWORD *)(v116 + 184) = 9354;
              *(_QWORD *)(v116 + 176) = "VmsPtNicReceiveNetBufferLists";
              *(_QWORD *)(v116 + 168) = retaddr;
            }
          }
        }
      }
      *(_QWORD *)v87 = v29;
      if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 4) != (_BYTE)v29 )
        *(_WORD *)(v87 + 258) = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
      v90 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70);
      v91 = *(_QWORD *)(v90 + 9000);
      if ( v91 )
      {
        if ( (*(_BYTE *)(v91 + 204) & 2) != 0 )
        {
          ShouldDropLoopBackPacket = VmsTmShouldDropLoopBackPacket(
                                       v90,
                                       *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50),
                                       v87);
          v29 = 0;
          if ( ShouldDropLoopBackPacket )
            break;
        }
      }
      if ( *(_QWORD *)(v87 + 288) != v29 )
      {
        LOBYTE(v37) = 3;
        WPP_RECORDER_SF_I(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v37,
          12,
          161,
          (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
          v87);
        LOBYTE(v133) = 1;
        VmsPktReportDroppedNbl(v44, v87, v133, 22, 16, -536862653);
        v134 = retaddr;
        *v88 = v87;
        if ( (VmsDiagnosticFlags & 1) == 0 )
          goto LABEL_236;
        if ( !*(_QWORD *)v87 )
          goto LABEL_236;
        v143 = *(_QWORD *)(*(_QWORD *)v87 + 288LL);
        if ( !v143 )
          goto LABEL_236;
        v144 = *(_QWORD *)(v143 + 16);
        if ( !v144 )
          goto LABEL_236;
        *(_DWORD *)(v144 + 184) = 9406;
        goto LABEL_261;
      }
      NetBufferListContext = VmsPtNicPvtAllocateNetBufferListContext(v44, v87);
      if ( NetBufferListContext >= 0 )
      {
        VmsPtNicPvtStoreOriginalNblOob(v87);
        LODWORD(v37) = 0;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          v119 = *(_QWORD *)(v87 + 288);
          if ( v119 )
          {
            v120 = *(_QWORD *)(v119 + 16);
            if ( v120 )
            {
              *(_QWORD *)(v120 + 176) = "VmsVrssPrimeVrssContextForNextNbl";
              *(_DWORD *)(v120 + 184) = 1123;
              *(_QWORD *)(v120 + 168) = retaddr;
            }
          }
        }
        LOBYTE(v27) = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD);
        v94 = -1;
        if ( (v27 & 4) != 0 || (LOBYTE(v93) = 0, (v27 & 2) != 0) )
          LOBYTE(v93) = 1;
        if ( (v27 & 1) != 0 )
        {
          v95 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8);
          LOWORD(v96) = -1;
          if ( (_WORD)v95 )
          {
            v97 = *(_DWORD *)(v87 + 208);
            if ( v97 )
            {
              v96 = v97 % v95;
              LODWORD(v37) = 0;
            }
          }
          if ( (_WORD)v96 == 0xFFFF )
            v94 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x12C);
          v98 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120)
                          + 8LL * (__int16)v96
                          + 8);
          *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v98;
          if ( !v98 )
          {
            if ( v94 == -1 )
            {
              ProcessorIndexForEntry = VmsQueueGroupGetProcessorIndexForEntry(
                                         *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100),
                                         (unsigned __int16)v96,
                                         v27,
                                         v93);
              LOBYTE(v27) = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD);
              v94 = ProcessorIndexForEntry;
              v98 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
              LODWORD(v37) = 0;
            }
            LOBYTE(v93) = (v27 & 4) != 0
                       || (v27 & 2) != 0
                       || v94 != -1
                       && (v94 != *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0)
                        || (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x134) & 6) != 0);
          }
        }
        else
        {
          v98 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) & -(__int64)((_BYTE)v93 != 0);
          *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v98;
          if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) )
          {
            v127 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8);
            LODWORD(v37) = 0xFFFF;
            if ( (_WORD)v127 )
            {
              v128 = *(_DWORD *)(v87 + 208);
              if ( v128 )
                LODWORD(v37) = v128 % v127;
            }
            LOWORD(v96) = (_WORD)v37;
          }
          else
          {
            LOWORD(v96) = -2;
          }
        }
        if ( (_BYTE)v93 )
        {
          if ( !v98 )
          {
            if ( v94 == -1 )
              v94 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0);
            NblGroup = VmsVrssPvtFindNblGroup(
                         *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118),
                         *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130),
                         *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128),
                         v94,
                         *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108),
                         (__int64)(v5 + 192));
            v101 = (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 1) == 0;
            v98 = NblGroup;
            *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = NblGroup;
            if ( !v101 )
              *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) + 8LL * (__int16)v96 + 8) = NblGroup;
            goto LABEL_158;
          }
LABEL_189:
          v102 = (__int64 **)(v98 + 32);
          v103 = (unsigned __int8 *)(v98 + 48);
        }
        else
        {
LABEL_158:
          if ( v98 )
            goto LABEL_189;
          v102 = (__int64 **)(v5 + 208);
          v103 = v5 + 244;
        }
        *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = v103;
        v29 = 0;
        *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = v102;
        **v102 = v87;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v87 )
          {
            v117 = *(_QWORD *)(*(_QWORD *)v87 + 288LL);
            if ( v117 )
            {
              v118 = *(_QWORD *)(v117 + 16);
              if ( v118 )
              {
                v37 = "VmsPtNicReceiveNetBufferLists";
                *(_DWORD *)(v118 + 184) = 9433;
                *(_QWORD *)(v118 + 176) = "VmsPtNicReceiveNetBufferLists";
                *(_QWORD *)(v118 + 168) = retaddr;
              }
            }
          }
        }
        **(_QWORD **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = v87;
        ++**(_DWORD **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0);
        if ( (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 1) != 0 )
        {
          v194 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8);
          v192 = 0;
          v37 = *(const char **)(v194 + 624);
          if ( v37 )
          {
            if ( (_WORD)v96 == 0xFFFF )
            {
              v192 = (const char *)(v194 + 400);
            }
            else if ( (_WORD)v96 == 0xFFFE )
            {
              v192 = (const char *)(v194 + 176);
            }
            else
            {
              v192 = &v37[224 * (__int16)v96];
            }
          }
          _InterlockedIncrement64((volatile signed __int64 *)v192 + 8);
        }
        else if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) )
        {
          v129 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8);
          v130 = 0;
          v131 = *(_QWORD *)(v129 + 624);
          if ( v131 )
          {
            if ( (_WORD)v96 == 0xFFFF )
            {
              v130 = v129 + 400;
            }
            else if ( (_WORD)v96 == 0xFFFE )
            {
              v130 = v129 + 176;
            }
            else
            {
              v130 = v131 + 224LL * (__int16)v96;
            }
          }
          _InterlockedIncrement64((volatile signed __int64 *)(v130 + 64));
          if ( (v96 & 0x8000u) == 0 )
          {
            v165 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFA);
            if ( (_WORD)v165 )
            {
              v166 = *(_DWORD *)(v87 + 208);
              LOWORD(v167) = -1;
              if ( v166 )
                v167 = v166 % v165;
              LOWORD(v96) = v167;
            }
          }
          if ( (unsigned int)VmsPlanGetPlannedProcessorForEntry(
                               *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) + 640LL,
                               (unsigned __int16)v96) != *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL)
                                                                   + 0xF0) )
            _InterlockedIncrement64((volatile signed __int64 *)(v132 + 96));
        }
        if ( VmsEtwTraceDatapath )
        {
          if ( (v201 = *(_QWORD *)(v44 + 1984)) != 0 && *(_BYTE *)(v201 + 10864) != (_BYTE)v29
            || !VmsEtwTraceFiltersExist )
          {
            VmsTrcTransferNblActivityId(v87, v44, v27);
            VmsEtwTraceNblReceiveDeliver(
              &VM_NBL_RECEIVE,
              v44 + 616,
              *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 72LL,
              *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 616LL,
              v87);
            v29 = 0;
          }
        }
        goto LABEL_164;
      }
      *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x24) = 0;
      VmsPktGetDropReason((unsigned int)NetBufferListContext, v5 + 36);
      LOBYTE(v146) = 1;
      VmsPktReportDroppedNbl(
        v44,
        v87,
        v146,
        *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x24),
        v147,
        -536862652);
      v134 = retaddr;
      *v88 = v87;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( *(_QWORD *)v87 )
        {
          v148 = *(_QWORD *)(*(_QWORD *)v87 + 288LL);
          if ( v148 )
          {
            v144 = *(_QWORD *)(v148 + 16);
            if ( v144 )
            {
              *(_DWORD *)(v144 + 184) = 9421;
LABEL_261:
              v37 = "VmsPtNicReceiveNetBufferLists";
              *(_QWORD *)(v144 + 176) = "VmsPtNicReceiveNetBufferLists";
              *(_QWORD *)(v144 + 168) = v134;
            }
          }
        }
      }
LABEL_236:
      v88 = (_QWORD *)v87;
      v29 = 0;
LABEL_164:
      v87 = v89;
      if ( !v89 )
      {
        *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = *(_QWORD *)(((unsigned __int64)&v207
                                                                                           & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                          + 0x88);
        goto LABEL_166;
      }
    }
    if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        8,
        160,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids);
    LOBYTE(v163) = 1;
    VmsPktReportDroppedPacketEx(v44, v87, 1, v163, -536870877, -536862654);
    v134 = retaddr;
    *v88 = v87;
    if ( (VmsDiagnosticFlags & 1) == 0 )
      goto LABEL_236;
    if ( !*(_QWORD *)v87 )
      goto LABEL_236;
    v164 = *(_QWORD *)(*(_QWORD *)v87 + 288LL);
    if ( !v164 )
      goto LABEL_236;
    v144 = *(_QWORD *)(v164 + 16);
    if ( !v144 )
      goto LABEL_236;
    *(_DWORD *)(v144 + 184) = 9380;
    goto LABEL_261;
  }
  v45 = 0;
  v27 = 0;
  LODWORD(v46) = 0;
  if ( VmsActiveProcCount )
  {
    do
    {
      v47 = (unsigned int)v46;
      LODWORD(v46) = (_DWORD)v46 + 1;
      v27 += *((_QWORD *)VmsPlanCpuTable + 680 * v47 + 672);
    }
    while ( (unsigned int)v46 < VmsActiveProcCount );
  }
  v48 = *(__int64 **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
  v49 = 0;
  if ( v27 >= 0 )
    v49 = v27;
  if ( !v48 )
    goto LABEL_46;
  do
  {
    if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 4) != (_BYTE)v29 )
      *((_WORD *)v48 + 129) = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
    v60 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70);
    if ( *(_BYTE *)(v60 + 9198) != (_BYTE)v29 )
    {
      v206 = -536862659;
      goto LABEL_201;
    }
    v61 = *(_QWORD *)(v60 + 9000);
    if ( v61 )
    {
      if ( (*(_BYTE *)(v61 + 204) & 2) != 0 )
      {
        v135 = VmsTmShouldDropLoopBackPacket(
                 v60,
                 *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50),
                 v48);
        v29 = 0;
        if ( v135 )
        {
          if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              8,
              157,
              (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids);
          v206 = -536862658;
          v65 = 0;
          BugCheckParameter4 = 35;
          goto LABEL_78;
        }
      }
    }
    if ( v49 >= VmsMaxOutstandingDuplicateNblBytes )
    {
      v206 = -536862657;
LABEL_201:
      BugCheckParameter4 = -102;
      v65 = 3;
LABEL_78:
      LOBYTE(v27) = 1;
      VmsPktReportDroppedNbl(v44, (_DWORD)v48, v27, v65, BugCheckParameter4, v206);
      v29 = 0;
      goto LABEL_79;
    }
    if ( v48[36] != v29 )
    {
      LOBYTE(v46) = 3;
      WPP_RECORDER_SF_I(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v46,
        12,
        158,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (char)v48);
      v206 = -536862656;
      v65 = 22;
      BugCheckParameter4 = 16;
      goto LABEL_78;
    }
    LOBYTE(v27) = 1;
    DuplicateNblsCopyData = VmsNblHelperCreateDuplicateNblsCopyData(
                              (_DWORD)v48,
                              *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) + 168LL),
                              v27,
                              1,
                              v29,
                              v29,
                              v29,
                              v29,
                              v29,
                              v29,
                              (__int64)(v5 + 152),
                              (__int64)(v5 + 36));
    v29 = 0;
    v64 = DuplicateNblsCopyData;
    if ( DuplicateNblsCopyData < 0 )
    {
      LOBYTE(v46) = 3;
      WPP_RECORDER_SF_id(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v46,
        12,
        159,
        (__int64)WPP_1a3332c0bd2932bd40992542520fdbc5_Traceguids,
        (char)v48,
        DuplicateNblsCopyData);
      *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = 0;
      VmsPktGetDropReason(v64, v5 + 56);
      v65 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38);
      v206 = -536862655;
      BugCheckParameter4 = v64;
      goto LABEL_78;
    }
    v75 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98);
    v49 += *(unsigned int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x24);
    v76 = VmsDiagnosticFlags;
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = v49;
    if ( (v76 & 1) != 0 )
    {
      if ( v75 )
      {
        v113 = *(_QWORD *)(v75 + 288);
        if ( v113 )
        {
          v114 = *(_QWORD *)(v113 + 16);
          if ( v114 )
          {
            v46 = "VmsVrssPrimeVrssContextForNextNbl";
            *(_DWORD *)(v114 + 184) = 1123;
            *(_QWORD *)(v114 + 176) = "VmsVrssPrimeVrssContextForNextNbl";
            *(_QWORD *)(v114 + 168) = retaddr;
          }
        }
      }
    }
    LOBYTE(v27) = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD);
    v77 = -1;
    if ( (v27 & 4) != 0 || (LOBYTE(v63) = 0, (v27 & 2) != 0) )
      LOBYTE(v63) = 1;
    if ( (v27 & 1) != 0 )
    {
      v78 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8);
      LOWORD(v79) = -1;
      if ( (_WORD)v78 )
      {
        v80 = *(_DWORD *)(v75 + 208);
        if ( v80 )
        {
          LODWORD(v46) = v80 % v78;
          v79 = v80 % v78;
        }
      }
      if ( (_WORD)v79 == 0xFFFF )
        v77 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x12C);
      v81 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) + 8LL * (__int16)v79 + 8);
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v81;
      if ( !v81 )
      {
        if ( v77 == -1 )
        {
          v82 = VmsQueueGroupGetProcessorIndexForEntry(
                  *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100),
                  (unsigned __int16)v79,
                  v27,
                  v63);
          LOBYTE(v27) = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD);
          v77 = v82;
          v29 = 0;
        }
        LOBYTE(v63) = (v27 & 4) != 0
                   || (v27 & 2) != 0
                   || v77 != -1
                   && (v77 != *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0)
                    || (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x134) & 6) != 0);
        v81 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
      }
    }
    else
    {
      v81 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) & -(__int64)((_BYTE)v63 != 0);
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v81;
      if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) )
      {
        v125 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8);
        LODWORD(v46) = 0xFFFF;
        if ( (_WORD)v125 )
        {
          v126 = *(_DWORD *)(v75 + 208);
          if ( v126 )
            LODWORD(v46) = v126 % v125;
          v81 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18);
        }
        LOWORD(v79) = (_WORD)v46;
      }
      else
      {
        LOWORD(v79) = -2;
      }
    }
    if ( (_BYTE)v63 )
    {
      if ( v81 )
        goto LABEL_184;
      if ( v77 == -1 )
        v77 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0);
      v81 = VmsVrssPvtFindNblGroup(
              *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x118),
              *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x130),
              *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x128),
              v77,
              *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x108),
              (__int64)(v5 + 192));
      v29 = 0;
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v81;
      if ( (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 1) != 0 )
      {
        LODWORD(v46) = (__int16)v79;
        *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) + 8LL * (__int16)v79 + 8) = v81;
      }
    }
    if ( !v81 )
    {
      v83 = (__int64 **)(v5 + 208);
      v84 = v5 + 244;
      goto LABEL_119;
    }
LABEL_184:
    v83 = (__int64 **)(v81 + 32);
    v84 = (unsigned __int8 *)(v81 + 48);
LABEL_119:
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = v84;
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = v83;
    **v83 = v75;
    if ( v75 )
    {
      do
      {
        *(_QWORD *)(v75 + 120) = v29;
        *(_WORD *)(v75 + 258) = *((_WORD *)v48 + 129);
        VmsNblHelperSetSourceInContext(v75, v44);
        LODWORD(v46) = (_DWORD)retaddr;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v75 )
          {
            v85 = *(_QWORD *)(*(_QWORD *)v75 + 288LL);
            if ( v85 )
            {
              v86 = *(_QWORD *)(v85 + 16);
              if ( v86 )
              {
                *(_DWORD *)(v86 + 184) = 9269;
                *(_QWORD *)(v86 + 176) = "VmsPtNicReceiveNetBufferLists";
                *(_QWORD *)(v86 + 168) = retaddr;
              }
            }
          }
        }
        ++v45;
        **(_QWORD **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = v75;
        ++**(_DWORD **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0);
        if ( (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 1) != 0 )
        {
          v111 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8);
          v112 = (const char *)v29;
          v46 = *(const char **)(v111 + 624);
          if ( v46 )
          {
            if ( (_WORD)v79 == 0xFFFF )
            {
              v112 = (const char *)(v111 + 400);
            }
            else if ( (_WORD)v79 == 0xFFFE )
            {
              v112 = (const char *)(v111 + 176);
            }
            else
            {
              v112 = &v46[224 * (__int16)v79];
            }
          }
          _InterlockedIncrement64((volatile signed __int64 *)v112 + 8);
        }
        else if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) != (_BYTE)v29 )
        {
          v154 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8);
          LODWORD(v46) = 0xFFFF;
          if ( (_WORD)v154 )
          {
            v155 = *(_DWORD *)(v75 + 208);
            if ( v155 )
              LODWORD(v46) = v155 % v154;
          }
          v156 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8);
          LOWORD(v79) = (_WORD)v46;
          v157 = v29;
          v27 = *(_QWORD *)(v156 + 624);
          if ( v27 )
          {
            if ( (_WORD)v46 == 0xFFFF )
            {
              v157 = v156 + 400;
            }
            else if ( (_WORD)v46 == 0xFFFE )
            {
              v157 = v156 + 176;
            }
            else
            {
              v157 = v27 + 224LL * (__int16)v46;
            }
          }
          _InterlockedIncrement64((volatile signed __int64 *)(v157 + 64));
          v158 = *(unsigned __int16 *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFA);
          if ( (_WORD)v158 )
          {
            v159 = *(_DWORD *)(v75 + 208);
            v160 = 0xFFFF;
            if ( v159 )
              v160 = v159 % v158;
            if ( (unsigned int)VmsPlanGetPlannedProcessorForEntry(
                                 *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) + 640LL,
                                 v160) != *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) )
              _InterlockedIncrement64((volatile signed __int64 *)(v161 + 96));
          }
        }
        if ( VmsEtwTraceDatapath )
        {
          if ( (v145 = *(_QWORD *)(v44 + 1984)) != 0 && *(_BYTE *)(v145 + 10864) != (_BYTE)v29
            || !VmsEtwTraceFiltersExist )
          {
            VmsTrcTransferNblActivityId(v75, v44, v27);
            VmsEtwTraceNblReceiveDeliver(
              &VM_NBL_RECEIVE,
              v44 + 616,
              *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 72LL,
              *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) + 616LL,
              v75);
            v29 = 0;
          }
        }
        v75 = *(_QWORD *)v75;
      }
      while ( v75 );
      v49 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88);
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
    }
LABEL_79:
    v48 = (__int64 *)*v48;
  }
  while ( v48 );
  if ( !v45 )
  {
LABEL_46:
    v18 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC);
    goto LABEL_47;
  }
LABEL_166:
  v40 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
  v41 = *(struct _KDPC **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
LABEL_167:
  v104 = v29;
  while ( 1 )
  {
    v105 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0);
    if ( !v105 )
      break;
    v106 = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD);
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = *(_QWORD *)v105;
    v104 += *(unsigned int *)(v105 + 48);
    v107 = *(_BYTE *)(v105 + 58) ^ (*(_BYTE *)(v105 + 58) ^ (v106 >> 2)) & 2;
    *(_BYTE *)(v105 + 58) = v107;
    *(_BYTE *)(v105 + 58) = v107
                          ^ (v107
                           ^ (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) >> 2))
                          & 4;
    if ( (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 4) == 0
      || *(struct _KDPC **)(v105 + 16) != v41 )
    {
      LOBYTE(v27) = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x132);
      v108 = *(_QWORD *)(v105 + 16);
      v109 = VmsVrssPvtPushNblGroupToQueue(
               v105,
               *(unsigned int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x134),
               v27);
      v29 = 0;
      if ( !v109 )
        continue;
      if ( v109 == 1 )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v108 + 464));
        v110 = (struct _KDPC *)v108;
        goto LABEL_173;
      }
      v202 = v109 - 2;
      if ( v109 != 2 )
      {
        if ( v109 == 3 )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v108 + 448));
          KeSetEvent((PRKEVENT)(v108 + 192), 3, 0);
        }
        else
        {
          LOBYTE(v202) = 2;
          WPP_RECORDER_SF_dq(
            VmsIfrLog,
            v202,
            20,
            14,
            (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
            v109,
            v108);
        }
        goto LABEL_174;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v108 + 456));
      v110 = (struct _KDPC *)(v108 + 64);
LABEL_173:
      KeInsertQueueDpc(v110, 0, 0);
LABEL_174:
      v29 = 0;
      continue;
    }
    if ( (unsigned __int8)VmsVrssPushNblGroupToBreakerQueue(v105) )
    {
      v110 = v41 + 2;
      goto LABEL_173;
    }
  }
  v168 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68);
  if ( v168 )
  {
    v199 = v29;
    if ( *(_QWORD *)(v168 + 624) != v29 )
      v199 = v168 + 176;
    _InterlockedAdd64((volatile signed __int64 *)(v199 + 64), v104);
  }
  v18 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC);
  if ( *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) != v29 )
  {
    v169 = *(int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4);
    v170 = VmsPtGetNicHeaderAtIndex(v44, (unsigned __int16)v18);
    if ( v170 )
      _InterlockedAdd64(
        (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                  + *(_QWORD *)(v170 + 24)
                                  + 8),
        v169);
    VmsExtPtRouteNetBufferLists(
      v44,
      (unsigned __int16)v18,
      *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8),
      *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4),
      *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C));
    if ( (*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFD) & 1) == 0
      && !*(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC)
      && v168 )
    {
      v200 = 0;
      if ( *(_QWORD *)(v168 + 624) )
        v200 = v168 + 176;
      _InterlockedAdd64(
        (volatile signed __int64 *)(v200 + 64),
        *(unsigned int *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0xF4));
    }
    v172 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34);
    if ( v172 != -1 && (unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v172) )
      v173 = (char *)VmsPlanCpuTable + v40;
    else
      v173 = 0;
    LOBYTE(v171) = *v5;
    VmsQsInlineRebalanceRoutine(v173, v171);
  }
LABEL_47:
  v50 = *(void **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120);
  if ( v50 )
  {
    ExFreeToNPagedLookasideList(&stru_1401FA0C0, v50);
    v9 = *(struct _NET_BUFFER_LIST **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
    v6 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
    *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x120) = 0;
  }
  else
  {
    v9 = *(struct _NET_BUFFER_LIST **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
    v6 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
  }
LABEL_49:
  LOBYTE(v50) = 12;
  VmsOmpObjectDereference(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70), v50);
LABEL_50:
  if ( v9 )
  {
    NvLibRscUncoalesceNbls(v9, &VmsRscLayerNvspVSwitchCookie, 0, 0);
    v51 = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 2);
    if ( v51 )
    {
      v195 = 0;
      Alignment = (_SLIST_HEADER *)v9;
      do
      {
        Alignment = (_SLIST_HEADER *)Alignment->Alignment;
        ++v195;
      }
      while ( Alignment );
      v197 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50);
      v198 = VmsPtGetNicHeaderAtIndex(*(_QWORD *)(v197 + 8), (unsigned __int16)v18);
      if ( v198 )
        _InterlockedAdd64(
          (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                    + *(_QWORD *)(v198 + 24)
                                    + 16),
          -v195);
      v9 = *(struct _NET_BUFFER_LIST **)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
    }
    else
    {
      v197 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50);
    }
    if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 1) )
      v203 = (NDIS_HANDLE *)v197;
    else
      v203 = (NDIS_HANDLE *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) + 112LL);
    NdisReturnNetBufferLists(*v203, v9, 0);
  }
  else
  {
    v51 = *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 2);
  }
  if ( *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20)
    && v51
    && (v73 = VmsPtGetNicHeaderAtIndex(
                *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) + 8LL),
                (unsigned __int16)v18)) != 0 )
  {
    v74 = KeGetCurrentProcessorNumberEx(0);
    v52 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
    _InterlockedAdd64((volatile signed __int64 *)(((unsigned __int64)v74 << 6) + *(_QWORD *)(v73 + 24) + 16), -v52);
  }
  else
  {
    v52 = *(_DWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
  }
  v53 = *(_QWORD *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
  if ( !*(_BYTE *)(v53 + 2400) && v6 )
  {
    LODWORD(v53) = v52;
    _InterlockedAdd64((volatile signed __int64 *)(v6 + 224), v52);
  }
  if ( *(_BYTE *)(((unsigned __int64)&v207 & 0xFFFFFFFFFFFFFFC0uLL) + 3) )
  {
    LODWORD(v53) = KeGetCurrentProcessorNumberEx(0);
    _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(v6 + 216)
                                                      + ((unsigned __int64)(unsigned int)v53 << 6)));
  }
  if ( *v5 )
  {
    v54 = KeGetCurrentProcessorNumberEx(0);
    v56 = v54;
    if ( v54 == -1 )
      goto LABEL_64;
    v57 = v54 >> 6;
    if ( (unsigned int)v57 >= 0x40 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v55,
        19,
        10,
        (__int64)WPP_1993566a47c33aa75355351056e61473_Traceguids,
        (__int64)"(*SetIndex < VMS_CPU_SET_ARRAY_COUNT)");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( !_bittest64(&VmsKnownProcessors[v57], v56 & 0x3F) || (v191 = (char *)VmsPlanCpuTable + 5440 * v56) == 0 )
    {
LABEL_64:
      v58 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v56, v58, 0, 0);
    }
    LODWORD(v53) = NetDispatchProfilerLeave(v191 + 1152);
  }
  return v53;
}

```

## disassembly

```asm
0x140014a60  push    rbp
0x140014a62  push    rbx
0x140014a63  push    rsi
0x140014a64  push    rdi
0x140014a65  push    r12
0x140014a67  push    r13
0x140014a69  push    r14
0x140014a6b  push    r15
0x140014a6d  sub     rsp, 1F8h
0x140014a74  lea     rbp, [rsp+0A0h]
0x140014a7c  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140014a80  mov     rax, cs:__security_cookie
0x140014a87  xor     rax, rsp
0x140014a8a  mov     [rbp+190h+var_50], rax
0x140014a91  xor     r12d, r12d
0x140014a94  mov     [rbp+190h+var_158], rdx
0x140014a98  xor     eax, eax
0x140014a9a  mov     [rbp+190h+var_140], rcx
0x140014a9e  mov     r15d, r8d
0x140014aa1  mov     [rbp+190h+var_110], rdx
0x140014aa8  mov     rsi, rdx
0x140014aab  mov     [rbp+190h+NetBufferLists], r12
0x140014aaf  xor     edx, edx; Val
0x140014ab1  mov     [rbp+190h+var_108], r12
0x140014ab8  mov     r8d, 80h; Size
0x140014abe  mov     [rbp+190h+var_118], r12d
0x140014ac2  lea     rcx, [rbp+190h+var_D0]; void *
0x140014ac9  mov     [rbp+190h+var_16C], r12d
0x140014acd  mov     edi, r12d
0x140014ad0  mov     [rbp+190h+var_F8], r12
0x140014ad7  mov     word ptr [rbp+190h+LockState.OldIrql], ax
0x140014adb  mov     [rbp+190h+LockState.Flags], al
0x140014ade  mov     [rbp+190h+var_180], r9d
0x140014ae2  call    memset
0x140014ae7  mov     r14d, [rsp+230h+arg_20]
0x140014aef  lea     r13d, [r12+1]
0x140014af4  xor     eax, eax
0x140014af6  mov     word ptr [rbp+190h+var_160.OldIrql], ax
0x140014afa  mov     [rbp+190h+var_160.Flags], al
0x140014afd  test    r13b, r14b
0x140014b00  jnz     loc_140014BAB
0x140014b06  call    cs:__imp_KeGetCurrentIrql
0x140014b0d  nop     dword ptr [rax+rax+00h]
0x140014b12  mov     bl, r12b
0x140014b15  cmp     al, 2
0x140014b17  jz      loc_140014BAB
0x140014b1d  xor     ecx, ecx; ProcNumber
0x140014b1f  mov     [rbp+190h+var_190], bl
0x140014b22  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014b29  nop     dword ptr [rax+rax+00h]
0x140014b2e  mov     [rbp+190h+var_15C], eax
0x140014b31  test    bl, bl
0x140014b33  jz      loc_1400164E1
0x140014b39  xor     ecx, ecx; ProcNumber
0x140014b3b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014b42  nop     dword ptr [rax+rax+00h]
0x140014b47  mov     ebx, eax
0x140014b49  cmp     eax, 0FFFFFFFFh
0x140014b4c  jz      short loc_140014B7A
0x140014b4e  mov     edi, ebx
0x140014b50  mov     esi, ebx
0x140014b52  shr     edi, 6
0x140014b55  and     esi, 3Fh
0x140014b58  cmp     edi, 40h ; '@'
0x140014b5b  jnb     loc_140016747
0x140014b61  mov     ecx, esi
0x140014b63  lea     r9, VmsKnownProcessors
0x140014b6a  bt      [r9+rdi*8], rcx
0x140014b6f  setb    al
0x140014b72  test    al, al
0x140014b74  jnz     loc_1400165F1
0x140014b7a  mov     rdi, rbx
0x140014b7d  xor     ecx, ecx; ProcNumber
0x140014b7f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014b86  nop     dword ptr [rax+rax+00h]
0x140014b8b  xor     r9d, r9d; BugCheckParameter3
0x140014b8e  mov     [rsp+230h+BugCheckParameter4], r12; BugCheckParameter4
0x140014b93  mov     r8d, eax; BugCheckParameter2
0x140014b96  mov     rdx, rdi; BugCheckParameter1
0x140014b99  mov     ecx, 121h; BugCheckCode
0x140014b9e  call    cs:__imp_KeBugCheckEx
0x140014bab  mov     bl, r13b
0x140014bae  jmp     loc_140014B1D
0x140014bb3  mov     rax, [rbp+190h+var_140]
0x140014bb7  xor     r15d, r15d
0x140014bba  test    rax, rax
0x140014bbd  jz      short loc_140014BCC
0x140014bbf  cmp     dword ptr [rax+0C0h], 4
0x140014bc6  jnz     loc_140015D8C
0x140014bcc  movzx   r14d, word ptr [rax+10h]
0x140014bd1  mov     eax, 3Fh ; '?'
0x140014bd6  mov     [rbp+190h+var_184], r14d
0x140014bda  cmp     r14w, ax
0x140014bde  ja      loc_1400167CA
0x140014be4  xor     r15d, r15d
0x140014be7  cmp     dword ptr [r13+750h], 2
0x140014bef  jz      loc_140014F72
0x140014bf5  lea     rbx, [r13+4D0h]
0x140014bfc  test    rbx, rbx
0x140014bff  jz      loc_140015CC2
0x140014c05  cmp     dword ptr [rbx+10h], 2
0x140014c09  jnz     loc_140015CC2
0x140014c0f  xor     eax, eax
0x140014c11  mov     [rbp+190h+var_18E], r15b
0x140014c15  movzx   edx, r14w
0x140014c19  mov     [rbp+190h+var_178], rax
0x140014c1d  mov     rcx, r13
0x140014c20  mov     [rbp+190h+var_18C], al
0x140014c23  call    VmsPtGetNicHeaderAtIndex
0x140014c28  xor     r8d, r8d
0x140014c2b  mov     rdi, rax
0x140014c2e  test    rax, rax
0x140014c31  jz      short loc_140014C58
0x140014c33  xor     ecx, ecx; ProcNumber
0x140014c35  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014c3c  nop     dword ptr [rax+rax+00h]
0x140014c41  movsxd  rdx, [rbp+190h+var_180]
0x140014c45  mov     ecx, eax
0x140014c47  mov     rax, [rdi+18h]
0x140014c4b  shl     rcx, 6
0x140014c4f  lock add [rcx+rax+10h], rdx
0x140014c55  xor     r8d, r8d
0x140014c58  mov     rdi, [rbp+190h+var_120]
0x140014c5c  mov     rax, [rbp+190h+var_168]
0x140014c60  mov     rcx, [rdi+2328h]
0x140014c67  test    rcx, rcx
0x140014c6a  jnz     loc_14001587A
0x140014c70  movzx   ecx, word ptr [rsi+102h]
0x140014c77  mov     [rbp+190h+var_138], ecx
0x140014c7a  test    ecx, ecx
0x140014c7c  jz      loc_1400150D3
0x140014c82  mov     rdx, [rax+590h]
0x140014c89  test    rdx, rdx
0x140014c8c  jz      loc_1400150D3
0x140014c92  cmp     [rax+960h], r8b
0x140014c99  jnz     loc_14001682A
0x140014c9f  lea     eax, [rcx-1]
0x140014ca2  mov     r12, [rdx+rax*8]
0x140014ca6  mov     [rbp+190h+var_148], r12
0x140014caa  mov     [rbp+190h+var_18D], r8b
0x140014cae  test    r12, r12
0x140014cb1  jz      short loc_140014CF4
0x140014cb3  cmp     dword ptr [r12+30h], 1
0x140014cb9  jnz     loc_140014FAA
0x140014cbf  mov     eax, [r12+34h]
0x140014cc4  test    al, 20h
0x140014cc6  jnz     loc_140014FAA
0x140014ccc  xor     ecx, ecx; ProcNumber
0x140014cce  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014cd5  nop     dword ptr [rax+rax+00h]
0x140014cda  mov     ecx, eax
0x140014cdc  shl     rcx, 6
0x140014ce0  add     rcx, [r12+0D8h]
0x140014ce8  lock inc qword ptr [rcx]
0x140014cec  mov     [rbp+190h+var_18D], 1
0x140014cf0  mov     [rbp+190h+var_148], r12
0x140014cf4  mov     rcx, [r13+38h]; Lock
0x140014cf8  lea     rdx, [rbp+190h+LockState]; LockState
0x140014cfc  call    cs:__imp_NdisReleaseRWLock
0x140014d03  nop     dword ptr [rax+rax+00h]
0x140014d08  mov     dil, [rdi+23D8h]
0x140014d0f  xor     r11d, r11d
0x140014d12  test    r12, r12
0x140014d15  jnz     loc_140015F25
0x140014d1b  mov     rbx, [rbp+190h+var_130]
0x140014d1f  mov     r12b, r11b
0x140014d22  mov     [rbp+190h+var_128], r11
0x140014d26  mov     esi, r11d
0x140014d29  mov     r14b, dil
0x140014d2c  cmp     [rbp+190h+var_170], r11d
0x140014d30  jz      loc_1400157D5
0x140014d36  mov     r13d, r11d
0x140014d39  cmp     [rbp+190h+var_148], r11
0x140014d3d  jnz     loc_1400159D3
0x140014d43  mov     ecx, [rbp+190h+var_15C]
0x140014d46  lea     rax, [rbp+190h+var_C8]
0x140014d4d  movzx   ebx, word ptr [rbp+190h+var_130+2]
0x140014d51  and     dil, 1
0x140014d55  mov     rdx, [rbp+190h+var_128]
0x140014d59  and     r14b, 1
0x140014d5d  add     dil, dil
0x140014d60  mov     [rbp+190h+var_94], r12b
0x140014d67  or      dil, r14b
0x140014d6a  mov     [rbp+190h+var_C0], rax
0x140014d71  mov     eax, cs:VmsExecutionMode
0x140014d77  mov     r14, cs:VmsPlanCpuTable
0x140014d7e  imul    r12, rcx, 1540h
0x140014d85  shl     dil, 3
0x140014d89  add     r14, 240h
0x140014d90  add     r14, r12
0x140014d93  mov     [rbp+190h+var_93], dil
0x140014d9a  mov     dil, [rbp+190h+var_190]
0x140014d9e  mov     [rbp+190h+var_9C], r11d
0x140014da5  mov     [rbp+190h+var_C8], r11
0x140014dac  mov     [rbp+190h+var_B0], r11
0x140014db3  mov     [rbp+190h+var_B8], r11
0x140014dba  mov     [rbp+190h+Entry], r11
0x140014dc1  mov     [rbp+190h+var_D0], r11
0x140014dc8  mov     [rbp+190h+var_A0], ecx
0x140014dce  mov     [rbp+190h+var_5C], eax
0x140014dd4  mov     [rbp+190h+var_A8], rdx
0x140014ddb  mov     [rbp+190h+var_96], r13w
0x140014de3  mov     [rbp+190h+var_98], bx
0x140014dea  mov     [rbp+190h+var_130], r12
0x140014dee  mov     [rbp+190h+var_110], r14
0x140014df5  test    al, 6
0x140014df7  jz      loc_140015101
0x140014dfd  mov     al, r11b
0x140014e00  test    r15b, r15b
0x140014e03  jnz     loc_14001512A
0x140014e09  mov     r13, [rbp+190h+var_100]
0x140014e10  mov     edi, 1
0x140014e15  mov     [rbp+190h+var_18E], dil
0x140014e19  cmp     [rbp+190h+var_170], r11d
0x140014e1d  jz      loc_140015488
0x140014e23  cmp     cs:VmsActiveProcCount, r11d
0x140014e2a  mov     r15d, r11d
0x140014e2d  mov     r8, r11
0x140014e30  mov     edx, r11d
0x140014e33  jbe     short loc_140014E5A
0x140014e35  mov     eax, edx
0x140014e37  add     edx, edi
0x140014e39  imul    rcx, rax, 1540h
0x140014e40  mov     rax, cs:VmsPlanCpuTable
0x140014e47  mov     rcx, [rcx+rax+1500h]
0x140014e4f  add     r8, rcx
0x140014e52  cmp     edx, cs:VmsActiveProcCount
0x140014e58  jb      short loc_140014E35
0x140014e5a  mov     rsi, [rbp+190h+var_158]
0x140014e5e  test    r8, r8
0x140014e61  mov     r14, r11
0x140014e64  cmovns  r14, r8
0x140014e68  test    rsi, rsi
0x140014e6b  jnz     loc_140014FB2
0x140014e71  mov     r14d, [rbp+190h+var_184]
0x140014e75  lea     r13, VmsKnownProcessors
0x140014e7c  mov     rdx, [rbp+190h+Entry]; Entry
0x140014e83  test    rdx, rdx
0x140014e86  jz      loc_140016A1A
0x140014e8c  lea     rcx, stru_1401FA0C0; Lookaside
0x140014e93  call    cs:__imp_ExFreeToNPagedLookasideList
0x140014e9a  nop     dword ptr [rax+rax+00h]
0x140014e9f  mov     rdi, [rbp+190h+NetBufferLists]
0x140014ea3  xor     r15d, r15d
0x140014ea6  mov     r12, [rbp+190h+var_148]
0x140014eaa  mov     [rbp+190h+Entry], r15
0x140014eb1  mov     rcx, [rbp+190h+var_120]
0x140014eb5  mov     dl, 0Ch
0x140014eb7  call    VmsOmpObjectDereference
0x140014ebc  test    rdi, rdi
0x140014ebf  jnz     loc_140016A2A
0x140014ec5  mov     sil, [rbp+190h+var_18E]
0x140014ec9  cmp     [rbp+190h+var_170], r15d
0x140014ecd  jnz     loc_1400151EB
0x140014ed3  mov     r8d, [rbp+190h+var_180]
0x140014ed7  mov     rax, [rbp+190h+var_168]
0x140014edb  cmp     [rax+960h], r15b
0x140014ee2  jnz     short loc_140014EF5
0x140014ee4  test    r12, r12
0x140014ee7  jz      short loc_140014EF5
0x140014ee9  mov     eax, r8d
0x140014eec  lock add [r12+0E0h], rax
0x140014ef5  cmp     [rbp+190h+var_18D], r15b
0x140014ef9  jnz     loc_1400161DA
0x140014eff  cmp     [rbp+190h+var_190], r15b
0x140014f03  jz      loc_14001637E
0x140014f09  xor     ecx, ecx; ProcNumber
0x140014f0b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014f12  nop     dword ptr [rax+rax+00h]
0x140014f17  mov     ebx, eax
0x140014f19  cmp     eax, 0FFFFFFFFh
0x140014f1c  jz      short loc_140014F44
0x140014f1e  mov     edi, ebx
0x140014f20  mov     esi, ebx
0x140014f22  shr     edi, 6
0x140014f25  and     esi, 3Fh
0x140014f28  cmp     edi, 40h ; '@'
0x140014f2b  jnb     loc_140016A80
0x140014f31  mov     ecx, esi
0x140014f33  bt      [r13+rdi*8+0], rcx
0x140014f39  setb    al
0x140014f3c  test    al, al
0x140014f3e  jnz     loc_14001660D
0x140014f44  xor     ecx, ecx; ProcNumber
0x140014f46  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140014f4d  nop     dword ptr [rax+rax+00h]
0x140014f52  xor     r9d, r9d; BugCheckParameter3
0x140014f55  mov     [rsp+230h+BugCheckParameter4], r15; BugCheckParameter4
0x140014f5a  mov     r8d, eax; BugCheckParameter2
0x140014f5d  mov     rdx, rbx; BugCheckParameter1
0x140014f60  mov     ecx, 121h; BugCheckCode
0x140014f65  call    cs:__imp_KeBugCheckEx
0x140014f72  test    r14w, r14w
0x140014f76  jz      loc_140014BF5
0x140014f7c  mov     rbx, [r13+0CF0h]
0x140014f83  test    rbx, rbx
0x140014f86  jz      loc_140015CC2
0x140014f8c  cmp     r14w, ax
0x140014f90  ja      loc_140015CC2
0x140014f96  lfence
  ... truncated ...
```
