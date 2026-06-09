# Smb2LeaseAcquireOrUpgrade

- ea: `0x14000e5f0`
- end: `0x14000f04f`
- name: `Smb2LeaseAcquireOrUpgrade`
- size: `2655`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x14000f4d0`
- `0x14001ed38`

## callees

- `0x140004960`
- `0x140005070`
- `0x14000e140`
- `0x14000e5f0`
- `0x14000f060`
- `0x140015520`
- `0x1400186a0`
- `0x1400187e0`
- `0x14001b3fc`
- `0x140021b20`
- `0x1400222ec`
- `0x140022690`
- `0x140022958`
- `0x140022a10`
- `0x14002f1c0`
- `0x14002f440`
- `0x14002f4ac`
- `0x14002f524`
- `0x140038490`
- `0x140091d10`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e907`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000ed67`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000edf2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e907`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000ed67`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000edf2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e6c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eaa1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e6c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000eaa1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ef60`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f02c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ef60`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f02c`
- `ntoskrnl!ObfReferenceObject` at `0x14000e99c`
- `ntoskrnl!ObfReferenceObject` at `0x14000e99c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14000e85c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14000e85c`
- `ntoskrnl!IofCallDriver` at `0x14000ea30`
- `ntoskrnl!IofCallDriver` at `0x14000ea30`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e84c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ec4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ec8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b902`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e84c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ec4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ec8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003b902`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b4be`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b83a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b4be`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003b83a`
- `ntoskrnl!IoAllocateIrpEx` at `0x14000e8d8`
- `ntoskrnl!IoAllocateIrpEx` at `0x14000e8d8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000ed82`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000ee0d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000ed82`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000ee0d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000e759`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000e759`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000e7d9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ec79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000e7d9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000ec79`

## string_xrefs

- `0x14000ed48`: `Srv2PostToThreadPool`
- `0x14000edd3`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2LeaseAcquireOrUpgrade(__int64 a1, __int64 a2, char a3, char a4, _WORD *a5, __int64 a6)
{
  int v6; // r8d
  int v8; // ecx
  unsigned int v10; // r15d
  __int64 v11; // rcx
  __int64 RelativeHandle; // r14
  int v13; // eax
  int v14; // edx
  KIRQL v15; // al
  int v16; // ecx
  _QWORD *v17; // rdx
  signed __int64 v18; // rdi
  __int64 v19; // r8
  int v20; // ecx
  __int64 v21; // r13
  KIRQL v22; // dl
  PDEVICE_OBJECT v23; // r9
  int i; // edx
  _OWORD *v25; // rcx
  IRP *v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rdx
  PIRP v29; // rdi
  struct _KTHREAD *v30; // rcx
  IRP *CurrentStackLocation; // rax
  signed __int64 v32; // rax
  PIRP v33; // rdx
  struct _DEVICE_OBJECT *v34; // rcx
  struct _IRP *v35; // rax
  int v36; // edi
  signed __int64 v37; // rax
  KIRQL v38; // al
  KIRQL v39; // cl
  int v40; // r13d
  unsigned int v41; // edi
  signed __int64 v42; // rsi
  unsigned int v44; // ecx
  void *v45; // rdi
  bool v46; // zf
  __int64 v47; // rdi
  __int64 v48; // rdi
  __int64 v49; // rbx
  __int64 v50; // rbx
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int16 v53; // ax
  __int64 v54; // r8
  int v55; // edi
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rcx
  void *v61; // r15
  int v62; // eax
  __int64 v63; // rdx
  int v64; // [rsp+20h] [rbp-99h]
  KIRQL v65; // [rsp+60h] [rbp-59h] BYREF
  char v66; // [rsp+61h] [rbp-58h]
  PIRP Irp; // [rsp+68h] [rbp-51h]
  PVOID P; // [rsp+70h] [rbp-49h]
  signed __int64 v69; // [rsp+78h] [rbp-41h]
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp-39h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-31h] BYREF
  PVOID BackTrace[2]; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v73; // [rsp+B0h] [rbp-9h]
  __int64 v74; // [rsp+C0h] [rbp+7h]

  v6 = a3 & 7;
  v66 = a4;
  v8 = v6;
  if ( !a4 )
    v8 = 0;
  v10 = v6 & 0xFFFFFFFB;
  LODWORD(P) = v8;
  v11 = *(_QWORD *)(a2 + 128);
  RelativeHandle = 0;
  v13 = *(_DWORD *)(a2 + 224);
  v14 = *(_DWORD *)(v11 + 288);
  if ( (v14 & 0x1000) == 0 )
    v10 = v6;
  if ( (v13 & 0x40) != 0 )
  {
    v10 &= ~4u;
    if ( !Smb2DirHandleLeasingEnabled || (v14 & 0x400000) != 0 )
      v10 &= ~2u;
  }
  if ( (*(_DWORD *)(v11 + 368) & 0x4000000) != 0 && !*(_BYTE *)(a2 + 245) )
    v10 &= 1u;
  *(_QWORD *)(a6 + 16) = 0;
  *(_QWORD *)(a6 + 24) = 0;
  *(_OWORD *)(a6 + 32) = 0;
  *(_OWORD *)a6 = *(_OWORD *)(a1 + 80);
  if ( !*(_QWORD *)(a1 + 112) && !*(_BYTE *)(a1 + 136) )
  {
    RelativeHandle = Smb2LeaseCreateRelativeHandle(a1, a2);
    if ( !RelativeHandle )
      return 3221225473LL;
  }
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v16 = *(_DWORD *)(a1 + 12);
  v65 = v15;
  if ( v16 == 225 )
  {
    _InterlockedIncrement(&dword_14004B390);
    goto LABEL_131;
  }
  if ( v16 == 224 )
  {
    _InterlockedIncrement(&dword_14004B39C);
    Smb2CancelQueuedDelayedLease(a1);
    v15 = v65;
LABEL_131:
    *(_DWORD *)(a1 + 12) = 220;
  }
  if ( !*(_QWORD *)(a1 + 112) && !*(_BYTE *)(a1 + 136) )
  {
    *(_QWORD *)(a1 + 112) = RelativeHandle;
    if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)RelativeHandle, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      __int2c();
    v15 = v65;
  }
  if ( *(_BYTE *)(a1 + 128) || *(_BYTE *)(a1 + 136) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v15);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1);
    }
    goto LABEL_77;
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(a2 + 112), &LockHandle);
  if ( *(_DWORD *)(a2 + 12) != 220 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a2, a1);
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
LABEL_76:
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v65);
LABEL_77:
    v41 = -1073741823;
    goto LABEL_54;
  }
  v17 = *(_QWORD **)(a1 + 160);
  if ( *v17 != a1 + 152 )
    __fastfail(3u);
  *(_QWORD *)(a2 + 416) = a1 + 152;
  *(_QWORD *)(a2 + 424) = v17;
  *v17 = a2 + 416;
  *(_QWORD *)(a1 + 160) = a2 + 416;
  *(_QWORD *)(a2 + 168) = a1;
  v18 = _InterlockedIncrement64((volatile signed __int64 *)a1);
  if ( ((v18 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0 )
  {
    v74 = 0;
    *(_OWORD *)BackTrace = 0;
    v73 = 0;
    RtlCaptureStackBackTrace(1u, 5u, BackTrace, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qPPqqqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
        a1,
        v18 - 1,
        v18,
        BackTrace[0],
        BackTrace[1],
        v73,
        *((_QWORD *)&v73 + 1),
        v74);
    }
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      &WPP_GLOBAL_Control,
      v19,
      a1,
      *(_DWORD *)(a1 + 104),
      *(_DWORD *)(a1 + 120),
      v10);
  }
  v20 = *(_DWORD *)(a1 + 104);
  if ( !v20 )
  {
    v21 = *(_QWORD *)(a1 + 112);
    if ( v21 )
    {
      if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)v21, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        __int2c();
      v22 = v65;
      *(_DWORD *)(a1 + 144) |= 2u;
      *(_DWORD *)(a1 + 104) = 16;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v22);
      DeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(v21 + 96));
      v23 = DeviceObject;
      if ( !v10 )
      {
        LODWORD(Irp) = -1073741823;
        goto LABEL_45;
      }
      for ( i = 0; i < 2; ++i )
      {
        v25 = (_OWORD *)(a1 + 32LL * i + 296);
        if ( *(_OWORD **)(a1 + 280) != v25 && *(_OWORD **)(a1 + 288) != v25 )
        {
          *v25 = 0;
          v25[1] = 0;
          *(_QWORD *)(a1 + 280) = v25;
          if ( v25 )
          {
            v26 = (IRP *)IoAllocateIrpEx(v23, (unsigned __int8)v23->StackSize, 0);
            Irp = v26;
            if ( !v26 )
            {
              v36 = -1073741670;
              LODWORD(Irp) = -1073741670;
              goto LABEL_41;
            }
            v26->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(v21 + 96);
            v27 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
            v28 = *(_QWORD *)(v27 + 8LL * KeGetCurrentNodeNumber() + 8);
            v29 = Irp;
            v30 = *(struct _KTHREAD **)(v28 + 224);
            Irp->IoStatus.Status = 0;
            v29->IoStatus.Information = 0;
            CurrentStackLocation = (IRP *)v29->Tail.Overlay.CurrentStackLocation;
            v29->Tail.Overlay.Thread = v30;
            v29->RequestorMode = 0;
            Irp = CurrentStackLocation;
            CurrentStackLocation[-1].Tail.Overlay.OriginalFileObject = (PFILE_OBJECT)&Smb2LeaseOplockCompletion;
            *((_QWORD *)&CurrentStackLocation[-1].Tail.CompletionKey + 10) = a1;
            *((_BYTE *)&CurrentStackLocation[-1].Tail.CompletionKey + 19) = -32;
            v32 = _InterlockedExchangeAdd64((volatile signed __int64 *)a1, 1u);
            v69 = v32 + 1;
            if ( ((v32 + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
              __int2c();
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0 )
            {
              v74 = 0;
              *(_OWORD *)BackTrace = 0;
              v73 = 0;
              RtlCaptureStackBackTrace(1u, 5u, BackTrace, 0);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qPPqqqqq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  13,
                  WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
                  a1,
                  v69 - 1,
                  v69,
                  BackTrace[0],
                  BackTrace[1],
                  v73,
                  *((_QWORD *)&v73 + 1),
                  v74);
              }
            }
            *((_WORD *)&Irp[-1].Tail.CompletionKey + 8) = 13;
            ObfReferenceObject(*(PVOID *)(v21 + 96));
            v33 = Irp;
            v34 = DeviceObject;
            Irp[-1].Tail.Overlay.CurrentStackLocation = *(struct _IO_STACK_LOCATION **)(v21 + 96);
            v33[-1].Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)v34;
            *((_DWORD *)&v33[-1].Tail.CompletionKey + 6) = 24;
            *((_DWORD *)&v33[-1].Tail.CompletionKey + 8) = 12;
            *((_DWORD *)&v33[-1].Tail.CompletionKey + 10) = 590400;
            v35 = *(struct _IRP **)(a1 + 280);
            v29->AssociatedIrp.MasterIrp = v35;
            v29->UserBuffer = v35;
            v29->MdlAddress = 0;
            v29->Flags = 16;
            **(_WORD **)(a1 + 280) = 1;
            *(_WORD *)(*(_QWORD *)(a1 + 280) + 2LL) = 12;
            *(_DWORD *)(*(_QWORD *)(a1 + 280) + 4LL) = v10;
            *(_DWORD *)(*(_QWORD *)(a1 + 280) + 8LL) = 1;
            *(_QWORD *)(*(_QWORD *)(a1 + 280) + 24LL) = v29;
            LODWORD(Irp) = IofCallDriver(v34, v29);
            v36 = (int)Irp;
            if ( (_DWORD)Irp != 259 )
LABEL_41:
              *(_QWORD *)(a1 + 280) = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                35,
                WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
                a1,
                v36);
            }
            if ( v36 == -1073741598 )
            {
              if ( (v10 & 4) == 0
                || (v10 &= ~4u) == 0
                || (LODWORD(Irp) = Smb2LeaseAcquire(a1, v21, v10), (_DWORD)Irp == -1073741598) )
              {
                if ( (v10 & 2) != 0 )
                {
                  v10 &= ~2u;
                  if ( v10 )
                    LODWORD(Irp) = Smb2LeaseAcquire(a1, v21, v10);
                }
              }
            }
LABEL_45:
            v37 = _InterlockedDecrement64((volatile signed __int64 *)v21);
            if ( v37 == -1 )
            {
              __int2c();
            }
            else if ( !v37 )
            {
              if ( KeGetCurrentIrql() )
              {
                v46 = *(_DWORD *)(v21 + 8) == 5;
                *(_QWORD *)(v21 + 48) = Smb2DereferenceHandleCallback;
                *(_DWORD *)(v21 + 72) = 0;
                if ( v46 )
                {
                  LOBYTE(v64) = 1;
                  LOBYTE(v51) = 1;
                  SRV2_PERF_ENTER_EX(v21 + 584, v51, 391, "Srv2PostToThreadPool", v64);
                }
                v47 = *(_QWORD *)(*(_QWORD *)(v21 + 64) + 136LL);
                v48 = *(_QWORD *)(v47 + 8LL * KeGetCurrentNodeNumber() + 8);
                if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v48, (PSLIST_ENTRY)(v21 + 32)) && *(_WORD *)(v48 + 66) )
                  RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v48);
              }
              else
              {
                Smb2DereferenceHandleCleanup((PVOID)v21, 0);
              }
            }
            v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
            *(_DWORD *)(a1 + 144) &= ~2u;
            v39 = v38;
            v40 = (int)Irp;
            v65 = v38;
            if ( (_DWORD)Irp == 259 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qLD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  42,
                  WPP_GLOBAL_Control,
                  a1,
                  v10,
                  *(unsigned __int16 *)(a1 + 168));
                v39 = v65;
              }
              v41 = 0;
              *(_DWORD *)(a1 + 104) = 1;
              if ( !v66 || !a5 || *a5 != *(_WORD *)(a1 + 168) || (_DWORD)P != v10 || ((unsigned __int8)P & 4) == 0 )
                ++*(_WORD *)(a1 + 168);
              *(_DWORD *)(a1 + 120) = v10;
              *(_DWORD *)(a6 + 16) = v10;
              *(_WORD *)(a6 + 48) = *(_WORD *)(a1 + 168);
              *(_DWORD *)(a1 + 124) = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  43,
                  WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
                  a1,
                  *(unsigned __int16 *)(a1 + 168));
                v39 = v65;
              }
              *(_DWORD *)(a1 + 104) = 0;
              *(_QWORD *)(a1 + 120) = 0;
              *(_DWORD *)(a6 + 16) = 0;
              if ( v40 != -1073741808 )
                v40 = -1073741823;
              v41 = v40;
              *(_WORD *)(a6 + 48) = *(_WORD *)(a1 + 168);
            }
            Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, v39);
            goto LABEL_54;
          }
LABEL_84:
          LODWORD(Irp) = -1073741595;
          goto LABEL_45;
        }
      }
      *(_QWORD *)(a1 + 280) = 0;
      goto LABEL_84;
    }
    goto LABEL_76;
  }
  if ( v20 != 1 )
  {
    if ( v20 == 16 || v20 == 32 || v20 == 64 || v20 == 128 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qLLD(
          WPP_GLOBAL_Control->AttachedDevice,
          47,
          WPP_GLOBAL_Control,
          a1,
          v20,
          *(_DWORD *)(a1 + 120),
          *(unsigned __int16 *)(a1 + 168));
      }
      *(_DWORD *)(a6 + 16) = *(_DWORD *)(a1 + 120);
      v53 = *(_WORD *)(a1 + 168);
      *(_DWORD *)(a6 + 20) |= 2u;
      *(_WORD *)(a6 + 48) = v53;
    }
    goto LABEL_72;
  }
  v44 = *(_DWORD *)(a1 + 120);
  if ( v10 <= v44 || (v10 & *(_DWORD *)(a1 + 120)) != v44 || (v45 = *(void **)(a1 + 112), (P = v45) == 0) )
  {
    *(_DWORD *)(a6 + 16) = v44;
    *(_WORD *)(a6 + 48) = *(_WORD *)(a1 + 168);
LABEL_72:
    v41 = -1073741823;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v65);
    goto LABEL_54;
  }
  if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)v45, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  v54 = v65;
  *(_DWORD *)(a1 + 104) = 64;
  Smb2LeaseReleaseSpinLockForOperation(a1, 2, v54);
  v55 = Smb2LeaseUpgrade(a1, v45, v10);
  Smb2DereferenceHandleEx(P);
  Smb2LeaseAcquireSpinLockFromOperation(a1, 2, &v65);
  if ( v55 == 259 )
  {
    if ( !*(_BYTE *)(a1 + 138) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qLLD(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          v56,
          a1,
          *(_DWORD *)(a1 + 120),
          v10,
          *(unsigned __int16 *)(a1 + 168));
      }
      v57 = *(_QWORD *)(a1 + 288);
      v41 = 0;
      ++*(_WORD *)(a1 + 168);
      v58 = v65;
      *(_QWORD *)(a1 + 280) = v57;
      *(_DWORD *)(a1 + 120) = v10;
      *(_DWORD *)(a1 + 104) = 1;
      *(_QWORD *)(a1 + 288) = 0;
      *(_DWORD *)(a6 + 16) = v10;
      *(_WORD *)(a6 + 48) = *(_WORD *)(a1 + 168);
      *(_DWORD *)(a1 + 124) = 0;
      Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, v58);
      goto LABEL_54;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qLLD(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        v56,
        a1,
        *(_DWORD *)(a1 + 120),
        v10,
        *(unsigned __int16 *)(a1 + 168));
    }
    v59 = *(_QWORD *)(a1 + 288);
    v41 = -1073741823;
    v60 = *(_QWORD *)(a1 + 280);
    *(_BYTE *)(a1 + 138) = 0;
    *(_DWORD *)(a1 + 104) = 1;
    *(_QWORD *)(v60 + 24) = *(_QWORD *)(v59 + 24);
    *(_QWORD *)(*(_QWORD *)(a1 + 288) + 24LL) = 0;
    LODWORD(v59) = *(_DWORD *)(a1 + 120);
    *(_QWORD *)(a1 + 288) = 0;
    *(_DWORD *)(a6 + 16) = v59;
    LOWORD(v59) = *(_WORD *)(a1 + 168);
    *(_DWORD *)(a6 + 20) |= 2u;
    *(_WORD *)(a6 + 48) = v59;
    v61 = *(void **)(a1 + 112);
    *(_QWORD *)(a1 + 112) = 0;
  }
  else
  {
    v61 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qLD(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        v56,
        a1,
        *(_DWORD *)(a1 + 120),
        *(unsigned __int16 *)(a1 + 168));
    }
    v62 = *(_DWORD *)(a1 + 120);
    v41 = -1073741823;
    *(_DWORD *)(a1 + 104) = 1;
    *(_QWORD *)(a1 + 288) = 0;
    *(_DWORD *)(a6 + 16) = v62;
    *(_WORD *)(a6 + 48) = *(_WORD *)(a1 + 168);
    if ( *(_BYTE *)(a1 + 138) )
    {
      *(_DWORD *)(a1 + 140) |= 2u;
      v63 = v65;
      *(_BYTE *)(a1 + 138) = 0;
      Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, v63);
      goto LABEL_54;
    }
  }
  Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock(a1, v65);
  if ( v61 )
    Smb2DereferenceHandleEx(v61);
LABEL_54:
  if ( RelativeHandle )
  {
    v42 = _InterlockedDecrement64((volatile signed __int64 *)RelativeHandle);
    if ( v42 == -1 )
    {
      __int2c();
    }
    else if ( !v42 )
    {
      if ( KeGetCurrentIrql() )
      {
        v46 = *(_DWORD *)(RelativeHandle + 8) == 5;
        *(_QWORD *)(RelativeHandle + 48) = Smb2DereferenceHandleCallback;
        *(_DWORD *)(RelativeHandle + 72) = 0;
        if ( v46 )
        {
          LOBYTE(v64) = 1;
          LOBYTE(v52) = 1;
          SRV2_PERF_ENTER_EX(RelativeHandle + 584, v52, 391, "Srv2PostToThreadPool", v64);
        }
        v49 = *(_QWORD *)(*(_QWORD *)(RelativeHandle + 64) + 136LL);
        v50 = *(_QWORD *)(v49 + 8LL * KeGetCurrentNodeNumber() + 8);
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v50, (PSLIST_ENTRY)(RelativeHandle + 32)) )
        {
          if ( *(_WORD *)(v50 + 66) )
            RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v50);
        }
      }
      else
      {
        Smb2DereferenceHandleCleanup((PVOID)RelativeHandle, 0);
      }
    }
  }
  return v41;
}

```

