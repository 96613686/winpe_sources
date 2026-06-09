# CaptureCompleteIsoch

- ea: `0x140001bcc`
- end: `0x140002923`
- name: `CaptureCompleteIsoch`
- size: `3415`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400015b0`
- `0x140001b60`

## callees

- `0x14000146c`
- `0x140001544`
- `0x140001a40`
- `0x140001bcc`
- `0x140002f64`
- `0x1400030e0`
- `0x140004450`
- `0x140004bac`
- `0x1400051e4`
- `0x14000566c`
- `0x140012e3c`
- `0x1400135a0`
- `0x1400190e8`
- `0x140019cd4`
- `0x14001ab4c`
- `0x14001b118`
- `0x14001b558`
- `0x140021814`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001c93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e4b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001c93`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e4b`
- `ntoskrnl!KeSetEvent` at `0x1400028d1`
- `ntoskrnl!KeSetEvent` at `0x1400028d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e6f`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400021e1`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002232`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400021e1`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140002232`
- `ks!KsStreamPointerUnlock` at `0x140001de9`
- `ks!KsStreamPointerUnlock` at `0x140002872`
- `ks!KsStreamPointerUnlock` at `0x140001de9`
- `ks!KsStreamPointerUnlock` at `0x140002872`
- `ks!KsIncrementCountedWorker` at `0x140002245`
- `ks!KsIncrementCountedWorker` at `0x140002245`

## pseudocode

```c
__int64 __fastcall CaptureCompleteIsoch(__int64 a1, __int64 a2, __int64 a3)
{
  struct _KSPIN *v3; // r13
  int v4; // esi
  struct _LIST_ENTRY *v5; // r14
  __int64 v6; // r8
  char *Context; // rdi
  __int64 v8; // r12
  __int64 v9; // rbx
  int v10; // r15d
  int v11; // r15d
  struct _KSPIN *v12; // rax
  unsigned int Flink_high; // r8d
  unsigned int *v14; // rsi
  unsigned int v15; // r12d
  int v16; // eax
  int v17; // eax
  bool v18; // cc
  int v19; // eax
  int v20; // eax
  KIRQL v21; // al
  KIRQL v22; // si
  __int64 v24; // r8
  unsigned int v25; // ecx
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // edx
  __int64 v30; // rsi
  unsigned int i; // r15d
  __int64 v32; // rcx
  int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // r15d
  __int64 v36; // r8
  int v37; // eax
  _DWORD *v38; // rax
  _DWORD *Data; // rax
  _DWORD *v40; // rax
  int v41; // eax
  __int64 v42; // rdx
  unsigned int v43; // ecx
  struct _KSPIN *v44; // rcx
  int v45; // eax
  __int64 v46; // rdx
  unsigned int v47; // ecx
  PDEVICE_OBJECT v48; // rcx
  __int64 v49; // r8
  unsigned int v50; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v51; // [rsp+54h] [rbp-15h]
  PKSSTREAM_POINTER StreamPointer; // [rsp+58h] [rbp-11h] BYREF
  PKSSTREAM_POINTER LeadingEdgeStreamPointer; // [rsp+60h] [rbp-9h] BYREF
  __int64 v54; // [rsp+68h] [rbp-1h]
  PKSPIN Pin; // [rsp+70h] [rbp+7h]
  KIRQL NewIrql; // [rsp+D0h] [rbp+67h]
  unsigned int v57; // [rsp+D8h] [rbp+6Fh]
  struct _LIST_ENTRY *v58; // [rsp+E0h] [rbp+77h] BYREF
  int v59; // [rsp+E8h] [rbp+7Fh] BYREF

  v58 = (struct _LIST_ENTRY *)a3;
  v3 = *(struct _KSPIN **)(a3 + 16);
  v4 = *(_DWORD *)(a2 + 48);
  v5 = (struct _LIST_ENTRY *)a3;
  v6 = *(_QWORD *)(a3 + 32);
  Context = (char *)v3->Context;
  v8 = *(_QWORD *)Context;
  v9 = *((_QWORD *)Context + 12);
  v54 = *(_QWORD *)Context;
  StreamPointer = 0;
  LeadingEdgeStreamPointer = 0;
  v59 = 0;
  v50 = 0;
  v10 = *(_DWORD *)(v6 + 4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qdqqdD(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      v6,
      Context,
      v3->Id,
      v5,
      v6,
      *(_DWORD *)((Context[440] != 0 ? 0x10 : 0) + v6 + 36),
      v4);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
        Context,
        v5,
        v10);
    ++*(_DWORD *)(v9 + 68);
    v4 = -1073741668;
  }
  v11 = 0;
  if ( !*(_DWORD *)v9 )
  {
LABEL_35:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 35, v6, Context, v5, v5[2].Flink, v4);
    goto LABEL_36;
  }
  if ( *((_DWORD *)Context + 9) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 17, v6, Context, v5, v5[2].Flink, v4);
    ++*(_DWORD *)(v9 + 84);
  }
  if ( *((_DWORD *)Context + 13) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 18, v6, Context, v5, v5[2].Flink, v4);
    ExInterlockedInsertTailList((PLIST_ENTRY)(v9 + 168), v5, (PKSPIN_LOCK)(v9 + 184));
    *(_DWORD *)(v9 + 24) = 0;
  }
  else
  {
    if ( v4 >= 0 )
    {
      NewIrql = 0;
      if ( *(_DWORD *)(v9 + 8) )
        *(_DWORD *)(v9 + 8) = 0;
      if ( !Context[440] )
        NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 304));
      StreamPointer = (PKSSTREAM_POINTER)CaptureGetLeadingEdgeStreamPointer(v3, &v59, 1);
      v12 = *(struct _KSPIN **)(136LL * v3->Id + *(_QWORD *)(*(_QWORD *)Context + 744LL) + 24);
      Pin = v12;
      if ( v12 )
        LeadingEdgeStreamPointer = (PKSSTREAM_POINTER)CaptureGetLeadingEdgeStreamPointer(v12, &v50, 1);
      Flink_high = HIDWORD(v5[2].Flink[8].Flink);
      v57 = Flink_high;
      if ( Flink_high != *(_DWORD *)(v8 + 704)
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
          Context,
          v3->Id);
        Flink_high = v57;
      }
      v14 = (unsigned int *)&v5[2].Flink[8].Blink + 1;
      if ( !Context[440] )
      {
        if ( !Flink_high )
          goto LABEL_28;
        v15 = 0;
        while ( StreamPointer )
        {
          v16 = v14[2];
          if ( v16 >= 0 )
          {
            v24 = *v14;
            if ( (_DWORD)v24 != v11 || (v25 = v14[1], v25 > *((_DWORD *)Context + 7)) || v16 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_ddDDD(WPP_GLOBAL_Control->AttachedDevice, 22, v24, v3->Id, v15, v24, v14[1], v16);
              v14[2] = -1073741805;
              ++*(_DWORD *)(v9 + 76);
              ++*(_DWORD *)(v9 + 88);
            }
            else if ( (int)CaptureProcessDataPayload(
                             (__int64)v5,
                             (size_t *)&StreamPointer,
                             (size_t *)&LeadingEdgeStreamPointer,
                             (unsigned __int8 *)v5[2].Blink + (unsigned int)v24,
                             v25,
                             (__int64)&v59,
                             &v50) < 0
                   && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v15);
            }
            Flink_high = v57;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids);
              Flink_high = v57;
            }
            ++*(_DWORD *)(v9 + 76);
          }
          v11 += *((_DWORD *)Context + 7);
          ++v15;
          v14 += 3;
          if ( v15 >= Flink_high )
            goto LABEL_28;
        }
