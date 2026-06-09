# StorPortNotification

- ea: `0x140058bd0`
- end: `0x14005a4e0`
- name: `StorPortNotification`
- size: `6416`
- prototype: `void(va_list, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `41`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1401c64c0`

## callees

- `0x140003fc0`
- `0x1400045b0`
- `0x140008258`
- `0x14000befc`
- `0x140012590`
- `0x140012eec`
- `0x140013d10`
- `0x140014790`
- `0x14001edc0`
- `0x140025440`
- `0x140025510`
- `0x1400280b0`
- `0x14002cbd8`
- `0x14002cd70`
- `0x140031330`
- `0x14004c7c0`
- `0x14004cfec`
- `0x140052e00`
- `0x140058bd0`
- `0x140065d90`
- `0x1400680d8`
- `0x14006fb34`
- `0x14009631c`
- `0x14009daa8`
- `0x14009dbd0`
- `0x1400a0b80`
- `0x1400a11a0`
- `0x1400a1b98`
- `0x1400b1bc4`
- `0x1400b5b7c`
- `0x1400b5e0c`
- `0x1400bb0e0`
- `0x1400bb558`
- `0x1400cae20`
- `0x1400d139c`
- `0x1400d1608`
- `0x1400fcc04`
- `0x140116f08`
- `0x14014b400`
- `0x14014b440`
- `0x14014b500`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059019`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400591e6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059d4d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005a211`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005a289`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059019`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400591e6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059d4d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005a211`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005a289`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x140059dcf`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x140059dcf`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059721`
- `ntoskrnl!KeInitializeSpinLock` at `0x140059721`
- `ntoskrnl!EtwWriteEx` at `0x140058ffd`
- `ntoskrnl!EtwWriteEx` at `0x140058ffd`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140059ff4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140059ff4`
- `ntoskrnl!IoQueueWorkItem` at `0x140059fc3`
- `ntoskrnl!IoQueueWorkItem` at `0x140059fc3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005a020`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005a020`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059908`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059908`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140059370`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140059370`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005a1bb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005a1bb`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005a045`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14005a045`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005998a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005998a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockForDpc` at `0x14005999f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockForDpc` at `0x14005999f`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x140059822`
- `ntoskrnl!KeInitializeThreadedDpc` at `0x140059822`
- `ntoskrnl!PsTerminateSystemThread` at `0x140059ead`
- `ntoskrnl!PsTerminateSystemThread` at `0x140059ead`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059035`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059151`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059203`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005985b`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059c04`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059d6a`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005a26e`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005a2a5`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059035`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059151`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059203`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005985b`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059c04`
- `ntoskrnl!KeInsertQueueDpc` at `0x140059d6a`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005a26e`
- `ntoskrnl!KeInsertQueueDpc` at `0x14005a2a5`
- `ntoskrnl!KeBugCheckEx` at `0x1400593a8`
- `ntoskrnl!KeBugCheckEx` at `0x1400593a8`
- `ntoskrnl!KeInitializeDpc` at `0x140059711`
- `ntoskrnl!KeInitializeDpc` at `0x14005974d`
- `ntoskrnl!KeInitializeDpc` at `0x140059711`
- `ntoskrnl!KeInitializeDpc` at `0x14005974d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140058e26`
- `ntoskrnl!KeGetCurrentIrql` at `0x140059191`
- `ntoskrnl!KeGetCurrentIrql` at `0x140059cec`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005a144`
- `ntoskrnl!KeGetCurrentIrql` at `0x140058e26`
- `ntoskrnl!KeGetCurrentIrql` at `0x140059191`
- `ntoskrnl!KeGetCurrentIrql` at `0x140059cec`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005a144`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14005a199`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14005a199`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400599d7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400599d7`
- `ntoskrnl!KeSetImportanceDpc` at `0x140059762`
- `ntoskrnl!KeSetImportanceDpc` at `0x140059762`

## pseudocode

```c
void StorPortNotification(va_list a1, _QWORD *a2, ...)
{
  PKDPC v2; // r8
  char v3; // r12
  int v4; // r14d
  _QWORD *v5; // r9
  unsigned int *v6; // rdi
  unsigned int *v7; // rbx
  unsigned int **v8; // rax
  unsigned int *v9; // rsi
  int v10; // ecx
  va_list v11; // rdx
  void **p_DeferredContext; // rax
  void **p_SystemArgument2; // rsi
  struct _SLIST_ENTRY *v14; // rsi
  _SLIST_ENTRY *Next; // rcx
  const wchar_t *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax
  char v21; // al
  const wchar_t *v22; // rax
  int v23; // edx
  int v24; // ecx
  int v25; // r8d
  unsigned int v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  PKDPC v30; // rsi
  unsigned int v31; // ebx
  char v32; // r14
  PKDPC v33; // rsi
  char v34; // r15
  _BYTE *DeferredItem; // rax
  PKDPC v36; // rsi
  int **v37; // rax
  PKDEFERRED_ROUTINE v38; // rsi
  int *v39; // rcx
  int v40; // edx
  PDEVICE_OBJECT v41; // rcx
  __int64 v42; // rdx
  void **v43; // rax
  void **v44; // rax
  PKDPC v45; // rbx
  PKDPC v46; // rbx
  KDPC_IMPORTANCE v47; // esi
  KDPC_IMPORTANCE v48; // edx
  struct _KDPC *v49; // rcx
  PKDPC v50; // rsi
  char v51; // bl
  _DWORD *v52; // rbx
  __int64 v53; // rax
  int v54; // ecx
  _DWORD *v55; // r8
  _DWORD *v56; // rbx
  PKDEFERRED_ROUTINE v57; // r9
  int v58; // ecx
  int v59; // ecx
  __int64 v60; // rax
  _DWORD *v61; // r10
  unsigned int TargetInfoAsUlong; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  __int64 v67; // rax
  __int64 v68; // rbx
  PKDPC v69; // rsi
  __int64 v70; // rax
  PKDEFERRED_ROUTINE v71; // rsi
  __int64 v72; // r10
  __int64 v73; // r11
  unsigned int v74; // r8d
  unsigned int v75; // r14d
  _DWORD *v76; // rbx
  unsigned __int8 v77; // r15
  unsigned __int8 v78; // r12
  unsigned __int8 v79; // r13
  _DWORD *v80; // rsi
  PKDEFERRED_ROUTINE v81; // r12
  struct _PROCESSOR_NUMBER v82; // ebx
  __int64 Unit; // rax
  __int64 v84; // r14
  __int64 v85; // r15
  _DWORD *v86; // rbx
  PKDPC v87; // rsi
  volatile unsigned __int16 Number; // ax
  _DWORD *DeferredContext; // rbx
  int SystemArgument1; // r14d
  __int64 v91; // rcx
  __int64 v92; // rbx
  PKDPC v93; // r13
  _SINGLE_LIST_ENTRY *p_DpcListEntry; // rsi
  __int64 v95; // r15
  int DpcData; // ebx
  unsigned __int64 v97; // rcx
  unsigned __int64 v98; // rax
  int v99; // eax
  unsigned int v100; // eax
  PKDEFERRED_ROUTINE v101; // rbx
  PKDPC v102; // r14
  __int64 v103; // rsi
  signed __int32 v104[8]; // [rsp+0h] [rbp-100h] BYREF
  va_list v105; // [rsp+60h] [rbp-A0h]
  int v106; // [rsp+68h] [rbp-98h]
  struct _PROCESSOR_NUMBER ProcNumber[2]; // [rsp+70h] [rbp-90h] BYREF
  char v108; // [rsp+78h] [rbp-88h] BYREF
  __int64 v109; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  int *v112; // [rsp+B0h] [rbp-50h]
  int v113; // [rsp+B8h] [rbp-48h]
  int v114; // [rsp+BCh] [rbp-44h]
  __int64 *v115; // [rsp+C0h] [rbp-40h]
  __int64 v116; // [rsp+C8h] [rbp-38h]
  unsigned int *v117; // [rsp+D0h] [rbp-30h]
  __int64 v118; // [rsp+D8h] [rbp-28h]
  struct _PROCESSOR_NUMBER *v119; // [rsp+E0h] [rbp-20h]
  __int64 v120; // [rsp+E8h] [rbp-18h]
  const wchar_t *v121; // [rsp+F0h] [rbp-10h]
  int v122; // [rsp+F8h] [rbp-8h]
  int v123; // [rsp+FCh] [rbp-4h]
  char *v124; // [rsp+100h] [rbp+0h]
  __int64 v125; // [rsp+108h] [rbp+8h]
  const wchar_t *v126; // [rsp+110h] [rbp+10h]
  int v127; // [rsp+118h] [rbp+18h]
  int v128; // [rsp+11Ch] [rbp+1Ch]
  __int64 retaddr; // [rsp+178h] [rbp+78h]
  PKDPC v131; // [rsp+190h] [rbp+90h] BYREF
  va_list va; // [rsp+190h] [rbp+90h]
  unsigned __int64 v133; // [rsp+198h] [rbp+98h]
  _DWORD *v134; // [rsp+1A0h] [rbp+A0h] BYREF
  va_list va1; // [rsp+1A0h] [rbp+A0h]
  _DWORD *v136; // [rsp+1A8h] [rbp+A8h]
  __int64 v137; // [rsp+1B0h] [rbp+B0h]
  _DWORD *v138; // [rsp+1B8h] [rbp+B8h]
  __int64 v139; // [rsp+1C0h] [rbp+C0h]
  __int64 v140; // [rsp+1C8h] [rbp+C8h]
  _DWORD *v141; // [rsp+1D0h] [rbp+D0h]
  va_list va2; // [rsp+1D8h] [rbp+D8h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v131 = va_arg(va1, PKDPC);
  v2 = v131;
  v133 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v134 = va_arg(va2, _DWORD *);
  v136 = va_arg(va2, _DWORD *);
  v137 = va_arg(va2, _QWORD);
  v138 = va_arg(va2, _DWORD *);
  v139 = va_arg(va2, _QWORD);
  v140 = va_arg(va2, _QWORD);
  v141 = va_arg(va2, _DWORD *);
  v3 = 0;
  v4 = (int)a1;
  v106 = (int)a1;
  v5 = a2;
  v105 = 0;
  v6 = 0;
  v7 = 0;
  if ( !a2 )
    goto LABEL_18;
  v8 = (unsigned int **)*(a2 - 2);
  if ( !v8 )
    goto LABEL_18;
  v9 = *v8;
  if ( !*v8 )
    goto LABEL_18;
  a1 = (va_list)*v9;
  if ( ((_DWORD)v8[31] & 1) != 0 )
  {
    if ( (_DWORD)a1 == 1314275652 )
      v7 = *v8;
    goto LABEL_18;
  }
  if ( (_DWORD)a1 != 1094997074 )
    goto LABEL_18;
  v10 = -1073741822;
  if ( !DisableExtensionDriver )
  {
    if ( EnableExtensionCalls )
    {
      _InterlockedIncrement(&ExtRefCount);
      v10 = ((__int64 (__fastcall *)(__int64 *, _QWORD, unsigned int *, PKDPC *))ExtNotificationReplace)(
              &qword_1401761E8,
              (unsigned int)v4,
              v9,
              (PKDPC *)va);
      _InterlockedDecrement(&ExtRefCount);
    }
    v5 = a2;
  }
  v105 = 0;
  if ( v10 == -1073741822 )
  {
    va_copy(a1, va);
    v6 = v9;
    if ( !DisableExtensionDriver )
    {
      if ( EnableExtensionCalls )
      {
        _InterlockedIncrement(&ExtRefCount);
        ((void (__fastcall *)(__int64 *, _QWORD, unsigned int *, PKDPC *))ExtNotificationPre)(
          &qword_1401761E8,
          (unsigned int)v4,
          v9,
          (PKDPC *)va);
        _InterlockedDecrement(&ExtRefCount);
      }
      v5 = a2;
    }
    v105 = 0;
LABEL_18:
    va_copy(v11, va);
    if ( v4 <= 4096 )
    {
      if ( v4 != 4096 )
      {
        switch ( v4 )
        {
          case 0:
            if ( v6 && v131 )
            {
              if ( LOBYTE(v131->Number) == 40 )
                p_DeferredContext = &v131[1].DeferredContext;
              else
                p_DeferredContext = &v131->SystemArgument2;
              if ( *p_DeferredContext )
              {
                RaidAdapterRequestComplete(v6, *p_DeferredContext, 0, v5);
                goto LABEL_176;
              }
            }
            else if ( v7 && v131 )
            {
              p_SystemArgument2 = &v131[1].DeferredContext;
              if ( LOBYTE(v131->Number) != 40 )
                p_SystemArgument2 = &v131->SystemArgument2;
              v14 = (struct _SLIST_ENTRY *)*p_SystemArgument2;
              if ( v14 )
              {
                if ( (qword_140176450 & 8) != 0 )
                  RaidLogMiniportCompletion(v14, (PKDPC *)va);
                Next = v14[10].Next;
                if ( Next )
                {
                  if ( *((_BYTE *)&Next[8].Next + 13) == 0xAB || *((_BYTE *)&Next[8].Next + 13) == 0xAC )
                  {
                    if ( (unsigned int)dword_140176178 > 5
                      && (qword_140176188 & 0x400000000000LL) != 0
                      && (qword_140176190 & 0x400000000000LL) == qword_140176190 )
                    {
                      v16 = (const wchar_t *)*((_QWORD *)v7 + 129);
                      v115 = &v109;
                      v117 = v7 + 262;
                      v17 = -1;
                      ProcNumber[0] = (struct _PROCESSOR_NUMBER)v7[14];
                      v119 = ProcNumber;
                      v109 = 0x1000000;
                      v116 = 8;
                      v118 = 16;
                      v120 = 4;
                      if ( v16 )
                      {
                        v18 = -1;
                        do
                          v19 = v16[++v18] == 0;
                        while ( !v19 );
                        v20 = 2 * v18 + 2;
                      }
                      else
                      {
                        v16 = &word_140155F3C;
                        v20 = 2;
                      }
                      v19 = (v7[38] & 1) == 0;
                      v122 = v20;
                      v21 = 20;
                      v121 = v16;
                      if ( v19 )
                        v21 = 17;
                      v123 = 0;
                      v108 = v21;
                      v125 = 1;
                      v124 = &v108;
                      v22 = (const wchar_t *)*((_QWORD *)v7 + 130);
                      if ( v22 )
                      {
                        do
                          v19 = v22[++v17] == 0;
                        while ( !v19 );
                        v23 = 2 * v17 + 2;
                      }
                      else
                      {
                        v22 = &word_140155F3C;
                        v23 = 2;
                      }
                      v126 = v22;
                      *(_DWORD *)&EventDescriptor.Level = 5;
                      UserData.Ptr = (unsigned __int64)off_140176180;
                      v127 = v23;
                      EventDescriptor.Keyword = 0x400000000000LL;
                      v128 = 0;
                      *(_DWORD *)&EventDescriptor.Id = 184549376;
                      UserData.Size = *(unsigned __int16 *)off_140176180;
                      v112 = &dword_14016917C;
                      v114 = 1;
                      UserData.Reserved = 2;
                      v113 = 119;
                      LODWORD(v105) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                      EtwWriteEx(RegHandle, &EventDescriptor, 0, 1u, 0, 0, 8u, &UserData);
                    }
                    break;
                  }
                  *((_BYTE *)&Next[8].Next + 13) = -85;
                }
                LOBYTE(v14[1].Next) = (__int64)v14[1].Next & 0xE3 | 0x10;
                if ( KeGetCurrentIrql() > 2u )
                {
                  ExpInterlockedPushEntrySList((PSLIST_HEADER)v7 + 70, v14 + 2);
                  KeInsertQueueDpc((PRKDPC)(*((_QWORD *)v7 + 1) + 200LL), 0, 0);
                }
                else
                {
                  ((void (__fastcall *)(struct _SLIST_ENTRY *))v14[41].Next)(v14);
                }
                break;
              }
            }
            break;
          case 3:
            if ( !v6 )
              break;
            DbgLogRequest((_DWORD)v6, 39, (_DWORD)v6, v6[14], retaddr, v6[146], 0);
            v26 = v6[146];
            if ( (Microsoft_Windows_StorPortEnableBits & 2) != 0 )
              McTemplateK0pqq_EtwWriteTransfer(v24, (unsigned int)EventResetDetected, v25, (_DWORD)a2, v6[14], v6[146]);
            if ( !v26 )
              break;
            if ( v26 > 0x3D0900 )
              v26 = 4000000;
            v27 = v26 / 0xF4240 + 1;
            if ( v26 == 1000000 * (v26 / 0xF4240) )
              v27 = v26 / 0xF4240;
            StorPortPause(a2, v27);
            goto LABEL_176;
          case 6:
            if ( !v6 )
              break;
            v30 = v131;
            v31 = v133;
            if ( (Microsoft_Windows_StorPortEnableBits & 2) != 0 )
              McTemplateK0pqq_EtwWriteTransfer(
                (_DWORD)a1,
                (unsigned int)EventRequestTimerCall,
                0x40000000u,
                (_DWORD)v5,
                v6[14],
                v133);
            if ( KeGetCurrentIrql() > 2u )
            {
              if ( _InterlockedCompareExchange((volatile signed __int32 *)v6 + 304, 134684676, 134684677) != 134684677
                || v6 == (unsigned int *)-1200LL )
              {
                _InterlockedIncrement(&RaidUnloggedErrors);
              }
              else
              {
                v6[308] = 1;
                *((_QWORD *)v6 + 155) = v30;
                v6[312] = v31;
                ExpInterlockedPushEntrySList((PSLIST_HEADER)v6 + 73, (PSLIST_ENTRY)v6 + 75);
                KeInsertQueueDpc((PRKDPC)(v6 + 270), v6 + 268, 0);
              }
            }
            else
            {
              RaidAdapterRequestTimer(v6, v30, v31);
            }
            goto LABEL_176;
          case 7:
            if ( !v6 )
              break;
            DbgLogRequest((_DWORD)v6, 38, (_DWORD)v6, v6[14], retaddr, v6[146], 0);
            if ( (Microsoft_Windows_StorPortEnableBits & 2) != 0 )
              McTemplateK0pq_EtwWriteTransfer(v28, EventBusChangeDetected, v29, a2, v6[14]);
            *(_WORD *)((char *)v6 + 105) = 257;
            KeInsertQueueDpc((PRKDPC)(v6 + 494), 0, 0);
            goto LABEL_176;
          case 8:
            v32 = v133;
            v33 = v131;
            if ( (_BYTE)v133 == 0xFF )
            {
              v34 = 0;
            }
            else
            {
              v34 = (char)v134;
              v3 = (char)v136;
            }
            if ( !v131 )
              break;
            if ( v131->TargetInfoAsUlong > 0x80 )
              break;
            if ( !v6 )
              break;
            DeferredItem = (_BYTE *)RaidAllocateDeferredItem(v6 + 364, (PKDPC *)va);
            if ( !DeferredItem )
              break;
            DeferredItem[32] = v32;
            if ( v32 != -1 )
            {
              DeferredItem[33] = v34;
              DeferredItem[34] = v3;
            }
            memmove(DeferredItem + 40, v33, v33->TargetInfoAsUlong);
            RaidQueueDeferredItem(v6 + 364);
            v105 = 0;
            goto LABEL_175;
          case 10:
            if ( !v6 )
              break;
            if ( (Microsoft_Windows_StorPortEnableBits & 2) != 0 )
              McTemplateK0pq_EtwWriteTransfer(a1, EventLinkUp, 0x140000000uLL, *((_QWORD *)v6 + 75) + 16LL, v6[14]);
            _InterlockedExchange((volatile __int32 *)v6 + 535, 1);
            if ( !(unsigned __int8)StorPortResume(*((_QWORD *)v6 + 75) + 16LL, v11) )
              break;
            IoInvalidateDeviceRelations(*((PDEVICE_OBJECT *)v6 + 4), BusRelations);
            goto LABEL_176;
          case 11:
            if ( !v6 )
              break;
            if ( (Microsoft_Windows_StorPortEnableBits & 2) != 0 )
              McTemplateK0pqq_EtwWriteTransfer(
                (_DWORD)a1,
                (unsigned int)EventLinkDown,
                0x40000000u,
                *((_QWORD *)v6 + 75) + 16,
                v6[14],
                v6[534]);
            if ( !(unsigned __int8)StorPortPause(*((_QWORD *)v6 + 75) + 16LL, v6[534]) )
              break;
            _InterlockedExchange((volatile __int32 *)v6 + 535, 0);
            goto LABEL_176;
          case 12:
            *(_QWORD *)&v131->TargetInfoAsUlong = MEMORY[0xFFFFF78000000320];
            break;
          case 13:
            KeBugCheckEx(0xF7u, 0, 0, 0, 0);
          case 14:
            RaidHandleTraceNotifyType(a1, (unsigned int)v131, v133, v5);
            break;
          case 15:
            if ( v7 )
              break;
            v36 = v131;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
                    }
                  }
                }
              }
            }
            if ( !v36 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
              }
              break;
            }
            if ( v6 )
            {
              *(_OWORD *)(v6 + 1158) = StorportExtensionTable;
              *(_OWORD *)(v6 + 1162) = xmmword_1401770B0;
              *(_OWORD *)(v6 + 1166) = xmmword_1401770C0;
              *(_OWORD *)(v6 + 1170) = xmmword_1401770D0;
              *(_OWORD *)(v6 + 1174) = xmmword_1401770E0;
              *((_QWORD *)v6 + 589) = qword_1401770F0;
              *(_QWORD *)&v36->TargetInfoAsUlong = v6 + 1158;
              goto LABEL_176;
            }
            *(_QWORD *)&v36->TargetInfoAsUlong = &StorportExtensionTable;
            return;
          default:
            break;
        }
