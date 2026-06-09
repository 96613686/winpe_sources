# IppDispatchSendPacketHelper

- ea: `0x14002a5d0`
- end: `0x14002b529`
- name: `IppDispatchSendPacketHelper`
- size: `3929`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140028dc0`

## callees

- `0x140016010`
- `0x140017740`
- `0x140017be0`
- `0x14001ad80`
- `0x140027b7c`
- `0x140028250`
- `0x140028790`
- `0x14002a0c0`
- `0x14002a5d0`
- `0x14002b530`
- `0x14002bfd0`
- `0x14002c210`
- `0x14002c410`
- `0x14002f9e0`
- `0x14004fd54`
- `0x14004fe5c`
- `0x140071db0`
- `0x140072e40`
- `0x1400826e4`
- `0x1400a7d40`
- `0x1400a81fc`
- `0x1400a96c0`
- `0x1400a9d00`
- `0x1400aacb0`
- `0x1400aadf0`
- `0x1400f37e0`
- `0x140114024`
- `0x14012ef5c`
- `0x14014e9bc`
- `0x1401c0fd0`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14002ab0f`
- `ntoskrnl!KfRaiseIrql` at `0x14002b03e`
- `ntoskrnl!KfRaiseIrql` at `0x14002ab0f`
- `ntoskrnl!KfRaiseIrql` at `0x14002b03e`
- `ntoskrnl!KeLowerIrql` at `0x14002abe2`
- `ntoskrnl!KeLowerIrql` at `0x14002b060`
- `ntoskrnl!KeLowerIrql` at `0x14002abe2`
- `ntoskrnl!KeLowerIrql` at `0x14002b060`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002aba1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002aba1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002ab37`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002ab37`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002abd2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002abd2`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002ad49`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002ad49`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002acf4`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002acf4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002a86f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002a944`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002a86f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002a944`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14002a8a7`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14002a978`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14002a8a7`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14002a978`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a85d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a85d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002ac47`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002ac47`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002adfb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b30a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002adfb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b30a`
- `NETIO!RtlCompute37Hash` at `0x14002acab`
- `NETIO!RtlCompute37Hash` at `0x14002acc3`
- `NETIO!RtlCompute37Hash` at `0x14002acab`
- `NETIO!RtlCompute37Hash` at `0x14002acc3`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14002a777`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14002a777`
- `NETIO!NetioPhFillUInt16AtOffset` at `0x1401c47e3`
- `NETIO!NetioPhFillUInt16AtOffset` at `0x1401c4819`
- `NETIO!NetioPhFillUInt16AtOffset` at `0x1401c47e3`
- `NETIO!NetioPhFillUInt16AtOffset` at `0x1401c4819`
- `NETIO!KfdAreAllIpv4InLayersEmpty` at `0x14002aa4a`
- `NETIO!KfdAreAllIpv4InLayersEmpty` at `0x14002aa4a`

## pseudocode

```c
void __fastcall IppDispatchSendPacketHelper(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  _QWORD **v5; // r13
  __int64 v6; // rsi
  unsigned __int16 *v7; // rbx
  __int64 *v8; // r15
  __int64 v9; // r14
  int v10; // eax
  unsigned __int8 v11; // r12
  _QWORD *v12; // rdx
  __int64 *v13; // r13
  int v14; // edi
  __int64 *v15; // r8
  __int64 v16; // rsi
  _QWORD *v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rbx
  unsigned int v21; // edx
  void *v22; // rax
  _QWORD *v23; // rcx
  int v24; // r12d
  int v25; // r15d
  __int64 v26; // rdi
  char v27; // r13
  char v28; // si
  int *v29; // rsi
  int v30; // ecx
  __int64 DpcTimeCount; // rcx
  int *v32; // rax
  int v33; // edx
  bool v34; // r13
  int v35; // eax
  int v36; // r15d
  _DWORD *v37; // rdi
  ULONG v38; // eax
  _DWORD *v39; // rcx
  _DWORD *v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 v43; // rax
  __int64 v44; // r10
  __int64 v45; // rdx
  _QWORD *j; // rdi
  bool v47; // zf
  KIRQL v48; // r15
  unsigned __int64 v49; // rbx
  _QWORD *v50; // rsi
  void **v51; // rax
  __int64 v52; // rax
  unsigned int v53; // eax
  unsigned int v54; // edi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rax
  struct _LIST_ENTRY **p_Blink; // rdi
  signed __int64 v57; // rdx
  int v58; // edi
  _QWORD **Neighbor; // rax
  struct _RTL_DYNAMIC_HASH_TABLE **v60; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v61; // rax
  __int64 v62; // rdi
  __int64 StrongClonePacket; // rax
  _QWORD *v64; // rcx
  PRTL_DYNAMIC_HASH_TABLE v65; // rax
  int v66; // eax
  __int64 v67; // r8
  __int64 v68; // rcx
  __int64 v69; // rdx
  _QWORD *i; // r12
  _QWORD *v71; // rdi
  __int64 ClonePacket; // rax
  PRTL_DYNAMIC_HASH_TABLE *p_HashTable; // rsi
  struct _RTL_DYNAMIC_HASH_TABLE *v74; // rax
  unsigned __int16 *v75; // rdi
  KIRQL v76; // di
  int v77; // r9d
  int PacketCount; // eax
  __int64 v79; // r8
  __int64 v80; // rcx
  __int64 v81; // rdx
  int v82; // r9d
  char v83; // al
  _QWORD **v84; // rax
  __int64 v85; // r8
  volatile signed __int32 *v86; // rax
  _DWORD *v87; // rcx
  int v88; // ecx
  int v89; // eax
  __int64 v90; // r9
  __int64 v91; // r10
  int v92; // eax
  __int64 v93; // r9
  __int64 v94; // r10
  unsigned int v95; // r9d
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rdx
  unsigned int v99; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v100; // [rsp+68h] [rbp-98h] BYREF
  __int64 v101; // [rsp+78h] [rbp-88h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+80h] [rbp-80h] BYREF
  void *Buf2; // [rsp+88h] [rbp-78h]
  __int64 v104; // [rsp+90h] [rbp-70h]
  _QWORD **v105; // [rsp+98h] [rbp-68h]
  __int128 v106; // [rsp+A0h] [rbp-60h] BYREF
  PKSPIN_LOCK SpinLock; // [rsp+B0h] [rbp-50h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Parameter; // [rsp+B8h] [rbp-48h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v110; // [rsp+E8h] [rbp-18h] BYREF
  struct _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+100h] [rbp+0h] BYREF

  v4 = *(_QWORD *)(a2 + 224);
  v5 = 0;
  v6 = *(_QWORD *)(a2 + 216);
  v100 = 0;
  *(_QWORD *)&v106 = a2;
  v7 = (unsigned __int16 *)a2;
  *(_QWORD *)&WatchdogInformation.DpcTimeLimit = a1;
  v110 = 0;
  v8 = *(__int64 **)(v4 + 8);
  v9 = a1;
  v10 = *(_DWORD *)v6;
  v11 = 1;
  LODWORD(v101) = 0;
  v99 = 0;
  if ( v10 == 1701736521 )
  {
    v5 = (_QWORD **)v6;
    if ( *(_DWORD *)(v6 + 24) == 3 && *(int *)(a1 + 19696) < 1 )
    {
      PacketCount = IppGetPacketCount(*(_QWORD *)(a2 + 8), a2, a3, a4);
      LODWORD(v80) = HIDWORD(KeGetPcr()[1].LockArray);
      v81 = *(_QWORD *)(v9 + 20264) + 192 * v80;
      *(_DWORD *)(v81 + 152) += PacketCount;
      if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 || byte_140229CC0 )
      {
        v92 = IppGetPacketCount(*((_QWORD *)v7 + 1), v81, v79, *((_QWORD *)v7 + 28));
        IppLogPacketDiscard(
          *(_WORD *)(v9 + 28),
          v7[52],
          *((int **)v7 + 33),
          *((int **)v7 + 31),
          0x81u,
          v92,
          0,
          v94,
          *(_DWORD **)(v93 + 8),
          3,
          -536854268);
      }
      v82 = 129;
      goto LABEL_139;
    }
