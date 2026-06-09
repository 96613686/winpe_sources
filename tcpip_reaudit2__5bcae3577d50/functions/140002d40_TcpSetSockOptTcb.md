# TcpSetSockOptTcb

- ea: `0x140002d40`
- end: `0x140004bb1`
- name: `TcpSetSockOptTcb`
- size: `7793`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140002c10`

## callees

- `0x140001500`
- `0x140002200`
- `0x140002d40`
- `0x140006384`
- `0x140009470`
- `0x140009990`
- `0x140013140`
- `0x140014430`
- `0x140037220`
- `0x1400387d0`
- `0x14003d080`
- `0x14004e23c`
- `0x140052630`
- `0x140081590`
- `0x1400822b4`
- `0x140082e50`
- `0x14008b220`
- `0x1400950f0`
- `0x140095184`
- `0x1400951fc`
- `0x1400c96d0`
- `0x1400e1500`
- `0x1400e15d4`
- `0x1400e7280`
- `0x1400f1d90`
- `0x1401015d8`
- `0x140108aa4`
- `0x140112d24`
- `0x14011e070`
- `0x14015f97c`
- `0x140170960`
- `0x14017f924`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bf780`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140003145`
- `ntoskrnl!KeLowerIrql` at `0x140003145`
- `ntoskrnl!IoFileObjectType` at `0x140003bff`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400033fe`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400033fe`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140003395`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140003395`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14000440e`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14000440e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003113`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003113`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400035dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003633`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000378f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400037f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003d9c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400035dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003633`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000378f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400037f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003d9c`
- `ntoskrnl!RtlCompareMemory` at `0x140003a39`
- `ntoskrnl!RtlCompareMemory` at `0x140003a5b`
- `ntoskrnl!RtlCompareMemory` at `0x140003bca`
- `ntoskrnl!RtlCompareMemory` at `0x14000401f`
- `ntoskrnl!RtlCompareMemory` at `0x140004240`
- `ntoskrnl!RtlCompareMemory` at `0x140003a39`
- `ntoskrnl!RtlCompareMemory` at `0x140003a5b`
- `ntoskrnl!RtlCompareMemory` at `0x140003bca`
- `ntoskrnl!RtlCompareMemory` at `0x14000401f`
- `ntoskrnl!RtlCompareMemory` at `0x140004240`
- `ntoskrnl!PsGetProcessId` at `0x140003b49`
- `ntoskrnl!PsGetProcessId` at `0x140004095`
- `ntoskrnl!PsGetProcessId` at `0x140003b49`
- `ntoskrnl!PsGetProcessId` at `0x140004095`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003608`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003676`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400036bd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400037b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000382f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003889`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400038dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000391b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003e1b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003608`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003676`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400036bd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400037b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000382f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003889`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400038dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000391b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003e1b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004205`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004205`
- `ntoskrnl!KeInitializeEvent` at `0x140004122`
- `ntoskrnl!KeInitializeEvent` at `0x140004122`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140003c24`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140003c24`
- `ntoskrnl!ObfDereferenceObject` at `0x140003e94`
- `ntoskrnl!ObfDereferenceObject` at `0x140003e94`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f59`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000319c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400032c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000333a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000335d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003382`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003428`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400041e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000479e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a38`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f59`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000319c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400032c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000333a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000335d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003382`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003428`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400041e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000479e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002df9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004214`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002df9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003c36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004214`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003876`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003876`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e3a`
- `ntoskrnl!ExAllocatePool2` at `0x14000365d`
- `ntoskrnl!ExAllocatePool2` at `0x1400038c2`
- `ntoskrnl!ExAllocatePool2` at `0x140003cde`
- `ntoskrnl!ExAllocatePool2` at `0x14000365d`
- `ntoskrnl!ExAllocatePool2` at `0x1400038c2`
- `ntoskrnl!ExAllocatePool2` at `0x140003cde`
- `NETIO!NetioInsertWorkQueue` at `0x1400041bb`
- `NETIO!NetioInsertWorkQueue` at `0x1400041bb`
- `NETIO!NetioNcmTlObjectRequest` at `0x140003aa4`
- `NETIO!NetioNcmTlObjectRequest` at `0x14000415c`
- `NETIO!NetioNcmTlObjectRequest` at `0x140003aa4`
- `NETIO!NetioNcmTlObjectRequest` at `0x14000415c`
- `NETIO!NetioNrtAssociateContext` at `0x140003c84`
- `NETIO!NetioNrtAssociateContext` at `0x140003c84`
- `NETIO!NetioNrtIsTrackerDevice` at `0x140003c58`
- `NETIO!NetioNrtIsTrackerDevice` at `0x140003c58`
- `NETIO!NmrClientDetachProviderComplete` at `0x140003617`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400037c8`
- `NETIO!NmrClientDetachProviderComplete` at `0x140003617`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400037c8`
- `NETIO!NetioNrtReferenceRecord` at `0x140003deb`
- `NETIO!NetioNrtReferenceRecord` at `0x140003deb`
- `NETIO!NetioNrtDereferenceRecord` at `0x140003dd5`
- `NETIO!NetioNrtDereferenceRecord` at `0x140003dd5`

## string_xrefs

- `0x140003f95`: `StringCchCopyA`
- `0x140003fe7`: `WfpStringCchCopyA`

## pseudocode

```c
__int64 __fastcall TcpSetSockOptTcb(
        unsigned __int8 *SpinLock,
        int a2,
        unsigned int a3,
        unsigned int *a4,
        KSPIN_LOCK *a5,
        void *a6,
        unsigned __int64 a7,
        size_t *a8)
{
  void *v9; // r14
  int v12; // ecx
  KIRQL v13; // r13
  int v14; // eax
  NTSTATUS v15; // r14d
  unsigned int LockArray_high; // edi
  unsigned __int64 MicrosecondCount; // rax
  PKSPIN_LOCK v19; // rsi
  int v20; // edx
  unsigned int v21; // r15d
  __int64 v22; // rax
  unsigned __int8 v23; // cl
  unsigned __int64 v24; // rdi
  unsigned int v25; // eax
  int v26; // esi
  bool v27; // cc
  int v28; // r9d
  unsigned int v29; // r8d
  int v30; // ecx
  KSPIN_LOCK v31; // rax
  int v32; // r15d
  unsigned int v33; // ecx
  __int64 v34; // rdx
  KSPIN_LOCK v35; // r13
  int v36; // r8d
  int v37; // edx
  int v38; // eax
  __int64 v39; // rax
  void *v40; // rsi
  __int64 v41; // rax
  __int64 *v42; // rdx
  __int64 v43; // rdi
  __int64 v44; // r14
  int v45; // eax
  __int64 v46; // rcx
  void *v47; // rdi
  __int64 *v48; // rcx
  __int64 v49; // rsi
  _QWORD *v50; // rdx
  __int64 v51; // rax
  char v52; // al
  _DWORD *v53; // rdi
  KSPIN_LOCK v54; // rax
  int v55; // eax
  unsigned __int8 ProcessId; // al
  KSPIN_LOCK v57; // rax
  __int64 v58; // rsi
  void *v59; // rcx
  int v60; // edx
  _QWORD *v61; // r12
  __int64 v62; // rdx
  __int64 v63; // r15
  KSPIN_LOCK v64; // rdi
  __int64 v65; // rsi
  _BYTE *v66; // rcx
  void *v67; // rsi
  bool v68; // zf
  struct _KSPIN_LOCK_QUEUE *volatile Next; // r15
  void *v70; // rsi
  __int64 v71; // rax
  const char *v72; // rdx
  int v73; // r8d
  _BYTE *v74; // rax
  char v75; // al
  __int16 v76; // cx
  int v77; // edx
  __int64 v78; // rdx
  char v79; // al
  unsigned int v80; // eax
  __int64 v81; // rax
  void *v82; // rdi
  size_t v83; // r15
  __int64 v84; // rcx
  int v85; // r12d
  __int64 v86; // rdx
  __int64 v87; // rcx
  bool v88; // al
  unsigned __int64 v89; // rcx
  int v90; // eax
  unsigned __int8 v91; // cf
  _DWORD *v92; // rdi
  char v93; // r9
  __int16 v94; // dx
  __int16 v95; // r10
  char v96; // r11
  char v97; // di
  __int16 v98; // ax
  int v99; // r8d
  int v100; // ecx
  int v101; // esi
  PKSPIN_LOCK v102; // rax
  KSPIN_LOCK v103; // r8
  __int64 *v104; // r11
  KSPIN_LOCK v105; // r10
  KSPIN_LOCK v106; // r9
  __int64 v107; // rdx
  _QWORD *v108; // rcx
  __int64 v109; // rax
  __int64 (__fastcall *v110)(__int128 *); // rax
  int v111; // eax
  char v112; // al
  unsigned int v113; // ecx
  unsigned int v114; // esi
  unsigned int v115; // esi
  unsigned __int8 v116; // cl
  bool v117; // r8
  KSPIN_LOCK v118; // rax
  __int64 (__fastcall *v119)(_BYTE *); // rax
  int PathInformation; // eax
  KSPIN_LOCK v121; // rdx
  __int64 (__fastcall *v122)(_BYTE *); // rax
  int SessionInfo; // eax
  KSPIN_LOCK v124; // rax
  __int64 (__fastcall *v125)(_BYTE *); // rax
  int v126; // eax
  int v127; // ecx
  __int64 v128; // rdx
  PVOID *Object; // [rsp+20h] [rbp-E0h]
  int HandleInformation; // [rsp+28h] [rbp-D8h]
  char v131; // [rsp+30h] [rbp-D0h]
  char v132; // [rsp+40h] [rbp-C0h]
  char v133; // [rsp+70h] [rbp-90h] BYREF
  char v134; // [rsp+71h] [rbp-8Fh] BYREF
  void *Pool2; // [rsp+78h] [rbp-88h]
  __int64 v136; // [rsp+80h] [rbp-80h] BYREF
  int v137; // [rsp+88h] [rbp-78h]
  __int64 v138; // [rsp+90h] [rbp-70h]
  PVOID v139; // [rsp+98h] [rbp-68h] BYREF
  struct _KLOCK_QUEUE_HANDLE v140; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v141[32]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v142[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 Src; // [rsp+100h] [rbp+0h] BYREF
  __int128 v144; // [rsp+110h] [rbp+10h]
  __int128 v145; // [rsp+120h] [rbp+20h]
  __int128 v146; // [rsp+130h] [rbp+30h]
  __int128 v147; // [rsp+140h] [rbp+40h]
  __int128 v148; // [rsp+150h] [rbp+50h]
  __int128 v149; // [rsp+160h] [rbp+60h]
  __int128 v150; // [rsp+170h] [rbp+70h]
  __int128 v151; // [rsp+180h] [rbp+80h]
  __int64 v152; // [rsp+190h] [rbp+90h]
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+1A0h] [rbp+A0h] BYREF

  v9 = a6;
  Pool2 = a6;
  LODWORD(v139) = a2;
  v133 = 0;
  if ( dword_1402201D4 && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
  {
    LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
    v12 = (int)a5;
    LockHandle.LockQueue.Lock = 0;
    if ( !a4 )
      v12 = 0;
    McTemplateK0pqqqbr3_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCPIP_SETSOCKOPT,
      (unsigned int)&LockHandle,
      (_DWORD)SpinLock,
      a2,
      a3,
      v12,
      (__int64)a4);
  }
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
  if ( (_DWORD)v139 == 6 )
  {
    if ( dword_1402201D4
      && (!TcpipTraceFiltersExist || (SpinLock[804] & 0x80u) != 0)
      && (BYTE3(WPP_MAIN_CB.Reserved) & 0x20) != 0 )
    {
      LockHandle.LockQueue.Lock = 0;
      LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
      McTemplateK0pqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_SET_TCP_OPTION,
        (unsigned int)&LockHandle,
        (_DWORD)SpinLock,
        a3,
        0);
    }
    if ( ((a3 - 2) & 0xFFFFFFFA) == 0
      && a3 != 3
      && ((unsigned __int8)TcpHasUrgentTcbInput(SpinLock) || (*((_DWORD *)SpinLock + 30) & 0x800) != 0) )
    {
      goto LABEL_18;
    }
    if ( a3 <= 0xF )
    {
      v14 = 37888;
      if ( _bittest(&v14, a3) )
        goto LABEL_18;
    }
    v15 = TcpSetTcpLevelOption((int)SpinLock + 760, a3, (_DWORD)a4, (_DWORD)a5, (__int64)&v133);
    if ( v15 < 0 || !v133 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
      goto LABEL_25;
    if ( a3 != 3 )
    {
      if ( a3 == 5 || a3 == 14 )
        *((_DWORD *)SpinLock + 187) = 0;
      goto LABEL_25;
    }
LABEL_23:
    if ( (SpinLock[794] & 4) != 0 )
    {
      SpinLock[754] = 0;
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      MicrosecondCount = TcpQueryMicrosecondCount(LockArray_high, 0);
      TcpStartTimerTcbInternal(
        (_DWORD)SpinLock,
        4,
        *((_DWORD *)SpinLock + 191),
        MicrosecondCount / 0x3E8,
        LockArray_high,
        4);
    }
    else if ( (*((_DWORD *)SpinLock + 202) & 0x40) == 0 )
    {
      TcpStopTimerTcbInternal(SpinLock, 4, 4);
    }
    goto LABEL_25;
  }
  if ( (_DWORD)v139 == 0xFFFF )
  {
    if ( ((a3 - 12293) & 0xFFFFFFFD) != 0 )
    {
      if ( dword_1402201D4
        && (!TcpipTraceFiltersExist || (SpinLock[804] & 0x80u) != 0)
        && (BYTE3(WPP_MAIN_CB.Reserved) & 0x20) != 0 )
      {
        LockHandle.LockQueue.Lock = 0;
        LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
        McTemplateK0pqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_SET_TCP_SO_OPTION,
          (unsigned int)&LockHandle,
          (_DWORD)SpinLock,
          0,
          a3);
      }
      if ( a3 == 256 )
      {
        if ( (unsigned __int8)TcpHasUrgentTcbInput(SpinLock) || (*((_DWORD *)SpinLock + 30) & 0x800) != 0 )
        {
LABEL_18:
          v15 = -1073741436;
          v133 = 0;
LABEL_25:
          KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
          return (unsigned int)v15;
        }
      }
      else if ( a3 == 4098 )
      {
        if ( (unsigned __int64)a5 < 4 )
        {
          v15 = -1073741306;
          v133 = 0;
          goto LABEL_25;
        }
        v28 = *((_DWORD *)SpinLock + 28);
        v29 = *a4;
        if ( v28 >= 2 && v29 > 0xFFFF << SpinLock[801] )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
          return (unsigned int)-1073741436;
        }
        v19 = (PKSPIN_LOCK)(SpinLock + 760);
        if ( v29 < *((_DWORD *)SpinLock + 190) && (SpinLock[795] & 0x80u) == 0 && v28 >= 4 )
        {
          v15 = 0;
          v133 = 0;
          goto LABEL_25;
        }
        v20 = 4098;
        goto LABEL_43;
      }
      v19 = (PKSPIN_LOCK)(SpinLock + 760);
      v20 = a3;
LABEL_43:
      v15 = TcpSetSoLevelOption((_DWORD)v19, v20, (_DWORD)a4, (_DWORD)a5, (__int64)&v133);
      if ( v15 < 0 || !v133 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
        goto LABEL_25;
      if ( a3 != 8 )
      {
        if ( a3 == 4098 )
        {
          *((_DWORD *)SpinLock + 30) |= 0x400u;
          v21 = HIDWORD(KeGetPcr()[1].LockArray);
          v22 = TcpQueryMicrosecondCount(v21, 0);
          v23 = SpinLock[801];
          v24 = v22;
          v25 = *(_DWORD *)v19;
          if ( *(_DWORD *)v19 >= (unsigned int)(0xFFFF << v23) )
            v25 = 0xFFFF << v23;
          *(_DWORD *)v19 = v25;
          v26 = 1 << v23;
          if ( v25 > 1 << v23 )
            v26 = v25;
          v27 = *((_DWORD *)SpinLock + 28) < 4;
          *((_DWORD *)SpinLock + 190) = v26;
          if ( !v27 )
          {
            if ( (unsigned __int8)TcpTryToIncreaseTcbRcvWnd(SpinLock, v21, 0) )
            {
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)SpinLock);
              TcpFlushDelay(v21, v24 / 0x3E8);
              KeLowerIrql(v13);
              return (unsigned int)v15;
            }
          }
        }
        goto LABEL_25;
      }
      goto LABEL_23;
    }