LABEL_174:
        v105 = 0;
        if ( !v6 )
          return;
        goto LABEL_175;
      }
      v37 = (int **)*(v5 - 2);
      v38 = (PKDEFERRED_ROUTINE)v133;
      if ( v37 )
      {
        v39 = *v37;
        if ( *v37 )
        {
          v40 = *v39;
          if ( ((_DWORD)v37[31] & 1) != 0 )
          {
            if ( v40 == 1314275652 )
            {
              if ( (v39[38] & 0x20) != 0 )
              {
                *((_QWORD *)v39 + 123) = v131;
                *(_DWORD *)v38 = 1;
                goto LABEL_174;
              }
              v41 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                v42 = 24;
LABEL_139:
                WPP_SF_(v41->AttachedDevice, v42, WPP_5c734f4f545033e286c5cb1278f67486_Traceguids);
              }
            }
          }
          else if ( v40 == 1094997074 )
          {
            if ( (v39[26] & 0x10) != 0 )
            {
              *((_QWORD *)v39 + 549) = v131;
              *(_DWORD *)v38 = 1;
              goto LABEL_174;
            }
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              v42 = 23;
              goto LABEL_139;
            }
          }
        }
      }
      *(_DWORD *)v38 = 0;
      goto LABEL_174;
    }
    if ( v4 <= 0x2000 )
    {
      if ( v4 != 0x2000 )
      {
        switch ( v4 )
        {
          case 4097:
            v45 = v131;
            if ( v131 && v133 )
            {
              KeInitializeDpc(v131, (PKDEFERRED_ROUTINE)v133, v5);
              KeInitializeSpinLock((PKSPIN_LOCK)&v45[1].TargetInfoAsUlong);
            }
            goto LABEL_174;
          case 4098:
            if ( v131 )
            {
              v52 = v136;
              *v52 = KeInsertQueueDpc(v131, (PVOID)v133, v134);
            }
            goto LABEL_174;
          case 4099:
            v53 = *(v5 - 2);
            v54 = (int)v131;
            if ( v53 && (v55 = *(_DWORD **)v53) != 0 && (*(_DWORD *)(v53 + 248) & 1) == 0 && *v55 == 1094997074
              || (_DWORD)v131 != 3 && (v55 = 0, (_DWORD)v131 != 2) )
            {
              v56 = v134;
              if ( v134 )
              {
                v57 = (PKDEFERRED_ROUTINE)v133;
                *v134 = (_DWORD)v131;
                v58 = v54 - 1;
                if ( v58 )
                {
                  v59 = v58 - 1;
                  if ( v59 )
                  {
                    if ( v59 == 1 )
                      *((_BYTE *)v56 + 24) = RaidAdapterAcquireInterruptLock(v55, (PKDPC *)va);
                    else
                      *v56 = 0;
                  }
                  else
                  {
                    RaidAdapterAcquireStartIoLock(v55, v56 + 2);
                  }
                }
                else if ( v57 )
                {
                  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v57 + 8, (PKLOCK_QUEUE_HANDLE)(v56 + 2));
                }
              }
            }
            goto LABEL_174;
          case 4100:
            v60 = *(v5 - 2);
            v61 = 0;
            if ( v60 && *(_QWORD *)v60 && (*(_DWORD *)(v60 + 248) & 1) == 0 && **(_DWORD **)v60 == 1094997074 )
              v61 = *(_DWORD **)v60;
            if ( v131 )
            {
              TargetInfoAsUlong = v131->TargetInfoAsUlong;
              if ( v131->TargetInfoAsUlong )
              {
                if ( v61 || TargetInfoAsUlong - 2 > 1 )
                {
                  v63 = TargetInfoAsUlong - 1;
                  if ( v63 )
                  {
                    v64 = v63 - 1;
                    if ( v64 )
                    {
                      v65 = v64 - 1;
                      if ( v65 )
                      {
                        v66 = v65 - 1;
                        if ( v66 )
                        {
                          if ( v66 == 1 )
                            KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)&v131->DpcListEntry);
                        }
                        else
                        {
                          KeReleaseInStackQueuedSpinLockForDpc((PKLOCK_QUEUE_HANDLE)&v131->DpcListEntry);
                        }
                      }
                      else
                      {
                        RaidAdapterReleaseInterruptLock(v61, LOBYTE(v131->DeferredRoutine));
                      }
                    }
                    else
                    {
                      RaidAdapterReleaseStartIoLock(v61, &v131->DpcListEntry);
                    }
                  }
                  else
                  {
                    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)&v131->DpcListEntry);
                  }
                }
              }
            }
            goto LABEL_174;
          case 4101:
            if ( !v6 )
              goto LABEL_174;
            v71 = (PKDEFERRED_ROUTINE)v133;
            v72 = (__int64)v136;
            v73 = v137;
            v74 = (unsigned int)v134;
            v75 = (unsigned int)v131;
            v76 = v138;
            LODWORD(v105) = (_DWORD)v134;
            v109 = (__int64)v136;
            *(_QWORD *)&ProcNumber[0].Group = v137;
            if ( v133 && *(_WORD *)v133 == 1 )
            {
              v77 = *(_BYTE *)(v133 + 8);
              v78 = *(_BYTE *)(v133 + 9);
              v79 = *(_BYTE *)(v133 + 10);
            }
            else
            {
              v77 = -1;
              v78 = -1;
              v79 = -1;
            }
            if ( (Microsoft_Windows_StorPortEnableBits & 2) != 0 )
            {
              McTemplateK0pqquuuqpp_EtwWriteTransfer(
                (_DWORD)a1,
                (unsigned int)va,
                0,
                (_DWORD)v5,
                v6[14],
                (char)v131,
                v77,
                v78,
                v79,
                (char)v134,
                (char)v136,
                v137);
              v74 = (unsigned int)v105;
              v72 = v109;
              v73 = *(_QWORD *)&ProcNumber[0].Group;
            }
            if ( !v71
              || *(_WORD *)v71 != 1
              || v77 > *((_BYTE *)v6 + 440)
              || (v75 & 3) != 0 && v78 > *((_BYTE *)v6 + 465)
              || (v75 & 1) != 0 && v79 > *((_BYTE *)v6 + 514)
              || (v75 & 6) == 0 && (v75 & 1) == 0 )
            {
              if ( v76 )
                *v76 = -1056964602;
LABEL_258:
              v105 = 0;
              break;
            }
            if ( _InterlockedCompareExchange((volatile signed __int32 *)v6 + 1222, 1, 0) == 1 )
            {
              if ( v76 )
              {
                *v76 = -1056964607;
                v105 = 0;
                break;
              }
              goto LABEL_258;
            }
            _InterlockedOr(v104, 0);
            v6[1223] = v75;
            *((_QWORD *)v6 + 613) = v71;
            v6[1224] = v74;
            *((_QWORD *)v6 + 614) = v72;
            *((_QWORD *)v6 + 615) = v73;
            _InterlockedOr(v104, 0);
            *((_BYTE *)v6 + 104) |= 0x40u;
            *((_BYTE *)v6 + 105) = 1;
            KeInsertQueueDpc((PRKDPC)(v6 + 494), 0, 0);
            if ( !v76 )
              goto LABEL_174;
            *v76 = 0;
            v105 = 0;
            break;
          case 4102:
            if ( !v7 )
            {
              if ( StorEtwLoggingEnabled )
              {
                va_copy(v105, va1);
                if ( v133 )
                {
                  v67 = 96;
                  if ( *(_BYTE *)(v133 + 2) != 40 )
                    v67 = 48;
                  v68 = *(_QWORD *)(v67 + v133);
                  if ( v68 )
                  {
                    v69 = v131;
                    if ( (byte_140177431 & 1) != 0 || (byte_140177433 & 2) != 0 )
                      *(_QWORD *)(v68 + 720) = v131;
                    if ( (byte_140177431 & 1) != 0 )
                    {
                      LOBYTE(v11) = 1;
                      StorEtwIORequestServiceTimeEventData(v68, v11, v69, v5);
                    }
                    v70 = *(_QWORD *)(v68 + 224);
                    if ( v70 && *(_DWORD *)(v70 + 1940) && (byte_140177433 & 2) != 0 )
                    {
                      LOBYTE(v11) = 1;
                      StorEtwLogoRequestServiceTimeEventData(v68, v11, v69, v5);
                    }
                  }
                }
              }
            }
            goto LABEL_174;
          case 4103:
            v80 = v134;
            ProcNumber[0] = 0;
            if ( v6 )
            {
              if ( !v131
                || LOWORD(v131->TargetInfoAsUlong) != 1
                || (v81 = (PKDEFERRED_ROUTINE)v133, (v133 & 0xFFFFFFFFFFFFFFF8uLL) != 0) )
              {
                *v134 = -1056964602;
                goto LABEL_176;
              }
              ProcNumber[0].Group = (unsigned __int16)v131->DpcListEntry.Next;
              ProcNumber[0].Number = BYTE2(v131->DpcListEntry.Next);
              v82 = ProcNumber[0];
              Unit = RaidAdapterFindUnit(v6, *(_DWORD *)ProcNumber, 0x140000000uLL, v5);
              v84 = Unit;
              if ( !Unit || (*(_DWORD *)(Unit + 1952) & 4) == 0 )
              {
                *v80 = -1056964601;
                v105 = 0;
                break;
              }
              v85 = Unit + 1992;
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(Unit + 2008), 1, 0) == 1 )
              {
                *v80 = -1056964596;
                v105 = 0;
                break;
              }
              if ( KeGetCurrentIrql() > 2u )
              {
                if ( _InterlockedCompareExchange((volatile signed __int32 *)(v84 + 1760), 134684676, 134684677) != 134684677
                  || v84 == -1744 )
                {
                  *v80 = -1056964596;
                }
                else
                {
                  *(_DWORD *)(v84 + 1776) = 12;
                  *(struct _PROCESSOR_NUMBER *)(v84 + 1780) = v82;
                  *(_QWORD *)(v84 + 1784) = v85;
                  *(_QWORD *)(v84 + 2000) = v81;
                  ExpInterlockedPushEntrySList((PSLIST_HEADER)v6 + 73, (PSLIST_ENTRY)(v84 + 1744));
                  KeInsertQueueDpc((PRKDPC)(v6 + 270), v6 + 268, 0);
                  *v80 = 0;
                }
              }
              else
              {
                *(_QWORD *)(v85 + 8) = v81;
                *v80 = RaidUnitProcessAsyncNotification(v6, *(unsigned int *)&v82, v85);
              }
            }
            else
            {
              *v134 = -1056964602;
            }
            goto LABEL_174;
          case 4104:
            if ( v6 && v131 )
            {
              if ( LOBYTE(v131->Number) == 40 )
                v43 = &v131[1].DeferredContext;
              else
                v43 = &v131->SystemArgument2;
              if ( *v43 )
              {
                RaidAdapterRequestDirectComplete(v6, *v43, 0x140000000uLL, v5);
                goto LABEL_176;
              }
            }
            else if ( v7 && v131 )
            {
              v44 = LOBYTE(v131->Number) == 40 ? &v131[1].DeferredContext : &v131->SystemArgument2;
              if ( *v44 )
                NvmeAdapterRequestDirectComplete(v7, *v44, 0x140000000uLL, v5);
            }
            goto LABEL_174;
          case 4105:
            v46 = v131;
            if ( !v131 )
              goto LABEL_174;
            if ( !v133 )
              goto LABEL_174;
            v47 = (int)v136;
            KeInitializeDpc(v131, (PKDEFERRED_ROUTINE)v133, v134);
            if ( v47 == LowImportance )
              goto LABEL_174;
            v48 = v47;
            v49 = v46;
            goto LABEL_173;
          case 4106:
            v50 = v131;
            if ( !v131 )
              goto LABEL_174;
            if ( !v133 )
              goto LABEL_174;
            v51 = (char)v136;
            KeInitializeThreadedDpc(v131, (PKDEFERRED_ROUTINE)v133, v134);
            if ( !v51 )
              goto LABEL_174;
            v48 = HighImportance;
            v49 = v50;