LABEL_145:
        if ( !Context[440] )
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_dd(
              WPP_GLOBAL_Control->AttachedDevice,
              32,
              WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
              Flink_high - v15,
              Flink_high);
          }
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
            McTemplateK0_EtwWriteTransfer(v48, USBVideo_USBBufferOverrun);
          *(_DWORD *)(v9 + 28) = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids);
          }
        }
LABEL_28:
        if ( StreamPointer )
        {
          KsStreamPointerUnlock(StreamPointer, 0);
          StreamPointer = 0;
        }
        if ( LeadingEdgeStreamPointer )
        {
          KsStreamPointerUnlock(LeadingEdgeStreamPointer, 0);
          LeadingEdgeStreamPointer = 0;
        }
        if ( !Context[440] )
          KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 304), NewIrql);
        v20 = CaptureReQueueUrb(v5);
        v4 = v20;
        if ( v20 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_36;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 34, v6, Context, v5, v9, v20);
        }
        goto LABEL_35;
      }
      v15 = 0;
      v51 = 0;
      memset((void *)(v9 + 1660), 0, 0x64Cu);
      *(_DWORD *)(v9 + 1660) = *(_DWORD *)(*((_QWORD *)Context + 52) + 24LL);
      v26 = *((_DWORD *)Context + 6);
      if ( v26 )
      {
        if ( v26 == 2 )
        {
          v27 = *((_QWORD *)Context + 52);
          goto LABEL_50;
        }
      }
      else
      {
        v27 = *(_QWORD *)(136LL * v3->Id + *(_QWORD *)(*(_QWORD *)Context + 744LL) + 24);
        if ( v27 )
        {
LABEL_50:
          v28 = *(_DWORD *)(v27 + 24);
LABEL_51:
          v29 = v57;
          *(_DWORD *)(v9 + 1664) = v28;
          if ( v57 )
          {
            v34 = *((_DWORD *)Context + 7);
            v35 = 0;
            do
            {
              v36 = v14[2];
              if ( (int)v36 >= 0 )
              {
                if ( *v14 != v15 || v14[1] > v34 || (_DWORD)v36 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_ddDDD(WPP_GLOBAL_Control->AttachedDevice, 25, v36, v3->Id, v35, *v14, v14[1], v14[2]);
                    v29 = v57;
                  }
                  *v14 = v15;
                  v14[1] = 0;
                  v14[2] = -1073741805;
                  ++*(_DWORD *)(v9 + 76);
                  ++*(_DWORD *)(v9 + 88);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids);
                  v29 = v57;
                }
                ++*(_DWORD *)(v9 + 76);
                v14[1] = 0;
              }
              v34 = *((_DWORD *)Context + 7);
              ++v35;
              v15 += v34;
              v14 += 3;
            }
            while ( v35 < v29 );
            v5 = v58;
            v15 = v51;
          }
          v30 = v54;
          memmove((void *)(v9 + 1728), (char *)&v5[2].Flink[8].Blink + 4, 12LL * *(unsigned int *)(v54 + 704));
          for ( i = 0; ; ++i )
          {
            if ( i >= *(_DWORD *)(v30 + 704) )
            {
LABEL_27:
              Flink_high = v57;
              if ( v15 >= v57 )
                goto LABEL_28;
              goto LABEL_145;
            }
            LODWORD(v58) = 0;
            memset((void *)(v9 + 3344), 0, 0x8020u);
            if ( StreamPointer )
            {
              v37 = *((_DWORD *)Context + 6);
              if ( v37 )
              {
                if ( v37 == 2 )
                {
                  Data = StreamPointer->StreamHeader->Data;
                  *(_OWORD *)(v9 + 1704) = *(_OWORD *)Data;
                  *(_DWORD *)(v9 + 1720) = Data[4];
                }
              }
              else
              {
                v38 = StreamPointer->StreamHeader->Data;
                *(_OWORD *)(v9 + 1684) = *(_OWORD *)v38;
                *(_DWORD *)(v9 + 1700) = v38[4];
              }
            }
            if ( LeadingEdgeStreamPointer )
            {
              v40 = LeadingEdgeStreamPointer->StreamHeader->Data;
              *(_OWORD *)(v9 + 1704) = *(_OWORD *)v40;
              *(_DWORD *)(v9 + 1720) = v40[4];
            }
            v32 = v54;
            *(struct _LIST_ENTRY *)(v9 + 1668) = *(struct _LIST_ENTRY *)((char *)&v5[2].Flink[2] + 4);
            *(_DWORD *)(v9 + 3268) = *(_DWORD *)(v32 + 704);
            *(_DWORD *)(v9 + 3264) = *((_DWORD *)Context + 7);
            if ( !StreamPointer && !LeadingEdgeStreamPointer )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids);
              }
              goto LABEL_27;
            }
            v33 = USBVideoCallTrustlet(
                    *(_QWORD *)(v32 + 24),
                    2228248,
                    (int)v9 + 1660,
                    1612,
                    v9 + 3344,
                    32800,
                    (__int64)&v58);
            if ( v33 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  30,
                  WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                  (unsigned int)v33);
              }
              goto LABEL_27;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_qddd(
                WPP_GLOBAL_Control->AttachedDevice,
                26,
                WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                Context,
                v3->Id,
                *((_DWORD *)Context + 6),
                (_DWORD)v58);
            if ( !StreamPointer )
              goto LABEL_63;
            v17 = *((_DWORD *)Context + 6);
            if ( v17 )
              break;
            *((_DWORD *)StreamPointer->StreamHeader->Data + 5) = *(_DWORD *)(v9 + 3348);
            v18 = *(_DWORD *)(v9 + 3356) <= 0x7F80u;
            v19 = *(_DWORD *)(v9 + 3348);
            *(_DWORD *)(v9 + 56) = v19;
            *(_DWORD *)(v9 + 52) = v19;
            *(_QWORD *)(v9 + 128) = *(_QWORD *)(v9 + 3408);
            if ( v18 )
            {
              UpdateSecureFrameMetadataInfo(StreamPointer, Context, v9 + 3344, v9 + 3500);
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                27,
                WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                Context,
                v3->Id);
            }
            if ( !*(_DWORD *)(v9 + 3344) )
              goto LABEL_27;
            *(_QWORD *)(v9 + 128) = *(_QWORD *)(v9 + 3408);
            if ( (int)CaptureEjectAndAcquireDataFrame(v3) < 0 || !*(_DWORD *)(v9 + 3492) )
              goto LABEL_27;