## disassembly

```asm
0x14000e5f0  push    rbp
0x14000e5f2  push    rbx
0x14000e5f3  push    rdi
0x14000e5f4  push    r12
0x14000e5f6  push    r14
0x14000e5f8  push    r15
0x14000e5fa  lea     rbp, [rsp-1Fh]
0x14000e5ff  sub     rsp, 0D8h
0x14000e606  mov     rax, cs:__security_cookie
0x14000e60d  xor     rax, rsp
0x14000e610  mov     [rbp+47h+var_38], rax
0x14000e614  mov     r12, [rbp+47h+arg_28]
0x14000e618  and     r8d, 7
0x14000e61c  xor     r10d, r10d
0x14000e61f  mov     [rbp+47h+var_9F], r9b
0x14000e623  test    r9b, r9b
0x14000e626  mov     rbx, rcx
0x14000e629  mov     ecx, r8d
0x14000e62c  mov     rdi, rdx
0x14000e62f  cmovz   ecx, r10d
0x14000e633  mov     r15d, r8d
0x14000e636  and     r15d, 0FFFFFFFBh
0x14000e63a  mov     dword ptr [rbp+47h+P], ecx
0x14000e63d  mov     rcx, [rdx+80h]
0x14000e644  mov     r14d, r10d
0x14000e647  mov     eax, [rdi+0E0h]
0x14000e64d  mov     edx, [rcx+120h]
0x14000e653  bt      edx, 0Ch
0x14000e657  cmovnb  r15d, r8d
0x14000e65b  test    al, 40h
0x14000e65d  jnz     loc_14000EBE3
0x14000e663  test    dword ptr [rcx+170h], 4000000h
0x14000e66d  jnz     loc_14000EE3D
0x14000e673  mov     [r12+10h], r10
0x14000e678  xorps   xmm0, xmm0
0x14000e67b  mov     [r12+18h], r10
0x14000e680  movups  xmmword ptr [r12+20h], xmm0
0x14000e686  movups  xmm0, xmmword ptr [rbx+50h]
0x14000e68a  movups  xmmword ptr [r12], xmm0
0x14000e68f  cmp     [rbx+70h], r10
0x14000e693  jnz     short loc_14000E6B5
0x14000e695  cmp     [rbx+88h], r10b
0x14000e69c  jnz     short loc_14000E6B5
0x14000e69e  mov     rdx, rdi
0x14000e6a1  mov     rcx, rbx
0x14000e6a4  call    Smb2LeaseCreateRelativeHandle
0x14000e6a9  mov     r14, rax
0x14000e6ac  test    rax, rax
0x14000e6af  jz      loc_14000EC03
0x14000e6b5  mov     [rsp+100h+arg_10], rsi
0x14000e6bd  lea     rcx, [rbx+60h]; SpinLock
0x14000e6c1  mov     [rsp+100h+var_30], r13
0x14000e6c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e6d0  nop     dword ptr [rax+rax+00h]
0x14000e6d5  mov     ecx, [rbx+0Ch]
0x14000e6d8  mov     [rbp+47h+var_A0], al
0x14000e6db  cmp     ecx, 0E1h
0x14000e6e1  jz      loc_14000EE6B
0x14000e6e7  cmp     ecx, 0E0h
0x14000e6ed  jz      loc_14000EE53
0x14000e6f3  cmp     qword ptr [rbx+70h], 0
0x14000e6f8  jnz     short loc_14000E723
0x14000e6fa  cmp     byte ptr [rbx+88h], 0
0x14000e701  jnz     short loc_14000E723
0x14000e703  mov     [rbx+70h], r14
0x14000e707  mov     eax, 1
0x14000e70c  lock xadd [r14], rax
0x14000e711  add     rax, 2
0x14000e715  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000e71b  jnz     short loc_14000E71F
0x14000e71d  int     2Ch; Windows NT - assertion failure
0x14000e71f  movzx   eax, [rbp+47h+var_A0]
0x14000e723  cmp     byte ptr [rbx+80h], 0
0x14000e72a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x14000e731  jnz     loc_14003B8FB
0x14000e737  cmp     byte ptr [rbx+88h], 0
0x14000e73e  jnz     loc_14003B8FB
0x14000e744  xorps   xmm0, xmm0
0x14000e747  lea     rcx, [rdi+70h]; SpinLock
0x14000e74b  xor     eax, eax
0x14000e74d  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14000e751  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x14000e755  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x14000e759  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14000e760  nop     dword ptr [rax+rax+00h]
0x14000e765  cmp     dword ptr [rdi+0Ch], 0DCh
0x14000e76c  jnz     loc_14000EC5E
0x14000e772  lea     rcx, [rbx+98h]
0x14000e779  mov     rdx, [rcx+8]
0x14000e77d  cmp     [rdx], rcx
0x14000e780  jnz     loc_14000EEB0
0x14000e786  lea     rax, [rdi+1A0h]
0x14000e78d  mov     r10d, 1
0x14000e793  mov     [rax], rcx
0x14000e796  mov     [rax+8], rdx
0x14000e79a  mov     [rdx], rax
0x14000e79d  mov     [rcx+8], rax
0x14000e7a1  mov     [rdi+0A8h], rbx
0x14000e7a8  mov     edi, r10d
0x14000e7ab  lock xadd [rbx], rdi
0x14000e7b0  inc     rdi
0x14000e7b3  lea     rax, [rdi+1]
0x14000e7b7  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000e7bd  jnz     short loc_14000E7C1
0x14000e7bf  int     2Ch; Windows NT - assertion failure
0x14000e7c1  mov     rax, cs:WPP_GLOBAL_Control
0x14000e7c8  test    dword ptr [rax+2Ch], 40000000h
0x14000e7cf  jnz     loc_14003B49E
0x14000e7d5  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14000e7d9  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000e7e0  nop     dword ptr [rax+rax+00h]
0x14000e7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7ec  lea     rdx, WPP_GLOBAL_Control
0x14000e7f3  cmp     rcx, rdx
0x14000e7f6  jz      short loc_14000E805
0x14000e7f8  test    dword ptr [rcx+2Ch], 40000000h
0x14000e7ff  jnz     loc_14000EEB7
0x14000e805  mov     ecx, [rbx+68h]
0x14000e808  test    ecx, ecx
0x14000e80a  jnz     loc_14000EC0D
0x14000e810  mov     r13, [rbx+70h]
0x14000e814  test    r13, r13
0x14000e817  jz      loc_14000EC85
0x14000e81d  mov     eax, 1
0x14000e822  lock xadd [r13+0], rax
0x14000e828  add     rax, 2
0x14000e82c  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000e832  jnz     short loc_14000E836
0x14000e834  int     2Ch; Windows NT - assertion failure
0x14000e836  movzx   edx, [rbp+47h+var_A0]; NewIrql
0x14000e83a  lea     rcx, [rbx+60h]; SpinLock
0x14000e83e  or      dword ptr [rbx+90h], 2
0x14000e845  mov     dword ptr [rbx+68h], 10h
0x14000e84c  call    cs:__imp_KeReleaseSpinLock
0x14000e853  nop     dword ptr [rax+rax+00h]
0x14000e858  mov     rcx, [r13+60h]; FileObject
0x14000e85c  call    cs:__imp_IoGetRelatedDeviceObject
0x14000e863  nop     dword ptr [rax+rax+00h]
0x14000e868  mov     [rbp+47h+DeviceObject], rax
0x14000e86c  mov     r9, rax
0x14000e86f  mov     eax, 0C0000001h
0x14000e874  test    r15d, r15d
0x14000e877  jz      loc_14000EBD4
0x14000e87d  xor     edx, edx
0x14000e87f  cmp     edx, 2
0x14000e882  jge     loc_14000ECCD
0x14000e888  movsxd  rcx, edx
0x14000e88b  shl     rcx, 5
0x14000e88f  add     rcx, 128h
0x14000e896  add     rcx, rbx
0x14000e899  cmp     [rbx+118h], rcx
0x14000e8a0  jz      loc_14000EBDC
0x14000e8a6  cmp     [rbx+120h], rcx
0x14000e8ad  jz      loc_14000EBDC
0x14000e8b3  xorps   xmm0, xmm0
0x14000e8b6  movups  xmmword ptr [rcx], xmm0
0x14000e8b9  movups  xmmword ptr [rcx+10h], xmm0
0x14000e8bd  mov     [rbx+118h], rcx
0x14000e8c4  test    rcx, rcx
0x14000e8c7  jz      loc_14000ECD8
0x14000e8cd  movzx   edx, byte ptr [r9+4Ch]
0x14000e8d2  xor     r8d, r8d
0x14000e8d5  mov     rcx, r9
0x14000e8d8  call    cs:__imp_IoAllocateIrpEx
0x14000e8df  nop     dword ptr [rax+rax+00h]
0x14000e8e4  mov     [rbp+47h+Irp], rax
0x14000e8e8  test    rax, rax
0x14000e8eb  jz      loc_14000EEEC
0x14000e8f1  mov     rcx, [r13+60h]
0x14000e8f5  mov     [rax+0C0h], rcx
0x14000e8fc  mov     rcx, [rbx+40h]
0x14000e900  mov     rdi, [rcx+88h]
0x14000e907  call    cs:__imp_KeGetCurrentNodeNumber
0x14000e90e  nop     dword ptr [rax+rax+00h]
0x14000e913  movzx   ecx, ax
0x14000e916  mov     r10d, 1
0x14000e91c  xor     eax, eax
0x14000e91e  mov     rdx, [rdi+rcx*8+8]
0x14000e923  mov     rdi, [rbp+47h+Irp]
0x14000e927  mov     rcx, [rdx+0E0h]
0x14000e92e  mov     [rdi+30h], eax
0x14000e931  mov     [rdi+38h], rax
0x14000e935  mov     rax, [rdi+0B8h]
0x14000e93c  mov     [rdi+98h], rcx
0x14000e943  lea     rcx, Smb2LeaseOplockCompletion
0x14000e94a  mov     byte ptr [rdi+40h], 0
0x14000e94e  mov     [rbp+47h+Irp], rax
0x14000e952  mov     [rax-10h], rcx
0x14000e956  mov     [rax-8], rbx
0x14000e95a  mov     byte ptr [rax-45h], 0E0h
0x14000e95e  mov     eax, r10d
0x14000e961  lock xadd [rbx], rax
0x14000e966  inc     rax
0x14000e969  mov     [rbp+47h+var_88], rax
0x14000e96d  inc     rax
0x14000e970  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000e976  jnz     short loc_14000E97A
0x14000e978  int     2Ch; Windows NT - assertion failure
0x14000e97a  mov     rax, cs:WPP_GLOBAL_Control
0x14000e981  test    dword ptr [rax+2Ch], 40000000h
0x14000e988  jnz     loc_14003B81A
0x14000e98e  mov     rax, [rbp+47h+Irp]
0x14000e992  mov     word ptr [rax-48h], 0Dh
0x14000e998  mov     rcx, [r13+60h]; Object
0x14000e99c  call    cs:__imp_ObfReferenceObject
0x14000e9a3  nop     dword ptr [rax+rax+00h]
0x14000e9a8  mov     rax, [r13+60h]
0x14000e9ac  mov     r8d, 0Ch
0x14000e9b2  mov     rdx, [rbp+47h+Irp]
0x14000e9b6  mov     rcx, [rbp+47h+DeviceObject]; DeviceObject
0x14000e9ba  mov     [rdx-18h], rax
0x14000e9be  mov     [rdx-20h], rcx
0x14000e9c2  mov     dword ptr [rdx-40h], 18h
0x14000e9c9  mov     [rdx-38h], r8d
0x14000e9cd  mov     dword ptr [rdx-30h], 90240h
0x14000e9d4  mov     edx, 1
0x14000e9d9  mov     rax, [rbx+118h]
0x14000e9e0  mov     [rdi+18h], rax
0x14000e9e4  mov     [rdi+70h], rax
0x14000e9e8  mov     qword ptr [rdi+8], 0
0x14000e9f0  mov     dword ptr [rdi+10h], 10h
0x14000e9f7  mov     rax, [rbx+118h]
0x14000e9fe  mov     [rax], dx
0x14000ea01  mov     rax, [rbx+118h]
0x14000ea08  mov     [rax+2], r8w
0x14000ea0d  mov     rax, [rbx+118h]
0x14000ea14  mov     [rax+4], r15d
0x14000ea18  mov     rax, [rbx+118h]
0x14000ea1f  mov     [rax+8], edx
0x14000ea22  mov     rdx, rdi; Irp
0x14000ea25  mov     rax, [rbx+118h]
0x14000ea2c  mov     [rax+18h], rdi
0x14000ea30  call    cs:__imp_IofCallDriver
0x14000ea37  nop     dword ptr [rax+rax+00h]
0x14000ea3c  mov     dword ptr [rbp+47h+Irp], eax
0x14000ea3f  mov     edi, eax
0x14000ea41  cmp     eax, 103h
0x14000ea46  jz      short loc_14000EA53
0x14000ea48  mov     qword ptr [rbx+118h], 0
0x14000ea53  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea5a  lea     rax, WPP_GLOBAL_Control
0x14000ea61  cmp     rcx, rax
0x14000ea64  jz      short loc_14000EA73
0x14000ea66  test    dword ptr [rcx+2Ch], 40000000h
0x14000ea6d  jnz     loc_14000EEF9
0x14000ea73  cmp     edi, 0C00000E2h
0x14000ea79  jz      loc_14000EF24
0x14000ea7f  mov     rax, rsi
0x14000ea82  lock xadd [r13+0], rax
0x14000ea88  dec     rax
0x14000ea8b  cmp     rax, rsi
0x14000ea8e  jnb     loc_14000EF59
0x14000ea94  test    rax, rax
0x14000ea97  jz      loc_14000EF60
0x14000ea9d  lea     rcx, [rbx+60h]; SpinLock
0x14000eaa1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000eaa8  nop     dword ptr [rax+rax+00h]
0x14000eaad  and     dword ptr [rbx+90h], 0FFFFFFFDh
0x14000eab4  movzx   ecx, al
0x14000eab7  mov     r13d, dword ptr [rbp+47h+Irp]
0x14000eabb  mov     [rbp+47h+var_A0], al
0x14000eabe  cmp     r13d, 103h
0x14000eac5  jnz     loc_14000EB7E
0x14000eacb  mov     r8, cs:WPP_GLOBAL_Control
0x14000ead2  lea     rax, WPP_GLOBAL_Control
0x14000ead9  cmp     r8, rax
0x14000eadc  jz      short loc_14000EAEC
0x14000eade  test    dword ptr [r8+2Ch], 40000000h
0x14000eae6  jnz     loc_14000EF83
0x14000eaec  xor     edi, edi
0x14000eaee  mov     dword ptr [rbx+68h], 1
0x14000eaf5  cmp     [rbp+47h+var_9F], dil
0x14000eaf9  jnz     loc_14000EFB8
0x14000eaff  inc     word ptr [rbx+0A8h]
0x14000eb06  mov     [rbx+78h], r15d
0x14000eb0a  mov     [r12+10h], r15d
0x14000eb0f  xor     r15d, r15d
0x14000eb12  movzx   eax, word ptr [rbx+0A8h]
0x14000eb19  mov     [r12+30h], ax
0x14000eb1f  mov     [rbx+7Ch], r15d
0x14000eb23  movzx   edx, cl
0x14000eb26  mov     rcx, rbx
0x14000eb29  call    Smb2LeaseProcessPendingLeaseOperationsAndReleaseSpinLock
0x14000eb2e  test    r14, r14
0x14000eb31  jz      short loc_14000EB4E
0x14000eb33  lock xadd [r14], rsi
0x14000eb38  dec     rsi
0x14000eb3b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000eb3f  jnb     loc_14000F025
0x14000eb45  test    rsi, rsi
0x14000eb48  jz      loc_14000F02C
0x14000eb4e  mov     rsi, [rsp+100h+arg_10]
0x14000eb56  mov     eax, edi
0x14000eb58  mov     r13, [rsp+100h+var_30]
0x14000eb60  mov     rcx, [rbp+47h+var_38]
0x14000eb64  xor     rcx, rsp; StackCookie
0x14000eb67  call    __security_check_cookie
0x14000eb6c  add     rsp, 0D8h
0x14000eb73  pop     r15
0x14000eb75  pop     r14
  ... truncated ...
```
