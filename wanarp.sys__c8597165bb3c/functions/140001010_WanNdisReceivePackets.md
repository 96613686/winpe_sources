# WanNdisReceivePackets

- ea: `0x140001010`
- end: `0x1400019b4`
- name: `WanNdisReceivePackets`
- size: `2468`
- prototype: `void __fastcall(__int64, struct _NET_BUFFER_LIST *Alignment, __int64, unsigned int, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x140001f10`
- `0x140002070`
- `0x140004b00`
- `0x1400050b0`
- `0x1400050f0`
- `0x14000f728`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140001471`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140001471`
- `ntoskrnl!KeReleaseMutex` at `0x14000193a`
- `ntoskrnl!KeReleaseMutex` at `0x14000193a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001182`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400011d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400013aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001182`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400011d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400013aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400018f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400018f2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000121d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001371`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400016ab`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000121d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001371`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400016ab`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000120a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001243`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000120a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001243`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400011ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001386`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001594`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000166f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001701`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000179b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400017ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400011ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001386`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001594`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000166f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001701`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000179b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400017ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000142b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001763`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000142b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001763`
- `NETIO!NetioInitializeNetBufferListContext` at `0x1400012ee`
- `NETIO!NetioInitializeNetBufferListContext` at `0x1400012ee`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x140001869`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x140001869`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x140001619`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x140001619`
- `NDIS!NdisReturnNetBufferLists` at `0x1400019a3`
- `NDIS!NdisReturnNetBufferLists` at `0x1400019a3`
- `NDIS!NdisGetDataBuffer` at `0x140001148`
- `NDIS!NdisGetDataBuffer` at `0x140001148`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400012ba`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400012ba`

## pseudocode

```c
void __fastcall WanNdisReceivePackets(
        __int64 a1,
        struct _NET_BUFFER_LIST *Alignment,
        __int64 a3,
        unsigned int a4,
        char a5)
{
  _QWORD *v6; // rdi
  char v7; // r10
  PNET_BUFFER_LIST *p_NetBufferLists; // rdx
  ULONG v9; // esi
  char v10; // cl
  int v11; // r12d
  __int64 v12; // rbx
  __int64 v13; // r13
  struct _NET_BUFFER *v14; // rcx
  char *DataBuffer; // rax
  __int64 v16; // r12
  KIRQL v17; // dl
  KIRQL v18; // r8
  __int64 v19; // rdx
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rdx
  struct _NET_BUFFER *v23; // rcx
  unsigned int v24; // edx
  __int64 v25; // rax
  __int64 *v26; // rax
  KIRQL v27; // dl
  KSPIN_LOCK *v28; // rcx
  _QWORD *j; // rax
  struct _KMUTANT **v30; // rdi
  KIRQL v31; // al
  struct _KMUTANT *v32; // rsi
  KIRQL v33; // r14
  BOOLEAN v34; // r12
  struct _LIST_ENTRY *v35; // rdi
  int v36; // eax
  _QWORD *v37; // rcx
  int v38; // ecx
  _QWORD *v39; // rcx
  struct _NET_BUFFER_LIST *v40; // rax
  _QWORD *v41; // rcx
  KIRQL v42; // dl
  KSPIN_LOCK *v43; // rcx
  _QWORD *i; // rax
  __int64 v45; // rax
  int LockArray_high; // edi
  struct _KMUTANT *v47; // rsi
  KIRQL CurrentIrql; // al
  _QWORD *v49; // rcx
  _QWORD *v50; // rcx
  int v51; // ecx
  int v52; // ecx
  PNET_BUFFER_LIST k; // rcx
  NDIS_HANDLE v54; // rcx
  char v55; // [rsp+30h] [rbp-91h]
  KIRQL v56; // [rsp+31h] [rbp-90h]
  int v57; // [rsp+34h] [rbp-8Dh]
  PNET_BUFFER_LIST *v58; // [rsp+38h] [rbp-89h]
  ULONG v59; // [rsp+40h] [rbp-81h]
  unsigned __int16 v60; // [rsp+44h] [rbp-7Dh]
  int v61; // [rsp+48h] [rbp-79h]
  _QWORD *v62; // [rsp+50h] [rbp-71h] BYREF
  __int64 *v63; // [rsp+58h] [rbp-69h]
  __int64 v64; // [rsp+60h] [rbp-61h]
  __int64 v65; // [rsp+68h] [rbp-59h]
  int v66; // [rsp+70h] [rbp-51h]
  __int64 v67; // [rsp+78h] [rbp-49h]
  __int64 *v68; // [rsp+80h] [rbp-41h]
  __int64 *v69; // [rsp+88h] [rbp-39h]
  PNET_BUFFER_LIST NetBufferLists; // [rsp+90h] [rbp-31h] BYREF
  int *v71; // [rsp+98h] [rbp-29h]
  __int128 Parameter; // [rsp+A0h] [rbp-21h] BYREF
  __int128 v73; // [rsp+B0h] [rbp-11h]
  __int64 Storage; // [rsp+C8h] [rbp+7h] BYREF
  int v75; // [rsp+D0h] [rbp+Fh]
  __int16 v76; // [rsp+D4h] [rbp+13h]
  int v77; // [rsp+140h] [rbp+7Fh]

  NetBufferLists = 0;
  v6 = 0;
  v62 = 0;
  if ( a1 == 212578788 )
  {
    v7 = 1;
    v69 = &qword_140009248;
    v71 = &dword_14000905C;
    v68 = &qword_1400090D8;
  }
  else
  {
    v7 = 0;
    v69 = &qword_140009498;
    v71 = &dword_1400092AC;
    v68 = &qword_140009328;
  }
  p_NetBufferLists = &NetBufferLists;
  v55 = v7;
  Storage = 0;
  v75 = 0;
  v9 = a5 & 1;
  v76 = 0;
  v59 = v9;
  v58 = &NetBufferLists;
  Parameter = 0;
  v73 = 0;
  _InterlockedAdd(&glReceivedNbls, a4);
  v10 = byte_1400099E6;
  if ( !v7 )
    v10 = byte_140009B06;
  if ( v10 )
  {
    if ( !Alignment )
      return;
    v11 = a5 & 2;
    v12 = 0;
    v56 = 0;
    v64 = 0;
    v13 = (__int64)Alignment;
    v67 = 0;
    v65 = 0;
    v61 = -1;
    v63 = (__int64 *)&v62;
    v77 = v11;
    v66 = v11;
    v57 = v11;
    while ( 1 )
    {
      v14 = *(struct _NET_BUFFER **)(v13 + 8);
      Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      *(_QWORD *)(v13 + 112) = 0;
      DataBuffer = (char *)NdisGetDataBuffer(v14, 0xEu, &Storage, 1u, 0);
      if ( !DataBuffer )
      {
        v36 = v11;
LABEL_51:
        if ( v36 )
        {
          p_NetBufferLists = v58;
        }
        else
        {
          v37 = v58;
          p_NetBufferLists = (PNET_BUFFER_LIST *)v13;
          v58 = (PNET_BUFFER_LIST *)v13;
          *v37 = v13;
        }
        v11 = v66;
        v57 = v66;
        v77 = v66;
        goto LABEL_28;
      }
      v60 = __ROR2__(*((_WORD *)DataBuffer + 6), 8);
      if ( v60 < 0x600u )
      {
        v36 = v57;
        goto LABEL_51;
      }
      v16 = *(unsigned int *)(DataBuffer + 2);
      v17 = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock);
      if ( (unsigned int)v16 >= g_ulConnTableSize )
      {
        KeReleaseSpinLock(&g_rlConnTableLock, v17);
        v11 = v77;
        if ( !v77 )
        {
          v41 = v58;
          p_NetBufferLists = (PNET_BUFFER_LIST *)v13;
          v58 = (PNET_BUFFER_LIST *)v13;
          *v41 = v13;
LABEL_99:
          v57 = v11;
          goto LABEL_28;
        }
LABEL_98:
        p_NetBufferLists = v58;
        goto LABEL_99;
      }
      v57 = v77;
      KeReleaseSpinLock(&g_rlConnTableLock, v17);
      if ( (_DWORD)v16 == v61 )
      {
        v22 = v67;
      }
      else
      {
        _mm_lfence();
        if ( v61 != -1 )
        {
          if ( *(_DWORD *)(v12 + 100) )
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v65 + 56));
          KeReleaseSpinLock(*(PKSPIN_LOCK *)(v12 + 80), v56);
          if ( v6 )
          {
            *v63 = 0;
            v42 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(v12 + 80));
            v43 = *(KSPIN_LOCK **)(v12 + 80);
            if ( *(_DWORD *)(v12 + 124) == 5 )
            {
              KeReleaseSpinLock(v43, v42);
            }
            else
            {
              KeReleaseSpinLock(v43, v42);
              for ( i = v62; i; i = (_QWORD *)*i )
                _InterlockedIncrement(&glFLPIndicatedNBLs);
              if ( *v69 )
              {
                *(_QWORD *)&Parameter = *(_QWORD *)(*(_QWORD *)(*v68 + 8) + 64LL);
                v45 = *(_QWORD *)(v12 + 128);
                BYTE8(v73) = v9;
                *((_QWORD *)&Parameter + 1) = v45;
                *(_QWORD *)&v73 = v62;
                LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
                v47 = (struct _KMUTANT *)*v69;
                CurrentIrql = KeGetCurrentIrql();
                NetioExpandKernelStackAndCallout(v47, LockArray_high, CurrentIrql);
                v9 = v59;
              }
              else
              {
                (*(void (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)(*v68 + 8) + 64LL))(
                  *(_QWORD *)(v12 + 128),
                  v62,
                  (unsigned __int8)v9);
              }
            }
            v6 = 0;
            v62 = 0;
            v63 = (__int64 *)&v62;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 96), 0xFFFFFFFF) == 1 )
            WanpDeleteConnEntry((PVOID)v12);
          v61 = -1;
          v67 = 0;
          v12 = 0;
          v65 = 0;
        }
        v18 = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock);
        v56 = v18;
        v19 = *((_QWORD *)g_puipConnTable + v16);
        if ( !v19 )
        {
          KeReleaseSpinLock(&g_rlConnTableLock, v18);
          if ( v77 )
          {
            p_NetBufferLists = v58;
          }
          else
          {
            v49 = v58;
            p_NetBufferLists = (PNET_BUFFER_LIST *)v13;
            v58 = (PNET_BUFFER_LIST *)v13;
            *v49 = v13;
          }
          v11 = v77;
          goto LABEL_28;
        }
        v12 = *((_QWORD *)g_puipConnTable + v16);
        _InterlockedIncrement((volatile signed __int32 *)(v19 + 96));
        KeAcquireSpinLockAtDpcLevel(*(PKSPIN_LOCK *)(v19 + 80));
        KeReleaseSpinLockFromDpcLevel(&g_rlConnTableLock);
        v20 = *(_DWORD *)(v12 + 100) == 0;
        v64 = *(_QWORD *)(v12 + 8);
        v21 = *(_QWORD *)(v12 + 16);
        v65 = v21;
        if ( !v20 )
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v21 + 56));
        v22 = v64;
        v67 = v64;
        v61 = v16;
      }
      _InterlockedAdd64((volatile signed __int64 *)(v22 + 240), *(unsigned int *)(*(_QWORD *)(v13 + 8) + 24LL));
      if ( *(_WORD *)v71 == 2 )
      {
        if ( v60 == 2048 )
          goto LABEL_19;
      }
      else if ( *(_WORD *)v71 == 23 && v60 == 0x86DD )
      {
LABEL_19:
        v11 = v77;
        if ( v77 )
        {
          v13 = NetioAllocateAndReferenceCopyNetBufferListEx(v13, FlpFreeNetBufferListChain, v12, (unsigned __int8)v9);
          if ( !v13 )
          {
            p_NetBufferLists = v58;
            v57 = v77;
            goto LABEL_28;
          }
        }
        v23 = *(struct _NET_BUFFER **)(v13 + 8);
        v24 = v23->CurrentMdlOffset + 14;
        if ( v24 < *(_DWORD *)(v23->Link.Region + 40) )
        {
          v23->DataOffset += 14;
          v23->DataLength -= 14;
          v23->CurrentMdlOffset = v24;
        }
        else
        {
          NdisAdvanceNetBufferDataStart(v23, 0xEu, 0, 0);
        }
        if ( *(_BYTE *)(v12 + 4)
          && *(_BYTE *)(v12 + 122) == 1
          && (unsigned __int8)WanpDropNetbiosPacket(*(PNET_BUFFER *)(v13 + 8)) )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v64 + 224));
          NetioRestoreNetBuffer(*(PNET_BUFFER *)(v13 + 8));
          if ( !v77 )
          {
            v50 = v58;
            p_NetBufferLists = (PNET_BUFFER_LIST *)v13;
            v58 = (PNET_BUFFER_LIST *)v13;
            *v50 = v13;
            goto LABEL_99;
          }
          NetioCompleteCopyNetBufferListChain(v6, 0, (unsigned __int8)v9);
          goto LABEL_98;
        }
        if ( !v77 )
        {
          NetioInitializeNetBufferListContext(v13, 0, FlpReturnNetBufferListChain, v12);
          *(_DWORD *)(v13 + 136) |= 0x20000000u;
          *(_QWORD *)(v13 + 112) = 0;
        }
        v25 = v64;
        *(_DWORD *)(v13 + 140) = 0;
        *(_QWORD *)(v13 + 272) = *(unsigned int *)(v25 + 360);
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 96));
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v12 + 8) + 248LL));
        v26 = v63;
        v63 = (__int64 *)v13;
        v57 = v77;
        *v26 = v13;
        v6 = v62;
        goto LABEL_27;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v22 + 216));
      v11 = v77;
      if ( !v77 )
      {
        v39 = v58;
        p_NetBufferLists = (PNET_BUFFER_LIST *)v13;
        v58 = (PNET_BUFFER_LIST *)v13;
        *v39 = v13;
        goto LABEL_28;
      }