LABEL_173:
            KeSetImportanceDpc(v49, v48);
            goto LABEL_174;
          case 4107:
            if ( v131 && v133 )
              KeSetTargetProcessorDpcEx(v131, (PPROCESSOR_NUMBER)v133);
            goto LABEL_174;
          case 4108:
            if ( !v6 || !v134 )
              goto LABEL_174;
            StorpMarkDeviceFailed((_DWORD)v6, (_DWORD)v131, v133, 0xFFFF, (__int64)v134, 0, 0, 0, 0);
            goto LABEL_176;
          case 4109:
            v86 = v141;
            if ( v6 && (_WORD)v134 && v136 )
            {
              StorpMarkDeviceFailed(
                (_DWORD)v6,
                (_DWORD)v131,
                v133,
                (unsigned __int16)v134,
                (__int64)v136,
                v137,
                (__int64)v138,
                v139,
                v140);
              *v86 = 0;
            }
            else
            {
              *v141 = -1056964602;
            }
            goto LABEL_174;
          case 4110:
            if ( !v7 )
            {
              if ( v6 )
                _InterlockedDecrement((volatile signed __int32 *)v6 + 1520);
              PsTerminateSystemThread(0);
            }
            goto LABEL_174;
          case 4111:
            if ( v7 )
            {
              v87 = v131;
              if ( LOWORD(v131->TargetInfoAsUlong) == 1 )
              {
                Number = v131->Number;
                if ( Number >= 0x30u && LODWORD(v131->DpcListEntry.Next) == 2 )
                {
                  DeferredContext = v131->DeferredContext;
                  if ( DeferredContext )
                  {
                    if ( Number >= 0x72u
                      && WORD2(v131->SystemArgument1) >= 0x42u
                      && *DeferredContext == 1314276178
                      && DeferredContext[142] == 2 )
                    {
                      SystemArgument1 = (int)v131->SystemArgument1;
                      if ( _interlockedbittestandset(DeferredContext + 270, 5u) != 1 )
                      {
                        v19 = (DeferredContext[346] & 0x20) == 0;
                        DeferredContext[142] = 4;
                        DeferredContext[304] = 35;
                        if ( !v19 )
                          NvmeDbgLogCriticalEvent((_DWORD)DeferredContext, 2, SystemArgument1, 0, 0, 0);
                        **((_DWORD **)DeferredContext + 13) = SystemArgument1;
                        v91 = *((_QWORD *)DeferredContext + 13);
                        *(_OWORD *)(v91 + 4) = *(_OWORD *)((char *)&v87->SystemArgument1 + 6);
                        *(_OWORD *)(v91 + 20) = *(_OWORD *)((char *)&v87->DpcData + 6);
                        *(_OWORD *)(v91 + 36) = *(_OWORD *)((char *)&v87[1].DpcListEntry.Next + 6);
                        *(_OWORD *)(v91 + 52) = *(_OWORD *)((char *)&v87[1].DeferredRoutine + 6);
                        *(_WORD *)(v91 + 68) = HIWORD(v87[1].SystemArgument1);
                        IoQueueWorkItem(
                          *((PIO_WORKITEM *)DeferredContext + 21),
                          NvmeAdapterFabricNvmeControllerTransportErrorWork,
                          DelayedWorkQueue,
                          DeferredContext);
                      }
                    }
                  }
                }
              }
            }
            goto LABEL_174;
          case 4112:
            if ( v7 )
            {
              if ( v131 )
              {
                v92 = *(_QWORD *)&v131[-1].TargetInfoAsUlong;
                if ( ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v92 + 552)) )
                {
                  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v92 + 976), 1, 0) )
                    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v92 + 552));
                  else
                    IoQueueWorkItemEx(
                      *(PIO_WORKITEM *)(v92 + 176),
                      NvmeAdapterStorMQControllerInitializeWorker,
                      DelayedWorkQueue,
                      (PVOID)v92);
                }
              }
            }
            goto LABEL_174;
          case 4113:
            if ( !v6 )
              goto LABEL_174;
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                 a1,
                                 (PKDPC *)va,
                                 0x140000000uLL,
                                 v5) )
            {
              if ( !*((_QWORD *)v6 + 710) )
                goto LABEL_174;
            }
            else if ( !*((_QWORD *)v6 + 711) )
            {
              goto LABEL_174;
            }
            RaidAdapterClearCryptoKeyTable(v6);
            goto LABEL_176;
          default:
            goto LABEL_174;
        }