LABEL_336:
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
    return (unsigned int)-1073741256;
  }
  if ( (_DWORD)v139 != 65532 )
  {
    if ( (_DWORD)v139 == 41 && a3 == 27 )
      goto LABEL_336;
    goto LABEL_337;
  }
  switch ( a3 )
  {
    case 0x98000004:
    case 0x9800012C:
      goto LABEL_172;
    case 0x98000010:
      goto LABEL_168;
    case 0x98000011:
LABEL_170:
      if ( *((int *)SpinLock + 28) >= 2 )
      {
        v52 = 0;
        v15 = -1073741436;
        v133 = 0;
        goto LABEL_173;
      }
LABEL_172:
      v15 = TcpSetSioLevelOption((int)SpinLock + 760, a3, (_DWORD)a4, (_DWORD)a5, (__int64)a6, a7, (__int64)&v133);
      v52 = v133;
LABEL_173:
      if ( a3 > 0x98000016 )
      {
        if ( a3 != -1744830441 )
        {
          if ( a3 == -1744830440 )
          {
            if ( a7 >= 8 )
            {
              v15 = 0;
              v92 = Pool2;
              *(_DWORD *)Pool2 = SpinLock[796] >> 5;
              v92[1] = ((unsigned __int8)~SpinLock[798] >> 4) & 2;
              if ( a8 )
                *a8 = 8;
              goto LABEL_25;
            }
          }
          else
          {
            if ( a3 != -671088601 )
              goto LABEL_25;
            v136 = 0;
            *(_WORD *)((char *)&v144 + 1) = 0;
            BYTE3(v144) = 0;
            *(_WORD *)((char *)&v148 + 5) = 0;
            BYTE7(v148) = 0;
            *(_WORD *)((char *)&v151 + 13) = 0;
            HIBYTE(v151) = 0;
            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)0x8800000058LL;
            LODWORD(LockHandle.LockQueue.Lock) = 152;
            if ( !a4 )
              goto LABEL_283;
            if ( a5 != (KSPIN_LOCK *)4 )
              goto LABEL_283;
            v81 = *a4;
            if ( (unsigned int)v81 >= 3 )
              goto LABEL_283;
            v82 = Pool2;
            if ( !Pool2 )
              goto LABEL_285;
            v83 = *((unsigned int *)&LockHandle.LockQueue.Next + v81);
            if ( a7 >= v83 )
            {
              KeQuerySystemTimePrecise(&v136);
              v84 = v136 - *((_QWORD *)SpinLock + 109);
              LODWORD(Src) = *((_DWORD *)SpinLock + 28);
              v85 = *((_DWORD *)SpinLock + 99);
              DWORD1(Src) = *((_DWORD *)SpinLock + 44);
              v86 = (unsigned __int128)(v84 * (__int128)0x346DC5D63886594BLL) >> 64;
              HIDWORD(v144) = *((_DWORD *)SpinLock + 36) - *((_DWORD *)SpinLock + 34);
              v87 = HIDWORD(v144);
              LODWORD(v87) = HIDWORD(KeGetPcr()[1].LockArray);
              HIDWORD(v150) = v85;
              v88 = (SpinLock[793] & 4) != 0;
              *((_QWORD *)&Src + 1) = ((unsigned __int64)v86 >> 63) + (v86 >> 11);
              LOBYTE(v144) = v88;
              DWORD1(v144) = *((_DWORD *)SpinLock + 178) >> 3;
              DWORD2(v144) = *((_DWORD *)SpinLock + 180);
              LODWORD(v145) = *((_DWORD *)SpinLock + 49);
              DWORD1(v145) = *((_DWORD *)SpinLock + 40);
              DWORD2(v145) = *((_DWORD *)SpinLock + 136);
              HIDWORD(v145) = *((_DWORD *)SpinLock + 190);
              *(_QWORD *)&v146 = *((_QWORD *)SpinLock + 48);
              *((_QWORD *)&v146 + 1) = *((_QWORD *)SpinLock + 64);
              LODWORD(v147) = *((_DWORD *)SpinLock + 286);
              *(_QWORD *)((char *)&v147 + 4) = *((_QWORD *)SpinLock + 140);
              HIDWORD(v147) = *((_DWORD *)SpinLock + 282);
              LODWORD(v148) = *((_DWORD *)SpinLock + 283);
              BYTE4(v148) = SpinLock[1140];
              DWORD2(v148) = *((_DWORD *)SpinLock + 102);
              v137 = *((_DWORD *)SpinLock + 103);
              HIDWORD(v148) = v137;
              *(_QWORD *)&v149 = *((_QWORD *)SpinLock + 52);
              DWORD2(v149) = *((_DWORD *)SpinLock + 106);
              LODWORD(v138) = *((_DWORD *)SpinLock + 107);
              HIDWORD(v149) = v138;
              *(_QWORD *)&v150 = *((_QWORD *)SpinLock + 54);
              DWORD2(v150) = *((_DWORD *)SpinLock + 98);
              *(_QWORD *)&v151 = *((_QWORD *)SpinLock + 50);
              v89 = TcpQueryMicrosecondCount(v87, 0) / 0x3E8uLL;
              v90 = *((_DWORD *)SpinLock + 125);
              if ( v90 )
              {
                if ( v90 == 1 )
                {
                  HIDWORD(v148) = v137 + v89 - *((_DWORD *)SpinLock + 110);
                }
                else if ( v90 == 2 )
                {
                  HIDWORD(v149) = v138 + v89 - *((_DWORD *)SpinLock + 110);
                }
              }
              else
              {
                HIDWORD(v150) = v85 + v89 - *((_DWORD *)SpinLock + 110);
              }
              v91 = _bittest16((const signed __int16 *)SpinLock + 64, 0xDu);
              DWORD2(v151) = *((_DWORD *)SpinLock + 288);
              if ( !v91 || (v91 = _bittest((const signed __int32 *)SpinLock + 202, 0xAu), BYTE12(v151) = 1, !v91) )
                BYTE12(v151) = 0;
              LODWORD(v152) = *((_DWORD *)SpinLock + 289);
              HIDWORD(v152) = *((_DWORD *)SpinLock + 284);
              memmove(v82, &Src, v83);
              if ( a8 )
                *a8 = v83;
              goto LABEL_25;
            }
          }
          goto LABEL_309;
        }
        if ( v15 < 0 || !v52 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
          goto LABEL_25;
        if ( !*((_WORD *)SpinLock + 406) )
          TcpTcbSelectDelAckParameters(SpinLock);
      }
      else
      {
        if ( a3 != -1744830442 )
        {
          if ( a3 != 1476395048 )
          {
            if ( a3 == -1744830460 )
            {
              if ( v15 < 0 || !v52 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
                goto LABEL_25;
              goto LABEL_23;
            }
            if ( a3 != -1744830445 )
            {
              if ( a3 != -1744830444 )
                goto LABEL_25;
              if ( a4 )
              {
                v53 = Pool2;
                if ( Pool2 )
                {
                  if ( (unsigned __int64)a5 >= 0x10 && a7 >= 4 )
                  {
                    if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY, a4, 0x10u) == 16
                      || RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY_EX, a4, 0x10u) == 16 )
                    {
                      v54 = *((_QWORD *)SpinLock + 5);
                      if ( v54 )
                      {
                        *(_OWORD *)&v141[16] = 0;
                        memset(v142, 0, sizeof(v142));
                        *(_OWORD *)v141 = v54;
                        NetioNcmTlObjectRequest(v141, 2);
                        v55 = DWORD2(v142[0]);
                        *v53 = DWORD2(v142[0]);
                        if ( (unsigned int)(v55 - 1) > 1 )
                        {
LABEL_192:
                          if ( v15 >= 0 && a8 )
                            *a8 = 4;
                          goto LABEL_196;
                        }
                        if ( *((_DWORD *)SpinLock + 28) == 4 )
                        {
                          if ( (*((_DWORD *)SpinLock + 202) & 0xE0000) != 0 )
                            TcpTcbSignalNotificationChannelEvent(SpinLock, 0, 0, 0);
                          goto LABEL_192;
                        }
                      }
                      else if ( *((_DWORD *)SpinLock + 28) == 4 )
                      {
                        v15 = -1073741637;
LABEL_196:
                        if ( dword_1402201D4 && (!TcpipTraceFiltersExist || (SpinLock[804] & 0x80u) != 0) )
                        {
                          LockHandle.LockQueue = 0;
                          if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 1) != 0 )
                          {
                            ProcessId = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)SpinLock + 106));
                            v132 = *v53;
                            v131 = ProcessId;
                            v57 = *((_QWORD *)SpinLock + 5);
                            LockHandle.LockQueue.Lock = 0;
                            LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
                            McTemplateK0ppqqqqq_EtwWriteTransfer(
                              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                              (unsigned int)TCP_QUERY_NOTIFICATION_CHANNEL_STATUS_REQUEST,
                              (unsigned int)&LockHandle,
                              (_DWORD)SpinLock,
                              v57,
                              0,
                              v131,
                              0,
                              v132,
                              v15);
                          }
                        }
                        goto LABEL_25;
                      }
                      *v53 = 5;
                      goto LABEL_192;
                    }
LABEL_283:
                    v15 = -1073741811;
                    goto LABEL_25;
                  }
                }
              }
              goto LABEL_285;
            }
            if ( !a4 || (unsigned __int64)a5 < 0x10 )
              goto LABEL_285;
            if ( RtlCompareMemory(&ASSOCIATE_NAMERES_CONTEXT, a4, 0x10u) != 16 )
            {
              if ( (unsigned __int64)a5 >= 0x20 )
              {
                if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY_EX, a4, 0x10u) == 16 )
                {
                  if ( (unsigned __int64)a5 < 0x24 )
                    goto LABEL_285;
                  if ( *((_BYTE *)a4 + 32) )
                  {
                    memset(&v140, 0, sizeof(v140));
                    if ( dword_1402201D4 && (!TcpipTraceFiltersExist || (SpinLock[804] & 0x80u) != 0) )
                    {
                      LockHandle.LockQueue = 0;
                      if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 1) != 0 )
                      {
                        v75 = (unsigned __int8)PsGetProcessId(*((PEPROCESS *)SpinLock + 106));
                        v76 = *((_WORD *)SpinLock + 406);
                        v77 = (*((_DWORD *)SpinLock + 31) >> 1) & 1;
                        LockHandle.LockQueue.Lock = 0;
                        HandleInformation = *((_DWORD *)SpinLock + 28);
                        Object = (PVOID *)*((_QWORD *)SpinLock + 5);
                        LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
                        McTemplateK0ppqqqqq_EtwWriteTransfer(
                          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                          (unsigned int)TCP_CREATE_NOTIFICATION_CHANNEL_UNMARK_REQUEST,
                          (unsigned int)&LockHandle,
                          (_DWORD)SpinLock,
                          (char)Object,
                          HandleInformation,
                          v75,
                          v76,
                          v77,
                          0);
                      }
                    }
                    if ( *((_QWORD *)SpinLock + 5) && (*((_DWORD *)SpinLock + 31) & 2) == 0 )
                    {
                      KeInitializeEvent((PRKEVENT)&v140, NotificationEvent, 0);
                      *(_OWORD *)v141 = *((unsigned __int64 *)SpinLock + 5);
                      *(_OWORD *)&v141[16] = 0;
                      memset(v142, 0, sizeof(v142));
                      NetioNcmTlObjectRequest(v141, 2);
                      v78 = *(_QWORD *)&v142[1];
                      v79 = *(_BYTE *)(*(_QWORD *)&v142[1] + 32LL);
                      if ( (v79 & 1) == 0 || (v79 & 2) != 0 )
                      {
                        *(_BYTE *)(*(_QWORD *)&v142[1] + 32LL) = v79 | 1;
                        *(_QWORD *)(v78 + 40) = &v140;
                        if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
                          __fastfail(0xEu);
                        NetioInsertWorkQueue(TcpNotificationChannelTcbWorkQueue, v78);
                      }
                      else
                      {
                        *(_QWORD *)(*(_QWORD *)&v142[1] + 40LL) = &v140;
                        *(_BYTE *)(v78 + 32) = v79 | 1;
                      }
                      if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
                        __fastfail(0xEu);
                      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
                      KeWaitForSingleObject(&v140, Executive, 0, 0, 0);
                      KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
                      TcpDereferenceTcb(SpinLock);
                    }
                    v15 = 0;
                    goto LABEL_25;
                  }
                }
                else if ( RtlCompareMemory(&REAL_TIME_NOTIFICATION_CAPABILITY, a4, 0x10u) != 16 )
                {
                  goto LABEL_283;
                }
                v15 = TcpTcbProcessNotificationChannelSetupRequest((PKSPIN_LOCK)SpinLock);
                goto LABEL_25;
              }