LABEL_27:
      p_NetBufferLists = v58;
LABEL_28:
      v13 = (__int64)Alignment;
      if ( !Alignment )
      {
        if ( v61 == -1 )
          goto LABEL_46;
        if ( *(_DWORD *)(v12 + 100) )
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v65 + 56));
        KeReleaseSpinLock(*(PKSPIN_LOCK *)(v12 + 80), v56);
        if ( !v6 )
          goto LABEL_43;
        *v63 = 0;
        v27 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(v12 + 80));
        v28 = *(KSPIN_LOCK **)(v12 + 80);
        if ( *(_DWORD *)(v12 + 124) == 5 )
        {
          KeReleaseSpinLock(v28, v27);
          goto LABEL_43;
        }
        KeReleaseSpinLock(v28, v27);
        for ( j = v62; j; j = (_QWORD *)*j )
          _InterlockedIncrement(&glFLPIndicatedNBLs);
        v30 = (struct _KMUTANT **)v69;
        if ( !*v69 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)(*v68 + 8) + 64LL))(
            *(_QWORD *)(v12 + 128),
            v62,
            (unsigned __int8)v9);
          goto LABEL_43;
        }
        *(_QWORD *)&Parameter = *(_QWORD *)(*(_QWORD *)(*v68 + 8) + 64LL);
        *((_QWORD *)&Parameter + 1) = *(_QWORD *)(v12 + 128);
        *(_QWORD *)&v73 = v62;
        BYTE8(v73) = v9;
        LODWORD(v13) = HIDWORD(KeGetPcr()[1].LockArray);
        v31 = KeGetCurrentIrql();
        v32 = *v30;
        v33 = v31;
        if ( v31 < 2u )
        {
          v34 = 1;
        }
        else
        {
          v34 = 0;
          if ( (v32[1].Header.SignalState & 1) == 0 )
          {
            v38 = (int)(&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v13];
            if ( (v38 & 1) == 0 )
            {
              LODWORD((&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v13]) = v38 | 1;
              v35 = (&v32[1].Header.WaitListHead.Flink)[2 * (unsigned int)v13];
LABEL_40:
              while ( KeExpandKernelStackAndCalloutEx(
                        WanNdisReceivePacketsCalloutRoutine,
                        &Parameter,
                        0x4800u,
                        v34,
                        v35) == -1073741801 )
              {
                if ( v35 )
                  goto LABEL_53;
                if ( v33 < 2u )
                {
                  KeWaitForSingleObject(v32, Executive, 0, 0, 0);
                  v52 = (int)(&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v32[1].Header.Lock];
                  if ( (v52 & 1) != 0 )
                    goto LABEL_110;
                  v35 = (&v32[1].Header.WaitListHead.Flink)[2 * (unsigned int)v32[1].Header.Lock];
                  LODWORD((&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v32[1].Header.Lock]) = v52 | 1;
                }
                else
                {
                  v51 = (int)(&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v13];
                  if ( (v51 & 1) != 0 )
                    goto LABEL_42;
                  LODWORD((&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v13]) = v51 | 1;
                  v35 = (&v32[1].Header.WaitListHead.Flink)[2 * v13];
                }
              }
              if ( !v35 )
                goto LABEL_42;
LABEL_53:
              if ( v33 >= 2u )
              {
                LODWORD((&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v13]) &= ~1u;
                goto LABEL_42;
              }
              LODWORD((&v32[1].Header.WaitListHead.Blink)[2 * (unsigned int)v32[1].Header.Lock]) &= ~1u;
LABEL_110:
              KeReleaseMutex(v32, 0);
LABEL_42:
              v9 = v59;
LABEL_43:
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 96), 0xFFFFFFFF) == 1 )
                WanpDeleteConnEntry((PVOID)v12);
              p_NetBufferLists = v58;
