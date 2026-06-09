# PgmNewInboundConnection

- ea: `0x140010ae4`
- end: `0x1400114da`
- name: `PgmNewInboundConnection`
- size: `2550`
- prototype: `__int64 __fastcall(__int64, __int64, __int128 *, __int64, __int16 *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140014540`

## callees

- `0x140005068`
- `0x14000521c`
- `0x1400052e4`
- `0x1400054d0`
- `0x140005524`
- `0x140007f1c`
- `0x140008c18`
- `0x1400091f8`
- `0x14000ca08`
- `0x140010ae4`
- `0x1400124cc`
- `0x140015a88`
- `0x14001cdf0`
- `0x14001ce30`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140011090`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140011148`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140011187`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140011090`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140011148`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140011187`
- `ntoskrnl!KeInitializeTimer` at `0x14001128d`
- `ntoskrnl!KeInitializeTimer` at `0x14001128d`
- `ntoskrnl!KeInitializeDpc` at `0x1400112aa`
- `ntoskrnl!KeInitializeDpc` at `0x1400112aa`
- `ntoskrnl!KeSetTimer` at `0x1400112cb`
- `ntoskrnl!KeSetTimer` at `0x1400112cb`
- `ntoskrnl!ExAllocatePool2` at `0x140010ebb`
- `ntoskrnl!ExAllocatePool2` at `0x140010ebb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d78`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fe6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ffc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011371`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011383`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011399`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011412`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011428`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d78`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fe6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010ffc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011371`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011383`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011399`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011412`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011428`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bc5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ccc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010d18`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bc5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010ccc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010d18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010faa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010faa`

## pseudocode

```c
__int64 __fastcall PgmNewInboundConnection(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        __int16 *a5,
        int a6,
        _QWORD *a7)
{
  _QWORD *v7; // r14
  bool v8; // zf
  int v11; // eax
  unsigned __int32 v12; // r13d
  KIRQL v13; // al
  __int64 v14; // rsi
  KSPIN_LOCK *v15; // rcx
  KIRQL v16; // dl
  __int128 v17; // xmm0
  __int16 v18; // ax
  __int64 v19; // xmm1_8
  __int64 (__fastcall *v20)(__int64, __int64, _BYTE *, _QWORD, _QWORD, _DWORD, _QWORD, __int64 *, PIRP *); // rbx
  unsigned int v21; // eax
  IRP *v22; // rcx
  unsigned __int16 *FsContext; // rbx
  __int64 inited; // rax
  __int64 result; // rax
  __int16 ActiveThreadCount; // ax
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  __int64 Pool2; // rax
  int FECContext; // r14d
  void *v33; // rcx
  unsigned int v34; // ebx
  char v35; // al
  __int16 v36; // cx
  unsigned __int16 v37; // ax
  __int64 v38; // rax
  int v39; // ecx
  int v40; // edx
  struct _LIST_ENTRY **Lock; // rcx
  struct _LIST_ENTRY ***v42; // rax
  char *v43; // rdx
  KIRQL v44; // [rsp+50h] [rbp-51h]
  KIRQL v45; // [rsp+51h] [rbp-50h]
  KIRQL NewIrql; // [rsp+52h] [rbp-4Fh]
  PIRP Irp; // [rsp+58h] [rbp-49h] BYREF
  _QWORD *v48; // [rsp+60h] [rbp-41h] BYREF
  __int64 v49; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v50[22]; // [rsp+70h] [rbp-31h] BYREF
  _OWORD v51[2]; // [rsp+88h] [rbp-19h] BYREF

  v7 = a7;
  v48 = a7;
  memset(v50, 0, sizeof(v50));
  v8 = (*((_BYTE *)a5 + 5) & 1) == 0;
  v49 = 0;
  Irp = 0;
  memset(v51, 0, sizeof(v51));
  if ( !v8 )
  {
    v11 = ProcessOptions((__int64)(a5 + 12), a6 - 24, a5[2] & 0xF, (__int64)v51, 0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          154,
          WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
          (unsigned int)v11);
      return 3221226011LL;
    }
  }
  v12 = _byteswap_ulong(*((_DWORD *)a5 + 4));
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 424));
  v14 = *(_QWORD *)(a1 + 120);
  v15 = (KSPIN_LOCK *)(a1 + 424);
  v16 = v13;
  if ( !v14 )
  {
    KeReleaseSpinLock(v15, v13);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, a1);
    return 3221226011LL;
  }
  v17 = *a3;
  v18 = *a5;
  v19 = *(_QWORD *)((char *)a3 + 14);
  v20 = *(__int64 (__fastcall **)(__int64, __int64, _BYTE *, _QWORD, _QWORD, _DWORD, _QWORD, __int64 *, PIRP *))(a1 + 112);
  *(_OWORD *)v50 = v17;
  *(_WORD *)&v50[8] = v18;
  *(_QWORD *)&v50[14] = v19;
  *(_DWORD *)v50 = 1;
  KeReleaseSpinLock(v15, v16);
  v21 = v20(v14, 22, v50, 0, 0, 0, 0, &v49, &Irp);
  v22 = Irp;
  if ( v21 != -1073741802 || !Irp )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_Dqq(
        WPP_GLOBAL_Control->AttachedDevice,
        156,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        v21,
        a1,
        *(_QWORD *)(a1 + 112));
      v22 = Irp;
    }
    if ( v22 )
      PgmIoComplete(v22);
    *a7 = 0;
    return 3221226011LL;
  }
  v45 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v44 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 424));
  FsContext = (unsigned __int16 *)Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( !FsContext || *((_DWORD *)FsContext + 4) != 1381188947 || *((_QWORD *)FsContext + 3) != a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 424), v44);
    KeReleaseSpinLock(&SpinLock, v45);
    v34 = -1073741595;
    PgmIoComplete(Irp);
    goto LABEL_61;
  }
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 45);
  inited = InitReceiverData(FsContext);
  *(_QWORD *)(*((_QWORD *)FsContext + 6) + 216LL) = inited;
  if ( !inited )
  {
    *((_DWORD *)FsContext + 8) |= 0x100u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 424), NewIrql);
    KeReleaseSpinLock(&SpinLock, v44);
    KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 45, v45);
    PgmIoComplete(Irp);
    *v48 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 158, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, FsContext, a1);
    return 3221225626LL;
  }
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 32LL) = _byteswap_ulong(*(unsigned int *)&v50[10]);
  ActiveThreadCount = WPP_MAIN_CB.ActiveThreadCount;
  v27 = *((_QWORD *)FsContext + 6);
  FsContext[76] = WPP_MAIN_CB.ActiveThreadCount;
  FsContext[77] = ActiveThreadCount + 14;
  if ( (*(_DWORD *)(a1 + 56) & 0x10) != 0 )
  {
    *(_WORD *)(v27 + 288) = 9000;
    *(_QWORD *)(*((_QWORD *)FsContext + 6) + 96LL) = 5;
  }
  else
  {
    *(_WORD *)(v27 + 288) = 3000;
    *(_QWORD *)(*((_QWORD *)FsContext + 6) + 96LL) = 100;
  }
  *(_QWORD *)(*((_QWORD *)FsContext + 6) + 80LL) = *(_QWORD *)(*((_QWORD *)FsContext + 6) + 96LL);
  v28 = *((_QWORD *)FsContext + 6);
  *((_BYTE *)FsContext + 160) = 1;
  *(_WORD *)(v28 + 46) = 1;
  v29 = *(_DWORD *)(a1 + 420);
  if ( v29 || *(_BYTE *)(a1 + 305) )
  {
    v30 = *((_QWORD *)FsContext + 6);
    if ( !v29 )
      v29 = *(_DWORD *)(v30 + 32);
    *(_DWORD *)(v30 + 36) = v29;
    if ( *(_BYTE *)(a1 + 305) )
    {
      Pool2 = ExAllocatePool2(64, 2 * *(unsigned __int8 *)(a1 + 304) * (unsigned __int64)FsContext[77], 862807888);
      *((_QWORD *)FsContext + 18) = Pool2;
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            159,
            WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
            2 * *(unsigned __int8 *)(a1 + 304) * (unsigned int)FsContext[77]);
LABEL_37:
        v33 = *(void **)(*((_QWORD *)FsContext + 6) + 216LL);
        if ( v33 )
        {
          ExFreePoolWithTag(v33, 0);
          *(_QWORD *)(*((_QWORD *)FsContext + 6) + 216LL) = 0;
        }
        *((_DWORD *)FsContext + 8) |= 0x100u;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 424), NewIrql);
        KeReleaseSpinLock(&SpinLock, v44);
        KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 45, v45);
        PgmIoComplete(Irp);
        v7 = v48;
        v34 = -1073741285;