LABEL_285:
              v15 = -1073741306;
              goto LABEL_25;
            }
            if ( (unsigned __int64)a5 < 0x18 )
              goto LABEL_285;
            LOBYTE(v58) = 0;
            KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
            v59 = (void *)*((_QWORD *)a4 + 2);
            v139 = 0;
            v15 = ObReferenceObjectByHandle(v59, 0, (POBJECT_TYPE)IoFileObjectType, 1, &v139, 0);
            v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
            if ( v15 < 0 )
            {
LABEL_235:
              if ( dword_1402201D4
                && (!TcpipTraceFiltersExist || (SpinLock[804] & 0x80u) != 0)
                && (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 0x20) != 0 )
              {
                LockHandle.LockQueue.Lock = 0;
                LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
                McTemplateK0pqpq_EtwWriteTransfer(
                  (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                  v60,
                  (unsigned int)&LockHandle,
                  (_DWORD)SpinLock,
                  1,
                  v58,
                  v15);
              }
              goto LABEL_25;
            }
            v61 = v139;
            if ( (unsigned __int8)NetioNrtIsTrackerDevice(*((_QWORD *)v139 + 1)) )
            {
              v58 = v61[3];
              v138 = v58;
              LOBYTE(v62) = 1;
              v15 = NetioNrtAssociateContext(SpinLock, v62, v58, SpinLock + 1112);
              if ( v15 >= 0 )
              {
                v63 = 0;
                v64 = *((_QWORD *)SpinLock + 113);
                LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)*((_QWORD *)SpinLock + 139);
                memset(v141, 0, 24);
                if ( !gAleDebugEnabled )
                {
                  v67 = 0;
LABEL_219:
                  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v64, (PKLOCK_QUEUE_HANDLE)v141);
                  while ( *(_DWORD *)(v64 + 8) )
                    ;
                  v68 = gAleDebugEnabled == 1;
                  *(_QWORD *)(v64 + 16) = KeGetCurrentThread();
                  if ( v68 && !v63 )
                    *(_QWORD *)(v64 + 24) = v67;
                  NetioNrtDereferenceRecord(*(_QWORD *)(v64 + 728));
                  Next = LockHandle.LockQueue.Next;
                  NetioNrtReferenceRecord(LockHandle.LockQueue.Next);
                  *(_QWORD *)(v64 + 728) = Next;
                  v68 = gAleDebugEnabled == 1;
                  v70 = 0;
                  *(_QWORD *)(v64 + 16) = 0;
                  if ( v68 )
                  {
                    v70 = *(void **)(v64 + 24);
                    *(_QWORD *)(v64 + 24) = 0;
                  }
                  KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)v141);
                  if ( gAleDebugEnabled == 1 && v70 )
                    ExFreePoolWithTag(v70, 0);
                  _InterlockedOr((volatile signed __int32 *)(v64 + 52), 0x800000u);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
                  {
                    WPP_SF_qq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      32,
                      WPP_f04769247d603da2e3d9e39cd4a85bd0_Traceguids,
                      Next,
                      v64);
                  }
                  LOBYTE(v58) = v138;
                  goto LABEL_234;
                }
                v65 = 27;
                Pool2 = (void *)ExAllocatePool2(64, 27, 1281715265);
                v66 = Pool2;
                if ( !Pool2 )
                {
                  v63 = -1073741801;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
                  {
                    WPP_SF_sd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      10,
                      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                      (unsigned int)"ExAllocatePool2",
                      23);
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
                  {
                    WPP_SF_sd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                      (unsigned int)"WfpPoolAllocNonPaged",
                      23);
LABEL_218:
                    v67 = Pool2;
                    goto LABEL_219;
                  }
                  v66 = Pool2;
                }
                if ( !v63 )
                {
                  v71 = 2147483646;
                  v72 = "WfpAleOnProxyHandleChanged";
                  do
                  {
                    if ( !v71 )
                      break;
                    if ( !*v72 )
                      break;
                    *v66++ = *v72++;
                    --v71;
                    --v65;
                  }
                  while ( v65 );
                  v73 = -2147024774;
                  if ( v65 )
                    v73 = 0;
                  v74 = v66 - 1;
                  if ( v65 )
                    v74 = v66;
                  v137 = v73;
                  *v74 = 0;
                  if ( !v65 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
                    {
                      WPP_SF_sd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        13,
                        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                        (unsigned int)"StringCchCopyA",
                        v73);
                      LOBYTE(v73) = v137;
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xCu) )
                    {
                      WPP_SF_sd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        15,
                        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                        (unsigned int)"WfpStringCchCopyA",
                        v73);
                    }
                  }
                }
                goto LABEL_218;
              }
            }
            else
            {
              v15 = -1073741816;
            }