LABEL_46:
              v7 = v55;
LABEL_47:
              if ( NetBufferLists )
              {
                *p_NetBufferLists = 0;
                for ( k = NetBufferLists; k; k = (PNET_BUFFER_LIST)k->Link.Alignment )
                  _InterlockedIncrement(&glReturnedNbls);
                v54 = (NDIS_HANDLE)qword_1400099E8;
                if ( !v7 )
                  v54 = NdisBindingHandle;
                NdisReturnNetBufferLists(v54, NetBufferLists, v9);
              }
              return;
            }
          }
        }
        v35 = 0;
        goto LABEL_40;
      }
    }
  }
  if ( Alignment )
  {
    do
    {
      v40 = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
      if ( (a5 & 2) == 0 )
      {
        *p_NetBufferLists = Alignment;
        p_NetBufferLists = &Alignment->Next;
      }
      Alignment = v40;
    }
    while ( v40 );
    goto LABEL_47;
  }
}

```

## disassembly

```asm
0x140001010  push    rbp
0x140001012  push    rsi
0x140001013  push    rdi
0x140001014  push    r12
0x140001016  push    r14
0x140001018  lea     rbp, [rsp-2Fh]
0x14000101d  sub     rsp, 0F0h
0x140001024  mov     rax, cs:__security_cookie
0x14000102b  xor     rax, rsp
0x14000102e  mov     [rbp+4Fh+var_38], rax
0x140001032  xor     r11d, r11d
0x140001035  mov     r14, rdx
0x140001038  mov     [rbp+4Fh+NetBufferLists], r11
0x14000103c  mov     edi, r11d
0x14000103f  mov     [rbp+4Fh+var_C0], r11
0x140001043  cmp     rcx, 0CABB1E4h
0x14000104a  jnz     loc_140001535
0x140001050  lea     rdx, qword_140009248
0x140001057  mov     r10b, 1
0x14000105a  mov     [rbp+4Fh+var_88], rdx
0x14000105e  lea     r8, dword_14000905C
0x140001065  lea     rdx, qword_1400090D8
0x14000106c  mov     [rbp+4Fh+var_78], r8
0x140001070  mov     [rbp+4Fh+var_90], rdx
0x140001074  mov     r12d, [rbp+4Fh+arg_20]
0x140001078  lea     rdx, [rbp+4Fh+NetBufferLists]
0x14000107c  xor     eax, eax
0x14000107e  mov     [rsp+110h+var_E0], r10b
0x140001083  xorps   xmm0, xmm0
0x140001086  mov     [rbp+4Fh+Storage], rax
0x14000108a  mov     esi, r12d
0x14000108d  mov     [rbp+4Fh+var_40], eax
0x140001090  and     esi, 1
0x140001093  mov     [rbp+4Fh+var_3C], ax
0x140001097  mov     [rsp+110h+var_D0], esi
0x14000109b  mov     [rsp+110h+var_D8], rdx
0x1400010a0  movups  [rbp+4Fh+Parameter], xmm0
0x1400010a4  movups  [rbp+4Fh+var_60], xmm0
0x1400010a8  lock add cs:glReceivedNbls, r9d
0x1400010b0  movzx   ecx, cs:byte_1400099E6
0x1400010b7  test    r10b, r10b
0x1400010ba  movzx   eax, cs:byte_140009B06
0x1400010c1  cmovz   ecx, eax
0x1400010c4  test    cl, cl
0x1400010c6  jz      loc_140001640
0x1400010cc  test    r14, r14
0x1400010cf  jz      loc_1400014D6
0x1400010d5  mov     [rsp+110h+arg_0], rbx
0x1400010dd  lea     rax, [rbp+4Fh+var_C0]
0x1400010e1  and     r12d, 2
0x1400010e5  mov     [rsp+110h+var_28], r13
0x1400010ed  mov     rbx, r11
0x1400010f0  mov     [rsp+110h+var_30], r15
0x1400010f8  mov     [rsp+110h+var_DF], bl
0x1400010fc  mov     r15d, 0FFFFFFFFh
0x140001102  mov     [rbp+4Fh+var_B0], r11
0x140001106  mov     r13, r14
0x140001109  mov     [rbp+4Fh+var_98], r11
0x14000110d  mov     [rbp+4Fh+var_A8], r11
0x140001111  mov     [rbp+4Fh+var_C8], 0FFFFFFFFh
0x140001118  mov     [rbp+4Fh+var_B8], rax
0x14000111c  mov     [rbp+4Fh+arg_20], r12d
0x140001120  mov     [rbp+4Fh+var_A0], r12d
0x140001124  mov     [rsp+110h+var_DC], r12d
0x140001129  mov     rcx, [r13+8]; NetBuffer
0x14000112d  lea     r8, [rbp+4Fh+Storage]; Storage
0x140001131  mov     r14, [r14]
0x140001134  mov     r9d, 1; AlignMultiple
0x14000113a  mov     edx, 0Eh; BytesNeeded
0x14000113f  mov     [r13+70h], r11
0x140001143  mov     [rsp+110h+AlignOffset], r11d; AlignOffset
0x140001148  call    cs:__imp_NdisGetDataBuffer
0x14000114f  nop     dword ptr [rax+rax+00h]
0x140001154  test    rax, rax
0x140001157  jz      loc_1400014FA
0x14000115d  movzx   ecx, word ptr [rax+0Ch]
0x140001161  mov     edx, 600h
0x140001166  ror     cx, 8
0x14000116a  mov     [rbp+4Fh+var_CC], cx
0x14000116e  cmp     cx, dx
0x140001171  jb      loc_1400015FF
0x140001177  mov     r12d, [rax+2]
0x14000117b  lea     rcx, g_rlConnTableLock; SpinLock
0x140001182  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001189  nop     dword ptr [rax+rax+00h]
0x14000118e  cmp     r12d, cs:g_ulConnTableSize
0x140001195  movzx   edx, al; NewIrql
0x140001198  jnb     loc_140001668
0x14000119e  mov     ecx, [rbp+4Fh+arg_20]
0x1400011a1  mov     [rsp+110h+var_DC], ecx
0x1400011a5  lea     rcx, g_rlConnTableLock; SpinLock
0x1400011ac  call    cs:__imp_KeReleaseSpinLock
0x1400011b3  nop     dword ptr [rax+rax+00h]
0x1400011b8  mov     edx, [rbp+4Fh+var_C8]
0x1400011bb  cmp     r12d, edx
0x1400011be  jz      loc_14000158B
0x1400011c4  lfence
0x1400011c7  cmp     edx, 0FFFFFFFFh
0x1400011ca  jnz     loc_14000169D
0x1400011d0  lea     rcx, g_rlConnTableLock; SpinLock
0x1400011d7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400011de  nop     dword ptr [rax+rax+00h]
0x1400011e3  movzx   r8d, al
0x1400011e7  mov     [rsp+110h+var_DF], al
0x1400011eb  mov     rax, cs:g_puipConnTable
0x1400011f2  mov     rdx, [rax+r12*8]
0x1400011f6  test    rdx, rdx
0x1400011f9  jz      loc_1400017E2
0x1400011ff  mov     rbx, rdx
0x140001202  lock inc dword ptr [rdx+60h]
0x140001206  mov     rcx, [rdx+50h]; SpinLock
0x14000120a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140001211  nop     dword ptr [rax+rax+00h]
0x140001216  lea     rcx, g_rlConnTableLock; SpinLock
0x14000121d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140001224  nop     dword ptr [rax+rax+00h]
0x140001229  cmp     dword ptr [rbx+64h], 0
0x14000122d  mov     rax, [rbx+8]
0x140001231  mov     [rbp+4Fh+var_B0], rax
0x140001235  mov     rax, [rbx+10h]
0x140001239  mov     [rbp+4Fh+var_A8], rax
0x14000123d  jz      short loc_14000124F
0x14000123f  lea     rcx, [rax+38h]; SpinLock
0x140001243  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000124a  nop     dword ptr [rax+rax+00h]
0x14000124f  mov     rdx, [rbp+4Fh+var_B0]
0x140001253  mov     [rbp+4Fh+var_98], rdx
0x140001257  mov     [rbp+4Fh+var_C8], r12d
0x14000125b  mov     rax, [r13+8]
0x14000125f  mov     ecx, [rax+18h]
0x140001262  lock add [rdx+0F0h], rcx
0x14000126a  mov     rax, [rbp+4Fh+var_78]
0x14000126e  movzx   eax, word ptr [rax]
0x140001271  cmp     ax, 2
0x140001275  jnz     loc_1400015A5
0x14000127b  mov     eax, 800h
0x140001280  cmp     [rbp+4Fh+var_CC], ax
0x140001284  jnz     loc_1400015AB
0x14000128a  mov     r12d, [rsp+110h+var_DC]
0x14000128f  test    r12d, r12d
0x140001292  jnz     loc_140001608
0x140001298  mov     rcx, [r13+8]; NetBuffer
0x14000129c  mov     rax, [rcx+8]
0x1400012a0  mov     edx, [rcx+10h]
0x1400012a3  add     edx, 0Eh
0x1400012a6  cmp     edx, [rax+28h]
0x1400012a9  jb      loc_1400015DE
0x1400012af  xor     r9d, r9d; FreeMdlHandler
0x1400012b2  xor     r8d, r8d; FreeMdl
0x1400012b5  mov     edx, 0Eh; DataOffsetDelta
0x1400012ba  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400012c1  nop     dword ptr [rax+rax+00h]
0x1400012c6  cmp     byte ptr [rbx+4], 0
0x1400012ca  jz      short loc_1400012D6
0x1400012cc  cmp     byte ptr [rbx+7Ah], 1
0x1400012d0  jz      loc_14000181D
0x1400012d6  test    r12d, r12d
0x1400012d9  jnz     loc_1400014F2
0x1400012df  mov     r9, rbx
0x1400012e2  lea     r8, FlpReturnNetBufferListChain
0x1400012e9  xor     edx, edx
0x1400012eb  mov     rcx, r13
0x1400012ee  call    cs:__imp_NetioInitializeNetBufferListContext
0x1400012f5  nop     dword ptr [rax+rax+00h]
0x1400012fa  or      dword ptr [r13+88h], 20000000h
0x140001305  xor     r11d, r11d
0x140001308  mov     [r13+70h], r11
0x14000130c  mov     rax, [rbp+4Fh+var_B0]
0x140001310  mov     [r13+8Ch], r11d
0x140001317  mov     eax, [rax+168h]
0x14000131d  mov     [r13+110h], rax
0x140001324  lock inc dword ptr [rbx+60h]
0x140001328  mov     rax, [rbx+8]
0x14000132c  lock inc qword ptr [rax+0F8h]
0x140001334  mov     rax, [rbp+4Fh+var_B8]
0x140001338  mov     [rbp+4Fh+var_B8], r13
0x14000133c  mov     [rsp+110h+var_DC], r12d
0x140001341  mov     [rax], r13
0x140001344  mov     rdi, [rbp+4Fh+var_C0]
0x140001348  mov     rdx, [rsp+110h+var_D8]
0x14000134d  mov     r13, r14
0x140001350  test    r14, r14
0x140001353  jnz     loc_140001129
0x140001359  cmp     [rbp+4Fh+var_C8], 0FFFFFFFFh
0x14000135d  jz      loc_1400014AD
0x140001363  cmp     [rbx+64h], r14d
0x140001367  jz      short loc_14000137D
0x140001369  mov     rcx, [rbp+4Fh+var_A8]
0x14000136d  add     rcx, 38h ; '8'; SpinLock
0x140001371  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140001378  nop     dword ptr [rax+rax+00h]
0x14000137d  movzx   edx, [rsp+110h+var_DF]; NewIrql
0x140001382  mov     rcx, [rbx+50h]; SpinLock
0x140001386  call    cs:__imp_KeReleaseSpinLock
0x14000138d  nop     dword ptr [rax+rax+00h]
0x140001392  test    rdi, rdi
0x140001395  jz      loc_140001495
0x14000139b  mov     rax, [rbp+4Fh+var_B8]
0x14000139f  mov     qword ptr [rax], 0
0x1400013a6  mov     rcx, [rbx+50h]; SpinLock
0x1400013aa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400013b1  nop     dword ptr [rax+rax+00h]
0x1400013b6  cmp     dword ptr [rbx+7Ch], 5
0x1400013ba  movzx   edx, al; NewIrql
0x1400013bd  mov     rcx, [rbx+50h]; SpinLock
0x1400013c1  jz      loc_140001594
0x1400013c7  call    cs:__imp_KeReleaseSpinLock
0x1400013ce  nop     dword ptr [rax+rax+00h]
0x1400013d3  mov     rdx, [rbp+4Fh+var_C0]
0x1400013d7  mov     rax, rdx
0x1400013da  test    rdx, rdx
0x1400013dd  jz      short loc_1400013EE
0x1400013df  lock inc cs:glFLPIndicatedNBLs
0x1400013e6  mov     rax, [rax]
0x1400013e9  test    rax, rax
0x1400013ec  jnz     short loc_1400013DF
0x1400013ee  mov     rax, [rbp+4Fh+var_90]
0x1400013f2  mov     rdi, [rbp+4Fh+var_88]
0x1400013f6  mov     rax, [rax]
0x1400013f9  cmp     qword ptr [rdi], 0
0x1400013fd  mov     rax, [rax+8]
0x140001401  mov     rax, [rax+40h]
0x140001405  jz      loc_14000194B
0x14000140b  mov     qword ptr [rbp+4Fh+Parameter], rax
0x14000140f  mov     rax, [rbx+80h]
0x140001416  mov     qword ptr [rbp+4Fh+Parameter+8], rax
0x14000141a  mov     qword ptr [rbp+4Fh+var_60], rdx
0x14000141e  mov     byte ptr [rbp+4Fh+var_60+8], sil
0x140001422  mov     r13d, gs:1A4h
0x14000142b  call    cs:__imp_KeGetCurrentIrql
0x140001432  nop     dword ptr [rax+rax+00h]
0x140001437  mov     rsi, [rdi]
0x14000143a  movzx   r14d, al
0x14000143e  cmp     al, 2
0x140001440  jb      loc_14000189B
0x140001446  mov     ecx, [rsi+3Ch]
0x140001449  xor     r12b, r12b
0x14000144c  test    cl, 1
0x14000144f  jz      loc_14000155E
0x140001455  xor     edi, edi
0x140001457  movzx   r9d, r12b; Wait
0x14000145b  mov     qword ptr [rsp+110h+AlignOffset], rdi; Context
0x140001460  mov     r8d, 4800h; Size
0x140001466  lea     rdx, [rbp+4Fh+Parameter]; Parameter
0x14000146a  lea     rcx, WanNdisReceivePacketsCalloutRoutine; Callout
0x140001471  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140001478  nop     dword ptr [rax+rax+00h]
0x14000147d  cmp     eax, 0C0000017h
0x140001482  jz      loc_1400018A3
0x140001488  test    rdi, rdi
0x14000148b  jnz     loc_14000151A
0x140001491  mov     esi, [rsp+110h+var_D0]
0x140001495  lock xadd [rbx+60h], r15d
0x14000149b  cmp     r15d, 1
0x14000149f  jz      loc_140001960
0x1400014a5  mov     rdx, [rsp+110h+var_D8]
0x1400014aa  xor     r11d, r11d
0x1400014ad  movzx   r10d, [rsp+110h+var_E0]
0x1400014b3  mov     r13, [rsp+110h+var_28]
0x1400014bb  mov     rbx, [rsp+110h+arg_0]
0x1400014c3  mov     r15, [rsp+110h+var_30]
0x1400014cb  cmp     [rbp+4Fh+NetBufferLists], 0
0x1400014d0  jnz     loc_14000196D
0x1400014d6  mov     rcx, [rbp+4Fh+var_38]
0x1400014da  xor     rcx, rsp; StackCookie
0x1400014dd  call    __security_check_cookie
0x1400014e2  add     rsp, 0F0h
0x1400014e9  pop     r14
0x1400014eb  pop     r12
0x1400014ed  pop     rdi
0x1400014ee  pop     rsi
0x1400014ef  pop     rbp
0x1400014f0  retn
0x1400014f2  xor     r11d, r11d
0x1400014f5  jmp     loc_14000130C
0x1400014fa  mov     eax, r12d
0x1400014fd  test    eax, eax
0x1400014ff  jnz     loc_140001881
0x140001505  mov     rcx, [rsp+110h+var_D8]
0x14000150a  mov     rdx, r13
0x14000150d  mov     [rsp+110h+var_D8], rdx
0x140001512  mov     [rcx], r13
0x140001515  jmp     loc_140001886
0x14000151a  cmp     r14b, 2
0x14000151e  jb      loc_140001929
0x140001524  mov     eax, r13d
0x140001527  shl     rax, 4
0x14000152b  and     dword ptr [rax+rsi+48h], 0FFFFFFFEh
0x140001530  jmp     loc_140001491
0x140001535  lea     rax, qword_140009498
0x14000153c  xor     r10b, r10b
0x14000153f  mov     [rbp+4Fh+var_88], rax
0x140001543  lea     rax, dword_1400092AC
0x14000154a  mov     [rbp+4Fh+var_78], rax
0x14000154e  lea     rax, qword_140009328
0x140001555  mov     [rbp+4Fh+var_90], rax
0x140001559  jmp     loc_140001074
0x14000155e  mov     edx, r13d
0x140001561  add     rdx, rdx
0x140001564  mov     eax, r13d
  ... truncated ...
```