LABEL_61:
        *v7 = 0;
        return v34;
      }
      FECContext = CreateFECContext((__int64)(FsContext + 56), *(unsigned __int8 *)(a1 + 304), 0xFFu, 1);
      if ( FECContext < 0 )
      {
        ExFreePoolWithTag(*((PVOID *)FsContext + 18), 0);
        *((_QWORD *)FsContext + 18) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            160,
            WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
            (unsigned int)FECContext);
        goto LABEL_37;
      }
      *((_BYTE *)FsContext + 160) = *(_BYTE *)(a1 + 304);
      v35 = *(_BYTE *)(a1 + 305);
      *((_BYTE *)FsContext + 161) = v35;
      if ( (v35 & 1) != 0 )
        *(_WORD *)(*((_QWORD *)FsContext + 6) + 46LL) = 2;
      ExInitializeNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)FsContext + 6) + 576LL),
        0,
        0,
        0x200u,
        40LL * *((unsigned __int8 *)FsContext + 160) + 96,
        0x326D6750u,
        (unsigned int)*(_WORD *)(*((_QWORD *)FsContext + 6) + 288LL) / *((unsigned __int8 *)FsContext + 160));
      v7 = v48;
    }
    *(_WORD *)(a1 + 304) = 0;
    *(_DWORD *)(a1 + 420) = 0;
  }
  v36 = *a5;
  *((_DWORD *)FsContext + 16) = *((_DWORD *)a5 + 2);
  v37 = a5[6];
  *((_DWORD *)FsContext + 5) += 2;
  FsContext[34] = v37;
  FsContext[35] = __ROR2__(v36, 8);
  ++*(_DWORD *)(a1 + 20);
  *((_DWORD *)FsContext + 8) |= 0x228u;
  *(_QWORD *)(*((_QWORD *)FsContext + 6) + 24LL) = a1;
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 276LL) = FsContext[76] + 16;
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 280LL) = *(_DWORD *)(*((_QWORD *)FsContext + 6) + 276LL);
  v38 = *((_QWORD *)FsContext + 6);
  *((_DWORD *)FsContext + 8) |= 0x8000u;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(v38 + 320),
    0,
    0,
    0x200u,
    *(unsigned int *)(v38 + 280),
    0x446D6750u,
    *(_WORD *)(v38 + 288));
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)FsContext + 6) + 448LL),
    0,
    0,
    0x200u,
    0x88u,
    0x326D6750u,
    *(_WORD *)(*((_QWORD *)FsContext + 6) + 288LL));
  v39 = *((unsigned __int8 *)FsContext + 160);
  v40 = -v39 & v12;
  LODWORD(v48) = v40;
  if ( (BYTE4(v51[0]) & 8) != 0 )
  {
    HIDWORD(v51[0]) = HIDWORD(v51[0]) - 1 + v39;
    v40 = HIDWORD(v51[0]) & -*((unsigned __int8 *)FsContext + 160);
    HIDWORD(v51[0]) = v40;
  }
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 52LL) = v40;
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 56LL) = *(_DWORD *)(*((_QWORD *)FsContext + 6) + 52LL);
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 48LL) = *(_DWORD *)(*((_QWORD *)FsContext + 6) + 56LL);
  *(_QWORD *)(*((_QWORD *)FsContext + 6) + 88LL) = *(_QWORD *)(*((_QWORD *)FsContext + 6) + 80LL);
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 60LL) = -*((unsigned __int8 *)FsContext + 160)
                                                 & (*(_DWORD *)(*((_QWORD *)FsContext + 6) + 52LL)
                                                  - *((unsigned __int8 *)FsContext + 160));
  *(_DWORD *)(*((_QWORD *)FsContext + 6) + 64LL) = *(_DWORD *)(*((_QWORD *)FsContext + 6) + 52LL) - 1;
  Lock = (struct _LIST_ENTRY **)WPP_MAIN_CB.DeviceQueue.Lock;
  if ( *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.DeviceQueue.Lock != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink )
    __fastfail(3u);
  v42 = (struct _LIST_ENTRY ***)*((_QWORD *)FsContext + 6);
  *v42 = &WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
  v42[1] = Lock;
  *Lock = (struct _LIST_ENTRY *)v42;
  WPP_MAIN_CB.DeviceQueue.Lock = (KSPIN_LOCK)v42;
  if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument2 & 2) != 0 )
  {
    *(_QWORD *)(*((_QWORD *)FsContext + 6) + 744LL) = WPP_MAIN_CB.Dpc.SystemArgument1;
  }
  else
  {
    WPP_MAIN_CB.Dpc.SystemArgument1 = (PVOID)1;
    *(_QWORD *)(*((_QWORD *)FsContext + 6) + 744LL) = 1;
    LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) |= 2u;
    WPP_MAIN_CB.Dpc.DeferredContext = (PVOID)MEMORY[0xFFFFF78000000008];
    WPP_MAIN_CB.Dpc.DeferredRoutine = (PKDEFERRED_ROUTINE)200000;
    KeInitializeTimer((PKTIMER)&WPP_MAIN_CB.SecurityDescriptor);
    KeInitializeDpc(&Dpc, ReceiveTimerTimeout, 0);
    KeSetTimer((PKTIMER)&WPP_MAIN_CB.SecurityDescriptor, (LARGE_INTEGER)-200000LL, &Dpc);
  }
  CheckAndAddNakRequests((__int64)FsContext, (int *)&v48, 0, 0, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    v43 = byte_14001F250;
    if ( *((char *)a5 + 5) >= 0 )
      v43 = "non-";
    WPP_SF_qqddsd(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v43,
      *((_QWORD *)FsContext + 6),
      a1,
      (char)FsContext,
      v12,
      (char)v48,
      (__int64)v43,
      *(_DWORD *)(*((_QWORD *)FsContext + 6) + 52LL));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 45, NewIrql);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 424), v44);
  KeReleaseSpinLock(&SpinLock, v45);
  PgmIoComplete(Irp);
  result = 0;
  *v7 = FsContext;
  return result;
}