LABEL_234:
            ObfDereferenceObject(v61);
            goto LABEL_235;
          }
          if ( a7 >= 4 )
          {
            *(_DWORD *)Pool2 = *((_DWORD *)SpinLock + 287);
            if ( a8 )
              *a8 = 4;
            goto LABEL_25;
          }
LABEL_309:
          v15 = -1073741789;
          goto LABEL_25;
        }
        if ( v15 < 0 || !v52 || (*((_DWORD *)SpinLock + 31) & 2) != 0 )
          goto LABEL_25;
        if ( SpinLock[786] )
        {
          v80 = *((_DWORD *)SpinLock + 44) * *((unsigned __int16 *)SpinLock + 391);
          if ( *((_DWORD *)SpinLock + 49) < v80 )
            *((_DWORD *)SpinLock + 49) = v80;
        }
        else if ( ((((int)(*((_DWORD *)SpinLock + 189) << 8) >> 8) - 5) & 0xFFFFFFFD) != 0 )
        {
          *((_WORD *)SpinLock + 391) = *((_WORD *)&TcpTemplates
                                       + 10 * ((__int64)(int)(*((_DWORD *)SpinLock + 189) << 8) >> 8)
                                       + 2);
        }
      }
      if ( dword_1402201D4
        && (!TcpipTraceFiltersExist || (SpinLock[804] & 0x80u) != 0)
        && (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
      {
        v93 = SpinLock[787];
        v94 = *((_WORD *)SpinLock + 391);
        v95 = *((_WORD *)SpinLock + 392);
        v96 = SpinLock[788];
        v97 = SpinLock[792] & 7;
        v98 = *((_WORD *)SpinLock + 389);
        v99 = (SpinLock[796] >> 1) & 1;
        v100 = (int)(*((_DWORD *)SpinLock + 189) << 8) >> 8;
        v101 = (SpinLock[797] >> 3) & 1;
        LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)SpinLock;
        LockHandle.LockQueue.Lock = 0;
        McTemplateK0pqqqqqqqqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_TEMPLATE_PARAMETERS,
          (unsigned int)&LockHandle,
          (_DWORD)SpinLock,
          v100,
          v98,
          v99,
          v94,
          v97,
          v96,
          v95,
          v93,
          1,
          v101);
      }
      goto LABEL_25;
  }
  if ( a3 + 1744830445 <= 1 )
    goto LABEL_172;
  if ( a3 == -1744830446 )
  {
LABEL_168:
    v52 = 0;
    v15 = -1073741637;
    v133 = 0;
    goto LABEL_173;
  }
  if ( a3 + 1744830442 <= 1 )
    goto LABEL_172;
  switch ( a3 )
  {
    case 0x98000018:
      goto LABEL_170;
    case 0xD8000027:
    case 0x980000E6:
    case 0x58000028u:
      goto LABEL_172;
    case 0x8800000B:
    case 0x8800001A:
      if ( !*((_QWORD *)SpinLock + 113) )
      {
        v15 = -1073741808;
        goto LABEL_25;
      }
      if ( _InterlockedIncrement64((volatile signed __int64 *)SpinLock + 1) <= 1 )
        __fastfail(0xEu);
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
      v35 = *((_QWORD *)SpinLock + 113);
      if ( a3 == -2013265909 )
      {
        v36 = *(_DWORD *)(v35 + 648);
        v37 = 0;
        memset(&v140, 0, sizeof(v140));
        if ( (v36 & 1) != 0 )
        {
          if ( (v36 & 0x200) != 0 )
          {
            v37 = 1;
          }
          else if ( (v36 & 0x400) != 0 )
          {
            v37 = 2;
          }
        }
        else if ( (v36 & 2) != 0 )
        {
          if ( (v36 & 0x200) != 0 )
          {
            v37 = 3;
          }
          else if ( (v36 & 0x400) != 0 )
          {
            v37 = 4;
          }
        }
        v136 = 0;
        memset(v141, 0, sizeof(v141));
        memset(v142, 0, 24);
        while ( 1 )
        {
          v38 = dword_140226F40;
          if ( (dword_140226F40 & 1) != 0 )
            break;
          if ( v38 == _InterlockedCompareExchange(&dword_140226F40, dword_140226F40 + 2, dword_140226F40) )
          {
            v39 = *(_QWORD *)(qword_140226F38 + 8);
            *(_QWORD *)&v141[24] = &v136;
            *(_QWORD *)&v141[16] = 0;
            memset((char *)v142 + 4, 0, 20);
            *(_QWORD *)v141 = a4;
            *(_QWORD *)&v141[8] = a5;
            LODWORD(v142[0]) = v37;
            v15 = (*(__int64 (__fastcall **)(_BYTE *))(v39 + 8))(v141);
            if ( _InterlockedExchangeAdd(&dword_140226F40, 0xFFFFFFFE) == 3 )
            {
              memset(&LockHandle, 0, sizeof(LockHandle));
              v40 = *(void **)(qword_140226F38 + 24);
              *(_QWORD *)(qword_140226F38 + 24) = 0;
              KeAcquireInStackQueuedSpinLock(&::SpinLock, &LockHandle);
              while ( dword_140226F50 )
                ;
              qword_140226F38 = 0;
              KeReleaseInStackQueuedSpinLock(&LockHandle);
              NmrClientDetachProviderComplete(v40);
            }
            if ( v15 < 0 )
              goto LABEL_167;
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v35 + 632), &v140);
            while ( *(_DWORD *)(v35 + 640) )
              ;
            if ( !*(_QWORD *)(v35 + 656) )
            {
              v41 = ExAllocatePool2(64, 24, 1699959109);
              *(_QWORD *)(v35 + 656) = v41;
              if ( !v41 )
              {
                KeReleaseInStackQueuedSpinLock(&v140);
                EQoSDeleteQoSFlow(v136);
                v15 = -1073741801;
                TcpDereferenceTcb(SpinLock);
                return (unsigned int)v15;
              }
              *(_OWORD *)v41 = 0;
              *(_QWORD *)(v41 + 16) = 0;
            }
            v42 = *(__int64 **)(v35 + 656);
            v43 = *v42;
            *v42 = v136;
            KeReleaseInStackQueuedSpinLock(&v140);
            if ( v43 )
              EQoSDereferenceQoSFlow(v43);
            v15 = 0;
            TcpDereferenceTcb(SpinLock);
            return (unsigned int)v15;
          }
        }
      }
      else
      {
        memset(&LockHandle, 0, sizeof(LockHandle));
        if ( !a5 )
        {
          v44 = 0;
LABEL_146:
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v35 + 632), &LockHandle);
          while ( *(_DWORD *)(v35 + 640) )
            ;
          v48 = *(__int64 **)(v35 + 656);
          v49 = 0;
          if ( v48 )
            v49 = *v48;
          if ( v44 )
          {
            if ( !v48 )
            {
              v51 = ExAllocatePool2(64, 24, 1699959109);
              v48 = (__int64 *)v51;
              if ( !v51 )
              {
                KeReleaseInStackQueuedSpinLock(&LockHandle);
                EQoSDereferenceQoSFlow(v44);
                v15 = -1073741801;
                TcpDereferenceTcb(SpinLock);
                return (unsigned int)v15;
              }
              *(_QWORD *)(v51 + 8) = 0;
              *(_QWORD *)(v51 + 16) = 0;
              *(_QWORD *)(v35 + 656) = v51;
            }
            *v48 = v44;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            if ( v49 )
              EQoSDereferenceQoSFlow(v49);
            v15 = 0;
            TcpDereferenceTcb(SpinLock);
          }
          else if ( v49 )
          {
            *v48 = 0;
            v50 = *(_QWORD **)(v35 + 656);
            if ( !*v50 && !v50[1] && ((*(_DWORD *)(v35 + 648) & 0x20) != 0 || !v50[2]) )
            {
              *(_QWORD *)(v35 + 656) = 0;
              ExFreePoolWithTag(v48, 0x65535145u);
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            EQoSDereferenceQoSFlow(v49);
            v15 = 0;
            TcpDereferenceTcb(SpinLock);
          }
          else
          {
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            v15 = 0;
            TcpDereferenceTcb(SpinLock);
          }
          return (unsigned int)v15;
        }
        memset(&v140, 0, sizeof(v140));
        while ( 1 )
        {
          v45 = dword_140226F40;
          if ( (dword_140226F40 & 1) != 0 )
            break;
          if ( v45 == _InterlockedCompareExchange(&dword_140226F40, dword_140226F40 + 2, dword_140226F40) )
          {
            v46 = *(_QWORD *)(qword_140226F38 + 8);
            v140.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a4;
            v140.LockQueue.Lock = a5;
            v15 = (*(__int64 (__fastcall **)(struct _KLOCK_QUEUE_HANDLE *))(v46 + 72))(&v140);
            if ( _InterlockedExchangeAdd(&dword_140226F40, 0xFFFFFFFE) == 3 )
            {
              memset(v141, 0, 24);
              v47 = *(void **)(qword_140226F38 + 24);
              *(_QWORD *)(qword_140226F38 + 24) = 0;
              KeAcquireInStackQueuedSpinLock(&::SpinLock, (PKLOCK_QUEUE_HANDLE)v141);
              while ( dword_140226F50 )
                ;
              qword_140226F38 = 0;
              KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)v141);
              NmrClientDetachProviderComplete(v47);
            }
            if ( v15 >= 0 )
            {
              v44 = *(_QWORD *)&v140.OldIrql;
              goto LABEL_146;
            }
            goto LABEL_167;
          }
        }
      }
      v15 = -1073741738;