LABEL_7:
    v13 = v5[1];
    if ( v13 != v8 )
    {
      if ( !(unsigned __int8)IppForwardPackets(v9, (int)v8, (int)v13, (int)v7, v6, 0, 0, (__int64)&v101, &v99) )
      {
        if ( (_DWORD)v101 != 257 )
        {
          IppDiscardSendPackets(v9, (_DWORD)v7, v101, v11, 1, 0, 3, v99);
          return;
        }
LABEL_113:
        IppCompleteAndFreePacketList(v7, 0);
        return;
      }
LABEL_9:
      if ( (*((_BYTE *)v8 + 394) & 8) != 0 && *((_DWORD *)v7 + 64) == 3 )
      {
        *(_QWORD *)&WatchdogInformation.DpcTimeLimit = 0;
        *(_QWORD *)&WatchdogInformation.DpcWatchdogLimit = &WatchdogInformation;
        v76 = KfRaiseIrql(2u);
        IppForwardMulticastPackets(v8, v7, &WatchdogInformation);
        KeLowerIrql(v76);
        if ( *(_QWORD *)&WatchdogInformation.DpcTimeLimit )
          IppFragmentPackets(v9, *(_QWORD **)&WatchdogInformation.DpcTimeLimit);
      }
      if ( *((_DWORD *)v13 + 10) > 1u && (unsigned int)(*((_DWORD *)v7 + 64) - 3) <= 1 )
      {
        IppCreateSubInterfaceSplitList(v7, &v110);
        v12 = (_QWORD *)v110;
        goto LABEL_4;
      }
LABEL_3:
      v12 = v7;
LABEL_4:
      IppFragmentPackets(v9, v12);
      return;
    }
    if ( *(_BYTE *)(*(unsigned __int16 *)(v9 + 44) + *((_QWORD *)v7 + 35)) )
      goto LABEL_9;
    v66 = IppGetPacketCount(*((_QWORD *)v7 + 1), a2, a3, a4);
    LODWORD(v68) = HIDWORD(KeGetPcr()[1].LockArray);
    v69 = *(_QWORD *)(v9 + 20264) + 192 * v68;
    *(_DWORD *)(v69 + 152) += v66;
    if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 || byte_140229CC0 )
    {
      v89 = IppGetPacketCount(*((_QWORD *)v7 + 1), v69, v67, *((_QWORD *)v7 + 28));
      IppLogPacketDiscard(
        *(_WORD *)(v9 + 28),
        v7[52],
        *((int **)v7 + 33),
        *((int **)v7 + 31),
        0x80u,
        v89,
        0,
        v91,
        *(_DWORD **)(v90 + 8),
        3,
        -536854268);
    }
    if ( !v11 )
      goto LABEL_113;
    v82 = 128;