```

## disassembly

```asm
0x140010ae4  mov     [rsp-8+arg_8], rbx
0x140010ae9  push    rbp
0x140010aea  push    rsi
0x140010aeb  push    rdi
0x140010aec  push    r12
0x140010aee  push    r13
0x140010af0  push    r14
0x140010af2  push    r15
0x140010af4  lea     rbp, [rsp-0Fh]
0x140010af9  sub     rsp, 0B0h
0x140010b00  mov     rax, cs:__security_cookie
0x140010b07  xor     rax, rsp
0x140010b0a  mov     [rbp+3Fh+var_38], rax
0x140010b0e  mov     r12, [rbp+3Fh+arg_20]
0x140010b12  xor     esi, esi
0x140010b14  mov     r14, [rbp+3Fh+arg_30]
0x140010b18  xorps   xmm0, xmm0
0x140010b1b  xor     eax, eax
0x140010b1d  mov     [rbp+3Fh+var_80], r14
0x140010b21  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x140010b25  test    byte ptr [r12+5], 1
0x140010b2b  mov     rbx, r8
0x140010b2e  mov     rdi, rcx
0x140010b31  mov     [rbp+3Fh+var_78], rsi
0x140010b35  mov     qword ptr [rbp+3Fh+var_70+0Eh], rax
0x140010b39  mov     [rbp+3Fh+Irp], rsi
0x140010b3d  movups  [rbp+3Fh+var_58], xmm0
0x140010b41  movups  [rbp+3Fh+var_48], xmm0
0x140010b45  jz      short loc_140010BB3
0x140010b47  movzx   r8d, byte ptr [r12+4]
0x140010b4d  lea     rcx, [r12+18h]
0x140010b52  mov     edx, [rbp+3Fh+arg_28]
0x140010b55  lea     r9, [rbp+3Fh+var_58]
0x140010b59  and     r8d, 0Fh
0x140010b5d  mov     [rsp+0E0h+Size], rsi
0x140010b62  add     edx, 0FFFFFFE8h
0x140010b65  call    ProcessOptions
0x140010b6a  test    eax, eax
0x140010b6c  jns     short loc_140010BB3
0x140010b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b75  lea     rdx, WPP_GLOBAL_Control
0x140010b7c  cmp     rcx, rdx
0x140010b7f  jz      loc_1400114AD
0x140010b85  mov     edx, [rcx+2Ch]
0x140010b88  mov     esi, 2
0x140010b8d  test    sil, dl
0x140010b90  jz      loc_1400114AD
0x140010b96  mov     rcx, [rcx+18h]
0x140010b9a  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010ba1  mov     edx, 9Ah
0x140010ba6  mov     r9d, eax
0x140010ba9  call    WPP_SF_d
0x140010bae  jmp     loc_1400114AD
0x140010bb3  mov     r13d, [r12+10h]
0x140010bb8  lea     r15, [rdi+1A8h]
0x140010bbf  mov     rcx, r15; SpinLock
0x140010bc2  bswap   r13d
0x140010bc5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010bcc  nop     dword ptr [rax+rax+00h]
0x140010bd1  mov     rsi, [rdi+78h]
0x140010bd5  mov     rcx, r15; SpinLock
0x140010bd8  mov     dl, al; NewIrql
0x140010bda  test    rsi, rsi
0x140010bdd  jnz     short loc_140010C30
0x140010bdf  call    cs:__imp_KeReleaseSpinLock
0x140010be6  nop     dword ptr [rax+rax+00h]
0x140010beb  mov     rcx, cs:WPP_GLOBAL_Control
0x140010bf2  lea     rdx, WPP_GLOBAL_Control
0x140010bf9  cmp     rcx, rdx
0x140010bfc  jz      loc_1400114AD
0x140010c02  mov     eax, [rcx+2Ch]
0x140010c05  mov     esi, 2
0x140010c0a  test    sil, al
0x140010c0d  jz      loc_1400114AD
0x140010c13  mov     rcx, [rcx+18h]
0x140010c17  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010c1e  mov     edx, 9Bh
0x140010c23  mov     r9, rdi
0x140010c26  call    WPP_SF_q
0x140010c2b  jmp     loc_1400114AD
0x140010c30  movups  xmm0, xmmword ptr [rbx]
0x140010c33  movzx   eax, word ptr [r12]
0x140010c38  movsd   xmm1, qword ptr [rbx+0Eh]
0x140010c3d  mov     rbx, [rdi+70h]
0x140010c41  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x140010c45  mov     word ptr [rbp+3Fh+var_70+8], ax
0x140010c49  movsd   qword ptr [rbp+3Fh+var_70+0Eh], xmm1
0x140010c4e  mov     dword ptr [rbp+3Fh+var_70], 1
0x140010c55  call    cs:__imp_KeReleaseSpinLock
0x140010c5c  nop     dword ptr [rax+rax+00h]
0x140010c61  lea     rax, [rbp+3Fh+Irp]
0x140010c65  xor     r9d, r9d
0x140010c68  mov     [rsp+0E0h+var_A0], rax
0x140010c6d  lea     r8, [rbp+3Fh+var_70]
0x140010c71  lea     rax, [rbp+3Fh+var_78]
0x140010c75  mov     rcx, rsi
0x140010c78  mov     [rsp+0E0h+var_A8], rax
0x140010c7d  xor     eax, eax
0x140010c7f  mov     qword ptr [rsp+0E0h+Depth], rax
0x140010c84  mov     [rsp+0E0h+Tag], eax
0x140010c88  mov     [rsp+0E0h+Size], rax
0x140010c8d  lea     edx, [rax+16h]
0x140010c90  mov     rax, rbx
0x140010c93  call    _guard_dispatch_icall
0x140010c98  mov     rcx, [rbp+3Fh+Irp]
0x140010c9c  mov     r9d, eax
0x140010c9f  cmp     eax, 0C0000016h
0x140010ca4  jnz     loc_140011452
0x140010caa  test    rcx, rcx
0x140010cad  jz      loc_140011452
0x140010cb3  lea     rcx, SpinLock; SpinLock
0x140010cba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010cc1  nop     dword ptr [rax+rax+00h]
0x140010cc6  mov     rcx, r15; SpinLock
0x140010cc9  mov     [rbp+3Fh+var_8F], al
0x140010ccc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010cd3  nop     dword ptr [rax+rax+00h]
0x140010cd8  mov     rcx, [rbp+3Fh+Irp]
0x140010cdc  mov     [rbp+3Fh+var_90], al
0x140010cdf  mov     rdx, [rcx+0B8h]
0x140010ce6  mov     rcx, [rdx+30h]
0x140010cea  mov     rbx, [rcx+18h]
0x140010cee  test    rbx, rbx
0x140010cf1  jz      loc_1400113BD
0x140010cf7  cmp     dword ptr [rbx+10h], 52534553h
0x140010cfe  jnz     loc_1400113BD
0x140010d04  cmp     [rbx+18h], rdi
0x140010d08  jnz     loc_1400113BD
0x140010d0e  lea     rsi, [rbx+168h]
0x140010d15  mov     rcx, rsi; SpinLock
0x140010d18  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010d1f  nop     dword ptr [rax+rax+00h]
0x140010d24  mov     rcx, rbx
0x140010d27  mov     [rbp+3Fh+NewIrql], al
0x140010d2a  call    InitReceiverData
0x140010d2f  mov     rdx, [rbx+30h]
0x140010d33  mov     [rdx+0D8h], rax
0x140010d3a  xor     edx, edx
0x140010d3c  test    rax, rax
0x140010d3f  jnz     loc_140010DE9
0x140010d45  mov     dl, [rbp+3Fh+NewIrql]; NewIrql
0x140010d48  mov     rcx, r15; SpinLock
0x140010d4b  bts     dword ptr [rbx+20h], 8
0x140010d50  call    cs:__imp_KeReleaseSpinLock
0x140010d57  nop     dword ptr [rax+rax+00h]
0x140010d5c  mov     dl, [rbp+3Fh+var_90]; NewIrql
0x140010d5f  lea     rcx, SpinLock; SpinLock
0x140010d66  call    cs:__imp_KeReleaseSpinLock
0x140010d6d  nop     dword ptr [rax+rax+00h]
0x140010d72  mov     dl, [rbp+3Fh+var_8F]; NewIrql
0x140010d75  mov     rcx, rsi; SpinLock
0x140010d78  call    cs:__imp_KeReleaseSpinLock
0x140010d7f  nop     dword ptr [rax+rax+00h]
0x140010d84  mov     rcx, [rbp+3Fh+Irp]; Irp
0x140010d88  mov     r14d, 0C000009Ah
0x140010d8e  mov     edx, r14d
0x140010d91  xor     r8d, r8d
0x140010d94  call    PgmIoComplete
0x140010d99  mov     rax, [rbp+3Fh+var_80]
0x140010d9d  mov     qword ptr [rax], 0
0x140010da4  mov     rcx, cs:WPP_GLOBAL_Control
0x140010dab  lea     rdx, WPP_GLOBAL_Control
0x140010db2  cmp     rcx, rdx
0x140010db5  jz      short loc_140010DE1
0x140010db7  mov     eax, [rcx+2Ch]
0x140010dba  mov     esi, 2
0x140010dbf  test    sil, al
0x140010dc2  jz      short loc_140010DE1
0x140010dc4  mov     rcx, [rcx+18h]
0x140010dc8  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010dcf  mov     edx, 9Eh
0x140010dd4  mov     [rsp+0E0h+Size], rdi
0x140010dd9  mov     r9, rbx
0x140010ddc  call    WPP_SF_qq
0x140010de1  mov     eax, r14d
0x140010de4  jmp     loc_1400114B2
0x140010de9  mov     ecx, dword ptr [rbp+3Fh+var_70+0Ah]
0x140010dec  mov     rax, [rbx+30h]
0x140010df0  bswap   ecx
0x140010df2  mov     [rax+20h], ecx
0x140010df5  movzx   eax, word ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x140010dfc  mov     rcx, [rbx+30h]
0x140010e00  mov     [rbx+98h], ax
0x140010e07  add     ax, 0Eh
0x140010e0b  mov     [rbx+9Ah], ax
0x140010e12  mov     eax, [rdi+38h]
0x140010e15  test    al, 10h
0x140010e17  jz      short loc_140010E30
0x140010e19  mov     word ptr [rcx+120h], 2328h
0x140010e22  mov     rax, [rbx+30h]
0x140010e26  mov     qword ptr [rax+60h], 5
0x140010e2e  jmp     short loc_140010E45
0x140010e30  mov     word ptr [rcx+120h], 0BB8h
0x140010e39  mov     rax, [rbx+30h]
0x140010e3d  mov     qword ptr [rax+60h], 64h ; 'd'
0x140010e45  mov     rcx, [rbx+30h]
0x140010e49  mov     r8d, 1
0x140010e4f  mov     rax, [rcx+60h]
0x140010e53  lea     esi, [r8+1]
0x140010e57  mov     [rcx+50h], rax
0x140010e5b  mov     rax, [rbx+30h]
0x140010e5f  mov     [rbx+0A0h], r8b
0x140010e66  mov     [rax+2Eh], r8w
0x140010e6b  mov     eax, [rdi+1A4h]
0x140010e71  test    eax, eax
0x140010e73  jnz     short loc_140010E81
0x140010e75  cmp     [rdi+131h], dl
0x140010e7b  jz      loc_1400110B5
0x140010e81  mov     rcx, [rbx+30h]
0x140010e85  test    eax, eax
0x140010e87  jnz     short loc_140010E8C
0x140010e89  mov     eax, [rcx+20h]
0x140010e8c  mov     [rcx+24h], eax
0x140010e8f  cmp     [rdi+131h], dl
0x140010e95  jz      loc_1400110A6
0x140010e9b  movzx   edx, word ptr [rbx+9Ah]
0x140010ea2  mov     ecx, 40h ; '@'
0x140010ea7  movzx   eax, byte ptr [rdi+130h]
0x140010eae  mov     r8d, 336D6750h
0x140010eb4  imul    rdx, rax
0x140010eb8  add     rdx, rdx
0x140010ebb  call    cs:__imp_ExAllocatePool2
0x140010ec2  nop     dword ptr [rax+rax+00h]
0x140010ec7  mov     [rbx+90h], rax
0x140010ece  test    rax, rax
0x140010ed1  jnz     short loc_140010F21
0x140010ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x140010eda  lea     rdx, WPP_GLOBAL_Control
0x140010ee1  cmp     rcx, rdx
0x140010ee4  jz      short loc_140010F19
0x140010ee6  mov     eax, [rcx+2Ch]
0x140010ee9  test    sil, al
0x140010eec  jz      short loc_140010F19
0x140010eee  movzx   r9d, word ptr [rbx+9Ah]
0x140010ef6  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010efd  movzx   eax, byte ptr [rdi+130h]
0x140010f04  mov     edx, 9Fh
0x140010f09  mov     rcx, [rcx+18h]
0x140010f0d  imul    r9d, eax
0x140010f11  add     r9d, r9d
0x140010f14  call    WPP_SF_d
0x140010f19  mov     r14d, 0C000009Ah
0x140010f1f  jmp     short loc_140010F98
0x140010f21  movzx   edx, byte ptr [rdi+130h]
0x140010f28  lea     rcx, [rbx+70h]
0x140010f2c  mov     r9b, 1
0x140010f2f  mov     r8d, 0FFh
0x140010f35  call    CreateFECContext
0x140010f3a  mov     r14d, eax
0x140010f3d  test    eax, eax
0x140010f3f  jns     loc_140011025
0x140010f45  mov     rcx, [rbx+90h]; P
0x140010f4c  xor     edx, edx; Tag
0x140010f4e  call    cs:__imp_ExFreePoolWithTag
0x140010f55  nop     dword ptr [rax+rax+00h]
0x140010f5a  mov     qword ptr [rbx+90h], 0
0x140010f65  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f6c  lea     rdx, WPP_GLOBAL_Control
0x140010f73  cmp     rcx, rdx
0x140010f76  jz      short loc_140010F98
0x140010f78  mov     eax, [rcx+2Ch]
0x140010f7b  test    sil, al
0x140010f7e  jz      short loc_140010F98
0x140010f80  mov     rcx, [rcx+18h]
0x140010f84  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140010f8b  mov     edx, 0A0h
0x140010f90  mov     r9d, r14d
0x140010f93  call    WPP_SF_d
0x140010f98  mov     rax, [rbx+30h]
0x140010f9c  mov     rcx, [rax+0D8h]; P
0x140010fa3  test    rcx, rcx
0x140010fa6  jz      short loc_140010FC5
0x140010fa8  xor     edx, edx; Tag
0x140010faa  call    cs:__imp_ExFreePoolWithTag
0x140010fb1  nop     dword ptr [rax+rax+00h]
0x140010fb6  mov     rax, [rbx+30h]
0x140010fba  mov     qword ptr [rax+0D8h], 0
0x140010fc5  mov     dl, [rbp+3Fh+NewIrql]; NewIrql
0x140010fc8  mov     rcx, r15; SpinLock
0x140010fcb  bts     dword ptr [rbx+20h], 8
0x140010fd0  call    cs:__imp_KeReleaseSpinLock
0x140010fd7  nop     dword ptr [rax+rax+00h]
0x140010fdc  mov     dl, [rbp+3Fh+var_90]; NewIrql
0x140010fdf  lea     rcx, SpinLock; SpinLock
0x140010fe6  call    cs:__imp_KeReleaseSpinLock
0x140010fed  nop     dword ptr [rax+rax+00h]
0x140010ff2  mov     dl, [rbp+3Fh+var_8F]; NewIrql
0x140010ff5  lea     rcx, [rbx+168h]; SpinLock
0x140010ffc  call    cs:__imp_KeReleaseSpinLock
0x140011003  nop     dword ptr [rax+rax+00h]
0x140011008  mov     rcx, [rbp+3Fh+Irp]; Irp
0x14001100c  xor     r8d, r8d
0x14001100f  mov     edx, r14d
0x140011012  call    PgmIoComplete
0x140011017  mov     r14, [rbp+3Fh+var_80]
0x14001101b  mov     ebx, 0C000021Bh
0x140011020  jmp     loc_140011447
0x140011025  mov     al, [rdi+130h]
0x14001102b  mov     [rbx+0A0h], al
0x140011031  mov     al, [rdi+131h]
  ... truncated ...
```