LABEL_175:
        v4 = v106;
        goto LABEL_176;
      }
      if ( !v6 )
        goto LABEL_174;
      v93 = v131;
      if ( !v131 )
        goto LABEL_174;
      p_DpcListEntry = &v131[-2].DpcListEntry;
      v95 = *(_QWORD *)&v131[1].TargetInfoAsUlong;
      DpcData = (int)v131[-2].DpcData;
      LODWORD(v2) = HIDWORD(KeGetPcr()[1].LockArray);
      if ( (_BYTE)v133 == 1 )
      {
        v97 = *(unsigned int *)(v95 + 8);
        if ( DpcData < 0 )
        {
          v98 = (unsigned __int64)&p_DpcListEntry[7].Next[0x8000];
          if ( v98 < v97 )
          {
            p_DpcListEntry[7].Next = (_SINGLE_LIST_ENTRY *)v98;
            LOBYTE(v2) = 1;
            RaidUnitSubmitIrpRequest(*(_QWORD *)(*(_QWORD *)(v95 + 40) + 64LL), &v93[-2].DpcListEntry, v2, v5);
            goto LABEL_176;
          }
        }
        p_DpcListEntry[7].Next = (_SINGLE_LIST_ENTRY *)v97;
        LODWORD(p_DpcListEntry[6].Next) = 0;
      }
      else
      {
        v99 = RaidSrbStatusToNtStatus((unsigned __int8)v133, (PKDPC *)va, v2, v5);
        LODWORD(p_DpcListEntry[6].Next) = v99;
        p_DpcListEntry[7].Next = 0;
        if ( v99 == -1073741790 && *(_BYTE *)v95 == 4 )
          LODWORD(p_DpcListEntry[6].Next) = -1073741662;
      }
      if ( ((_DWORD)v2 == (DpcData & 0x7FFFFFFF) || (*((_BYTE *)v6 + 4435) & 2) != 0) && KeGetCurrentIrql() == 2 )
      {
        RaidUnitCompleteIrpRequest((PIRP)&v93[-2].DpcListEntry);
      }
      else
      {
        *(_DWORD *)(v95 + 24) = DpcData;
        v100 = v6[152];
        ProcNumber[0] = 0;
        if ( (v100 & 4) != 0 )
          _InterlockedIncrement((volatile signed __int32 *)v6 + 1288);
        *(_BYTE *)((((unsigned __int64)&v93->DpcListEntry.Next + 7) & 0xFFFFFFFFFFFFFFF0uLL) + 8) = ((_BYTE)v93 + 0x80) & 0xF;
        if ( KeGetProcessorNumberFromIndex(DpcData & 0x7FFFFFFF, ProcNumber) < 0 )
          goto LABEL_340;
        if ( (*((_BYTE *)v6 + 4435) & 2) != 0 )
          KeGetCurrentProcessorNumberEx(ProcNumber);
        if ( ProcNumber[0].Group >= (unsigned int)g_RaidPerfRedirectGroupCount
          || (unsigned int)ProcNumber[0].Number >= *((_DWORD *)g_RaidDPCRedirectionProcessors + ProcNumber[0].Group) )
        {
LABEL_340:
          ExpInterlockedPushEntrySList(
            (PSLIST_HEADER)v6 + 17,
            (PSLIST_ENTRY)(((unsigned __int64)&v93->DpcListEntry.Next + 7) & 0xFFFFFFFFFFFFFFF0uLL));
          KeInsertQueueDpc((PRKDPC)(*((_QWORD *)v6 + 1) + 200LL), 0, 0);
        }
        else
        {
          if ( ExpInterlockedPushEntrySList(
                 (PSLIST_HEADER)g_RaidPerProcessorState
               + 8 * (unsigned __int64)(ProcNumber[0].Number + (ProcNumber[0].Group << 6))
               + 5,
                 (PSLIST_ENTRY)(((unsigned __int64)&v93->DpcListEntry.Next + 7) & 0xFFFFFFFFFFFFFFF0uLL)) )
          {
            goto LABEL_174;
          }
          if ( *((_DWORD *)g_RaidPerProcessorState
               + 32 * (unsigned __int64)(ProcNumber[0].Number + (ProcNumber[0].Group << 6))
               + 24) != 2 )
            KeInsertQueueDpc(
              (PRKDPC)g_RaidPerProcessorState
            + 2 * (unsigned __int64)(ProcNumber[0].Number + (ProcNumber[0].Group << 6)),
              *((PVOID *)v6 + 1),
              0);
        }
      }
      goto LABEL_175;
    }
    if ( v4 > 8197 )
    {
      if ( v4 == 0x8000 )
      {
        if ( !v6 )
          goto LABEL_174;
        RaProcessMFNDChildControllerEvent(v6, v131, v2, v5);
      }
      else if ( v4 == 32769 )
      {
        if ( !v6
          || !v131
          || LOWORD(v131->TargetInfoAsUlong) != 1
          || *((_DWORD *)&v131->0 + 1) < 0x210u
          || HIDWORD(v131->DpcListEntry.Next) < 0x200 )
        {
          goto LABEL_174;
        }
        StorLogNVMeErrorRecoveryInfo(v6, &v131->ProcessorHistory, v2, v5);
      }
      else
      {
        if ( v4 != 32770 || !v6 )
          goto LABEL_174;
        RaProcessStorageEventNotification(v6, v131, v2, v5);
      }
    }
    else
    {
      if ( v4 == 8197 )
      {
LABEL_346:
        if ( !v6 )
          goto LABEL_174;
        StorNvmeNotifyCallbacks((PKSPIN_LOCK)v6 + 788);
        goto LABEL_176;
      }
      if ( v4 != 8193 )
      {
        if ( v4 == 8194 )
        {
          if ( !v7 )
          {
            if ( StorEtwLoggingEnabled )
            {
              v101 = (PKDEFERRED_ROUTINE)v133;
              if ( v133 )
              {
                v102 = v131;
                v103 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v133 + 64) + 40LL) + 64LL);
                if ( (byte_140177431 & 1) != 0 )
                {
                  LOBYTE(v11) = 1;
                  StorEtwIOIrpRequestServiceTimeEventData(v133 - 120, v11, v131, v5);
                }
                if ( v103 && *(_DWORD *)(v103 + 1940) && (byte_140177433 & 2) != 0 )
                {
                  LOBYTE(v11) = 1;
                  StorEtwLogoIrpRequestServiceTimeEventData((char *)v101 - 120, v11, v102, v5);
                }
              }
            }
          }
          goto LABEL_174;
        }
        if ( (unsigned int)(v4 - 8195) > 1 )
          goto LABEL_174;
        goto LABEL_346;
      }
      if ( !v6 || !v131 || !v133 )
        goto LABEL_174;
      RaUnitFillIrpData(&v131[-2].DpcListEntry, v133, v2, v5);
    }
