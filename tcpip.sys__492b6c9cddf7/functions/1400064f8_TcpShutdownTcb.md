# TcpShutdownTcb

- ea: `0x1400064f8`
- end: `0x140007263`
- name: `TcpShutdownTcb`
- size: `3435`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `10`
- callee_count: `39`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140005740`
- `0x140005bb0`
- `0x140006470`
- `0x14000726c`
- `0x14001e4c0`
- `0x1400b8818`
- `0x1400b8d50`
- `0x140118920`
- `0x14012b87c`
- `0x14012c5b0`

## callees

- `0x1400052c8`
- `0x140005710`
- `0x1400058f0`
- `0x1400064f8`
- `0x140008da0`
- `0x140009470`
- `0x14000a7c0`
- `0x14001b350`
- `0x1400222b0`
- `0x14002f200`
- `0x14003880c`
- `0x14003a0c0`
- `0x1400525d0`
- `0x14008ef00`
- `0x1400b8080`
- `0x1400b8130`
- `0x1400b84c0`
- `0x1400b86c0`
- `0x1400d404c`
- `0x1400e8980`
- `0x1400efbc0`
- `0x1400f0f88`
- `0x1400f1670`
- `0x1400f3020`
- `0x1400f4714`
- `0x1401015b8`
- `0x140108f68`
- `0x140109468`
- `0x14010eea4`
- `0x1401167a8`
- `0x140118920`
- `0x1401281e0`
- `0x14014cec8`
- `0x14015164c`
- `0x14015f8d4`
- `0x140160628`
- `0x14018b0f0`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140006f65`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140006f65`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006f13`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006f13`
- `ntoskrnl!KeBugCheckEx` at `0x140006c46`
- `ntoskrnl!KeBugCheckEx` at `0x140006c46`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140006a59`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140006b62`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140006a59`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140006b62`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400065b3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140006e63`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400070aa`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400070e5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400065b3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140006e63`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400070aa`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400070e5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400065de`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000705c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400065de`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000705c`
- `ntoskrnl!PsGetProcessStartKey` at `0x14000665d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14000679e`
- `ntoskrnl!PsGetProcessStartKey` at `0x14000665d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14000679e`
- `ntoskrnl!KeSetEvent` at `0x1400071c9`
- `ntoskrnl!KeSetEvent` at `0x1400071c9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006cfb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006d44`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006cfb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140006d44`
- `ntoskrnl!PsGetProcessId` at `0x14000663f`
- `ntoskrnl!PsGetProcessId` at `0x14000677c`
- `ntoskrnl!PsGetProcessId` at `0x14000663f`
- `ntoskrnl!PsGetProcessId` at `0x14000677c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070d6`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140006c24`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140006c24`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140006c65`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140006c65`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14000706d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x140007087`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14000706d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x140007087`

## pseudocode

```c
char __fastcall TcpShutdownTcb(PKSPIN_LOCK SpinLock, int a2, int a3, int a4)
{
  unsigned int LockArray_high; // r14d
  int v6; // esi
  int v8; // eax
  int v9; // eax
  int v10; // edx
  KSPIN_LOCK v11; // r8
  ADDRESS_FAMILY v12; // di
  unsigned __int8 ProcessId; // al
  KSPIN_LOCK v14; // rcx
  char v15; // bl
  char ProcessStartKey; // al
  PKSPIN_LOCK v17; // r12
  ADDRESS_FAMILY v18; // cx
  UCHAR v19; // al
  _QWORD *v20; // r8
  __int64 v21; // rdx
  int v22; // r14d
  __int64 v23; // r10
  __int64 v24; // rax
  KSPIN_LOCK v25; // r9
  __int64 v26; // rbx
  KSPIN_LOCK v27; // r10
  unsigned int v28; // edx
  __int64 v29; // rcx
  unsigned __int8 v30; // al
  KSPIN_LOCK v31; // rcx
  char v32; // bl
  char v33; // al
  __int64 v34; // r9
  ADDRESS_FAMILY *v35; // r10
  int v36; // ecx
  ADDRESS_FAMILY v37; // bx
  ADDRESS_FAMILY v38; // si
  bool v39; // r12
  __int64 v40; // rax
  int v41; // edi
  KSPIN_LOCK v42; // r14
  __int64 v43; // r15
  UCHAR v44; // si
  UCHAR v45; // al
  __int64 v46; // rdx
  UCHAR v47; // bl
  __int64 v48; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  __int16 v51; // cx
  __int16 v52; // ax
  unsigned int v53; // ebx
  KSPIN_LOCK v54; // rax
  void (__fastcall *v55)(KSPIN_LOCK, _QWORD, _QWORD, __int128 *); // rax
  KSPIN_LOCK v56; // rcx
  signed int v57; // r12d
  int v58; // eax
  __int64 v59; // rdx
  __int64 BindingHandleByTcb; // rax
  __int64 v61; // rdx
  __int64 v62; // rbx
  __int64 v63; // r8
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  KSPIN_LOCK v67; // rax
  ADDRESS_FAMILY *v68; // r10
  int v69; // ecx
  bool v70; // r15
  __int64 v71; // r14
  int v72; // esi
  UCHAR v73; // al
  __int64 v74; // rdx
  int v75; // edi
  KSPIN_LOCK v76; // rcx
  __int16 v77; // bx
  __int64 v78; // rax
  int v79; // edx
  int v80; // r8d
  KSPIN_LOCK v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  PKSPIN_LOCK v86; // rdi
  KSPIN_LOCK v87; // rbx
  _QWORD *v88; // rsi
  _QWORD *v89; // rbx
  KSPIN_LOCK *v90; // rcx
  __int64 v91; // rdx
  int v92; // r8d
  int v93; // eax
  PKSPIN_LOCK v94; // rcx
  KSPIN_LOCK v95; // rcx
  char v96; // dl
  int BugCheckParameter4; // [rsp+20h] [rbp-99h]
  int BugCheckParameter4a; // [rsp+20h] [rbp-99h]
  int v100; // [rsp+28h] [rbp-91h]
  __int16 v101; // [rsp+28h] [rbp-91h]
  char v102; // [rsp+28h] [rbp-91h]
  char v103; // [rsp+28h] [rbp-91h]
  char v104; // [rsp+40h] [rbp-79h]
  char v105; // [rsp+60h] [rbp-59h]
  unsigned int v107; // [rsp+68h] [rbp-51h]
  __int64 v109; // [rsp+70h] [rbp-49h] BYREF
  int v110; // [rsp+78h] [rbp-41h]
  unsigned __int64 v111; // [rsp+80h] [rbp-39h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-31h] BYREF
  __int128 v113; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v114; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v115; // [rsp+C0h] [rbp+7h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v107 = LockArray_high;
  v6 = a2;
  v110 = a3;
  v105 = 0;
  LODWORD(v111) = 0;
  if ( (Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_featureState & 0x10) != 0 )
    v8 = Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_featureState & 1;
  else
    v8 = Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_IsEnabledDeviceUsageNoInline();
  if ( !v8 )
    v111 = TcpQueryMicrosecondCount(LockArray_high, 0) / 0x3E8uLL;
  v9 = *((_DWORD *)SpinLock + 30);
  if ( (v9 & 0x300000) == 0 )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.SectorSize);
    if ( (*((_DWORD *)SpinLock + 31) & 1) != 0 )
      ++*(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock;
    else
      ++WPP_MAIN_CB.SecurityDescriptor;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.SectorSize);
    v11 = SpinLock[4];
    v12 = 23;
    if ( !v11 )
    {
      if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
      {
        v113 = 0;
        if ( (BYTE1(WPP_MAIN_CB.Reserved) & 0x20) != 0 )
        {
          ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)SpinLock[106]);
          v14 = SpinLock[106];
          v15 = ProcessId;
          v113 = (unsigned __int64)SpinLock;
          ProcessStartKey = PsGetProcessStartKey(v14);
          McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_SHUTDOWN_TCB_V1,
            (unsigned int)&v113,
            0,
            0,
            0,
            0,
            v6,
            v15,
            0,
            (char)SpinLock,
            ProcessStartKey);
        }
      }
      goto LABEL_63;
    }
    v17 = SpinLock + 3;
    *(_QWORD *)&v114 = SpinLock + 3;
    if ( (BYTE1(WPP_MAIN_CB.Reserved) & 0x20) == 0 )
    {
      LOBYTE(v22) = 0;
      v29 = 0;
      v26 = 0;
      goto LABEL_26;
    }
    v18 = 23;
    if ( (SpinLock[15] & 8) == 0 )
      v18 = *(_WORD *)(*v17 + 24);
    v19 = SOCKADDR_SIZE(v18);
    LOBYTE(v21) = (_DWORD)v21 != 0;
    v22 = v19;
    v24 = InetFormatLocalSockAddrAtDispatchLevel(v23, v21, *v20, *((unsigned __int16 *)SpinLock + 58));
    v25 = SpinLock[4];
    v26 = v24;
    v27 = *v17;
    v28 = *((_DWORD *)SpinLock + 30);
    v101 = *((_WORD *)SpinLock + 59);
    *(_QWORD *)&v113 = v24;
    v28 >>= 3;
    LOBYTE(v28) = v28 & 1;
    v29 = InetFormatSockAddrAtDispatchLevel(
            *(unsigned __int16 *)(v27 + 24),
            v28,
            1,
            *(_QWORD *)(v25 + 16),
            *(_DWORD *)(v25 + 8),
            v101);
    v109 = v29;
    if ( dword_1402201D4 )
    {
      if ( TcpipTraceFiltersExist && *((char *)SpinLock + 804) >= 0 )
      {
LABEL_26:
        if ( a4 && v6 < 0 )
        {
          if ( (_BYTE)v22 )
          {
            v34 = v29;
            LOBYTE(v11) = v22;
            LOBYTE(v29) = v22;
            TcpRecentFailureTrace(v29, v26, v11, v34, SpinLock[106], v6, *((_DWORD *)SpinLock + 28), a4);
          }
          else
          {
            v35 = (ADDRESS_FAMILY *)(*v17 + 24);
            v36 = SpinLock[15] & 8;
            if ( v36 )
            {
              v37 = 23;
              v38 = 23;
            }
            else
            {
              v37 = *v35;
              v38 = *v35;
            }
            v39 = v36 != 0;
            LOBYTE(v10) = v36 != 0;
            v40 = InetFormatSockAddrAtDispatchLevel(
                    *v35,
                    v10,
                    1,
                    *(_QWORD *)(SpinLock[4] + 16),
                    *(_DWORD *)(SpinLock[4] + 8),
                    *((_WORD *)SpinLock + 59));
            v41 = *((_DWORD *)SpinLock + 28);
            v42 = SpinLock[106];
            v43 = v40;
            v44 = SOCKADDR_SIZE(v38);
            v45 = SOCKADDR_SIZE(v37);
            LOBYTE(v46) = v39;
            v17 = (PKSPIN_LOCK)v114;
            v47 = v45;
            v48 = InetFormatLocalSockAddrAtDispatchLevel(
                    *(_QWORD *)v114,
                    v46,
                    *(_QWORD *)SpinLock[4],
                    *((unsigned __int16 *)SpinLock + 58));
            LOBYTE(v49) = v44;
            LOBYTE(v50) = v47;
            TcpRecentFailureTrace(v50, v48, v49, v43, v42, a2, v41, a4);
            v6 = a2;
          }
        }
        if ( (*((_BYTE *)SpinLock + 797) & 0x20) == 0 )
          goto LABEL_62;
        if ( (SpinLock[15] & 1) == 0 )
          goto LABEL_62;
        v51 = *((_WORD *)SpinLock + 64);
        v52 = v51 & 0x1F;
        if ( (v51 & 0x1F) == 0 || v52 == 19 )
          goto LABEL_62;
        v109 = 0;
        v114 = 0;
        v115 = 0;
        switch ( v52 )
        {
          case 21:
            DWORD2(v115) = 1;
            break;
          case 22:
            v10 = 7;
            DWORD2(v115) = 7;
            break;
          case 16:
            DWORD2(v115) = 2;
            break;
          case 18:
            DWORD2(v115) = 3;
            break;
          default:
            if ( v6 == -1073741643 )
            {
              DWORD2(v115) = 4;
            }
            else if ( SpinLock[64] )
            {
              if ( v6 != -1073741247 || !SpinLock[57] )
              {
                v53 = v52 != 7 ? 0xC000022D : 0;
LABEL_55:
                if ( dword_1402201D4 )
                {
                  v113 = 0;
                  if ( *((char *)&WPP_MAIN_CB.Reserved + 11) < 0 )
                  {
                    v102 = SpinLock[64];
                    *(_QWORD *)&v113 = SpinLock;
                    McTemplateK0pqxqq_EtwWriteTransfer(
                      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                      v10,
                      (unsigned int)&v113,
                      (_DWORD)SpinLock,
                      v51 & 0x1F,
                      v102,
                      v6,
                      v53);
                  }
                }
                *((_QWORD *)&v114 + 1) = SpinLock[64];
                *(_QWORD *)&v115 = __PAIR64__(SpinLock[16] & 0x1F, v6);
                KeQuerySystemTimePrecise(&v109);
                v54 = *v17;
                *(_QWORD *)&v114 = (__int64)(v109 - SpinLock[109]) / 10000;
                v55 = *(void (__fastcall **)(KSPIN_LOCK, _QWORD, _QWORD, __int128 *))(*(_QWORD *)(v54 + 48) + 304LL);
                if ( v55 )
                {
                  v56 = SpinLock[4];
                  if ( (char *)v55 == (char *)IpNlpFeatureFallbackUpdate )
                    IpNlpFeatureFallbackUpdate(v56, 0, v53, &v114);
                  else
                    v55(v56, 0, v53, &v114);
                }
LABEL_62:
                InetSetPathInfoRttAf(*v17, SpinLock[4], *((_DWORD *)SpinLock + 178) >> 3);
                LockArray_high = v107;
                v12 = 23;
LABEL_63:
                *((_DWORD *)SpinLock + 31) |= 2u;
                v57 = *((_DWORD *)SpinLock + 28);
                if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
                {
                  v113 = 0;
                  if ( (BYTE1(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
                  {
                    v103 = *((_DWORD *)SpinLock + 35);
                    *(_QWORD *)&v113 = SpinLock;
                    McTemplateK0qqqp_EtwWriteTransfer(
                      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                      v10,
                      (unsigned int)&v113,
                      v57,
                      0,
                      v103,
                      (char)SpinLock);
                  }
                }
                *((_DWORD *)SpinLock + 28) = 0;
                KeQuerySystemTimePrecise(SpinLock + 111);
                if ( (*(_BYTE *)(&WPP_MAIN_CB.Reserved + 1) & 0x20) != 0
                  || !TcpipIsServerSKU
                  && (unsigned int)dword_1402201F8 > 0x10
                  && (unsigned __int8)tlgKeywordOn(&dword_1402201F8, 0x200000000000LL) )
                {
                  TcpTraceConnectionSummary(SpinLock);
                }
                if ( (Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_featureState & 0x10) != 0 )
                  v58 = Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_featureState & 1;
                else
                  v58 = Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_IsEnabledDeviceUsageNoInline();
                if ( !v58 )
                  TcpHistogramIncrement(SpinLock, (unsigned int)v111, LockArray_high);
                v59 = 192LL * LockArray_high;
                *(_QWORD *)(*(_QWORD *)(SpinLock[3] + 128) + v59 + 144) += SpinLock[48];
                *(_QWORD *)(*(_QWORD *)(SpinLock[3] + 128) + v59 + 152) += *((unsigned int *)SpinLock + 280);
                if ( (*((_BYTE *)SpinLock + 804) & 0x20) != 0 )
                {
                  if ( !SpinLock[56] && (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
                    KeBugCheckEx(0x150u, 0, 0, 0, 0);
                  BindingHandleByTcb = OlmQueryBindingHandleByTcb(SpinLock);
                  LOBYTE(v61) = 1;
                  NetioNcmFastActiveReferenceRequest(11, v61, BindingHandleByTcb);
                  *((_WORD *)SpinLock + 402) &= ~0x20u;
                }
                v62 = TcpGetAndWriteLockPartitionAtDpcLevel(SpinLock[8], &LockHandle);
                if ( (SpinLock[15] & 2) != 0 )
                {
                  TcpCleanupTimerTcb(v62, SpinLock);
                  TcpInvokeCcb(
                    *(unsigned __int16 *)(SpinLock[3] + 24),
                    v57 + 1,
                    1,
                    *(_QWORD *)SpinLock[4],
                    *(_QWORD *)(SpinLock[4] + 16),
                    *((_WORD *)SpinLock + 58),
                    *((_WORD *)SpinLock + 59),
                    *(_DWORD *)(SpinLock[4] + 8));
                  TcpRemoveTcb(SpinLock, v62, 0);
                  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
                  LOBYTE(v63) = 1;
                  v64 = TcpRemoveTcb(SpinLock, 0, v63);
                  LODWORD(v64) = HIDWORD(KeGetPcr()[1].LockArray);
                  v65 = 192 * v64;
                  v66 = *(_QWORD *)(SpinLock[3] + 128);
                  v67 = (unsigned int)(*(_DWORD *)(192 * v64 + v66 + 76) - 1);
                  *(_DWORD *)(v65 + v66 + 76) = v67;
                }
                else
                {
                  TcpCleanupTimerTcb(v62, SpinLock);
                  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
                }
                if ( v57 >= 3 && v57 != 10 )
                {
                  v67 = v6 + 0x80000000;
                  if ( (v67 & 0x80000000) == 0LL && v6 != -1073741299 )
                  {
                    if ( SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
                    {
                      v68 = (ADDRESS_FAMILY *)(SpinLock[3] + 24);
                      v69 = SpinLock[15] & 8;
                      if ( !v69 )
                        v12 = *v68;
                      v70 = v69 != 0;
                      LOBYTE(v65) = v69 != 0;
                      v71 = InetFormatSockAddrAtDispatchLevel(
                              *v68,
                              v65,
                              1,
                              *(_QWORD *)(SpinLock[4] + 16),
                              *(_DWORD *)(SpinLock[4] + 8),
                              *((_WORD *)SpinLock + 59));
                      v72 = SOCKADDR_SIZE(v12);
                      v73 = SOCKADDR_SIZE(v12);
                      LOBYTE(v74) = v70;
                      v75 = v73;
                      v76 = SpinLock[3];
                      v77 = *(_WORD *)(v76 + 24);
                      v78 = InetFormatLocalSockAddrAtDispatchLevel(
                              v76,
                              v74,
                              *(_QWORD *)SpinLock[4],
                              *((unsigned __int16 *)SpinLock + 58));
                      McTemplateK0pqqqbr3qbr5q_EtwWriteTransfer(
                        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                        v79,
                        v80,
                        (_DWORD)SpinLock,
                        BugCheckParameter4,
                        v77,
                        v75,
                        v78,
                        v72,
                        v71,
                        10);
                      v6 = a2;
                    }
                    TcpTcbHeaderSend(SpinLock);
                    KeAcquireSpinLockAtDpcLevel(SpinLock);
                  }
                }
                if ( (*((_BYTE *)SpinLock + 804) & 2) != 0 )
                {
                  v67 = SpinLock[115];
                  if ( v67 )
                  {
                    v67 = *(_QWORD *)(v67 + 8);
                    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v67 + 24) + 108LL));
                  }
                }
                if ( v57 )
                {
                  if ( v57 >= 4 )
                  {
                    if ( v57 == 4 || v57 == 7 )
                    {
                      LODWORD(v67) = HIDWORD(KeGetPcr()[1].LockArray);
                      v82 = 192 * v67;
                      v83 = *(_QWORD *)(SpinLock[3] + 128);
                      v84 = (unsigned int)(*(_DWORD *)(192 * v67 + v83 + 16) - 1);
                      *(_DWORD *)(v82 + v83 + 16) = v84;
                      LODWORD(v84) = HIDWORD(KeGetPcr()[1].LockArray);
                      ++*(_DWORD *)(192 * v84 + *(_QWORD *)(SpinLock[3] + 128) + 12);
                    }
                  }
                  else
                  {
                    LODWORD(v67) = HIDWORD(KeGetPcr()[1].LockArray);
                    ++*(_DWORD *)(192 * v67 + *(_QWORD *)(SpinLock[3] + 128) + 8);
                    v105 = *((_BYTE *)SpinLock + 124) & 1;
                    if ( (SpinLock[15] & 1) != 0 )
                    {
                      if ( SpinLock[85] )
                        TcpCreateAndConnectTcbComplete((unsigned int *)SpinLock, v6);
                    }
                    else if ( v57 == 3 )
                    {
                      if ( _bittest16((const signed __int16 *)SpinLock + 402, 8u) )
                      {
                        if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)SpinLock[103]) == 1 )
                        {
                          v81 = SpinLock[103];
                          *(_QWORD *)&v113 = SpinLock[83];
                          *((_QWORD *)&v113 + 1) = *((unsigned int *)SpinLock + 168);
                          (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(v81 + 216) + 24LL))(
                            *(_QWORD *)(v81 + 224),
                            &v113);
                          ExReleaseRundownProtection((PEX_RUNDOWN_REF)SpinLock[103]);
                        }
                        *((_WORD *)SpinLock + 402) &= ~0x100u;
                      }
                      SpinLock[83] = 0;
                    }
                  }
                }
                if ( (v110 & 1) != 0 && (*((_DWORD *)SpinLock + 31) & 1) == 0 )
                  TcpNotifyAbortDelivery(SpinLock);
                TcpFlushTcbSend(SpinLock);
                v85 = TcpTotalAvailableTcbInput(SpinLock);
                if ( v85 )
                {
                  v86 = SpinLock + 69;
                  if ( SpinLock != (PKSPIN_LOCK)-552LL )
                  {
                    do
                    {
                      LODWORD(v85) = HIDWORD(KeGetPcr()[1].LockArray);
                      v87 = v86[6];
                      v88 = (_QWORD *)v86[5];
                      v86[6] = 0;
                      v86[7] = 0;
                      v86[5] = 0;
                      *(_QWORD *)(192 * v85 + *(_QWORD *)(SpinLock[3] + 128) + 80) -= v86[3];
                      v86[3] = 0;
                      KeReleaseSpinLockFromDpcLevel(SpinLock);
                      NetioDereferenceNetBufferListChain(v87, 0);
                      while ( v88 )
                      {
                        v89 = v88;
                        v88 = (_QWORD *)*v88;
                        NetioDereferenceNetBufferListChain(v89[1], 0);
                        PplFreeToLookasideList(TcpInputPool);
                      }
                      KeAcquireSpinLockAtDpcLevel(SpinLock);
                      v85 = SpinLock[82];
                      if ( v86 == (PKSPIN_LOCK)v85 )
                        break;
                      v86 = (PKSPIN_LOCK)SpinLock[82];
                    }
                    while ( v85 );
                  }
                  KeReleaseSpinLock(SpinLock, 2u);
                  KeAcquireSpinLockAtDpcLevel(SpinLock);
                }
                if ( (unsigned __int8)TcpHasRequestReceive(SpinLock) )
                  TcpFlushRequestReceive(v90);
                TcpSendTrackerUnInit(SpinLock + 121);
                if ( (*((_DWORD *)SpinLock + 31) & 0x10) != 0 )
                {
                  TcpTcbReassemblyEmptyList(SpinLock);
                  if ( dword_1402201D4 )
                  {
                    if ( (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
                      && (BYTE3(WPP_MAIN_CB.Reserved) & 4) != 0 )
                    {
                      BugCheckParameter4a = *((_DWORD *)SpinLock + 34);
                      v113 = (unsigned __int64)SpinLock;
                      McTemplateK0pqqzq_EtwWriteTransfer(
                        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                        (unsigned int)TCP_FLUSH_REASSEMBLY,
                        (unsigned int)&v113,
                        (_DWORD)SpinLock,
                        BugCheckParameter4a,
                        v100,
                        (__int64)L"Connection shutdown",
                        0);
                    }
                  }
                }
                if ( SpinLock[5] )
                {
                  LOBYTE(v91) = 1;
                  TcpTcbSignalNotificationChannelEvent(SpinLock, v91, 0, 0);
                  LOBYTE(v92) = 1;
                  TcpScheduleNotificationChannelWorkItemTcb((_DWORD)SpinLock, 0, v92, 0, 0);
                }
                if ( (*((_BYTE *)SpinLock + 804) & 0x10) != 0 )
                  KeSetEvent((PRKEVENT)SpinLock[137], 0, 0);
                if ( SpinLock[85] )
                {
                  if ( v57 != 4 )
                  {
                    if ( (unsigned int)v57 > 9 || (v93 = 936, !_bittest(&v93, v57)) )
                      MicrosoftTelemetryAssertTriggeredNoArgsKM();
                  }
                  TcpDisconnectTcbComplete(SpinLock);
                }
                TcpAbortTcbComplete(SpinLock);
                return v105;
              }
              DWORD2(v115) = 6;
            }
            else
            {
              DWORD2(v115) = 5;
            }
            break;
        }
        v53 = -1073741823;
        goto LABEL_55;
      }
      v114 = 0;
      if ( (BYTE1(WPP_MAIN_CB.Reserved) & 0x20) != 0 )
      {
        v30 = (unsigned __int8)PsGetProcessId((PEPROCESS)SpinLock[106]);
        v31 = SpinLock[106];
        v32 = v30;
        v114 = (unsigned __int64)SpinLock;
        v33 = PsGetProcessStartKey(v31);
        v104 = v32;
        v26 = v113;
        McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_SHUTDOWN_TCB_V1,
          (unsigned int)&v114,
          v22,
          v113,
          v22,
          v109,
          v6,
          v104,
          0,
          (char)SpinLock,
          v33);
        v29 = v109;
        *(_QWORD *)&v114 = SpinLock + 3;
        goto LABEL_26;
      }
    }
    *(_QWORD *)&v114 = SpinLock + 3;
    goto LABEL_26;
  }
  v94 = SpinLock + 69;
  if ( (v9 & 0x100000) == 0 )
    v94 = (PKSPIN_LOCK)SpinLock[82];
  v95 = *v94;
  if ( (*(_BYTE *)v95 & 1) == 0 )
  {
    v96 = *(_BYTE *)v95 | 1;
    *(_DWORD *)(v95 + 4) = v6;
    *(_BYTE *)v95 = v96;
    *(_DWORD *)(v95 + 16) = a4;
  }
  return v105;
}