LABEL_139:
    IppSendErrorListForDiscardReason(0, v9, (_DWORD)v7, v82, 0);
    goto LABEL_113;
  }
  if ( v10 != 1634496585 )
    goto LABEL_3;
  v14 = *(_DWORD *)(v6 + 24);
  if ( v14 == 4 )
  {
LABEL_85:
    v51 = *(void ***)(v6 + 16);
    memset(&LockHandle, 0, sizeof(LockHandle));
    Buf2 = *v51;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v8 + 37, &LockHandle);
    while ( *((_DWORD *)v8 + 76) )
      ;
    memset(&Parameter, 0, sizeof(Parameter));
    SpinLock = (PKSPIN_LOCK)v8[43];
    HashTable = (PRTL_DYNAMIC_HASH_TABLE)&CONTAINING_RECORD(SpinLock, struct _RTL_DYNAMIC_HASH_TABLE, Flags)->DivisorMask;
    v52 = *v8;
    LODWORD(v105) = v14;
    LODWORD(v104) = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v52 + 40) + 16LL) + 6LL);
    v53 = RtlCompute37Hash((unsigned int)g_37HashSeed, Buf2, (unsigned int)v104);
    *(_OWORD *)&Parameter.ChainHead = 0;
    v54 = RtlCompute37Hash(v53, v8 + 1, 4);
    RtlAcquireReadLockAtDpcLevel(SpinLock);
    NextEntryHashTable = RtlLookupEntryHashTable(
                           (PRTL_DYNAMIC_HASH_TABLE)(SpinLock + 2),
                           v54 | 0x80000000LL,
                           &Parameter);
    if ( NextEntryHashTable )
    {
      do
      {
        p_Blink = &NextEntryHashTable[-2].Linkage.Blink;
        if ( (__int64 *)NextEntryHashTable[-2].Signature == v8
          && !memcmp(p_Blink + 21, Buf2, (unsigned __int16)v104)
          && (!v5 || *((_DWORD *)p_Blink + 7) > *((_DWORD *)v5 + 7)) )
        {
          v5 = (_QWORD **)p_Blink;
        }
        NextEntryHashTable = RtlGetNextEntryHashTable(HashTable, &Parameter);
      }
      while ( NextEntryHashTable );
      v7 = (unsigned __int16 *)v106;
      v11 = 1;
      v9 = *(_QWORD *)&WatchdogInformation.DpcTimeLimit;
      if ( v5 )
      {
        v57 = _InterlockedExchangeAdd64((volatile signed __int64 *)v5 + 12, 2u) + 2;
        if ( v57 - 2 < 1 )
          __fastfail(0xEu);
        if ( (v57 & 0xFFFFFFFFFFFFFFFEuLL) == 2 && (v57 & 1) != 0 )
        {
          v86 = (volatile signed __int32 *)v5[1];
          v105 = v5;
          _InterlockedDecrement(v86 + 79);
          _InterlockedDecrement((volatile signed __int32 *)(v5[1][43] + 88LL));
          _InterlockedDecrement((volatile signed __int32 *)SpinLock + 2);
          KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_102:
          if ( *(__int64 **)(v6 + 8) == v8 )
          {
            v60 = (struct _RTL_DYNAMIC_HASH_TABLE **)*((_QWORD *)v7 + 1);
            *(_QWORD *)&v100 = 0;
            *((_QWORD *)&v100 + 1) = &v100;
            Buf2 = v60;
            if ( ((_DWORD)v60[18] & 0xC) != 0 && *((_DWORD *)v7 + 64) == 1 )
              *((_BYTE *)v7 + 186) |= 8u;
            v61 = v60[1];
            *(_QWORD *)&WatchdogInformation.DpcTimeLimit = v61;
            while ( 1 )
            {
              HashTable = v61;
              if ( !v61 )
                break;
              v62 = *(_QWORD *)&v61->Flags;
              *(_QWORD *)&v61->Flags = 0;
              v60[1] = v61;
              StrongClonePacket = IppCreateStrongClonePacket((__int64)v7);
              v64 = Buf2;
              a2 = StrongClonePacket;
              v65 = HashTable;
              a3 = *(_QWORD *)&WatchdogInformation.DpcTimeLimit;
              *(_QWORD *)&HashTable->Flags = v62;
              v64[1] = a3;
              if ( !a2 )
              {
                a2 = v100;
                if ( (_QWORD)v100 )
                {
                  IppLbLogAndDropPackets(v9, v100, 264, 3758113087LL);
                  *(_QWORD *)&v100 = 0;
                  *((_QWORD *)&v100 + 1) = &v100;
                }
                goto LABEL_142;
              }
              *(_OWORD *)(a2 + 16) = 0;
              **((_QWORD **)&v100 + 1) = a2;
              v60 = (struct _RTL_DYNAMIC_HASH_TABLE **)Buf2;
              *((_QWORD *)&v100 + 1) = a2;
              v61 = *(struct _RTL_DYNAMIC_HASH_TABLE **)&v65->Flags;
            }
            if ( (_QWORD)v100 )
            {
              v11 = 0;
              LOBYTE(a3) = 1;
              IppLoopbackEnqueue(&v100, v9, a3);
            }
          }
LABEL_142:
          v83 = *((_BYTE *)v7 + 184);
          if ( (v83 & 0x20) != 0 )
          {
            IppDereferencePath(*((_QWORD *)v7 + 26));
            *((_BYTE *)v7 + 184) &= ~0x20u;
            v83 = *((_BYTE *)v7 + 184);
          }
          *((_QWORD *)v7 + 26) = 0;
          if ( v83 < 0 )
          {
            v87 = (_DWORD *)*((_QWORD *)v7 + 27);
            if ( *v87 == 1634496585 )
            {
              IppDereferenceLocalAddress(v87);
            }
            else if ( *v87 == 1701736521 )
            {
              IppDereferenceNeighbor(v87);
            }
          }
          v84 = v105;
          *((_BYTE *)v7 + 184) |= 0x80u;
          *((_QWORD *)v7 + 27) = v84;
          goto LABEL_7;
        }
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)SpinLock + 2);
    if ( !v5 )
    {
      v58 = (int)v105;
      if ( (_DWORD)v105 != 3 || (*(_DWORD *)(v8[6] + 28) & 2) != 0 )
      {
        Neighbor = (_QWORD **)IppCreateNeighbor(v8);
        v105 = Neighbor;
        v5 = Neighbor;
        if ( Neighbor )
        {
          v5 = IppInitializeNeighbor(Neighbor, 0, Buf2, v58);
          v105 = v5;
        }
LABEL_101:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( !v5 )
          goto LABEL_15;
        goto LABEL_102;
      }
      v5 = 0;
    }
    v105 = v5;
    goto LABEL_101;
  }
  if ( v14 == 3 )
  {
    if ( *(int *)(a1 + 19696) < 1 )
    {
      IppDiscardSendPackets(a1, a2, 129, 1, 1, 0, 3, -536854268);
      return;
    }
    goto LABEL_85;
  }