LABEL_167:
      TcpDereferenceTcb(SpinLock);
      return (unsigned int)v15;
  }
  if ( a3 + 1744830264 <= 0x15 && (v30 = 3145757, _bittest(&v30, a3 + 1744830264)) || a3 == -671088439 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
    return (unsigned int)InetInspectSocketOption(SpinLock, *((_QWORD *)SpinLock + 113), a3, a4, a5, a6, a7, a8);
  }
  if ( a3 == 1476395213 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
    if ( *((_QWORD *)SpinLock + 113) && a7 >= 8 && a6 )
    {
      v15 = 0;
      *(_QWORD *)Pool2 = WfpAleQueryOrInsertEndpointHandle();
      if ( a8 )
        *a8 = 8;
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)v15;
  }
  if ( a3 == 1207959589 )
  {
    if ( a7 >= 8 )
    {
      v31 = *((_QWORD *)SpinLock + 115);
      if ( v31 )
      {
        v15 = -1073741637;
        v32 = *(_DWORD *)(*(_QWORD *)(v31 + 8) + 8LL);
        KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
        if ( ExAcquireRundownProtectionCacheAware(OlmRssHashRundown) )
        {
          v33 = 1024;
          if ( *((_WORD *)SpinLock + 409) != 23 )
            v33 = 256;
          v34 = 4096;
          if ( *((_WORD *)SpinLock + 409) != 23 )
            v34 = 512;
          v15 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, void *))TcpRssHash + 3))(
                  *((unsigned int *)SpinLock + 16),
                  v34,
                  *((unsigned int *)SpinLock + 22),
                  v33,
                  v32,
                  Pool2);
          ExReleaseRundownProtectionCacheAware(OlmRssHashRundown);
        }
        *a8 = (((__int64)v15 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
      }
      else
      {
        KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
        return (unsigned int)-1073741634;
      }
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
      return (unsigned int)-1073741306;
    }
    return (unsigned int)v15;
  }