LABEL_176:
    if ( !DisableExtensionDriver )
    {
      if ( EnableExtensionCalls )
      {
        _InterlockedIncrement(&ExtRefCount);
        ((void (__fastcall *)(__int64 *, _QWORD, unsigned int *, PKDPC *))ExtNotificationPost)(
          &qword_1401761E8,
          (unsigned int)v4,
          v6,
          (PKDPC *)va);
        _InterlockedDecrement(&ExtRefCount);
      }
    }
  }
}

```

## disassembly

```asm
0x140058bd0  mov     [rsp-8+arg_8], rdx
0x140058bd5  mov     [rsp-8+arg_10], r8
0x140058bda  mov     [rsp-8+arg_18], r9
0x140058bdf  push    rbp
0x140058be0  push    rbx
0x140058be1  push    rsi
0x140058be2  push    rdi
0x140058be3  push    r12
0x140058be5  push    r14
0x140058be7  lea     rbp, [rsp-48h]
0x140058bec  sub     rsp, 148h
0x140058bf3  mov     rax, cs:__security_cookie
0x140058bfa  xor     rax, rsp
0x140058bfd  mov     [rbp+70h+var_50], rax
0x140058c01  xor     r12d, r12d
0x140058c04  movsxd  r14, ecx
0x140058c07  mov     [rsp+170h+var_108], r14d
0x140058c0c  mov     r9, rdx
0x140058c0f  mov     [rsp+170h+var_110], r12
0x140058c14  mov     edi, r12d
0x140058c17  mov     ebx, r12d
0x140058c1a  test    rdx, rdx
0x140058c1d  jz      loc_140058D34
0x140058c23  mov     rax, [rdx-10h]
0x140058c27  test    rax, rax
0x140058c2a  jz      loc_140058D34
0x140058c30  mov     rsi, [rax]
0x140058c33  test    rsi, rsi
0x140058c36  jz      loc_140058D34
0x140058c3c  mov     eax, [rax+0F8h]
0x140058c42  mov     ecx, [rsi]
0x140058c44  test    al, 1
0x140058c46  jz      short loc_140058C5C
0x140058c48  cmp     ecx, 4E564144h
0x140058c4e  jnz     loc_140058D34
0x140058c54  mov     rbx, rsi
0x140058c57  jmp     loc_140058D34
0x140058c5c  cmp     ecx, 41445452h
0x140058c62  jnz     loc_140058D34
0x140058c68  cmp     cs:DisableExtensionDriver, bl
0x140058c6e  lea     rdx, [rbp+70h+arg_10]
0x140058c75  mov     ecx, 0C0000002h
0x140058c7a  jnz     short loc_140058CC5
0x140058c7c  movzx   eax, cs:EnableExtensionCalls
0x140058c83  test    al, al
0x140058c85  jz      short loc_140058CBE
0x140058c87  lock inc cs:ExtRefCount
0x140058c8e  movzx   eax, cs:EnableExtensionCalls
0x140058c95  test    al, al
0x140058c97  jz      short loc_140058CB7
0x140058c99  mov     rax, cs:ExtNotificationReplace
0x140058ca0  lea     rcx, qword_1401761E8
0x140058ca7  mov     r9, rdx
0x140058caa  mov     r8, rsi
0x140058cad  mov     edx, r14d
0x140058cb0  call    _guard_dispatch_icall
0x140058cb5  mov     ecx, eax
0x140058cb7  lock dec cs:ExtRefCount
0x140058cbe  mov     r9, [rbp+70h+arg_8]
0x140058cc5  mov     [rsp+170h+var_110], r12
0x140058cca  cmp     ecx, 0C0000002h
0x140058cd0  jnz     loc_1400597DE
0x140058cd6  cmp     cs:DisableExtensionDriver, bl
0x140058cdc  lea     rcx, [rbp+70h+arg_10]
0x140058ce3  mov     rdi, rsi
0x140058ce6  jnz     short loc_140058D2F
0x140058ce8  movzx   eax, cs:EnableExtensionCalls
0x140058cef  test    al, al
0x140058cf1  jz      short loc_140058D28
0x140058cf3  lock inc cs:ExtRefCount
0x140058cfa  movzx   eax, cs:EnableExtensionCalls
0x140058d01  test    al, al
0x140058d03  jz      short loc_140058D21
0x140058d05  mov     rax, cs:ExtNotificationPre
0x140058d0c  mov     r9, rcx
0x140058d0f  lea     rcx, qword_1401761E8
0x140058d16  mov     r8, rsi
0x140058d19  mov     edx, r14d
0x140058d1c  call    _guard_dispatch_icall
0x140058d21  lock dec cs:ExtRefCount
0x140058d28  mov     r9, [rbp+70h+arg_8]
0x140058d2f  mov     [rsp+170h+var_110], r12
0x140058d34  mov     [rsp+170h+var_30], r13
0x140058d3c  lea     rdx, [rbp+70h+arg_10]
0x140058d43  mov     [rsp+170h+var_38], r15
0x140058d4b  cmp     r14d, 1000h
0x140058d52  jg      loc_140059653
0x140058d58  jz      loc_140059580
0x140058d5e  cmp     r14d, 0Fh; switch 16 cases
0x140058d62  ja      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058d68  lea     r8, cs:140000000h
0x140058d6f  mov     rax, r12
0x140058d72  mov     ecx, ds:(jpt_140058D7D - 140000000h)[r8+r14*4]
0x140058d7a  add     rcx, r8
0x140058d7d  jmp     rcx; switch jump
0x140058d83  mov     rax, [rdx]; jumptable 0000000140058D7D case 0
0x140058d86  test    rdi, rdi
0x140058d89  jz      short loc_140058DBC
0x140058d8b  test    rax, rax
0x140058d8e  jz      short loc_140058DBC
0x140058d90  cmp     byte ptr [rax+2], 28h ; '('
0x140058d94  jnz     short loc_140058D9C
0x140058d96  add     rax, 60h ; '`'
0x140058d9a  jmp     short loc_140058DA0
0x140058d9c  add     rax, 30h ; '0'
0x140058da0  mov     rdx, [rax]
0x140058da3  test    rdx, rdx
0x140058da6  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058dac  xor     r8d, r8d
0x140058daf  mov     rcx, rdi
0x140058db2  call    RaidAdapterRequestComplete
0x140058db7  jmp     loc_140059781
0x140058dbc  test    rbx, rbx
0x140058dbf  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058dc5  test    rax, rax
0x140058dc8  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058dce  cmp     byte ptr [rax+2], 28h ; '('
0x140058dd2  lea     rsi, [rax+60h]
0x140058dd6  jz      short loc_140058DDC
0x140058dd8  lea     rsi, [rax+30h]
0x140058ddc  mov     rsi, [rsi]
0x140058ddf  test    rsi, rsi
0x140058de2  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058de8  mov     rax, cs:qword_140176450
0x140058def  test    al, 8
0x140058df1  jz      short loc_140058DFB
0x140058df3  mov     rcx, rsi
0x140058df6  call    RaidLogMiniportCompletion
0x140058dfb  mov     rcx, [rsi+0A0h]
0x140058e02  test    rcx, rcx
0x140058e05  jz      short loc_140058E1B
0x140058e07  movzx   eax, byte ptr [rcx+8Dh]
0x140058e0e  add     al, 55h ; 'U'
0x140058e10  cmp     al, 1
0x140058e12  jbe     short loc_140058E4E
0x140058e14  mov     byte ptr [rcx+8Dh], 0ABh
0x140058e1b  movzx   eax, byte ptr [rsi+10h]
0x140058e1f  and     al, 0F3h
0x140058e21  or      al, 10h
0x140058e23  mov     [rsi+10h], al
0x140058e26  call    cs:__imp_KeGetCurrentIrql
0x140058e2d  nop     dword ptr [rax+rax+00h]
0x140058e32  cmp     al, 2
0x140058e34  ja      loc_14005900E
0x140058e3a  mov     rax, [rsi+290h]
0x140058e41  mov     rcx, rsi
0x140058e44  call    _guard_dispatch_icall
0x140058e49  jmp     def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058e4e  mov     eax, cs:dword_140176178
0x140058e54  cmp     eax, 5
0x140058e57  jbe     def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058e5d  mov     rcx, cs:qword_140176190
0x140058e64  mov     r8, 400000000000h
0x140058e6e  mov     rax, cs:qword_140176188
0x140058e75  test    r8, rax
0x140058e78  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058e7e  mov     rax, rcx
0x140058e81  and     rax, r8
0x140058e84  cmp     rax, rcx
0x140058e87  jnz     def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140058e8d  mov     rcx, [rbx+408h]
0x140058e94  lea     rax, [rbp+70h+var_F0]
0x140058e98  mov     [rbp+70h+var_B0], rax
0x140058e9c  lea     rax, [rbx+418h]
0x140058ea3  mov     [rbp+70h+var_A0], rax
0x140058ea7  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140058eae  mov     eax, [rbx+38h]
0x140058eb1  mov     r10d, 2
0x140058eb7  mov     dword ptr [rsp+170h+ProcNumber.Group], eax
0x140058ebb  lea     rax, [rsp+170h+ProcNumber]
0x140058ec0  mov     [rbp+70h+var_90], rax
0x140058ec4  mov     [rbp+70h+var_F0], 1000000h
0x140058ecc  mov     [rbp+70h+var_A8], 8
0x140058ed4  mov     [rbp+70h+var_98], 10h
0x140058edc  mov     [rbp+70h+var_88], 4
0x140058ee4  test    rcx, rcx
0x140058ee7  jz      short loc_140058F05
0x140058ee9  mov     rax, rdx
0x140058eec  nop     dword ptr [rax+00h]
0x140058ef0  cmp     [rcx+rax*2+2], r12w
0x140058ef6  lea     rax, [rax+1]
0x140058efa  jnz     short loc_140058EF0
0x140058efc  lea     eax, ds:2[rax*2]
0x140058f03  jmp     short loc_140058F0F
0x140058f05  lea     rcx, word_140155F3C
0x140058f0c  mov     eax, r10d
0x140058f0f  test    byte ptr [rbx+98h], 1
0x140058f16  mov     [rbp+70h+var_78], eax
0x140058f19  mov     eax, 14h
0x140058f1e  mov     [rbp+70h+var_80], rcx
0x140058f22  mov     ecx, 11h
0x140058f27  cmovz   eax, ecx
0x140058f2a  mov     [rbp+70h+var_74], r12d
0x140058f2e  mov     [rsp+170h+var_F8], al
0x140058f32  mov     ecx, 1
0x140058f37  lea     rax, [rsp+170h+var_F8]
0x140058f3c  mov     [rbp+70h+var_68], rcx
0x140058f40  mov     [rbp+70h+var_70], rax
0x140058f44  mov     rax, [rbx+410h]
0x140058f4b  test    rax, rax
0x140058f4e  jz      short loc_140058F65
0x140058f50  cmp     [rax+rdx*2+2], r12w
0x140058f56  lea     rdx, [rdx+1]
0x140058f5a  jnz     short loc_140058F50
0x140058f5c  lea     edx, ds:2[rdx*2]
0x140058f63  jmp     short loc_140058F6F
0x140058f65  lea     rax, word_140155F3C
0x140058f6c  mov     edx, r10d
0x140058f6f  mov     [rbp+70h+var_60], rax
0x140058f73  mov     r9d, ecx; Flags
0x140058f76  movzx   eax, cs:word_140169172
0x140058f7d  mov     dword ptr [rbp+70h+EventDescriptor.Level], eax
0x140058f80  mov     rax, cs:off_140176180
0x140058f87  mov     [rbp+70h+var_D0.Ptr], rax
0x140058f8b  mov     [rbp+70h+var_58], edx
0x140058f8e  lea     rdx, _TraceLoggingMetadata
0x140058f95  mov     [rbp+70h+EventDescriptor.Keyword], r8
0x140058f99  xor     r8d, r8d; Filter
0x140058f9c  mov     [rbp+70h+var_54], r12d
0x140058fa0  mov     dword ptr [rbp+70h+EventDescriptor.Id], 0B000000h
0x140058fa7  movzx   eax, word ptr [rax]
0x140058faa  mov     [rbp+70h+var_D0.Size], eax
0x140058fad  lea     rax, dword_14016917C
0x140058fb4  mov     [rbp+70h+var_C0], rax
0x140058fb8  lea     rax, _TraceLoggingMetadataEnd
0x140058fbf  sub     eax, edx
0x140058fc1  mov     [rbp+70h+var_B4], ecx
0x140058fc4  mov     dword ptr [rbp+70h+var_D0.___u2], r10d
0x140058fc8  lea     rdx, [rbp+70h+EventDescriptor]; EventDescriptor
0x140058fcc  mov     [rbp+70h+var_B8], 77h ; 'w'
0x140058fd3  mov     dword ptr [rsp+170h+var_110], eax
0x140058fd7  mov     eax, dword ptr [rsp+170h+var_110]
0x140058fdb  mov     rcx, cs:RegHandle; RegHandle
0x140058fe2  lea     rax, [rbp+70h+var_D0]
0x140058fe6  mov     [rsp+170h+UserData], rax; UserData
0x140058feb  mov     [rsp+170h+UserDataCount], 8; UserDataCount
0x140058ff3  mov     [rsp+170h+RelatedActivityId], r12; RelatedActivityId
0x140058ff8  mov     [rsp+170h+ActivityId], r12; ActivityId
0x140058ffd  call    cs:__imp_EtwWriteEx
0x140059004  nop     dword ptr [rax+rax+00h]
0x140059009  jmp     def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x14005900e  lea     rdx, [rsi+20h]; ListEntry
0x140059012  lea     rcx, [rbx+460h]; ListHead
0x140059019  call    cs:__imp_ExpInterlockedPushEntrySList
0x140059020  nop     dword ptr [rax+rax+00h]
0x140059025  mov     rcx, [rbx+8]
0x140059029  xor     r8d, r8d; SystemArgument2
0x14005902c  add     rcx, 0C8h; Dpc
0x140059033  xor     edx, edx; SystemArgument1
0x140059035  call    cs:__imp_KeInsertQueueDpc
0x14005903c  nop     dword ptr [rax+rax+00h]
0x140059041  jmp     def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x140059046  test    rdi, rdi; jumptable 0000000140058D7D case 3
0x140059049  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x14005904f  mov     ecx, [rdi+248h]
0x140059055  mov     r8, rdi
0x140059058  mov     rdx, [rbp+78h]
0x14005905c  mov     r9d, [rdi+38h]
0x140059060  mov     qword ptr [rsp+170h+UserDataCount], rax
0x140059065  mov     [rsp+170h+RelatedActivityId], rcx
0x14005906a  mov     rcx, rdi
0x14005906d  mov     [rsp+170h+ActivityId], rdx
0x140059072  mov     edx, 27h ; '''
0x140059077  call    DbgLogRequest
0x14005907c  test    cs:Microsoft_Windows_StorPortEnableBits, 2
0x140059083  mov     ebx, [rdi+248h]
0x140059089  jz      short loc_1400590A9
0x14005908b  mov     eax, [rdi+38h]
0x14005908e  lea     rdx, EventResetDetected
0x140059095  mov     r9, [rbp+70h+arg_8]
0x14005909c  mov     dword ptr [rsp+170h+RelatedActivityId], ebx
0x1400590a0  mov     dword ptr [rsp+170h+ActivityId], eax
0x1400590a4  call    McTemplateK0pqq_EtwWriteTransfer
0x1400590a9  test    ebx, ebx
0x1400590ab  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x1400590b1  mov     eax, 3D0900h
0x1400590b6  cmp     ebx, eax
0x1400590b8  cmova   ebx, eax
0x1400590bb  mov     eax, 431BDE83h
0x1400590c0  mul     ebx
0x1400590c2  mov     ecx, edx
0x1400590c4  shr     ecx, 12h
0x1400590c7  imul    eax, ecx, 0F4240h
0x1400590cd  lea     edx, [rcx+1]
0x1400590d0  cmp     ebx, eax
0x1400590d2  cmovz   edx, ecx
0x1400590d5  mov     rcx, [rbp+70h+arg_8]
0x1400590dc  call    StorPortPause
0x1400590e1  jmp     loc_140059781
0x1400590e6  test    rdi, rdi; jumptable 0000000140058D7D case 7
0x1400590e9  jz      def_140058D7D; jumptable 0000000140058D7D default case, cases 1,2,4,5,9
0x1400590ef  mov     ecx, [rdi+248h]
0x1400590f5  mov     r8, rdi
0x1400590f8  mov     rdx, [rbp+78h]
0x1400590fc  mov     r9d, [rdi+38h]
0x140059100  mov     qword ptr [rsp+170h+UserDataCount], rax
0x140059105  mov     [rsp+170h+RelatedActivityId], rcx
0x14005910a  mov     rcx, rdi
0x14005910d  mov     [rsp+170h+ActivityId], rdx
0x140059112  mov     edx, 26h ; '&'
  ... truncated ...
```