LABEL_15:
  v15 = *(__int64 **)(v6 + 8);
  if ( v15 != v8 && !(unsigned __int8)IppForwardPackets(v9, (int)v8, (int)v15, (int)v7, v6, 0, 0, (__int64)&v101, &v99) )
  {
    if ( (_DWORD)v101 != 257 )
    {
      LOBYTE(v77) = 1;
      IppDiscardSendPackets(v9, (_DWORD)v7, v101, v77, 1, 0, 3, v99);
      return;
    }
    goto LABEL_113;
  }
  v16 = *((_QWORD *)v7 + 1);
  *(_QWORD *)&v100 = 0;
  *((_QWORD *)&v100 + 1) = &v100;
  if ( (*(_DWORD *)(v16 + 144) & 0xC) != 0 && *((_DWORD *)v7 + 64) == 1 )
    *((_BYTE *)v7 + 186) |= 8u;
  v17 = *(_QWORD **)(v16 + 8);
  if ( *v17 )
  {
    for ( i = *(_QWORD **)(v16 + 8); i; i = (_QWORD *)*i )
    {
      v71 = (_QWORD *)*i;
      *i = 0;
      *(_QWORD *)(v16 + 8) = i;
      ClonePacket = IppCreateClonePacket(v7);
      *i = v71;
      *(_QWORD *)(v16 + 8) = v17;
      if ( !ClonePacket )
      {
        if ( (_QWORD)v100 )
        {
          IppLbLogAndDropPackets(v9, v100, 264, 3758113087LL);
          *(_QWORD *)&v100 = 0;
          *((_QWORD *)&v100 + 1) = &v100;
        }
        break;
      }
      *(_OWORD *)(ClonePacket + 16) = 0;
      **((_QWORD **)&v100 + 1) = ClonePacket;
      *((_QWORD *)&v100 + 1) = ClonePacket;
    }
    HashTable = 0;
    p_HashTable = &HashTable;
    do
    {
      v74 = (struct _RTL_DYNAMIC_HASH_TABLE *)*((_QWORD *)v7 + 1);
      v75 = *(unsigned __int16 **)v7;
      if ( v74 )
      {
        *p_HashTable = v74;
        p_HashTable = (PRTL_DYNAMIC_HASH_TABLE *)v74;
      }
      IppFreePacket(v7);
      v7 = v75;
    }
    while ( v75 );
    if ( HashTable )
      NetioDereferenceNetBufferListChain(HashTable, 0);
  }
  else
  {
    v18 = IppPendPacket(v7);
    if ( v18 )
    {
      **((_QWORD **)&v100 + 1) = v18;
      *((_QWORD *)&v100 + 1) = v18;
    }
    else
    {
      IppLbLogAndDropPackets(v9, v7, 264, 3758113086LL);
    }
  }
  v19 = v100;
  if ( (_QWORD)v100 )
  {
    v99 = 0;
    while ( 1 )
    {
      if ( !v19 )
        return;
      *(_QWORD *)&v106 = 0;
      *((_QWORD *)&v106 + 1) = &v106;
      v20 = v19;
      v21 = *(_DWORD *)(*(_QWORD *)(v19 + 8) + 208LL);
      LODWORD(v105) = v21;
      while ( !*(_DWORD *)(v9 + 19736) || *(_DWORD *)(*(_QWORD *)(v20 + 8) + 208LL) == v21 )
      {
        v22 = *(void **)(*(_QWORD *)(v20 + 216) + 8LL);
        *(_BYTE *)(v20 + 185) &= ~0x40u;
        v23 = (_QWORD *)v100;
        Buf2 = v22;
        if ( (_QWORD)v100 )
        {
          *(_QWORD *)&v100 = *(_QWORD *)v100;
          *v23 = 0;
          if ( *((_QWORD **)&v100 + 1) == v23 )
            *((_QWORD *)&v100 + 1) = &v100;
        }
        v24 = 0;
        v25 = 0xFFFF;
        v26 = *(_QWORD *)(v20 + 8);
        v27 = *(_BYTE *)(v20 + 88);
        if ( !*(_BYTE *)(v9 + 19732) )
          v25 = 1500;
        LODWORD(v104) = *(_DWORD *)(v20 + 196);
        LOWORD(v101) = *(_WORD *)(v20 + 60);
        if ( (int *)v9 != &Ipv4Global )
          v24 = 41;
        v28 = 0;
        HashTable = *(PRTL_DYNAMIC_HASH_TABLE *)(v20 + 224);
        if ( KeGetCurrentIrql() == 2 )
        {
          v29 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          v30 = *v29;
          if ( *v29 == 1 )
          {
            memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
            KeQueryDpcWatchdogInformation(&WatchdogInformation);
            DpcTimeCount = WatchdogInformation.DpcTimeCount;
            v32 = v29 + 20;
            goto LABEL_39;
          }
          if ( !v30 )
          {
            *v29 = 3;
            v32 = v29 + 2;
            *(_OWORD *)(v29 + 14) = 0;
            *(_OWORD *)(v29 + 18) = 0;
            *(_OWORD *)(v29 + 22) = 0;
            *(_OWORD *)(v29 + 2) = 0;
            *(_OWORD *)(v29 + 6) = 0;
            *(_OWORD *)(v29 + 10) = 0;
            v29[26] = 1;
            DpcTimeCount = MEMORY[0xFFFFF78000000008];
            goto LABEL_39;
          }
          v88 = v30 - 2;
          if ( !v88 )
          {
            DpcTimeCount = MEMORY[0xFFFFF78000000008];
            v32 = v29 + 16;
            goto LABEL_39;
          }
          if ( v88 == 1 )
          {
            ++v29[26];
            DpcTimeCount = MEMORY[0xFFFFF78000000008];
            v32 = v29 + 2;
LABEL_39:
            *((_QWORD *)v32 + 4) = DpcTimeCount;
          }
          v28 = 1;
        }
        v33 = v20 + 232;
        v34 = (v27 & 4) != 0;
        if ( (int *)v9 == &Ipv4Global )
          v35 = ShimIpPacketOutV4((_DWORD)HashTable, v33, (_DWORD)Buf2, 0, (unsigned __int16)v101, v104, v25, 1, v26);
        else
          v35 = ShimIpPacketOutV6((_DWORD)HashTable, v33, (_DWORD)Buf2, 0, (unsigned __int16)v101, v104, v25, 1, v26);
        v36 = IpSecNLPacketsOutProcessing(v24, v34, v25, v26, v35);
        if ( v26 )
          *(_DWORD *)(v26 + 136) &= ~0x800000u;
        if ( v28 )
        {
          v37 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          switch ( *v37 )
          {
            case 1:
              memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
              KeQueryDpcWatchdogInformation(&WatchdogInformation);
              v38 = WatchdogInformation.DpcTimeCount;
              v39 = v37 + 30;
              v40 = v37 + 28;
              break;
            case 2:
              v39 = v37 + 26;
              v40 = v37 + 24;
              v38 = MEMORY[0xFFFFF78000000008];
              break;
            case 3:
              --v37[26];
              v38 = MEMORY[0xFFFFF78000000008];
              if ( !v37[26] )
                *v37 = 0;
              v39 = v37 + 12;
              v40 = v37 + 10;
              break;
            default:
              goto LABEL_54;
          }
          *v39 += v38 - *v40;
        }
LABEL_54:
        if ( v36 >= 1 )
        {
          if ( (unsigned int)(v36 - 1) <= 1 )
          {
            v85 = 9;
            *(_DWORD *)(*(_QWORD *)(v20 + 8) + 140LL) = -1073741285;
          }
          else
          {
            v85 = 257;
          }
          IppLbLogAndDropPackets(v9, v20, v85, 3758113085LL);
          goto LABEL_68;
        }
        IppLbLogTransmitPacket(v20);
        v42 = *(_QWORD *)(v20 + 8);
        v43 = *(_QWORD *)(v42 + 144);
        v44 = *(_QWORD *)(v42 + 320);
        v104 = v43;
        if ( (v43 & 4) != 0 )
        {
          LODWORD(v104) = v43 & 0xFFFFFEF0 | 0x108;
          *(_QWORD *)(v42 + 144) = v104;
        }
        else if ( (v43 & 8) != 0 || (_DWORD)v44 )
        {
          LODWORD(v104) = v43 & 0xFFFFFEE4 | 0x110;
          *(_QWORD *)(v42 + 144) = v104;
        }
        v45 = (unsigned __int16)v44;
        if ( (_DWORD)v44 )
        {
          v95 = *(_DWORD *)(*(_QWORD *)(v42 + 8) + 24LL) - (((unsigned int)v44 >> 20) & 0x3FF);
          *(_WORD *)(v42 + 282) = v44;
          v95 -= 8;
          *(_QWORD *)(v42 + 320) = 0;
          v96 = v95 + 8;
          LOWORD(v96) = __ROR2__(v95 + 8, 8);
          *(_WORD *)(v42 + 280) = ((unsigned __int16)v44 + v95 - 1) / (unsigned __int16)v44;
          NetioPhFillUInt16AtOffset(v96, (((unsigned int)v44 >> 20) & 0x3FF) + 4);
          v97 = *(unsigned __int16 *)(*(_QWORD *)(v42 + 8) + 24LL);
          if ( (int *)v9 == &Ipv4Global )
          {
            v98 = 2;
          }
          else
          {
            LOWORD(v97) = v97 - *(_WORD *)(v9 + 40);
            v98 = 4;
          }
          LOWORD(v97) = __ROR2__(v97, 8);
          NetioPhFillUInt16AtOffset(v97, v98);
        }
        if ( (Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState & 0x10) != 0 )
        {
          if ( (Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState & 1) != 0 )
          {
LABEL_61:
            if ( (int *)v9 == &Ipv4Global
              && !*(_DWORD *)(v42 + 320)
              && !*(_DWORD *)(v42 + 160)
              && !(unsigned __int8)KfdAreAllIpv4InLayersEmpty() )
            {
              for ( j = *(_QWORD **)(v42 + 8); j; j = (_QWORD *)*j )
                Ipv4pFillPacketChecksum(j);
            }
          }
        }
        else if ( (unsigned int)Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_IsEnabledDeviceUsageNoInline(
                                  v41,
                                  v45) )
        {
          goto LABEL_61;
        }
        ++v99;
        *(_QWORD *)(*(_QWORD *)(v20 + 8) + 272LL) = *((unsigned int *)Buf2 + 2);
        **((_QWORD **)&v106 + 1) = v20;
        *((_QWORD *)&v106 + 1) = v20;
LABEL_68:
        v19 = v100;
        v21 = (unsigned int)v105;
        v20 = v100;
        if ( !(_QWORD)v100 )
          break;
      }
      if ( (_QWORD)v106 )
      {
        v47 = *(_DWORD *)(v9 + 19736) == 0;
        *(_OWORD *)&WatchdogInformation.DpcTimeLimit = v106;
        if ( v47 )
        {
          memset(&Parameter, 0, sizeof(Parameter));
          while ( *(_QWORD *)&WatchdogInformation.DpcTimeLimit )
          {
            v48 = KfRaiseIrql(2u);
            v49 = *(_QWORD *)(*(_QWORD *)(v9 + 20192) + 8LL * HIDWORD(KeGetPcr()[1].LockArray));
            KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v49);
            v50 = (_QWORD *)(v49 + 8);
            if ( *(_QWORD *)&WatchdogInformation.DpcTimeLimit )
            {
              **(_QWORD **)(v49 + 16) = *(_QWORD *)&WatchdogInformation.DpcTimeLimit;
              *(_QWORD *)(v49 + 16) = *(_QWORD *)&WatchdogInformation.DpcWatchdogLimit;
            }
            *(_QWORD *)&WatchdogInformation.DpcTimeLimit = 0;
            *(_QWORD *)&WatchdogInformation.DpcWatchdogLimit = &WatchdogInformation;
            if ( !*(_BYTE *)(v49 + 28) )
            {
              *(_BYTE *)(v49 + 28) = 1;
              *(_OWORD *)&Parameter.ChainHead = v49;
              LOBYTE(Parameter.Signature) = v48;
              KeExpandKernelStackAndCalloutEx(IppLbTransmitStackCallout, &Parameter, 0x4800u, 0, *(PVOID *)(v49 + 32));
              if ( *v50 )
              {
                **(_QWORD **)&WatchdogInformation.DpcWatchdogLimit = *v50;
                *(_QWORD *)&WatchdogInformation.DpcWatchdogLimit = *(_QWORD *)(v49 + 16);
              }
              *v50 = 0;
              *(_QWORD *)(v49 + 16) = v49 + 8;
              *(_BYTE *)(v49 + 28) &= ~1u;
            }
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v49);
            KeLowerIrql(v48);
          }
        }
        else
        {
          IppLbEnqueueAdaptiveOrWorkerMode(v9, &WatchdogInformation, v99, v21);
        }
        v19 = v100;
      }
    }
  }
}