```

## disassembly

```asm
0x1400064f8  mov     [rsp-8+arg_10], rbx
0x1400064fd  push    rbp
0x1400064fe  push    rsi
0x1400064ff  push    rdi
0x140006500  push    r12
0x140006502  push    r13
0x140006504  push    r14
0x140006506  push    r15
0x140006508  lea     rbp, [rsp-27h]
0x14000650d  sub     rsp, 0E0h
0x140006514  mov     rax, cs:__security_cookie
0x14000651b  xor     rax, rsp
0x14000651e  mov     [rbp+57h+var_40], rax
0x140006522  xor     eax, eax
0x140006524  mov     [rbp+57h+var_A4], r9d
0x140006528  xorps   xmm0, xmm0
0x14000652b  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000652f  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140006533  mov     r14d, gs:1A4h
0x14000653c  mov     r15d, r9d
0x14000653f  mov     [rbp+57h+var_A8], r14d
0x140006543  mov     esi, edx
0x140006545  mov     [rbp+57h+var_98], r8d
0x140006549  mov     r13, rcx
0x14000654c  mov     [rbp+57h+var_AC], edx
0x14000654f  mov     [rbp+57h+var_B0], al
0x140006552  mov     dword ptr [rbp+57h+var_90], eax
0x140006555  mov     eax, cs:Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_featureState
0x14000655b  mov     ebx, 10h
0x140006560  test    bl, al
0x140006562  jz      short loc_140006569
0x140006564  and     eax, 1
0x140006567  jmp     short loc_14000656E
0x140006569  call    Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_IsEnabledDeviceUsageNoInline
0x14000656e  test    eax, eax
0x140006570  jnz     short loc_14000659D
0x140006572  xor     edx, edx
0x140006574  mov     ecx, r14d
0x140006577  call    TcpQueryMicrosecondCount
0x14000657c  mov     rcx, rax
0x14000657f  mov     rax, 624DD2F1A9FBE77h
0x140006589  mul     rcx
0x14000658c  sub     rcx, rdx
0x14000658f  shr     rcx, 1
0x140006592  add     rcx, rdx
0x140006595  shr     rcx, 9
0x140006599  mov     [rbp+57h+var_90], rcx
0x14000659d  mov     eax, [r13+78h]
0x1400065a1  test    eax, 300000h
0x1400065a6  jnz     loc_14000720E
0x1400065ac  lea     rcx, WPP_MAIN_CB.SectorSize; SpinLock
0x1400065b3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400065ba  nop     dword ptr [rax+rax+00h]
0x1400065bf  mov     eax, [r13+7Ch]
0x1400065c3  test    al, 1
0x1400065c5  jz      short loc_1400065D0
0x1400065c7  inc     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header
0x1400065ce  jmp     short loc_1400065D7
0x1400065d0  inc     cs:WPP_MAIN_CB.SecurityDescriptor
0x1400065d7  lea     rcx, WPP_MAIN_CB.SectorSize; SpinLock
0x1400065de  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400065e5  nop     dword ptr [rax+rax+00h]
0x1400065ea  mov     r8, [r13+20h]
0x1400065ee  mov     edi, 17h
0x1400065f3  test    r8, r8
0x1400065f6  jnz     loc_1400066AE
0x1400065fc  xor     r15d, r15d
0x1400065ff  cmp     cs:dword_1402201D4, r15d
0x140006606  jz      loc_140006AF5
0x14000660c  cmp     cs:TcpipTraceFiltersExist, r15b
0x140006613  jz      short loc_140006624
0x140006615  mov     al, [r13+324h]
0x14000661c  test    al, al
0x14000661e  jns     loc_140006AF5
0x140006624  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 20h
0x14000662b  xorps   xmm0, xmm0
0x14000662e  movups  [rbp+57h+var_70], xmm0
0x140006632  jz      loc_140006AF5
0x140006638  mov     rcx, [r13+350h]; Process
0x14000663f  call    cs:__imp_PsGetProcessId
0x140006646  nop     dword ptr [rax+rax+00h]
0x14000664b  mov     rcx, [r13+350h]
0x140006652  mov     rbx, rax
0x140006655  mov     qword ptr [rbp+57h+var_70+8], r15
0x140006659  mov     qword ptr [rbp+57h+var_70], r13
0x14000665d  call    cs:__imp_PsGetProcessStartKey
0x140006664  nop     dword ptr [rax+rax+00h]
0x140006669  mov     [rsp+110h+var_B8], rax
0x14000666e  xor     r9d, r9d
0x140006671  mov     [rsp+110h+var_C0], r13
0x140006676  lea     r8, [rbp+57h+var_70]
0x14000667a  mov     dword ptr [rsp+110h+var_C8], r15d
0x14000667f  lea     rdx, TCP_SHUTDOWN_TCB_V1
0x140006686  mov     dword ptr [rsp+110h+var_D0], ebx
0x14000668a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140006691  mov     dword ptr [rsp+110h+var_D8], esi
0x140006695  mov     [rsp+110h+var_E0], r15
0x14000669a  mov     dword ptr [rsp+110h+var_E8], r15d
0x14000669f  mov     [rsp+110h+BugCheckParameter4], r15
0x1400066a4  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x1400066a9  jmp     loc_140006AF0
0x1400066ae  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 20h
0x1400066b5  lea     r12, [r13+18h]
0x1400066b9  mov     qword ptr [rbp+57h+var_60], r12
0x1400066bd  jz      loc_140006805
0x1400066c3  mov     edx, [r13+78h]
0x1400066c7  movzx   ecx, di
0x1400066ca  mov     r10, [r12]
0x1400066ce  and     edx, 8
0x1400066d1  jnz     short loc_1400066D8
0x1400066d3  movzx   ecx, word ptr [r10+18h]; af
0x1400066d8  call    SOCKADDR_SIZE
0x1400066dd  movzx   r9d, word ptr [r13+74h]
0x1400066e2  test    edx, edx
0x1400066e4  mov     r8, [r8]
0x1400066e7  mov     rcx, r10
0x1400066ea  setnz   dl
0x1400066ed  movzx   r14d, al
0x1400066f1  call    InetFormatLocalSockAddrAtDispatchLevel
0x1400066f6  mov     r9, [r13+20h]
0x1400066fa  mov     rbx, rax
0x1400066fd  movzx   ecx, word ptr [r13+76h]
0x140006702  mov     r8d, 1
0x140006708  mov     r10, [r12]
0x14000670c  mov     edx, [r13+78h]
0x140006710  mov     word ptr [rsp+110h+var_E8], cx
0x140006715  mov     qword ptr [rbp+57h+var_70], rax
0x140006719  mov     eax, [r9+8]
0x14000671d  mov     r9, [r9+10h]
0x140006721  movzx   ecx, word ptr [r10+18h]
0x140006726  shr     edx, 3
0x140006729  and     dl, 1
0x14000672c  mov     dword ptr [rsp+110h+BugCheckParameter4], eax
0x140006730  call    InetFormatSockAddrAtDispatchLevel
0x140006735  cmp     cs:dword_1402201D4, 0
0x14000673c  mov     rcx, rax
0x14000673f  mov     [rbp+57h+var_A0], rax
0x140006743  jz      loc_1400067FF
0x140006749  cmp     cs:TcpipTraceFiltersExist, 0
0x140006750  jz      short loc_140006761
0x140006752  mov     al, [r13+324h]
0x140006759  test    al, al
0x14000675b  jns     loc_14000680C
0x140006761  test    byte ptr cs:WPP_MAIN_CB.Reserved+1, 20h
0x140006768  xorps   xmm0, xmm0
0x14000676b  movups  [rbp+57h+var_60], xmm0
0x14000676f  jz      loc_1400067FF
0x140006775  mov     rcx, [r13+350h]; Process
0x14000677c  call    cs:__imp_PsGetProcessId
0x140006783  nop     dword ptr [rax+rax+00h]
0x140006788  mov     rcx, [r13+350h]
0x14000678f  mov     rbx, rax
0x140006792  mov     qword ptr [rbp+57h+var_60+8], 0
0x14000679a  mov     qword ptr [rbp+57h+var_60], r13
0x14000679e  call    cs:__imp_PsGetProcessStartKey
0x1400067a5  nop     dword ptr [rax+rax+00h]
0x1400067aa  mov     [rsp+110h+var_B8], rax
0x1400067af  mov     r9d, r14d
0x1400067b2  mov     rax, [rbp+57h+var_A0]
0x1400067b6  lea     r8, [rbp+57h+var_60]
0x1400067ba  mov     [rsp+110h+var_C0], r13
0x1400067bf  lea     rdx, TCP_SHUTDOWN_TCB_V1
0x1400067c6  mov     dword ptr [rsp+110h+var_C8], 0
0x1400067ce  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400067d5  mov     dword ptr [rsp+110h+var_D0], ebx
0x1400067d9  mov     rbx, qword ptr [rbp+57h+var_70]
0x1400067dd  mov     dword ptr [rsp+110h+var_D8], esi
0x1400067e1  mov     [rsp+110h+var_E0], rax
0x1400067e6  mov     dword ptr [rsp+110h+var_E8], r14d
0x1400067eb  mov     [rsp+110h+BugCheckParameter4], rbx
0x1400067f0  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x1400067f5  mov     rcx, [rbp+57h+var_A0]
0x1400067f9  mov     qword ptr [rbp+57h+var_60], r12
0x1400067fd  jmp     short loc_14000680C
0x1400067ff  mov     qword ptr [rbp+57h+var_60], r12
0x140006803  jmp     short loc_14000680C
0x140006805  xor     r14b, r14b
0x140006808  xor     ecx, ecx
0x14000680a  xor     ebx, ebx
0x14000680c  test    r15d, r15d
0x14000680f  jz      loc_140006910
0x140006815  test    esi, esi
0x140006817  jns     loc_140006910
0x14000681d  test    r14b, r14b
0x140006820  jz      short loc_140006855
0x140006822  mov     eax, [r13+70h]
0x140006826  mov     r9, rcx
0x140006829  mov     dword ptr [rsp+110h+var_D8], r15d
0x14000682e  mov     r8b, r14b
0x140006831  mov     dword ptr [rsp+110h+var_E0], eax
0x140006835  mov     rdx, rbx
0x140006838  mov     rax, [r13+350h]
0x14000683f  mov     cl, r14b
0x140006842  mov     dword ptr [rsp+110h+var_E8], esi
0x140006846  mov     [rsp+110h+BugCheckParameter4], rax
0x14000684b  call    TcpRecentFailureTrace
0x140006850  jmp     loc_140006910
0x140006855  mov     r10, [r12]
0x140006859  mov     ecx, [r13+78h]
0x14000685d  lea     r10, [r10+18h]
0x140006861  and     ecx, 8
0x140006864  jz      short loc_14000686E
0x140006866  movzx   ebx, di
0x140006869  movzx   esi, di
0x14000686c  jmp     short loc_140006875
0x14000686e  movzx   ebx, word ptr [r10]
0x140006872  movzx   esi, bx
0x140006875  mov     r9, [r13+20h]
0x140006879  test    ecx, ecx
0x14000687b  movzx   ecx, word ptr [r13+76h]
0x140006880  mov     r8d, 1
0x140006886  mov     word ptr [rsp+110h+var_E8], cx
0x14000688b  setnz   r12b
0x14000688f  movzx   ecx, word ptr [r10]
0x140006893  mov     dl, r12b
0x140006896  mov     eax, [r9+8]
0x14000689a  mov     r9, [r9+10h]
0x14000689e  mov     dword ptr [rsp+110h+BugCheckParameter4], eax
0x1400068a2  call    InetFormatSockAddrAtDispatchLevel
0x1400068a7  mov     edi, [r13+70h]
0x1400068ab  movzx   ecx, si; af
0x1400068ae  mov     r14, [r13+350h]
0x1400068b5  mov     r15, rax
0x1400068b8  call    SOCKADDR_SIZE
0x1400068bd  movzx   ecx, bx; af
0x1400068c0  mov     sil, al
0x1400068c3  call    SOCKADDR_SIZE
0x1400068c8  mov     r8, [r13+20h]
0x1400068cc  mov     dl, r12b
0x1400068cf  mov     r12, qword ptr [rbp+57h+var_60]
0x1400068d3  mov     bl, al
0x1400068d5  movzx   r9d, word ptr [r13+74h]
0x1400068da  mov     r8, [r8]
0x1400068dd  mov     rcx, [r12]
0x1400068e1  call    InetFormatLocalSockAddrAtDispatchLevel
0x1400068e6  mov     rdx, rax
0x1400068e9  mov     r9, r15
0x1400068ec  mov     eax, [rbp+57h+var_A4]
0x1400068ef  mov     r8b, sil
0x1400068f2  mov     dword ptr [rsp+110h+var_D8], eax
0x1400068f6  mov     cl, bl
0x1400068f8  mov     eax, [rbp+57h+var_AC]
0x1400068fb  mov     dword ptr [rsp+110h+var_E0], edi
0x1400068ff  mov     dword ptr [rsp+110h+var_E8], eax
0x140006903  mov     [rsp+110h+BugCheckParameter4], r14
0x140006908  call    TcpRecentFailureTrace
0x14000690d  mov     esi, [rbp+57h+var_AC]
0x140006910  test    byte ptr [r13+31Dh], 20h
0x140006918  jz      loc_140006ACC
0x14000691e  mov     eax, [r13+78h]
0x140006922  test    al, 1
0x140006924  jz      loc_140006ACC
0x14000692a  movzx   ecx, word ptr [r13+80h]
0x140006932  mov     edi, 1Fh
0x140006937  movzx   eax, cx
0x14000693a  and     ax, di
0x14000693d  jz      loc_140006ACC
0x140006943  xor     r15d, r15d
0x140006946  cmp     ax, 13h
0x14000694a  jz      loc_140006ACF
0x140006950  mov     [rbp+57h+var_A0], r15
0x140006954  xorps   xmm0, xmm0
0x140006957  movups  [rbp+57h+var_60], xmm0
0x14000695b  movups  [rbp+57h+var_50], xmm0
0x14000695f  cmp     ax, 15h
0x140006963  jnz     short loc_14000696E
0x140006965  mov     dword ptr [rbp+57h+var_50+8], 1
0x14000696c  jmp     short loc_1400069DD
0x14000696e  cmp     ax, 16h
0x140006972  jnz     short loc_14000697E
0x140006974  mov     edx, 7
0x140006979  mov     dword ptr [rbp+57h+var_50+8], edx
0x14000697c  jmp     short loc_1400069DD
0x14000697e  mov     r8d, 10h
0x140006984  cmp     ax, r8w
0x140006988  jnz     short loc_140006993
0x14000698a  mov     dword ptr [rbp+57h+var_50+8], 2
0x140006991  jmp     short loc_1400069DD
0x140006993  cmp     ax, 12h
0x140006997  jnz     short loc_1400069A2
0x140006999  mov     dword ptr [rbp+57h+var_50+8], 3
0x1400069a0  jmp     short loc_1400069DD
0x1400069a2  cmp     esi, 0C00000B5h
0x1400069a8  jnz     short loc_1400069B3
0x1400069aa  mov     dword ptr [rbp+57h+var_50+8], 4
0x1400069b1  jmp     short loc_1400069DD
0x1400069b3  cmp     [r13+200h], r15
0x1400069ba  jnz     short loc_1400069C5
0x1400069bc  mov     dword ptr [rbp+57h+var_50+8], 5
0x1400069c3  jmp     short loc_1400069DD
0x1400069c5  cmp     esi, 0C0000241h
0x1400069cb  jnz     short loc_1400069E4
0x1400069cd  cmp     [r13+1C8h], r15
0x1400069d4  jz      short loc_1400069E4
0x1400069d6  mov     dword ptr [rbp+57h+var_50+8], 6
0x1400069dd  mov     ebx, 0C0000001h
0x1400069e2  jmp     short loc_1400069F3
0x1400069e4  sub     ax, 7
0x1400069e8  neg     ax
0x1400069eb  sbb     ebx, ebx
  ... truncated ...
```