LABEL_337:
  v102 = (PKSPIN_LOCK)(SpinLock + 912);
  if ( !*((_QWORD *)SpinLock + 114) )
  {
    v15 = InetInitializeSessionInformationAf(*((_QWORD *)SpinLock + 3), SpinLock + 912);
    if ( v15 < 0 )
      goto LABEL_25;
    v9 = Pool2;
    v102 = (PKSPIN_LOCK)(SpinLock + 912);
  }
  v103 = *v102;
  v104 = (__int64 *)*((_QWORD *)SpinLock + 4);
  v105 = *((_QWORD *)SpinLock + 3);
  v106 = *((_QWORD *)SpinLock + 113);
  HIDWORD(v144) = 0;
  v107 = *v104;
  *((_QWORD *)&v145 + 1) = 0;
  HIDWORD(v148) = 0;
  *(_QWORD *)&v150 = 0;
  v152 = 0;
  *(_QWORD *)&Src = *(_QWORD *)(v105 + 40);
  LODWORD(v136) = 0;
  LODWORD(v138) = 0;
  v137 = 0;
  v108 = *(_QWORD **)(v107 + 8);
  v151 = 0;
  *(_QWORD *)&v146 = v103;
  HIDWORD(v146) = a3;
  *(_QWORD *)&v144 = *v108;
  *(_QWORD *)&v147 = a4;
  *((_QWORD *)&v147 + 1) = (unsigned int)a5;
  DWORD2(v144) = *(_DWORD *)v144;
  *((_QWORD *)&v149 + 1) = 0;
  if ( !v107 )
    v108 = 0;
  *(_QWORD *)&v149 = 0;
  *(_QWORD *)&v145 = v108;
  DWORD2(v148) = a7;
  v109 = *(_QWORD *)(v105 + 48);
  DWORD2(v146) = (_DWORD)v139;
  *(_QWORD *)&v148 = v9;
  *((_QWORD *)&v150 + 1) = v106;
  *((_QWORD *)&Src + 1) = v104;
  v110 = *(__int64 (__fastcall **)(__int128 *))(v109 + 256);
  if ( (char *)v110 == (char *)IpNlpSetSessionInfo )
    v111 = IpNlpSetSessionInfo(&Src);
  else
    v111 = v110(&Src);
  v15 = v111;
  if ( v111 < 0 )
  {
    v112 = 0;
  }
  else
  {
    if ( a8 )
      *a8 = DWORD2(v148);
    v112 = BYTE1(v151);
    if ( BYTE1(v151) == 1 )
    {
      v113 = DWORD1(v151);
      v114 = v152;
      LODWORD(v138) = DWORD2(v151);
      v137 = WORD6(v151);
LABEL_354:
      if ( _bittest((const signed __int32 *)SpinLock + 31, 9u) )
        v113 = v138;
      TcpRecomputeMss(SpinLock, v113, v114);
      *((_WORD *)SpinLock + 408) = v137;
      *((_DWORD *)SpinLock + 202) = *((_DWORD *)SpinLock + 202) & 0xFFFF7FFF | (v114 != 0 ? 0x8000 : 0);
      goto LABEL_357;
    }
  }
  if ( v15 < 0 )
    goto LABEL_25;
  if ( v112 == 1 )
  {
    v113 = v136;
    v114 = v136;
    goto LABEL_354;
  }
LABEL_357:
  v115 = (unsigned int)v139;
  if ( (!(_DWORD)v139 || (_DWORD)v139 == 41) && a3 == 71 )
  {
    v116 = SpinLock[795];
    SpinLock[795] = v116 | 4;
    v117 = *(_BYTE *)a4 < 2u;
    SpinLock[795] = (2 * v117) | v116 & 0xF9 | 4;
    if ( v117 != ((v116 & 2) != 0) )
    {
      if ( v117 )
      {
        *(_QWORD *)&v151 = 0;
        *(_QWORD *)&v141[24] = 0;
        *(_QWORD *)v141 = *((_QWORD *)SpinLock + 4);
        *(_QWORD *)&v141[16] = &Src;
        *(_QWORD *)&v141[8] = *((_QWORD *)SpinLock + 114);
        v118 = *((_QWORD *)SpinLock + 3);
        Src = 0;
        v144 = 0;
        v145 = 0;
        v146 = 0;
        v147 = 0;
        v148 = 0;
        v149 = 0;
        v150 = 0;
        v119 = *(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)(v118 + 48) + 80LL);
        if ( (char *)v119 == (char *)IpNlpQueryPathInformation )
          PathInformation = IpNlpQueryPathInformation(v141);
        else
          PathInformation = v119(v141);
        if ( PathInformation >= 0 )
          TcpRefreshMssForTcb(SpinLock, DWORD1(v144));
        if ( (_QWORD)v150 )
          InetDereferenceNextHopAf(*((_QWORD *)SpinLock + 3));
      }
      else
      {
        TcpRefreshMssForTcb(SpinLock, 0);
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, v13);
  if ( (!v115 || v115 == 41) && a3 == 14 )
  {
    v121 = *((_QWORD *)SpinLock + 3);
    *(_QWORD *)&v151 = 0;
    *(_QWORD *)&v141[16] = 0;
    v134 = 0;
    Src = 0;
    *(_QWORD *)&v142[1] = 1;
    v144 = 0;
    *(_QWORD *)&v142[0] = v115 | 0xE00000000LL;
    v145 = 0;
    v146 = 0;
    v147 = 0;
    v148 = 0;
    v149 = 0;
    v150 = 0;
    *(_QWORD *)v141 = *(_QWORD *)(v121 + 40);
    *(_QWORD *)&v141[24] = *((_QWORD *)SpinLock + 114);
    *(_QWORD *)&v141[8] = **(_QWORD **)(**((_QWORD **)SpinLock + 4) + 8LL);
    *((_QWORD *)&v142[0] + 1) = &v134;
    v122 = *(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)(v121 + 48) + 248LL);
    if ( (char *)v122 == (char *)IpNlpQuerySessionInfo )
      SessionInfo = IpNlpQuerySessionInfo(v141);
    else
      SessionInfo = v122(v141);
    if ( SessionInfo < 0 )
      v134 = 0;
    *(_QWORD *)v141 = *((_QWORD *)SpinLock + 4);
    *(_QWORD *)&v141[16] = &Src;
    *(_QWORD *)&v141[8] = *((_QWORD *)SpinLock + 114);
    v124 = *((_QWORD *)SpinLock + 3);
    *(_QWORD *)&v141[24] = 0;
    v125 = *(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)(v124 + 48) + 80LL);
    if ( (char *)v125 == (char *)IpNlpQueryPathInformation )
      v126 = IpNlpQueryPathInformation(v141);
    else
      v126 = v125(v141);
    if ( v126 >= 0 )
    {
      if ( !BYTE9(v150) && v134 )
      {
        v127 = 0;
LABEL_384:
        v128 = v150;
        *((_DWORD *)SpinLock + 202) = v127 | *((_DWORD *)SpinLock + 202) & 0xFFFFBFFF;
        if ( v128 )
          InetDereferenceNextHopAf(*((_QWORD *)SpinLock + 3));
        return (unsigned int)v15;
      }
    }
    else
    {
      BYTE9(v150) = 1;
    }
    v127 = 0x4000;
    goto LABEL_384;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140002d40  push    rbp