```

## disassembly

```asm
0x14002a5d0  mov     [rsp-8+arg_10], rbx
0x14002a5d5  push    rbp
0x14002a5d6  push    rsi
0x14002a5d7  push    rdi
0x14002a5d8  push    r12
0x14002a5da  push    r13
0x14002a5dc  push    r14
0x14002a5de  push    r15
0x14002a5e0  lea     rbp, [rsp-30h]
0x14002a5e5  sub     rsp, 130h
0x14002a5ec  mov     rax, cs:__security_cookie
0x14002a5f3  xor     rax, rsp
0x14002a5f6  mov     [rbp+60h+var_40], rax
0x14002a5fa  mov     rax, [rdx+0E0h]
0x14002a601  xor     r13d, r13d
0x14002a604  mov     rsi, [rdx+0D8h]
0x14002a60b  xorps   xmm0, xmm0
0x14002a60e  movups  [rsp+160h+var_F8], xmm0
0x14002a613  mov     qword ptr [rbp+60h+var_C0], rdx
0x14002a617  mov     rbx, rdx
0x14002a61a  xorps   xmm1, xmm1
0x14002a61d  mov     qword ptr [rbp+60h+WatchdogInformation.DpcTimeLimit], rcx
0x14002a621  movups  [rbp+60h+var_78], xmm1
0x14002a625  mov     r15, [rax+8]
0x14002a629  mov     r14, rcx
0x14002a62c  mov     eax, [rsi]
0x14002a62e  mov     r12b, 1
0x14002a631  mov     dword ptr [rsp+160h+var_E8], r13d
0x14002a636  mov     [rsp+160h+var_100], r13d
0x14002a63b  cmp     eax, 656E7049h
0x14002a640  jz      short loc_14002A680
0x14002a642  cmp     eax, 616C7049h
0x14002a647  jz      loc_14002A6EC
0x14002a64d  mov     rdx, rbx
0x14002a650  mov     rcx, r14
0x14002a653  call    IppFragmentPackets
0x14002a658  mov     rcx, [rbp+60h+var_40]
0x14002a65c  xor     rcx, rsp; StackCookie
0x14002a65f  call    __security_check_cookie
0x14002a664  mov     rbx, [rsp+160h+arg_10]
0x14002a66c  add     rsp, 130h
0x14002a673  pop     r15
0x14002a675  pop     r14
0x14002a677  pop     r13
0x14002a679  pop     r12
0x14002a67b  pop     rdi
0x14002a67c  pop     rsi
0x14002a67d  pop     rbp
0x14002a67e  retn
0x14002a680  cmp     dword ptr [rsi+18h], 3
0x14002a684  mov     r13, rsi
0x14002a687  jz      loc_14002B0FE
0x14002a68d  mov     r13, [r13+8]
0x14002a691  cmp     r13, r15
0x14002a694  jnz     loc_14002B207
0x14002a69a  movzx   ecx, word ptr [r14+2Ch]
0x14002a69f  mov     rax, [rbx+118h]
0x14002a6a6  cmp     byte ptr [rcx+rax], 0
0x14002a6aa  jz      loc_14002AEB6
0x14002a6b0  test    byte ptr [r15+18Ah], 8
0x14002a6b8  jnz     loc_14002B01F
0x14002a6be  cmp     dword ptr [r13+28h], 1
0x14002a6c3  jbe     short loc_14002A64D
0x14002a6c5  mov     eax, [rbx+100h]
0x14002a6cb  sub     eax, 3
0x14002a6ce  cmp     eax, 1
0x14002a6d1  ja      loc_14002A64D
0x14002a6d7  lea     rdx, [rbp+60h+var_78]
0x14002a6db  mov     rcx, rbx
0x14002a6de  call    IppCreateSubInterfaceSplitList
0x14002a6e3  mov     rdx, qword ptr [rbp+60h+var_78]
0x14002a6e7  jmp     loc_14002A650
0x14002a6ec  mov     edi, [rsi+18h]
0x14002a6ef  cmp     edi, 4
0x14002a6f2  jz      loc_14002AC27
0x14002a6f8  cmp     edi, 3
0x14002a6fb  jz      loc_14002AC1A
0x14002a701  mov     r8, [rsi+8]; int
0x14002a705  cmp     r8, r15
0x14002a708  jnz     loc_14002B086
0x14002a70e  mov     rsi, [rbx+8]
0x14002a712  lea     rax, [rsp+160h+var_F8]
0x14002a717  mov     qword ptr [rsp+160h+var_F8], r13
0x14002a71c  mov     qword ptr [rsp+160h+var_F8+8], rax
0x14002a721  mov     eax, [rsi+90h]
0x14002a727  test    al, 0Ch
0x14002a729  jz      short loc_14002A73B
0x14002a72b  cmp     dword ptr [rbx+100h], 1
0x14002a732  jnz     short loc_14002A73B
0x14002a734  or      byte ptr [rbx+0BAh], 8
0x14002a73b  mov     r15, [rsi+8]
0x14002a73f  cmp     qword ptr [r15], 0
0x14002a743  jnz     loc_14002AF38
0x14002a749  mov     rcx, rbx
0x14002a74c  call    IppPendPacket
0x14002a751  mov     rcx, rax
0x14002a754  test    rax, rax
0x14002a757  jz      loc_14002B2BB
0x14002a75d  mov     rax, qword ptr [rsp+160h+var_F8+8]
0x14002a762  mov     [rax], rcx
0x14002a765  mov     qword ptr [rsp+160h+var_F8+8], rcx
0x14002a76a  jmp     short loc_14002A783
0x14002a76c  mov     rcx, [rbp+60h+HashTable]
0x14002a770  test    rcx, rcx
0x14002a773  jz      short loc_14002A783
0x14002a775  xor     edx, edx
0x14002a777  call    cs:__imp_NetioDereferenceNetBufferListChain
0x14002a77e  nop     dword ptr [rax+rax+00h]
0x14002a783  mov     rcx, qword ptr [rsp+160h+var_F8]
0x14002a788  test    rcx, rcx
0x14002a78b  jz      loc_14002A658
0x14002a791  mov     [rsp+160h+var_100], r13d
0x14002a796  mov     r10d, 29h ; ')'
0x14002a79c  lea     r8, Ipv4Global
0x14002a7a3  mov     r9d, 5DCh
0x14002a7a9  test    rcx, rcx
0x14002a7ac  jz      loc_14002A658
0x14002a7b2  lea     rax, [rbp+60h+var_C0]
0x14002a7b6  mov     qword ptr [rbp+60h+var_C0], r13
0x14002a7ba  mov     qword ptr [rbp+60h+var_C0+8], rax
0x14002a7be  mov     rbx, rcx
0x14002a7c1  mov     rax, [rcx+8]
0x14002a7c5  mov     edx, [rax+0D0h]
0x14002a7cb  mov     dword ptr [rbp+60h+var_C8], edx
0x14002a7ce  cmp     dword ptr [r14+4D18h], 0
0x14002a7d6  jnz     loc_14002AAC3
0x14002a7dc  mov     rax, [rbx+0D8h]
0x14002a7e3  mov     rax, [rax+8]
0x14002a7e7  and     byte ptr [rbx+0B9h], 0BFh
0x14002a7ee  mov     rcx, qword ptr [rsp+160h+var_F8]
0x14002a7f3  mov     [rbp+60h+Buf2], rax
0x14002a7f7  test    rcx, rcx
0x14002a7fa  jz      short loc_14002A818
0x14002a7fc  mov     rax, [rcx]
0x14002a7ff  mov     qword ptr [rsp+160h+var_F8], rax
0x14002a804  mov     [rcx], r13
0x14002a807  cmp     qword ptr [rsp+160h+var_F8+8], rcx
0x14002a80c  jnz     short loc_14002A818
0x14002a80e  lea     rax, [rsp+160h+var_F8]
0x14002a813  mov     qword ptr [rsp+160h+var_F8+8], rax
0x14002a818  mov     eax, [rbx+0C4h]
0x14002a81e  mov     r12d, r13d
0x14002a821  cmp     byte ptr [r14+4D14h], 0
0x14002a829  mov     r15d, 0FFFFh
0x14002a82f  mov     rdi, [rbx+8]
0x14002a833  movzx   r13d, byte ptr [rbx+58h]
0x14002a838  cmovz   r15d, r9d
0x14002a83c  mov     dword ptr [rbp+60h+var_D0], eax
0x14002a83f  cmp     r14, r8
0x14002a842  movzx   eax, word ptr [rbx+3Ch]
0x14002a846  mov     word ptr [rsp+160h+var_E8], ax
0x14002a84b  cmovnz  r12d, r10d
0x14002a84f  mov     rax, [rbx+0E0h]
0x14002a856  xor     sil, sil
0x14002a859  mov     [rbp+60h+HashTable], rax
0x14002a85d  call    cs:__imp_KeGetCurrentIrql
0x14002a864  nop     dword ptr [rax+rax+00h]
0x14002a869  cmp     al, 2
0x14002a86b  jnz     short loc_14002A8C1
0x14002a86d  xor     ecx, ecx; ProcNumber
0x14002a86f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002a876  nop     dword ptr [rax+rax+00h]
0x14002a87b  lea     ecx, [rax+rax*8]
0x14002a87e  mov     rax, cs:gWfpPerProContext
0x14002a885  shl     ecx, 3
0x14002a888  mov     rsi, [rcx+rax]
0x14002a88c  mov     ecx, [rsi]
0x14002a88e  cmp     ecx, 1
0x14002a891  jnz     loc_14002AFD7
0x14002a897  xorps   xmm0, xmm0
0x14002a89a  lea     rcx, [rbp+60h+WatchdogInformation]; WatchdogInformation
0x14002a89e  xor     eax, eax
0x14002a8a0  movups  xmmword ptr [rbp+60h+WatchdogInformation.DpcTimeLimit], xmm0
0x14002a8a4  mov     [rbp+60h+WatchdogInformation.Reserved], eax
0x14002a8a7  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14002a8ae  nop     dword ptr [rax+rax+00h]
0x14002a8b3  mov     ecx, [rbp+60h+WatchdogInformation.DpcTimeCount]
0x14002a8b6  lea     rax, [rsi+50h]
0x14002a8ba  mov     [rax+20h], rcx
0x14002a8be  mov     sil, 1
0x14002a8c1  mov     r8d, dword ptr [rbp+60h+var_D0]
0x14002a8c5  lea     rcx, Ipv4Global
0x14002a8cc  movzx   eax, word ptr [rsp+160h+var_E8]
0x14002a8d1  lea     rdx, [rbx+0E8h]
0x14002a8d8  mov     [rsp+160h+var_120], rdi
0x14002a8dd  xor     r9d, r9d
0x14002a8e0  mov     byte ptr [rsp+160h+var_128], 1
0x14002a8e5  shr     r13b, 2
0x14002a8e9  mov     dword ptr [rsp+160h+var_130], r15d
0x14002a8ee  and     r13b, 1
0x14002a8f2  mov     dword ptr [rsp+160h+var_138], r8d
0x14002a8f7  cmp     r14, rcx
0x14002a8fa  mov     rcx, [rbp+60h+HashTable]
0x14002a8fe  mov     r8, [rbp+60h+Buf2]
0x14002a902  mov     dword ptr [rsp+160h+Context], eax
0x14002a906  jz      loc_14002B514
0x14002a90c  call    ShimIpPacketOutV6
0x14002a911  movzx   edx, r13b
0x14002a915  mov     r9, rdi
0x14002a918  mov     r8d, r15d
0x14002a91b  mov     dword ptr [rsp+160h+Context], eax
0x14002a91f  mov     ecx, r12d
0x14002a922  call    IpSecNLPacketsOutProcessing
0x14002a927  mov     r15d, eax
0x14002a92a  test    rdi, rdi
0x14002a92d  jz      short loc_14002A939
0x14002a92f  and     dword ptr [rdi+88h], 0FF7FFFFFh
0x14002a939  test    sil, sil
0x14002a93c  jz      loc_14002A9C7
0x14002a942  xor     ecx, ecx; ProcNumber
0x14002a944  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002a94b  nop     dword ptr [rax+rax+00h]
0x14002a950  lea     ecx, [rax+rax*8]
0x14002a953  mov     rax, cs:gWfpPerProContext
0x14002a95a  shl     ecx, 3
0x14002a95d  mov     rdi, [rcx+rax]
0x14002a961  mov     ecx, [rdi]
0x14002a963  cmp     ecx, 1
0x14002a966  jnz     short loc_14002A991
0x14002a968  xorps   xmm0, xmm0
0x14002a96b  lea     rcx, [rbp+60h+WatchdogInformation]; WatchdogInformation
0x14002a96f  xor     eax, eax
0x14002a971  movups  xmmword ptr [rbp+60h+WatchdogInformation.DpcTimeLimit], xmm0
0x14002a975  mov     [rbp+60h+WatchdogInformation.Reserved], eax
0x14002a978  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14002a97f  nop     dword ptr [rax+rax+00h]
0x14002a984  mov     eax, [rbp+60h+WatchdogInformation.DpcTimeCount]
0x14002a987  lea     rcx, [rdi+78h]
0x14002a98b  add     rdi, 70h ; 'p'
0x14002a98f  jmp     short loc_14002A9C3
0x14002a991  sub     ecx, 2
0x14002a994  jz      loc_14002B448
0x14002a99a  cmp     ecx, 1
0x14002a99d  jnz     short loc_14002A9C7
0x14002a99f  dec     dword ptr [rdi+68h]
0x14002a9a2  mov     rax, 0FFFFF78000000008h
0x14002a9ac  mov     rax, [rax]
0x14002a9af  cmp     dword ptr [rdi+68h], 0
0x14002a9b3  jnz     short loc_14002A9BB
0x14002a9b5  mov     dword ptr [rdi], 0
0x14002a9bb  lea     rcx, [rdi+30h]
0x14002a9bf  add     rdi, 28h ; '('
0x14002a9c3  sub     eax, [rdi]
0x14002a9c5  add     [rcx], eax
0x14002a9c7  cmp     r15d, 1
0x14002a9cb  jge     loc_14002B292
0x14002a9d1  mov     rcx, rbx
0x14002a9d4  call    IppLbLogTransmitPacket
0x14002a9d9  mov     rdi, [rbx+8]
0x14002a9dd  mov     rax, [rdi+90h]
0x14002a9e4  mov     r10, [rdi+140h]
0x14002a9eb  mov     [rbp+60h+var_D0], rax
0x14002a9ef  test    al, 4
0x14002a9f1  jnz     loc_14002B1EC
0x14002a9f7  test    al, 8
0x14002a9f9  jnz     loc_14002AF18
0x14002a9ff  test    r10d, r10d
0x14002aa02  jnz     loc_14002AF18
0x14002aa08  movzx   edx, r10w
0x14002aa0c  test    r10d, r10d
0x14002aa0f  jnz     loc_1401C478E
0x14002aa15  lea     rsi, Ipv4Global
0x14002aa1c  mov     eax, cs:Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState
0x14002aa22  test    al, 10h
0x14002aa24  jnz     loc_14002B1DF
0x14002aa2a  call    Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_IsEnabledDeviceUsageNoInline
0x14002aa2f  test    eax, eax
0x14002aa31  jz      short loc_14002AA73
0x14002aa33  cmp     r14, rsi
0x14002aa36  jnz     short loc_14002AA73
0x14002aa38  cmp     dword ptr [rdi+140h], 0
0x14002aa3f  jnz     short loc_14002AA73
0x14002aa41  cmp     dword ptr [rdi+0A0h], 0
0x14002aa48  jnz     short loc_14002AA73
0x14002aa4a  call    cs:__imp_KfdAreAllIpv4InLayersEmpty
0x14002aa51  nop     dword ptr [rax+rax+00h]
0x14002aa56  test    al, al
0x14002aa58  jnz     short loc_14002AA73
0x14002aa5a  mov     rdi, [rdi+8]
0x14002aa5e  test    rdi, rdi
0x14002aa61  jz      short loc_14002AA73
0x14002aa63  mov     rcx, rdi
0x14002aa66  call    Ipv4pFillPacketChecksum
0x14002aa6b  mov     rdi, [rdi]
0x14002aa6e  test    rdi, rdi
0x14002aa71  jnz     short loc_14002AA63
0x14002aa73  mov     rax, [rbp+60h+Buf2]
0x14002aa77  inc     [rsp+160h+var_100]
0x14002aa7b  mov     ecx, [rax+8]
0x14002aa7e  mov     rax, [rbx+8]
0x14002aa82  mov     [rax+110h], rcx
0x14002aa89  mov     rax, qword ptr [rbp+60h+var_C0+8]
0x14002aa8d  mov     [rax], rbx
0x14002aa90  mov     qword ptr [rbp+60h+var_C0+8], rbx
0x14002aa94  mov     rcx, qword ptr [rsp+160h+var_F8]
0x14002aa99  lea     r8, Ipv4Global
0x14002aaa0  mov     edx, dword ptr [rbp+60h+var_C8]
0x14002aaa3  mov     rbx, rcx
0x14002aaa6  mov     r13d, 0
0x14002aaac  mov     r9d, 5DCh
  ... truncated ...
```