LABEL_64:
            v30 = v54;
          }
          if ( v17 == 2 )
          {
            *((_DWORD *)StreamPointer->StreamHeader->Data + 5) = *(_DWORD *)(v9 + 3420);
            v41 = *(_DWORD *)(v9 + 3420);
            v42 = *(unsigned int *)(v9 + 3356);
            v43 = v42 + *(_DWORD *)(v9 + 3428);
            *(_DWORD *)(v9 + 56) = v41;
            *(_DWORD *)(v9 + 52) = v41;
            if ( v43 > 0x7F80 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  28,
                  WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                  Context,
                  v3->Id);
            }
            else
            {
              UpdateSecureFrameMetadataInfo(StreamPointer, Context, v9 + 3416, v9 + v42 + 3500);
            }
            if ( !*(_DWORD *)(v9 + 3416) )
              goto LABEL_27;
            v44 = v3;
          }
          else
          {
LABEL_63:
            if ( !LeadingEdgeStreamPointer )
              goto LABEL_64;
            *((_DWORD *)LeadingEdgeStreamPointer->StreamHeader->Data + 5) = *(_DWORD *)(v9 + 3420);
            v45 = *(_DWORD *)(v9 + 3420);
            v46 = *(unsigned int *)(v9 + 3356);
            v47 = v46 + *(_DWORD *)(v9 + 3428);
            *(_DWORD *)(v9 + 56) = v45;
            *(_DWORD *)(v9 + 52) = v45;
            *(_QWORD *)(v9 + 128) = *(_QWORD *)(v9 + 3480);
            if ( v47 > 0x7F80 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  29,
                  WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                  Context,
                  v3->Id);
            }
            else
            {
              UpdateSecureFrameMetadataInfo(StreamPointer, Context, v9 + 3416, v9 + v46 + 3500);
            }
            if ( !*(_DWORD *)(v9 + 3416) )
              goto LABEL_27;
            v44 = Pin;
          }
          *(_QWORD *)(v9 + 128) = *(_QWORD *)(v9 + 3480);
          if ( (int)CaptureEjectAndAcquireDataFrame(v44) < 0 )
            goto LABEL_27;
          goto LABEL_64;
        }
      }
      v28 = -1;
      goto LABEL_51;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 19, v6, Context, v5, v5[2].Flink, v4);
    *((_DWORD *)Context + 13) = 1;
    *(_DWORD *)(v9 + 24) = 0;
    ExInterlockedInsertTailList((PLIST_ENTRY)(v9 + 168), v5, (PKSPIN_LOCK)(v9 + 184));
    KsIncrementCountedWorker(*(PKSWORKER *)(v9 + 208));
  }