0x140002d42  push    rbx
0x140002d43  push    rsi
0x140002d44  push    rdi
0x140002d45  push    r12
0x140002d47  push    r13
0x140002d49  push    r14
0x140002d4b  push    r15
0x140002d4d  lea     rbp, [rsp-0C8h]
0x140002d55  sub     rsp, 1C8h
0x140002d5c  mov     rax, cs:__security_cookie
0x140002d63  xor     rax, rsp
0x140002d66  mov     [rbp+100h+var_48], rax
0x140002d6d  cmp     cs:dword_1402201D4, 0
0x140002d74  mov     r15, r9
0x140002d77  mov     r14, [rbp+100h+arg_28]
0x140002d7e  mov     edi, r8d
0x140002d81  mov     rsi, [rbp+100h+arg_38]
0x140002d88  mov     rbx, rcx
0x140002d8b  mov     r12, [rbp+100h+arg_20]
0x140002d92  mov     [rsp+200h+var_188], r14
0x140002d97  mov     dword ptr [rbp+100h+var_168], edx
0x140002d9a  mov     [rsp+200h+var_190], 0
0x140002d9f  jz      short loc_140002DF6
0x140002da1  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x140002da8  jz      short loc_140002DF6
0x140002daa  mov     [rsp+200h+var_1C8], r9
0x140002daf  xor     eax, eax
0x140002db1  mov     [rbp+100h+LockHandle.LockQueue.Next], rcx
0x140002db8  test    r9, r9
0x140002dbb  mov     ecx, r12d
0x140002dbe  mov     [rbp+100h+LockHandle.LockQueue.Lock], 0
0x140002dc9  cmovz   ecx, eax
0x140002dcc  mov     r9, rbx
0x140002dcf  mov     dword ptr [rsp+200h+var_1D0], ecx
0x140002dd3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140002dda  mov     dword ptr [rsp+200h+HandleInformation], r8d
0x140002ddf  lea     r8, [rbp+100h+LockHandle]
0x140002de6  mov     dword ptr [rsp+200h+Object], edx
0x140002dea  lea     rdx, TCPIP_SETSOCKOPT
0x140002df1  call    McTemplateK0pqqqbr3_EtwWriteTransfer
0x140002df6  mov     rcx, rbx; SpinLock
0x140002df9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002e00  nop     dword ptr [rax+rax+00h]
0x140002e05  movzx   r13d, al
0x140002e09  mov     eax, dword ptr [rbp+100h+var_168]
0x140002e0c  cmp     eax, 6
0x140002e0f  jnz     loc_140002FA2
0x140002e15  cmp     cs:dword_1402201D4, 0
0x140002e1c  jz      short loc_140002E76
0x140002e1e  cmp     cs:TcpipTraceFiltersExist, 0
0x140002e25  jz      short loc_140002E32
0x140002e27  movzx   ecx, byte ptr [rbx+324h]
0x140002e2e  test    cl, cl
0x140002e30  jns     short loc_140002E76
0x140002e32  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 20h
0x140002e39  jz      short loc_140002E76
0x140002e3b  mov     dword ptr [rsp+200h+HandleInformation], 0
0x140002e43  lea     r8, [rbp+100h+LockHandle]
0x140002e4a  mov     r9, rbx
0x140002e4d  mov     dword ptr [rsp+200h+Object], edi
0x140002e51  lea     rdx, TCP_SET_TCP_OPTION
0x140002e58  mov     [rbp+100h+LockHandle.LockQueue.Lock], 0
0x140002e63  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140002e6a  mov     [rbp+100h+LockHandle.LockQueue.Next], rbx
0x140002e71  call    McTemplateK0pqq_EtwWriteTransfer
0x140002e76  lea     eax, [rdi-2]
0x140002e79  test    eax, 0FFFFFFFAh
0x140002e7e  jnz     short loc_140002E9A
0x140002e80  cmp     edi, 3
0x140002e83  jz      short loc_140002E9A
0x140002e85  mov     rcx, rbx
0x140002e88  call    TcpHasUrgentTcbInput
0x140002e8d  test    al, al
0x140002e8f  jnz     short loc_140002EA9
0x140002e91  test    dword ptr [rbx+78h], 800h
0x140002e98  jnz     short loc_140002EA9
0x140002e9a  cmp     edi, 0Fh
0x140002e9d  ja      short loc_140002EB9
0x140002e9f  mov     eax, 9400h
0x140002ea4  bt      eax, edi
0x140002ea7  jnb     short loc_140002EB9
0x140002ea9  mov     r14d, 0C0000184h
0x140002eaf  mov     [rsp+200h+var_190], 0
0x140002eb4  jmp     loc_140002F52
0x140002eb9  lea     rax, [rsp+200h+var_190]
0x140002ebe  mov     r9, r12
0x140002ec1  lea     rcx, [rbx+2F8h]
0x140002ec8  mov     [rsp+200h+Object], rax
0x140002ecd  mov     r8, r15
0x140002ed0  mov     edx, edi
0x140002ed2  call    TcpSetTcpLevelOption
0x140002ed7  mov     r14d, eax
0x140002eda  test    eax, eax
0x140002edc  js      short loc_140002F52
0x140002ede  cmp     [rsp+200h+var_190], 0
0x140002ee3  jz      short loc_140002F52
0x140002ee5  mov     ecx, [rbx+7Ch]
0x140002ee8  test    cl, 2
0x140002eeb  jnz     short loc_140002F52
0x140002eed  cmp     edi, 3
0x140002ef0  jnz     loc_140002F8C
0x140002ef6  test    byte ptr [rbx+31Ah], 4
0x140002efd  jz      short loc_140002F6E
0x140002eff  mov     byte ptr [rbx+2F2h], 0
0x140002f06  xor     edx, edx
0x140002f08  mov     edi, gs:1A4h
0x140002f10  mov     ecx, edi
0x140002f12  call    TcpQueryMicrosecondCount
0x140002f17  mov     r8d, [rbx+2FCh]
0x140002f1e  mov     r9, rax
0x140002f21  mov     rax, 624DD2F1A9FBE77h
0x140002f2b  mov     rcx, rbx
0x140002f2e  mul     r9
0x140002f31  mov     eax, 4
0x140002f36  sub     r9, rdx
0x140002f39  mov     dword ptr [rsp+200h+HandleInformation], eax
0x140002f3d  shr     r9, 1
0x140002f40  add     r9, rdx
0x140002f43  mov     dword ptr [rsp+200h+Object], edi
0x140002f47  shr     r9, 9
0x140002f4b  mov     edx, eax
0x140002f4d  call    TcpStartTimerTcbInternal
0x140002f52  movzx   edx, r13b; NewIrql
0x140002f56  mov     rcx, rbx; SpinLock
0x140002f59  call    cs:__imp_KeReleaseSpinLock
0x140002f60  nop     dword ptr [rax+rax+00h]
0x140002f65  mov     eax, r14d
0x140002f68  jmp     loc_140004B8E
0x140002f6e  mov     eax, [rbx+328h]
0x140002f74  test    al, 40h
0x140002f76  jnz     short loc_140002F52
0x140002f78  mov     eax, 4
0x140002f7d  mov     rcx, rbx
0x140002f80  mov     r8d, eax
0x140002f83  mov     edx, eax
0x140002f85  call    TcpStopTimerTcbInternal
0x140002f8a  jmp     short loc_140002F52
0x140002f8c  cmp     edi, 5
0x140002f8f  jz      short loc_140002F96
0x140002f91  cmp     edi, 0Eh
0x140002f94  jnz     short loc_140002F52
0x140002f96  mov     dword ptr [rbx+2ECh], 0
0x140002fa0  jmp     short loc_140002F52
0x140002fa2  mov     edx, 0FFFFh
0x140002fa7  cmp     eax, edx
0x140002fa9  jnz     loc_1400031E5
0x140002faf  lea     eax, [rdi-3005h]
0x140002fb5  test    eax, 0FFFFFFFDh
0x140002fba  jz      loc_140004797
0x140002fc0  cmp     cs:dword_1402201D4, 0
0x140002fc7  jz      short loc_140003026
0x140002fc9  cmp     cs:TcpipTraceFiltersExist, 0
0x140002fd0  jz      short loc_140002FDD
0x140002fd2  movzx   eax, byte ptr [rbx+324h]
0x140002fd9  test    al, al
0x140002fdb  jns     short loc_140003026
0x140002fdd  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 20h
0x140002fe4  jz      short loc_140003026
0x140002fe6  mov     dword ptr [rsp+200h+HandleInformation], edi
0x140002fea  lea     r8, [rbp+100h+LockHandle]
0x140002ff1  mov     r9, rbx
0x140002ff4  mov     dword ptr [rsp+200h+Object], 0
0x140002ffc  lea     rdx, TCP_SET_TCP_SO_OPTION
0x140003003  mov     [rbp+100h+LockHandle.LockQueue.Lock], 0
0x14000300e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140003015  mov     [rbp+100h+LockHandle.LockQueue.Next], rbx
0x14000301c  call    McTemplateK0pqq_EtwWriteTransfer
0x140003021  mov     edx, 0FFFFh
0x140003026  mov     r8d, 100h
0x14000302c  cmp     edi, r8d
0x14000302f  jnz     loc_140003156
0x140003035  mov     rcx, rbx
0x140003038  call    TcpHasUrgentTcbInput
0x14000303d  test    al, al
0x14000303f  jnz     loc_140002EA9
0x140003045  test    dword ptr [rbx+78h], 800h
0x14000304c  jnz     loc_140002EA9
0x140003052  lea     rsi, [rbx+2F8h]
0x140003059  mov     edx, edi
0x14000305b  lea     rax, [rsp+200h+var_190]
0x140003060  mov     r9, r12
0x140003063  mov     r8, r15
0x140003066  mov     [rsp+200h+Object], rax
0x14000306b  mov     rcx, rsi
0x14000306e  call    TcpSetSoLevelOption
0x140003073  mov     r14d, eax
0x140003076  test    eax, eax
0x140003078  js      loc_140002F52
0x14000307e  cmp     [rsp+200h+var_190], 0
0x140003083  jz      loc_140002F52
0x140003089  mov     eax, [rbx+7Ch]
0x14000308c  test    al, 2
0x14000308e  jnz     loc_140002F52
0x140003094  cmp     edi, 8
0x140003097  jz      loc_140002EF6
0x14000309d  cmp     edi, 1002h
0x1400030a3  jnz     loc_140002F52
0x1400030a9  mov     ecx, 400h
0x1400030ae  xor     edx, edx
0x1400030b0  or      [rbx+78h], ecx
0x1400030b3  mov     r15d, gs:1A4h
0x1400030bc  mov     ecx, r15d
0x1400030bf  call    TcpQueryMicrosecondCount
0x1400030c4  movzx   ecx, byte ptr [rbx+321h]
0x1400030cb  mov     rdi, rax
0x1400030ce  mov     eax, [rsi]
0x1400030d0  mov     edx, 0FFFFh
0x1400030d5  shl     edx, cl
0x1400030d7  cmp     eax, edx
0x1400030d9  cmovnb  eax, edx
0x1400030dc  mov     [rsi], eax
0x1400030de  mov     esi, 1
0x1400030e3  shl     esi, cl
0x1400030e5  cmp     eax, esi
0x1400030e7  cmova   esi, eax
0x1400030ea  cmp     dword ptr [rbx+70h], 4
0x1400030ee  mov     [rbx+2F8h], esi
0x1400030f4  jl      loc_140002F52
0x1400030fa  xor     r8d, r8d
0x1400030fd  mov     edx, r15d
0x140003100  mov     rcx, rbx
0x140003103  call    TcpTryToIncreaseTcbRcvWnd
0x140003108  test    al, al
0x14000310a  jz      loc_140002F52
0x140003110  mov     rcx, rbx; SpinLock
0x140003113  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000311a  nop     dword ptr [rax+rax+00h]
0x14000311f  mov     rax, 624DD2F1A9FBE77h
0x140003129  mov     ecx, r15d
0x14000312c  mul     rdi
0x14000312f  sub     rdi, rdx
0x140003132  shr     rdi, 1
0x140003135  add     rdx, rdi
0x140003138  shr     rdx, 9
0x14000313c  call    TcpFlushDelay
0x140003141  movzx   ecx, r13b; NewIrql
0x140003145  call    cs:__imp_KeLowerIrql
0x14000314c  nop     dword ptr [rax+rax+00h]
0x140003151  jmp     loc_140002F65
0x140003156  cmp     edi, 1002h
0x14000315c  jnz     loc_140003052
0x140003162  cmp     r12, 4
0x140003166  jnb     short loc_140003178
0x140003168  mov     r14d, 0C0000206h
0x14000316e  mov     [rsp+200h+var_190], 0
0x140003173  jmp     loc_140002F52
0x140003178  mov     r9d, [rbx+70h]
0x14000317c  mov     r8d, [r15]
0x14000317f  cmp     r9d, 2
0x140003183  jl      short loc_1400031B3
0x140003185  movzx   ecx, byte ptr [rbx+321h]
0x14000318c  mov     eax, edx
0x14000318e  shl     eax, cl
0x140003190  cmp     r8d, eax
0x140003193  jbe     short loc_1400031B3
0x140003195  movzx   edx, r13b; NewIrql
0x140003199  mov     rcx, rbx; SpinLock
0x14000319c  call    cs:__imp_KeReleaseSpinLock
0x1400031a3  nop     dword ptr [rax+rax+00h]
0x1400031a8  mov     r14d, 0C0000184h
0x1400031ae  jmp     loc_140002F65
0x1400031b3  lea     rsi, [rbx+2F8h]
0x1400031ba  cmp     r8d, [rsi]
0x1400031bd  jnb     short loc_1400031DB
0x1400031bf  cmp     byte ptr [rbx+31Bh], 0
0x1400031c6  jl      short loc_1400031DB
0x1400031c8  cmp     r9d, 4
0x1400031cc  jl      short loc_1400031DB
0x1400031ce  xor     r14d, r14d
0x1400031d1  mov     [rsp+200h+var_190], r14b
0x1400031d6  jmp     loc_140002F52
0x1400031db  mov     edx, 1002h
0x1400031e0  jmp     loc_14000305B
0x1400031e5  cmp     eax, 0FFFCh
0x1400031ea  jnz     loc_14000478D
0x1400031f0  cmp     edi, 98000004h
0x1400031f6  jz      loc_140003965
0x1400031fc  cmp     edi, 9800012Ch
0x140003202  jz      loc_140003965
0x140003208  cmp     edi, 98000010h
0x14000320e  jz      loc_140003957
0x140003214  cmp     edi, 98000011h
0x14000321a  jz      loc_14000396D
0x140003220  lea     eax, [rdi+67FFFFEDh]
0x140003226  cmp     eax, 1
0x140003229  jbe     loc_140003981
0x14000322f  cmp     edi, 98000012h
0x140003235  jz      loc_140003957
0x14000323b  lea     eax, [rdi+67FFFFEAh]
0x140003241  cmp     eax, 1
0x140003244  jbe     loc_140003981
0x14000324a  cmp     edi, 98000018h
0x140003250  jz      loc_14000396D
0x140003256  cmp     edi, 0D8000027h
0x14000325c  jz      loc_140003981
0x140003262  cmp     edi, 980000E6h
0x140003268  jz      loc_140003981
0x14000326e  cmp     edi, 58000028h
0x140003274  jz      loc_140003981
  ... truncated ...
```
