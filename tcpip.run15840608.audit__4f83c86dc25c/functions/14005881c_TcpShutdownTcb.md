# TcpShutdownTcb

- ea: `0x14005881c`
- end: `0x140059587`
- name: `TcpShutdownTcb`
- size: `3435`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `10`
- callee_count: `39`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140009820`
- `0x14000b6ac`
- `0x14000cbf0`
- `0x14000f330`
- `0x140057c48`
- `0x140058180`
- `0x14005a1a0`
- `0x140122ba0`
- `0x140132fa4`
- `0x140133ce0`

## callees

- `0x140009590`
- `0x14000bd04`
- `0x140013140`
- `0x14001ea80`
- `0x14001eb30`
- `0x14003b4c0`
- `0x14003fe90`
- `0x140041ab0`
- `0x140044880`
- `0x1400577c0`
- `0x1400579c0`
- `0x140057aec`
- `0x14005881c`
- `0x140059d24`
- `0x14005a170`
- `0x14005a350`
- `0x140071ac0`
- `0x1400a18e0`
- `0x1400a5bc0`
- `0x1400d2680`
- `0x1400d289c`
- `0x1400f00d0`
- `0x1400f6eb0`
- `0x1400f74d0`
- `0x1400f95e0`
- `0x140111204`
- `0x140113288`
- `0x140113788`
- `0x1401186e4`
- `0x140120c68`
- `0x140122ba0`
- `0x140131ee0`
- `0x14014ec00`
- `0x14015362c`
- `0x140161694`
- `0x1401623e8`
- `0x14018cd60`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140059289`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140059289`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140059237`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140059237`
- `ntoskrnl!KeBugCheckEx` at `0x140058f6a`
- `ntoskrnl!KeBugCheckEx` at `0x140058f6a`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140058d7d`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140058e86`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140058d7d`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140058e86`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400588d7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140059187`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400593ce`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140059409`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400588d7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140059187`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400593ce`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140059409`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140058902`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140059380`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140058902`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140059380`
- `ntoskrnl!PsGetProcessStartKey` at `0x140058981`
- `ntoskrnl!PsGetProcessStartKey` at `0x140058ac2`
- `ntoskrnl!PsGetProcessStartKey` at `0x140058981`
- `ntoskrnl!PsGetProcessStartKey` at `0x140058ac2`
- `ntoskrnl!KeSetEvent` at `0x1400594ed`
- `ntoskrnl!KeSetEvent` at `0x1400594ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005901f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140059068`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005901f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140059068`
- `ntoskrnl!PsGetProcessId` at `0x140058963`
- `ntoskrnl!PsGetProcessId` at `0x140058aa0`
- `ntoskrnl!PsGetProcessId` at `0x140058963`
- `ntoskrnl!PsGetProcessId` at `0x140058aa0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400593fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400593fa`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140058f48`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140058f48`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140058f89`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140058f89`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x140059391`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400593ab`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x140059391`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400593ab`

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
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DpcListEntry);
    if ( (*((_DWORD *)SpinLock + 31) & 1) != 0 )
      ++WPP_MAIN_CB.DeviceQueue.Lock;
    else
      ++WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DpcListEntry);
    v11 = SpinLock[4];
    v12 = 23;
    if ( !v11 )
    {
      if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
      {
        v113 = 0;
        if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
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
    if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) == 0 )
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
    if ( dword_1402241D4 )
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
                if ( dword_1402241D4 )
                {
                  v113 = 0;
                  if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
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
                if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
                {
                  v113 = 0;
                  if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
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
                if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 0x20) != 0
                  || !TcpipIsServerSKU
                  && (unsigned int)dword_1402241F8 > 0x10
                  && (unsigned __int8)tlgKeywordOn(&dword_1402241F8, 0x200000000000LL) )
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
                    if ( SBYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
                  if ( dword_1402241D4 )
                  {
                    if ( (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
                      && (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
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
      if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
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
0x14005881c  mov     [rsp-8+arg_10], rbx
0x140058821  push    rbp
0x140058822  push    rsi
0x140058823  push    rdi
0x140058824  push    r12
0x140058826  push    r13
0x140058828  push    r14
0x14005882a  push    r15
0x14005882c  lea     rbp, [rsp-27h]
0x140058831  sub     rsp, 0E0h
0x140058838  mov     rax, cs:__security_cookie
0x14005883f  xor     rax, rsp
0x140058842  mov     [rbp+57h+var_40], rax
0x140058846  xor     eax, eax
0x140058848  mov     [rbp+57h+var_A4], r9d
0x14005884c  xorps   xmm0, xmm0
0x14005884f  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140058853  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140058857  mov     r14d, gs:1A4h
0x140058860  mov     r15d, r9d
0x140058863  mov     [rbp+57h+var_A8], r14d
0x140058867  mov     esi, edx
0x140058869  mov     [rbp+57h+var_98], r8d
0x14005886d  mov     r13, rcx
0x140058870  mov     [rbp+57h+var_AC], edx
0x140058873  mov     [rbp+57h+var_B0], al
0x140058876  mov     dword ptr [rbp+57h+var_90], eax
0x140058879  mov     eax, cs:Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_featureState
0x14005887f  mov     ebx, 10h
0x140058884  test    bl, al
0x140058886  jz      short loc_14005888D
0x140058888  and     eax, 1
0x14005888b  jmp     short loc_140058892
0x14005888d  call    Feature_TCPIP_2025_KCSAN_RemoveHistograms__private_IsEnabledDeviceUsageNoInline
0x140058892  test    eax, eax
0x140058894  jnz     short loc_1400588C1
0x140058896  xor     edx, edx
0x140058898  mov     ecx, r14d
0x14005889b  call    TcpQueryMicrosecondCount
0x1400588a0  mov     rcx, rax
0x1400588a3  mov     rax, 624DD2F1A9FBE77h
0x1400588ad  mul     rcx
0x1400588b0  sub     rcx, rdx
0x1400588b3  shr     rcx, 1
0x1400588b6  add     rcx, rdx
0x1400588b9  shr     rcx, 9
0x1400588bd  mov     [rbp+57h+var_90], rcx
0x1400588c1  mov     eax, [r13+78h]
0x1400588c5  test    eax, 300000h
0x1400588ca  jnz     loc_140059532
0x1400588d0  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; SpinLock
0x1400588d7  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400588de  nop     dword ptr [rax+rax+00h]
0x1400588e3  mov     eax, [r13+7Ch]
0x1400588e7  test    al, 1
0x1400588e9  jz      short loc_1400588F4
0x1400588eb  inc     cs:WPP_MAIN_CB.DeviceQueue.Lock
0x1400588f2  jmp     short loc_1400588FB
0x1400588f4  inc     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400588fb  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; SpinLock
0x140058902  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140058909  nop     dword ptr [rax+rax+00h]
0x14005890e  mov     r8, [r13+20h]
0x140058912  mov     edi, 17h
0x140058917  test    r8, r8
0x14005891a  jnz     loc_1400589D2
0x140058920  xor     r15d, r15d
0x140058923  cmp     cs:dword_1402241D4, r15d
0x14005892a  jz      loc_140058E19
0x140058930  cmp     cs:TcpipTraceFiltersExist, r15b
0x140058937  jz      short loc_140058948
0x140058939  mov     al, [r13+324h]
0x140058940  test    al, al
0x140058942  jns     loc_140058E19
0x140058948  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, 20h
0x14005894f  xorps   xmm0, xmm0
0x140058952  movups  [rbp+57h+var_70], xmm0
0x140058956  jz      loc_140058E19
0x14005895c  mov     rcx, [r13+350h]; Process
0x140058963  call    cs:__imp_PsGetProcessId
0x14005896a  nop     dword ptr [rax+rax+00h]
0x14005896f  mov     rcx, [r13+350h]
0x140058976  mov     rbx, rax
0x140058979  mov     qword ptr [rbp+57h+var_70+8], r15
0x14005897d  mov     qword ptr [rbp+57h+var_70], r13
0x140058981  call    cs:__imp_PsGetProcessStartKey
0x140058988  nop     dword ptr [rax+rax+00h]
0x14005898d  mov     [rsp+110h+var_B8], rax
0x140058992  xor     r9d, r9d
0x140058995  mov     [rsp+110h+var_C0], r13
0x14005899a  lea     r8, [rbp+57h+var_70]
0x14005899e  mov     dword ptr [rsp+110h+var_C8], r15d
0x1400589a3  lea     rdx, TCP_SHUTDOWN_TCB_V1
0x1400589aa  mov     dword ptr [rsp+110h+var_D0], ebx
0x1400589ae  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400589b5  mov     dword ptr [rsp+110h+var_D8], esi
0x1400589b9  mov     [rsp+110h+var_E0], r15
0x1400589be  mov     dword ptr [rsp+110h+var_E8], r15d
0x1400589c3  mov     [rsp+110h+BugCheckParameter4], r15
0x1400589c8  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x1400589cd  jmp     loc_140058E14
0x1400589d2  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, 20h
0x1400589d9  lea     r12, [r13+18h]
0x1400589dd  mov     qword ptr [rbp+57h+var_60], r12
0x1400589e1  jz      loc_140058B29
0x1400589e7  mov     edx, [r13+78h]
0x1400589eb  movzx   ecx, di
0x1400589ee  mov     r10, [r12]
0x1400589f2  and     edx, 8
0x1400589f5  jnz     short loc_1400589FC
0x1400589f7  movzx   ecx, word ptr [r10+18h]; af
0x1400589fc  call    SOCKADDR_SIZE
0x140058a01  movzx   r9d, word ptr [r13+74h]
0x140058a06  test    edx, edx
0x140058a08  mov     r8, [r8]
0x140058a0b  mov     rcx, r10
0x140058a0e  setnz   dl
0x140058a11  movzx   r14d, al
0x140058a15  call    InetFormatLocalSockAddrAtDispatchLevel
0x140058a1a  mov     r9, [r13+20h]
0x140058a1e  mov     rbx, rax
0x140058a21  movzx   ecx, word ptr [r13+76h]
0x140058a26  mov     r8d, 1
0x140058a2c  mov     r10, [r12]
0x140058a30  mov     edx, [r13+78h]
0x140058a34  mov     word ptr [rsp+110h+var_E8], cx
0x140058a39  mov     qword ptr [rbp+57h+var_70], rax
0x140058a3d  mov     eax, [r9+8]
0x140058a41  mov     r9, [r9+10h]
0x140058a45  movzx   ecx, word ptr [r10+18h]
0x140058a4a  shr     edx, 3
0x140058a4d  and     dl, 1
0x140058a50  mov     dword ptr [rsp+110h+BugCheckParameter4], eax
0x140058a54  call    InetFormatSockAddrAtDispatchLevel
0x140058a59  cmp     cs:dword_1402241D4, 0
0x140058a60  mov     rcx, rax
0x140058a63  mov     [rbp+57h+var_A0], rax
0x140058a67  jz      loc_140058B23
0x140058a6d  cmp     cs:TcpipTraceFiltersExist, 0
0x140058a74  jz      short loc_140058A85
0x140058a76  mov     al, [r13+324h]
0x140058a7d  test    al, al
0x140058a7f  jns     loc_140058B30
0x140058a85  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, 20h
0x140058a8c  xorps   xmm0, xmm0
0x140058a8f  movups  [rbp+57h+var_60], xmm0
0x140058a93  jz      loc_140058B23
0x140058a99  mov     rcx, [r13+350h]; Process
0x140058aa0  call    cs:__imp_PsGetProcessId
0x140058aa7  nop     dword ptr [rax+rax+00h]
0x140058aac  mov     rcx, [r13+350h]
0x140058ab3  mov     rbx, rax
0x140058ab6  mov     qword ptr [rbp+57h+var_60+8], 0
0x140058abe  mov     qword ptr [rbp+57h+var_60], r13
0x140058ac2  call    cs:__imp_PsGetProcessStartKey
0x140058ac9  nop     dword ptr [rax+rax+00h]
0x140058ace  mov     [rsp+110h+var_B8], rax
0x140058ad3  mov     r9d, r14d
0x140058ad6  mov     rax, [rbp+57h+var_A0]
0x140058ada  lea     r8, [rbp+57h+var_60]
0x140058ade  mov     [rsp+110h+var_C0], r13
0x140058ae3  lea     rdx, TCP_SHUTDOWN_TCB_V1
0x140058aea  mov     dword ptr [rsp+110h+var_C8], 0
0x140058af2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140058af9  mov     dword ptr [rsp+110h+var_D0], ebx
0x140058afd  mov     rbx, qword ptr [rbp+57h+var_70]
0x140058b01  mov     dword ptr [rsp+110h+var_D8], esi
0x140058b05  mov     [rsp+110h+var_E0], rax
0x140058b0a  mov     dword ptr [rsp+110h+var_E8], r14d
0x140058b0f  mov     [rsp+110h+BugCheckParameter4], rbx
0x140058b14  call    McTemplateK0qbr0qbr2qqqpx_EtwWriteTransfer
0x140058b19  mov     rcx, [rbp+57h+var_A0]
0x140058b1d  mov     qword ptr [rbp+57h+var_60], r12
0x140058b21  jmp     short loc_140058B30
0x140058b23  mov     qword ptr [rbp+57h+var_60], r12
0x140058b27  jmp     short loc_140058B30
0x140058b29  xor     r14b, r14b
0x140058b2c  xor     ecx, ecx
0x140058b2e  xor     ebx, ebx
0x140058b30  test    r15d, r15d
0x140058b33  jz      loc_140058C34
0x140058b39  test    esi, esi
0x140058b3b  jns     loc_140058C34
0x140058b41  test    r14b, r14b
0x140058b44  jz      short loc_140058B79
0x140058b46  mov     eax, [r13+70h]
0x140058b4a  mov     r9, rcx
0x140058b4d  mov     dword ptr [rsp+110h+var_D8], r15d
0x140058b52  mov     r8b, r14b
0x140058b55  mov     dword ptr [rsp+110h+var_E0], eax
0x140058b59  mov     rdx, rbx
0x140058b5c  mov     rax, [r13+350h]
0x140058b63  mov     cl, r14b
0x140058b66  mov     dword ptr [rsp+110h+var_E8], esi
0x140058b6a  mov     [rsp+110h+BugCheckParameter4], rax
0x140058b6f  call    TcpRecentFailureTrace
0x140058b74  jmp     loc_140058C34
0x140058b79  mov     r10, [r12]
0x140058b7d  mov     ecx, [r13+78h]
0x140058b81  lea     r10, [r10+18h]
0x140058b85  and     ecx, 8
0x140058b88  jz      short loc_140058B92
0x140058b8a  movzx   ebx, di
0x140058b8d  movzx   esi, di
0x140058b90  jmp     short loc_140058B99
0x140058b92  movzx   ebx, word ptr [r10]
0x140058b96  movzx   esi, bx
0x140058b99  mov     r9, [r13+20h]
0x140058b9d  test    ecx, ecx
0x140058b9f  movzx   ecx, word ptr [r13+76h]
0x140058ba4  mov     r8d, 1
0x140058baa  mov     word ptr [rsp+110h+var_E8], cx
0x140058baf  setnz   r12b
0x140058bb3  movzx   ecx, word ptr [r10]
0x140058bb7  mov     dl, r12b
0x140058bba  mov     eax, [r9+8]
0x140058bbe  mov     r9, [r9+10h]
0x140058bc2  mov     dword ptr [rsp+110h+BugCheckParameter4], eax
0x140058bc6  call    InetFormatSockAddrAtDispatchLevel
0x140058bcb  mov     edi, [r13+70h]
0x140058bcf  movzx   ecx, si; af
0x140058bd2  mov     r14, [r13+350h]
0x140058bd9  mov     r15, rax
0x140058bdc  call    SOCKADDR_SIZE
0x140058be1  movzx   ecx, bx; af
0x140058be4  mov     sil, al
0x140058be7  call    SOCKADDR_SIZE
0x140058bec  mov     r8, [r13+20h]
0x140058bf0  mov     dl, r12b
0x140058bf3  mov     r12, qword ptr [rbp+57h+var_60]
0x140058bf7  mov     bl, al
0x140058bf9  movzx   r9d, word ptr [r13+74h]
0x140058bfe  mov     r8, [r8]
0x140058c01  mov     rcx, [r12]
0x140058c05  call    InetFormatLocalSockAddrAtDispatchLevel
0x140058c0a  mov     rdx, rax
0x140058c0d  mov     r9, r15
0x140058c10  mov     eax, [rbp+57h+var_A4]
0x140058c13  mov     r8b, sil
0x140058c16  mov     dword ptr [rsp+110h+var_D8], eax
0x140058c1a  mov     cl, bl
0x140058c1c  mov     eax, [rbp+57h+var_AC]
0x140058c1f  mov     dword ptr [rsp+110h+var_E0], edi
0x140058c23  mov     dword ptr [rsp+110h+var_E8], eax
0x140058c27  mov     [rsp+110h+BugCheckParameter4], r14
0x140058c2c  call    TcpRecentFailureTrace
0x140058c31  mov     esi, [rbp+57h+var_AC]
0x140058c34  test    byte ptr [r13+31Dh], 20h
0x140058c3c  jz      loc_140058DF0
0x140058c42  mov     eax, [r13+78h]
0x140058c46  test    al, 1
0x140058c48  jz      loc_140058DF0
0x140058c4e  movzx   ecx, word ptr [r13+80h]
0x140058c56  mov     edi, 1Fh
0x140058c5b  movzx   eax, cx
0x140058c5e  and     ax, di
0x140058c61  jz      loc_140058DF0
0x140058c67  xor     r15d, r15d
0x140058c6a  cmp     ax, 13h
0x140058c6e  jz      loc_140058DF3
0x140058c74  mov     [rbp+57h+var_A0], r15
0x140058c78  xorps   xmm0, xmm0
0x140058c7b  movups  [rbp+57h+var_60], xmm0
0x140058c7f  movups  [rbp+57h+var_50], xmm0
0x140058c83  cmp     ax, 15h
0x140058c87  jnz     short loc_140058C92
0x140058c89  mov     dword ptr [rbp+57h+var_50+8], 1
0x140058c90  jmp     short loc_140058D01
0x140058c92  cmp     ax, 16h
0x140058c96  jnz     short loc_140058CA2
0x140058c98  mov     edx, 7
0x140058c9d  mov     dword ptr [rbp+57h+var_50+8], edx
0x140058ca0  jmp     short loc_140058D01
0x140058ca2  mov     r8d, 10h
0x140058ca8  cmp     ax, r8w
0x140058cac  jnz     short loc_140058CB7
0x140058cae  mov     dword ptr [rbp+57h+var_50+8], 2
0x140058cb5  jmp     short loc_140058D01
0x140058cb7  cmp     ax, 12h
0x140058cbb  jnz     short loc_140058CC6
0x140058cbd  mov     dword ptr [rbp+57h+var_50+8], 3
0x140058cc4  jmp     short loc_140058D01
0x140058cc6  cmp     esi, 0C00000B5h
0x140058ccc  jnz     short loc_140058CD7
0x140058cce  mov     dword ptr [rbp+57h+var_50+8], 4
0x140058cd5  jmp     short loc_140058D01
0x140058cd7  cmp     [r13+200h], r15
0x140058cde  jnz     short loc_140058CE9
0x140058ce0  mov     dword ptr [rbp+57h+var_50+8], 5
0x140058ce7  jmp     short loc_140058D01
0x140058ce9  cmp     esi, 0C0000241h
0x140058cef  jnz     short loc_140058D08
0x140058cf1  cmp     [r13+1C8h], r15
0x140058cf8  jz      short loc_140058D08
0x140058cfa  mov     dword ptr [rbp+57h+var_50+8], 6
0x140058d01  mov     ebx, 0C0000001h
0x140058d06  jmp     short loc_140058D17
0x140058d08  sub     ax, 7
0x140058d0c  neg     ax
0x140058d0f  sbb     ebx, ebx
  ... truncated ...
```