LABEL_36:
  v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 15);
  _InterlockedDecrement((volatile signed __int32 *)Context + 9);
  v22 = v21;
  if ( !*((_DWORD *)Context + 9) )
  {
    KeSetEvent((PRKEVENT)(Context + 128), 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqqD(WPP_GLOBAL_Control->AttachedDevice, 36, v49, Context, v5, v5[2].Flink, -1073741802);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 15, v22);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001bcc  mov     [rsp-8+arg_10], r8
0x140001bd1  mov     qword ptr [rsp-8+NewIrql], rcx
0x140001bd6  push    rbp
0x140001bd7  push    rbx
0x140001bd8  push    rsi
0x140001bd9  push    rdi
0x140001bda  push    r12
0x140001bdc  push    r13
0x140001bde  push    r14
0x140001be0  push    r15
0x140001be2  lea     rbp, [rsp-1Fh]
0x140001be7  sub     rsp, 88h
0x140001bee  mov     r13, [r8+10h]
0x140001bf2  xor     eax, eax
0x140001bf4  mov     esi, [rdx+30h]
0x140001bf7  mov     r14, r8
0x140001bfa  mov     r8, [r8+20h]
0x140001bfe  mov     rdi, [r13+10h]
0x140001c02  mov     r12, [rdi]
0x140001c05  mov     rbx, [rdi+60h]
0x140001c09  mov     [rbp+57h+var_58], r12
0x140001c0d  mov     [rbp+57h+StreamPointer], rax
0x140001c11  mov     [rbp+57h+var_60], rax
0x140001c15  mov     [rbp+57h+arg_18], eax
0x140001c18  mov     [rbp+57h+var_70], eax
0x140001c1b  mov     al, [rdi+1B8h]
0x140001c21  lea     rdx, WPP_GLOBAL_Control
0x140001c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c2f  neg     al
0x140001c31  mov     r15d, [r8+4]
0x140001c35  sbb     rax, rax
0x140001c38  and     eax, 10h
0x140001c3b  cmp     rcx, rdx
0x140001c3e  jnz     loc_140001F06
0x140001c44  test    r15d, r15d
0x140001c47  jnz     loc_14000210F
0x140001c4d  xor     r15d, r15d
0x140001c50  cmp     [rbx], r15d
0x140001c53  jz      loc_140001EFA
0x140001c59  cmp     dword ptr [rdi+24h], 1
0x140001c5d  jz      loc_140002157
0x140001c63  cmp     [rdi+34h], r15d
0x140001c67  jnz     loc_14000219B
0x140001c6d  test    esi, esi
0x140001c6f  js      loc_14000225D
0x140001c75  mov     [rbp+57h+NewIrql], r15b
0x140001c79  cmp     [rbx+8], r15d
0x140001c7d  jnz     loc_140002271
0x140001c83  cmp     [rdi+1B8h], r15b
0x140001c8a  jnz     short loc_140001CA2
0x140001c8c  lea     rcx, [rbx+130h]; SpinLock
0x140001c93  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001c9a  nop     dword ptr [rax+rax+00h]
0x140001c9f  mov     [rbp+57h+NewIrql], al
0x140001ca2  mov     r8d, 1
0x140001ca8  lea     rdx, [rbp+57h+arg_18]
0x140001cac  mov     rcx, r13
0x140001caf  call    CaptureGetLeadingEdgeStreamPointer
0x140001cb4  mov     [rbp+57h+StreamPointer], rax
0x140001cb8  mov     eax, [r13+18h]
0x140001cbc  imul    rdx, rax, 88h
0x140001cc3  mov     rax, [rdi]
0x140001cc6  mov     rcx, [rax+2E8h]
0x140001ccd  mov     rax, [rdx+rcx+18h]
0x140001cd2  mov     [rbp+57h+Pin], rax
0x140001cd6  test    rax, rax
0x140001cd9  jnz     loc_14000227A
0x140001cdf  mov     rax, [r14+20h]
0x140001ce3  mov     r8d, [rax+84h]
0x140001cea  mov     [rbp+57h+arg_8], r8d
0x140001cee  cmp     r8d, [r12+2C0h]
0x140001cf6  jnz     loc_140002295
0x140001cfc  lea     rdx, WPP_GLOBAL_Control
0x140001d03  mov     rsi, [r14+20h]
0x140001d07  add     rsi, 8Ch
0x140001d0e  cmp     [rdi+1B8h], r15b
0x140001d15  jnz     loc_140001F7E
0x140001d1b  test    r8d, r8d
0x140001d1e  jz      loc_140001DD7
0x140001d24  mov     r12d, r15d
0x140001d27  cmp     [rbp+57h+StreamPointer], 0
0x140001d2c  jz      loc_1400027D6
0x140001d32  mov     eax, [rsi+8]
0x140001d35  test    eax, eax
0x140001d37  jns     loc_140001E95
0x140001d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d44  cmp     rcx, rdx
0x140001d47  jnz     loc_1400022DF
0x140001d4d  inc     dword ptr [rbx+4Ch]
0x140001d50  add     r15d, [rdi+1Ch]
0x140001d54  inc     r12d
0x140001d57  add     rsi, 0Ch
0x140001d5b  cmp     r12d, r8d
0x140001d5e  jb      short loc_140001D27
0x140001d60  jmp     short loc_140001DD4
0x140001d62  mov     eax, [rdi+18h]
0x140001d65  test    eax, eax
0x140001d67  jnz     loc_14000261A
0x140001d6d  mov     rax, [rcx+10h]
0x140001d71  mov     rcx, [rax+28h]
0x140001d75  mov     eax, [rbx+0D14h]
0x140001d7b  mov     [rcx+14h], eax
0x140001d7e  cmp     dword ptr [rbx+0D1Ch], 7F80h
0x140001d88  mov     eax, [rbx+0D14h]
0x140001d8e  mov     [rbx+38h], eax
0x140001d91  mov     [rbx+34h], eax
0x140001d94  mov     rax, [rbx+0D50h]
0x140001d9b  mov     [rbx+80h], rax
0x140001da2  ja      loc_14000259C
0x140001da8  mov     rcx, [rbp+57h+StreamPointer]
0x140001dac  lea     r9, [rbx+0DACh]
0x140001db3  mov     r8, rsi
0x140001db6  mov     rdx, rdi
0x140001db9  call    UpdateSecureFrameMetadataInfo
0x140001dbe  cmp     dword ptr [rsi], 0
0x140001dc1  jnz     loc_1400025DB
0x140001dc7  mov     r8d, [rbp+57h+arg_8]
0x140001dcb  cmp     r12d, r8d
0x140001dce  jb      loc_1400027D6
0x140001dd4  xor     r15d, r15d
0x140001dd7  lea     r13, WPP_GLOBAL_Control
0x140001dde  mov     rcx, [rbp+57h+StreamPointer]; StreamPointer
0x140001de2  test    rcx, rcx
0x140001de5  jz      short loc_140001DF9
0x140001de7  xor     edx, edx; Eject
0x140001de9  call    cs:__imp_KsStreamPointerUnlock
0x140001df0  nop     dword ptr [rax+rax+00h]
0x140001df5  mov     [rbp+57h+StreamPointer], r15
0x140001df9  mov     rcx, [rbp+57h+var_60]; StreamPointer
0x140001dfd  test    rcx, rcx
0x140001e00  jnz     loc_140002870
0x140001e06  cmp     [rdi+1B8h], r15b
0x140001e0d  jnz     short loc_140001E25
0x140001e0f  mov     dl, [rbp+57h+NewIrql]; NewIrql
0x140001e12  lea     rcx, [rbx+130h]; SpinLock
0x140001e19  call    cs:__imp_KeReleaseSpinLock
0x140001e20  nop     dword ptr [rax+rax+00h]
0x140001e25  mov     rcx, r14
0x140001e28  call    CaptureReQueueUrb
0x140001e2d  mov     esi, eax
0x140001e2f  test    eax, eax
0x140001e31  js      loc_140002887
0x140001e37  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e3e  cmp     rcx, r13
0x140001e41  jnz     loc_140001F4C
0x140001e47  lea     rcx, [rdi+78h]; SpinLock
0x140001e4b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001e52  nop     dword ptr [rax+rax+00h]
0x140001e57  lock dec dword ptr [rdi+24h]
0x140001e5b  mov     sil, al
0x140001e5e  cmp     [rdi+24h], r15d
0x140001e62  jz      loc_1400028C5
0x140001e68  mov     dl, sil; NewIrql
0x140001e6b  lea     rcx, [rdi+78h]; SpinLock
0x140001e6f  call    cs:__imp_KeReleaseSpinLock
0x140001e76  nop     dword ptr [rax+rax+00h]
0x140001e7b  mov     eax, 0C0000016h
0x140001e80  add     rsp, 88h
0x140001e87  pop     r15
0x140001e89  pop     r14
0x140001e8b  pop     r13
0x140001e8d  pop     r12
0x140001e8f  pop     rdi
0x140001e90  pop     rsi
0x140001e91  pop     rbx
0x140001e92  pop     rbp
0x140001e93  retn
0x140001e95  mov     r8d, [rsi]
0x140001e98  cmp     r8d, r15d
0x140001e9b  jnz     loc_14000235A
0x140001ea1  mov     ecx, [rsi+4]
0x140001ea4  cmp     ecx, [rdi+1Ch]
0x140001ea7  ja      loc_14000235A
0x140001ead  test    eax, eax
0x140001eaf  jnz     loc_14000235A
0x140001eb5  mov     r9d, r8d
0x140001eb8  lea     rax, [rbp+57h+var_70]
0x140001ebc  add     r9, [r14+28h]
0x140001ec0  lea     r8, [rbp+57h+var_60]
0x140001ec4  mov     [rsp+0C0h+var_90], rax
0x140001ec9  lea     rdx, [rbp+57h+StreamPointer]
0x140001ecd  lea     rax, [rbp+57h+arg_18]
0x140001ed1  mov     [rsp+0C0h+var_98], rax
0x140001ed6  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x140001eda  mov     rcx, r14
0x140001edd  call    CaptureProcessDataPayload
0x140001ee2  test    eax, eax
0x140001ee4  js      loc_14000231B
0x140001eea  lea     rdx, WPP_GLOBAL_Control
0x140001ef1  mov     r8d, [rbp+57h+arg_8]
0x140001ef5  jmp     loc_140001D50
0x140001efa  lea     r13, WPP_GLOBAL_Control
0x140001f01  jmp     loc_140001E37
0x140001f06  cmp     byte ptr [rcx+29h], 5
0x140001f0a  jb      loc_140001C44
0x140001f10  mov     eax, [rax+r8+24h]
0x140001f15  mov     edx, 0Fh
0x140001f1a  mov     rcx, [rcx+18h]
0x140001f1e  mov     r9, rdi
0x140001f21  mov     [rsp+0C0h+var_80], esi
0x140001f25  mov     [rsp+0C0h+var_88], eax
0x140001f29  mov     eax, [r13+18h]
0x140001f2d  mov     [rsp+0C0h+var_90], r8
0x140001f32  mov     [rsp+0C0h+var_98], r14
0x140001f37  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140001f3b  call    WPP_SF_qdqqdD
0x140001f40  lea     rdx, WPP_GLOBAL_Control
0x140001f47  jmp     loc_140001C44
0x140001f4c  cmp     byte ptr [rcx+29h], 5
0x140001f50  jb      loc_140001E47
0x140001f56  mov     rax, [r14+20h]
0x140001f5a  mov     edx, 23h ; '#'
0x140001f5f  mov     rcx, [rcx+18h]
0x140001f63  mov     r9, rdi
0x140001f66  mov     dword ptr [rsp+0C0h+var_90], esi
0x140001f6a  mov     [rsp+0C0h+var_98], rax
0x140001f6f  mov     [rsp+0C0h+var_A0], r14
0x140001f74  call    WPP_SF_qqqD
0x140001f79  jmp     loc_140001E47
0x140001f7e  mov     r12d, r15d
0x140001f81  mov     [rbp+57h+var_6C], r15d
0x140001f85  lea     r15, [rbx+67Ch]
0x140001f8c  xor     edx, edx; Val
0x140001f8e  mov     rcx, r15; void *
0x140001f91  mov     r8d, 64Ch; Size
0x140001f97  call    memset
0x140001f9c  mov     rax, [rdi+1A0h]
0x140001fa3  mov     ecx, [rax+18h]
0x140001fa6  mov     [r15], ecx
0x140001fa9  mov     eax, [rdi+18h]
0x140001fac  test    eax, eax
0x140001fae  jnz     loc_1400023AC
0x140001fb4  mov     eax, [r13+18h]
0x140001fb8  imul    rdx, rax, 88h
0x140001fbf  mov     rax, [rdi]
0x140001fc2  mov     rcx, [rax+2E8h]
0x140001fc9  mov     rax, [rdx+rcx+18h]
0x140001fce  test    rax, rax
0x140001fd1  jz      loc_1400023BD
0x140001fd7  mov     eax, [rax+18h]
0x140001fda  mov     edx, [rbp+57h+arg_8]
0x140001fdd  mov     [rbx+680h], eax
0x140001fe3  test    edx, edx
0x140001fe5  jnz     loc_1400023C5
0x140001feb  mov     rdx, [r14+20h]
0x140001fef  lea     rcx, [rbx+6C0h]; void *
0x140001ff6  mov     rsi, [rbp+57h+var_58]
0x140001ffa  add     rdx, 8Ch; Src
0x140002001  mov     eax, [rsi+2C0h]
0x140002007  lea     r8, [rax+rax*2]
0x14000200b  shl     r8, 2; Size
0x14000200f  call    memmove
0x140002014  xor     r15d, r15d
0x140002017  cmp     r15d, [rsi+2C0h]
0x14000201e  jnb     loc_140001DC7
0x140002024  lea     rsi, [rbx+0D10h]
0x14000202b  mov     dword ptr [rbp+57h+arg_10], 0
0x140002032  mov     rcx, rsi; void *
0x140002035  xor     edx, edx; Val
0x140002037  mov     r8d, 8020h; Size
0x14000203d  call    memset
0x140002042  mov     rcx, [rbp+57h+StreamPointer]
0x140002046  test    rcx, rcx
0x140002049  jnz     loc_1400024A8
0x14000204f  mov     rax, [rbp+57h+var_60]
0x140002053  test    rax, rax
0x140002056  jnz     loc_1400024FA
0x14000205c  mov     rax, [r14+20h]
0x140002060  mov     rcx, [rbp+57h+var_58]
0x140002064  movups  xmm0, xmmword ptr [rax+24h]
0x140002068  movdqu  xmmword ptr [rbx+684h], xmm0
0x140002070  mov     eax, [rcx+2C0h]
0x140002076  mov     [rbx+0CC4h], eax
0x14000207c  mov     eax, [rdi+1Ch]
0x14000207f  mov     [rbx+0CC0h], eax
0x140002085  cmp     [rbp+57h+StreamPointer], 0
0x14000208a  jz      loc_14000251B
0x140002090  mov     rcx, [rcx+18h]
0x140002094  lea     rax, [rbp+57h+arg_10]
0x140002098  mov     [rsp+0C0h+var_90], rax
0x14000209d  lea     r8, [rbx+67Ch]
0x1400020a4  mov     dword ptr [rsp+0C0h+var_98], 8020h
0x1400020ac  mov     r9d, 64Ch
0x1400020b2  mov     edx, 220018h
0x1400020b7  mov     [rsp+0C0h+var_A0], rsi
0x1400020bc  call    USBVideoCallTrustlet
0x1400020c1  mov     r9d, eax
0x1400020c4  test    eax, eax
0x1400020c6  js      loc_14000279A
0x1400020cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020d3  lea     r8, WPP_GLOBAL_Control
0x1400020da  cmp     rcx, r8
0x1400020dd  jz      short loc_1400020E9
0x1400020df  cmp     byte ptr [rcx+29h], 5
0x1400020e3  jnb     loc_140002562
0x1400020e9  mov     rcx, [rbp+57h+StreamPointer]
0x1400020ed  test    rcx, rcx
0x1400020f0  jnz     loc_140001D62
0x1400020f6  mov     rcx, [rbp+57h+var_60]
0x1400020fa  test    rcx, rcx
  ... truncated ...
```
