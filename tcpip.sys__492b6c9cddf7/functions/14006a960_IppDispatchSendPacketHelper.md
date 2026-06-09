# IppDispatchSendPacketHelper

- ea: `0x14006a960`
- end: `0x14006b2df`
- name: `IppDispatchSendPacketHelper`
- size: `2431`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140069150`

## callees

- `0x14002f4f0`
- `0x140030580`
- `0x140032740`
- `0x1400554a0`
- `0x140056af0`
- `0x140058270`
- `0x140059f34`
- `0x14005aa88`
- `0x14006891c`
- `0x140068d10`
- `0x14006a450`
- `0x14006a960`
- `0x14006b2f0`
- `0x14006ba40`
- `0x14006bc80`
- `0x14006fde4`
- `0x14006feec`
- `0x14009d754`
- `0x1400ebdf0`
- `0x14010a1b0`
- `0x1401250bc`
- `0x14013f1d0`
- `0x1401bfe60`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14006aec4`
- `ntoskrnl!KfRaiseIrql` at `0x14006aec4`
- `ntoskrnl!KeLowerIrql` at `0x14006aee6`
- `ntoskrnl!KeLowerIrql` at `0x14006aee6`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006ac92`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006ac92`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006ac3d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006ac3d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006ab90`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006ab90`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006ad3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b131`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006ad3d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b131`
- `NETIO!RtlCompute37Hash` at `0x14006abf4`
- `NETIO!RtlCompute37Hash` at `0x14006ac0c`
- `NETIO!RtlCompute37Hash` at `0x14006abf4`
- `NETIO!RtlCompute37Hash` at `0x14006ac0c`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006ab38`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006ab38`

## pseudocode

```c
__int64 __fastcall IppDispatchSendPacketHelper(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // rax
  __int64 v3; // r12
  __int64 v4; // r14
  unsigned __int16 *v5; // rbx
  __int64 *v6; // r15
  __int64 v7; // rsi
  unsigned __int8 v8; // r13
  __int64 result; // rax
  __int64 v10; // r12
  int v11; // edi
  __int64 *v12; // r8
  __int64 v13; // r14
  _QWORD *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int16 **v17; // r14
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  void **v20; // rax
  KSPIN_LOCK v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // edi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rax
  struct _LIST_ENTRY **p_Blink; // rdi
  signed __int64 v26; // rdx
  void *Neighbor; // rax
  __int64 v28; // rdx
  void *v29; // r8
  PRTL_DYNAMIC_HASH_TABLE v30; // rcx
  __int64 *v31; // rax
  __int64 v32; // rdi
  __int64 StrongClonePacket; // rax
  PRTL_DYNAMIC_HASH_TABLE v34; // rcx
  unsigned __int16 *v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  _QWORD *i; // r12
  _QWORD *v39; // rdi
  __int64 ClonePacket; // rax
  KIRQL v41; // di
  int v42; // r9d
  __int64 PacketCount; // rax
  int v44; // r9d
  int v45; // r9d
  char v46; // al
  _DWORD *v47; // rcx
  int v48; // eax
  __int64 v49; // r9
  __int64 v50; // r10
  int v51; // eax
  __int64 v52; // r9
  __int64 v53; // r11
  __int128 v54; // [rsp+60h] [rbp-69h] BYREF
  void *Buf2; // [rsp+70h] [rbp-59h]
  PRTL_DYNAMIC_HASH_TABLE HashTable[2]; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v57; // [rsp+88h] [rbp-41h]
  int v58; // [rsp+8Ch] [rbp-3Dh]
  PKSPIN_LOCK SpinLock; // [rsp+90h] [rbp-39h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+98h] [rbp-31h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v62[5]; // [rsp+C8h] [rbp-1h] BYREF
  unsigned __int16 *v64; // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v65; // [rsp+140h] [rbp+77h] BYREF
  int v66; // [rsp+148h] [rbp+7Fh] BYREF

  v64 = a2;
  v2 = *((_QWORD *)a2 + 28);
  v3 = 0;
  v4 = *((_QWORD *)a2 + 27);
  v54 = 0;
  LODWORD(v65) = 0;
  v5 = a2;
  v66 = 0;
  v62[0] = 0;
  v6 = *(__int64 **)(v2 + 8);
  v7 = a1;
  v8 = 1;
  if ( *(_DWORD *)v4 == 1701736521 )
  {
    v3 = v4;
    if ( *(_DWORD *)(v4 + 24) == 3 && *(int *)(a1 + 19696) < 1 )
    {
      PacketCount = IppGetPacketCount(*((_QWORD *)a2 + 1));
      v44 = PacketCount;
      LODWORD(PacketCount) = HIDWORD(KeGetPcr()[1].LockArray);
      *(_DWORD *)(192 * PacketCount + *(_QWORD *)(v7 + 20264) + 152) += v44;
      if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
      {
        v51 = IppGetPacketCount(*((_QWORD *)v5 + 1));
        IppLogPacketDiscard(
          *(unsigned __int16 *)(v7 + 28),
          v5[52],
          *((_QWORD *)v5 + 33),
          *((_QWORD *)v5 + 31),
          129,
          v51,
          0,
          v53,
          *(_QWORD *)(v52 + 8),
          3,
          -536854268);
      }
      v45 = 129;
      goto LABEL_76;
    }
    goto LABEL_6;
  }
  if ( *(_DWORD *)v4 != 1634496585 )
    return IppFragmentPackets(v7);
  v11 = *(_DWORD *)(v4 + 24);
  if ( v11 != 4 )
  {
    if ( v11 != 3 )
      goto LABEL_14;
    if ( *(int *)(a1 + 19696) < 1 )
      return IppDiscardSendPackets(a1, (_DWORD)a2, 129, 1, 1, 0, 3, -536854268);
  }
  v20 = *(void ***)(v4 + 16);
  memset(&LockHandle, 0, sizeof(LockHandle));
  Buf2 = *v20;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v6 + 37, &LockHandle);
  while ( *((_DWORD *)v6 + 76) )
    ;
  memset(&Context, 0, sizeof(Context));
  SpinLock = (PKSPIN_LOCK)v6[43];
  HashTable[0] = (PRTL_DYNAMIC_HASH_TABLE)&CONTAINING_RECORD(SpinLock, struct _RTL_DYNAMIC_HASH_TABLE, Flags)->DivisorMask;
  v21 = *v6;
  v58 = v11;
  v57 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v21 + 40) + 16LL) + 6LL);
  v22 = RtlCompute37Hash((unsigned int)g_37HashSeed, Buf2, v57);
  *(_OWORD *)&Context.ChainHead = 0;
  v23 = RtlCompute37Hash(v22, v6 + 1, 4);
  RtlAcquireReadLockAtDpcLevel(SpinLock);
  NextEntryHashTable = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(SpinLock + 2), v23 | 0x80000000LL, &Context);
  if ( NextEntryHashTable )
  {
    do
    {
      p_Blink = &NextEntryHashTable[-2].Linkage.Blink;
      if ( (__int64 *)NextEntryHashTable[-2].Signature == v6
        && !memcmp(p_Blink + 21, Buf2, (unsigned __int16)v57)
        && (!v3 || *((_DWORD *)p_Blink + 7) > *(_DWORD *)(v3 + 28)) )
      {
        v3 = (__int64)p_Blink;
      }
      NextEntryHashTable = RtlGetNextEntryHashTable(HashTable[0], &Context);
    }
    while ( NextEntryHashTable );
    v5 = v64;
    v8 = 1;
    v7 = a1;
    if ( v3 )
    {
      v26 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 96), 2u) + 2;
      if ( v26 - 2 < 1 )
        __fastfail(0xEu);
      if ( (v26 & 0xFFFFFFFFFFFFFFFEuLL) == 2 && (v26 & 1) != 0 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(v3 + 8) + 316LL));
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 344LL) + 88LL));
        _InterlockedDecrement((volatile signed __int32 *)SpinLock + 2);
        goto LABEL_90;
      }
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)SpinLock + 2);
  if ( v3 )
  {
LABEL_90:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_49:
    if ( *(__int64 **)(v4 + 8) == v6 )
    {
      v30 = (PRTL_DYNAMIC_HASH_TABLE)*((_QWORD *)v5 + 1);
      *(_QWORD *)&v54 = 0;
      *((_QWORD *)&v54 + 1) = &v54;
      HashTable[0] = v30;
      if ( (v30[3].NonEmptyBuckets & 0xC) != 0 && *((_DWORD *)v5 + 64) == 1 )
        *((_BYTE *)v5 + 186) |= 8u;
      v31 = *(__int64 **)&v30->TableSize;
      Buf2 = v31;
      while ( 1 )
      {
        v64 = (unsigned __int16 *)v31;
        if ( !v31 )
          break;
        v32 = *v31;
        *v31 = 0;
        *(_QWORD *)&v30->TableSize = v31;
        StrongClonePacket = IppCreateStrongClonePacket(v5);
        v34 = HashTable[0];
        v28 = StrongClonePacket;
        v35 = v64;
        v29 = Buf2;
        *(_QWORD *)v64 = v32;
        *(_QWORD *)&v34->TableSize = v29;
        if ( !v28 )
        {
          v28 = v54;
          if ( (_QWORD)v54 )
          {
            IppLbLogAndDropPackets(v7, v54, 264, 3758113087LL);
            *(_QWORD *)&v54 = 0;
            *((_QWORD *)&v54 + 1) = &v54;
          }
          goto LABEL_79;
        }
        *(_OWORD *)(v28 + 16) = 0;
        **((_QWORD **)&v54 + 1) = v28;
        v30 = HashTable[0];
        *((_QWORD *)&v54 + 1) = v28;
        v31 = *(__int64 **)v35;
      }
      if ( (_QWORD)v54 )
      {
        v8 = 0;
        LOBYTE(v29) = 1;
        IppLoopbackEnqueue(&v54, v7, v29);
      }
    }
LABEL_79:
    v46 = *((_BYTE *)v5 + 184);
    if ( (v46 & 0x20) != 0 )
    {
      IppDereferencePath(*((_QWORD *)v5 + 26), v28, v29);
      *((_BYTE *)v5 + 184) &= ~0x20u;
      v46 = *((_BYTE *)v5 + 184);
    }
    *((_QWORD *)v5 + 26) = 0;
    if ( v46 < 0 )
    {
      v47 = (_DWORD *)*((_QWORD *)v5 + 27);
      if ( *v47 == 1634496585 )
      {
        IppDereferenceLocalAddress(v47);
      }
      else if ( *v47 == 1701736521 )
      {
        IppDereferenceNeighbor(v47);
        *((_BYTE *)v5 + 184) |= 0x80u;
        *((_QWORD *)v5 + 27) = v3;
        goto LABEL_6;
      }
    }
    *((_BYTE *)v5 + 184) |= 0x80u;
    *((_QWORD *)v5 + 27) = v3;
LABEL_6:
    v10 = *(_QWORD *)(v3 + 8);
    if ( (__int64 *)v10 != v6 )
    {
      if ( !(unsigned __int8)IppForwardPackets(v7, (int)v6, v10, (int)v5, v4, 0, 0, (__int64)&v65, &v66) )
      {
        if ( (_DWORD)v65 != 257 )
          return IppDiscardSendPackets(v7, (_DWORD)v5, v65, v8, 1, 0, 3, v66);
        return IppCompleteAndFreePacketList(v5, 0);
      }
LABEL_8:
      if ( (*((_BYTE *)v6 + 394) & 8) != 0 && *((_DWORD *)v5 + 64) == 3 )
      {
        HashTable[0] = 0;
        HashTable[1] = (PRTL_DYNAMIC_HASH_TABLE)HashTable;
        v41 = KfRaiseIrql(2u);
        IppForwardMulticastPackets(v6, v5, HashTable);
        KeLowerIrql(v41);
        if ( HashTable[0] )
          IppFragmentPackets(v7);
      }
      if ( *(_DWORD *)(v10 + 40) > 1u && (unsigned int)(*((_DWORD *)v5 + 64) - 3) <= 1 )
        IppCreateSubInterfaceSplitList(v5, v62);
      return IppFragmentPackets(v7);
    }
    if ( *(_BYTE *)(*(unsigned __int16 *)(v7 + 44) + *((_QWORD *)v5 + 35)) )
      goto LABEL_8;
    v36 = IppGetPacketCount(*((_QWORD *)v5 + 1));
    LODWORD(v37) = HIDWORD(KeGetPcr()[1].LockArray);
    *(_DWORD *)(*(_QWORD *)(v7 + 20264) + 192 * v37 + 152) += v36;
    if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C70 )
    {
      v48 = IppGetPacketCount(*((_QWORD *)v5 + 1));
      IppLogPacketDiscard(
        *(unsigned __int16 *)(v7 + 28),
        v5[52],
        *((_QWORD *)v5 + 33),
        *((_QWORD *)v5 + 31),
        128,
        v48,
        0,
        v50,
        *(_QWORD *)(v49 + 8),
        3,
        -536854268);
    }
    if ( !v8 )
      return IppCompleteAndFreePacketList(v5, 0);
    v45 = 128;
LABEL_76:
    IppSendErrorListForDiscardReason(0, v7, (_DWORD)v5, v45, 0);
    return IppCompleteAndFreePacketList(v5, 0);
  }
  if ( v58 == 3 && (*(_DWORD *)(v6[6] + 28) & 2) == 0 )
  {
    v3 = 0;
  }
  else
  {
    Neighbor = (void *)IppCreateNeighbor(v6);
    v3 = (__int64)Neighbor;
    if ( Neighbor )
      v3 = IppInitializeNeighbor(Neighbor);
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v3 )
    goto LABEL_49;
LABEL_14:
  v12 = *(__int64 **)(v4 + 8);
  if ( v12 != v6 && !(unsigned __int8)IppForwardPackets(v7, (int)v6, (int)v12, (int)v5, v4, 0, 0, (__int64)&v65, &v66) )
  {
    if ( (_DWORD)v65 != 257 )
    {
      LOBYTE(v42) = 1;
      return IppDiscardSendPackets(v7, (_DWORD)v5, v65, v42, 1, 0, 3, v66);
    }
    return IppCompleteAndFreePacketList(v5, 0);
  }
  v13 = *((_QWORD *)v5 + 1);
  *(_QWORD *)&v54 = 0;
  *((_QWORD *)&v54 + 1) = &v54;
  if ( (*(_DWORD *)(v13 + 144) & 0xC) != 0 && *((_DWORD *)v5 + 64) == 1 )
    *((_BYTE *)v5 + 186) |= 8u;
  v14 = *(_QWORD **)(v13 + 8);
  if ( *v14 )
  {
    for ( i = *(_QWORD **)(v13 + 8); i; i = (_QWORD *)*i )
    {
      v39 = (_QWORD *)*i;
      *i = 0;
      *(_QWORD *)(v13 + 8) = i;
      ClonePacket = IppCreateClonePacket(v5);
      *i = v39;
      *(_QWORD *)(v13 + 8) = v14;
      if ( !ClonePacket )
      {
        if ( (_QWORD)v54 )
        {
          IppLbLogAndDropPackets(v7, v54, 264, 3758113087LL);
          *(_QWORD *)&v54 = 0;
          *((_QWORD *)&v54 + 1) = &v54;
        }
        break;
      }
      *(_OWORD *)(ClonePacket + 16) = 0;
      **((_QWORD **)&v54 + 1) = ClonePacket;
      *((_QWORD *)&v54 + 1) = ClonePacket;
    }
    v64 = 0;
    v17 = &v64;
    do
    {
      v18 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
      v19 = *(unsigned __int16 **)v5;
      if ( v18 )
      {
        *v17 = v18;
        v17 = (unsigned __int16 **)v18;
      }
      result = IppFreePacket(v5);
      v5 = v19;
    }
    while ( v19 );
    if ( v64 )
      result = NetioDereferenceNetBufferListChain(v64, 0);
  }
  else
  {
    v15 = IppPendPacket(v5);
    if ( v15 )
    {
      result = *((_QWORD *)&v54 + 1);
      **((_QWORD **)&v54 + 1) = v15;
      *((_QWORD *)&v54 + 1) = v15;
    }
    else
    {
      result = IppLbLogAndDropPackets(v7, v5, 264, 3758113086LL);
    }
  }
  if ( (_QWORD)v54 )
  {
    LOBYTE(v16) = 1;
    return IppLoopbackEnqueue(&v54, v7, v16);
  }
  return result;
}

```

## disassembly

```asm
0x14006a960  mov     [rsp-8+arg_8], rdx
0x14006a965  mov     [rsp-8+arg_0], rcx
0x14006a96a  push    rbp
0x14006a96b  push    rbx
0x14006a96c  push    rsi
0x14006a96d  push    rdi
0x14006a96e  push    r12
0x14006a970  push    r13
0x14006a972  push    r14
0x14006a974  push    r15
0x14006a976  lea     rbp, [rsp-1Fh]
0x14006a97b  sub     rsp, 0E8h
0x14006a982  mov     rax, [rdx+0E0h]
0x14006a989  xor     r12d, r12d
0x14006a98c  mov     r14, [rdx+0D8h]
0x14006a993  xorps   xmm0, xmm0
0x14006a996  movups  [rbp+57h+var_C0], xmm0
0x14006a99a  mov     dword ptr [rbp+57h+arg_10], r12d
0x14006a99e  mov     rbx, rdx
0x14006a9a1  xorps   xmm1, xmm1
0x14006a9a4  mov     [rbp+57h+arg_18], r12d
0x14006a9a8  movups  [rbp+57h+var_58], xmm1
0x14006a9ac  mov     r15, [rax+8]
0x14006a9b0  mov     rsi, rcx
0x14006a9b3  mov     eax, [r14]
0x14006a9b6  mov     r13b, 1
0x14006a9b9  cmp     eax, 656E7049h
0x14006a9be  jz      short loc_14006A9EB
0x14006a9c0  cmp     eax, 616C7049h
0x14006a9c5  jz      loc_14006AA55
0x14006a9cb  mov     rdx, rbx
0x14006a9ce  mov     rcx, rsi
0x14006a9d1  call    IppFragmentPackets
0x14006a9d6  add     rsp, 0E8h
0x14006a9dd  pop     r15
0x14006a9df  pop     r14
0x14006a9e1  pop     r13
0x14006a9e3  pop     r12
0x14006a9e5  pop     rdi
0x14006a9e6  pop     rsi
0x14006a9e7  pop     rbx
0x14006a9e8  pop     rbp
0x14006a9e9  retn
0x14006a9eb  cmp     dword ptr [r14+18h], 3
0x14006a9f0  mov     r12, r14
0x14006a9f3  jz      loc_14006AF80
0x14006a9f9  mov     r12, [r12+8]
0x14006a9fe  cmp     r12, r15
0x14006aa01  jnz     loc_14006B061
0x14006aa07  movzx   ecx, word ptr [rsi+2Ch]
0x14006aa0b  mov     rax, [rbx+118h]
0x14006aa12  cmp     byte ptr [rcx+rax], 0
0x14006aa16  jz      loc_14006ADF3
0x14006aa1c  test    byte ptr [r15+18Ah], 8
0x14006aa24  jnz     loc_14006AEA5
0x14006aa2a  cmp     dword ptr [r12+28h], 1
0x14006aa30  jbe     short loc_14006A9CB
0x14006aa32  mov     eax, [rbx+100h]
0x14006aa38  sub     eax, 3
0x14006aa3b  cmp     eax, 1
0x14006aa3e  ja      short loc_14006A9CB
0x14006aa40  lea     rdx, [rbp+57h+var_58]
0x14006aa44  mov     rcx, rbx
0x14006aa47  call    IppCreateSubInterfaceSplitList
0x14006aa4c  mov     rdx, qword ptr [rbp+57h+var_58]
0x14006aa50  jmp     loc_14006A9CE
0x14006aa55  mov     edi, [r14+18h]
0x14006aa59  cmp     edi, 4
0x14006aa5c  jz      loc_14006AB70
0x14006aa62  cmp     edi, 3
0x14006aa65  jz      loc_14006AB63
0x14006aa6b  mov     r8, [r14+8]; int
0x14006aa6f  cmp     r8, r15
0x14006aa72  jnz     loc_14006AF0C
0x14006aa78  mov     r14, [rbx+8]
0x14006aa7c  lea     rax, [rbp+57h+var_C0]
0x14006aa80  mov     qword ptr [rbp+57h+var_C0], r12
0x14006aa84  mov     qword ptr [rbp+57h+var_C0+8], rax
0x14006aa88  mov     eax, [r14+90h]
0x14006aa8f  test    al, 0Ch
0x14006aa91  jz      short loc_14006AAA3
0x14006aa93  cmp     dword ptr [rbx+100h], 1
0x14006aa9a  jnz     short loc_14006AAA3
0x14006aa9c  or      byte ptr [rbx+0BAh], 8
0x14006aaa3  mov     r15, [r14+8]
0x14006aaa7  cmp     qword ptr [r15], 0
0x14006aaab  jnz     loc_14006AE58
0x14006aab1  mov     rcx, rbx
0x14006aab4  call    IppPendPacket
0x14006aab9  mov     rcx, rax
0x14006aabc  test    rax, rax
0x14006aabf  jz      loc_14006B0E4
0x14006aac5  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x14006aac9  mov     [rax], rcx
0x14006aacc  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x14006aad0  jmp     short loc_14006AB44
0x14006aad2  mov     rdx, qword ptr [rbp+57h+var_C0]
0x14006aad6  test    rdx, rdx
0x14006aad9  jz      short loc_14006AAFF
0x14006aadb  mov     r9d, 0E000413Fh
0x14006aae1  mov     r8d, 108h
0x14006aae7  mov     rcx, rsi
0x14006aaea  call    IppLbLogAndDropPackets
0x14006aaef  lea     rax, [rbp+57h+var_C0]
0x14006aaf3  mov     qword ptr [rbp+57h+var_C0], 0
0x14006aafb  mov     qword ptr [rbp+57h+var_C0+8], rax
0x14006aaff  mov     [rbp+57h+arg_8], 0
0x14006ab07  lea     r14, [rbp+57h+arg_8]
0x14006ab0b  mov     rax, [rbx+8]
0x14006ab0f  mov     rdi, [rbx]
0x14006ab12  test    rax, rax
0x14006ab15  jz      short loc_14006AB1D
0x14006ab17  mov     [r14], rax
0x14006ab1a  mov     r14, rax
0x14006ab1d  mov     rcx, rbx; Entry
0x14006ab20  call    IppFreePacket
0x14006ab25  mov     rbx, rdi
0x14006ab28  test    rdi, rdi
0x14006ab2b  jnz     short loc_14006AB0B
0x14006ab2d  mov     rcx, [rbp+57h+arg_8]
0x14006ab31  test    rcx, rcx
0x14006ab34  jz      short loc_14006AB44
0x14006ab36  xor     edx, edx
0x14006ab38  call    cs:__imp_NetioDereferenceNetBufferListChain
0x14006ab3f  nop     dword ptr [rax+rax+00h]
0x14006ab44  cmp     qword ptr [rbp+57h+var_C0], 0
0x14006ab49  jz      loc_14006A9D6
0x14006ab4f  mov     r8b, 1
0x14006ab52  lea     rcx, [rbp+57h+var_C0]
0x14006ab56  mov     rdx, rsi
0x14006ab59  call    IppLoopbackEnqueue
0x14006ab5e  jmp     loc_14006A9D6
0x14006ab63  cmp     dword ptr [rcx+4CF0h], 1
0x14006ab6a  jl      loc_14006B21E
0x14006ab70  mov     rax, [r14+10h]
0x14006ab74  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14006ab78  lea     rcx, [r15+128h]; SpinLock
0x14006ab7f  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14006ab83  mov     rax, [rax]
0x14006ab86  mov     [rbp+57h+Buf2], rax
0x14006ab8a  xor     eax, eax
0x14006ab8c  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14006ab90  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14006ab97  nop     dword ptr [rax+rax+00h]
0x14006ab9c  mov     eax, [r15+130h]
0x14006aba3  test    eax, eax
0x14006aba5  jnz     short loc_14006AB9C
0x14006aba7  mov     rdx, [rbp+57h+Buf2]
0x14006abab  mov     eax, 1
0x14006abb0  xorps   xmm0, xmm0
0x14006abb3  cmp     edi, 2
0x14006abb6  movups  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x14006abba  cmovz   edi, eax
0x14006abbd  mov     rax, [r15+158h]
0x14006abc4  mov     [rbp+57h+SpinLock], rax
0x14006abc8  add     rax, 10h
0x14006abcc  mov     [rbp+57h+HashTable], rax
0x14006abd0  xor     eax, eax
0x14006abd2  mov     [rbp+57h+Context.Signature], rax
0x14006abd6  mov     rax, [r15]
0x14006abd9  mov     [rbp+57h+var_94], edi
0x14006abdc  mov     rcx, [rax+28h]
0x14006abe0  mov     rax, [rcx+10h]
0x14006abe4  mov     ecx, cs:g_37HashSeed
0x14006abea  movzx   eax, word ptr [rax+6]
0x14006abee  mov     r8d, eax
0x14006abf1  mov     [rbp+57h+var_98], eax
0x14006abf4  call    cs:__imp_RtlCompute37Hash
0x14006abfb  nop     dword ptr [rax+rax+00h]
0x14006ac00  lea     rdx, [r15+8]
0x14006ac04  mov     r8d, 4
0x14006ac0a  mov     ecx, eax
0x14006ac0c  call    cs:__imp_RtlCompute37Hash
0x14006ac13  nop     dword ptr [rax+rax+00h]
0x14006ac18  mov     rcx, [rbp+57h+SpinLock]; SpinLock
0x14006ac1c  xorps   xmm0, xmm0
0x14006ac1f  movdqu  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x14006ac24  mov     edi, eax
0x14006ac26  call    RtlAcquireReadLockAtDpcLevel
0x14006ac2b  mov     rcx, [rbp+57h+HashTable]; HashTable
0x14006ac2f  lea     r8, [rbp+57h+Context]; Context
0x14006ac33  mov     eax, 80000000h
0x14006ac38  mov     edx, edi
0x14006ac3a  or      rdx, rax; Signature
0x14006ac3d  call    cs:__imp_RtlLookupEntryHashTable
0x14006ac44  nop     dword ptr [rax+rax+00h]
0x14006ac49  test    rax, rax
0x14006ac4c  jz      loc_14006ACE2
0x14006ac52  mov     rsi, [rbp+57h+Buf2]
0x14006ac56  mov     rbx, [rbp+57h+HashTable]
0x14006ac5a  mov     r13d, [rbp+57h+var_98]
0x14006ac5e  cmp     [rax-20h], r15
0x14006ac62  lea     rdi, [rax-28h]
0x14006ac66  jnz     short loc_14006AC8B
0x14006ac68  movzx   r8d, r13w; Size
0x14006ac6c  lea     rcx, [rdi+0A8h]; Buf1
0x14006ac73  mov     rdx, rsi; Buf2
0x14006ac76  call    memcmp
0x14006ac7b  test    eax, eax
0x14006ac7d  jnz     short loc_14006AC8B
0x14006ac7f  test    r12, r12
0x14006ac82  jnz     loc_14006B2B5
0x14006ac88  mov     r12, rdi
0x14006ac8b  lea     rdx, [rbp+57h+Context]; Context
0x14006ac8f  mov     rcx, rbx; HashTable
0x14006ac92  call    cs:__imp_RtlGetNextEntryHashTable
0x14006ac99  nop     dword ptr [rax+rax+00h]
0x14006ac9e  test    rax, rax
0x14006aca1  jnz     short loc_14006AC5E
0x14006aca3  mov     rbx, [rbp+57h+arg_8]
0x14006aca7  mov     r13b, 1
0x14006acaa  mov     rsi, [rbp+57h+arg_0]
0x14006acae  test    r12, r12
0x14006acb1  jz      short loc_14006ACE2
0x14006acb3  mov     edx, 2
0x14006acb8  lock xadd [r12+60h], rdx
0x14006acbf  add     rdx, 2
0x14006acc3  lea     rax, [rdx-2]
0x14006acc7  cmp     rax, 1
0x14006accb  jl      loc_14006B2C8
0x14006acd1  mov     rax, rdx
0x14006acd4  and     rax, 0FFFFFFFFFFFFFFFEh
0x14006acd8  cmp     rax, 2
0x14006acdc  jz      loc_14006B100
0x14006ace2  mov     rax, [rbp+57h+SpinLock]
0x14006ace6  lock dec dword ptr [rax+8]
0x14006acea  test    r12, r12
0x14006aced  jnz     loc_14006B12D
0x14006acf3  mov     edi, [rbp+57h+var_94]
0x14006acf6  cmp     edi, 3
0x14006acf9  jnz     short loc_14006AD0B
0x14006acfb  mov     rax, [r15+30h]
0x14006acff  mov     ecx, [rax+1Ch]
0x14006ad02  test    cl, 2
0x14006ad05  jz      loc_14006B0DC
0x14006ad0b  mov     rax, ds:0FFFFF78000000008h
0x14006ad15  mov     rcx, r15
0x14006ad18  call    IppCreateNeighbor
0x14006ad1d  mov     r12, rax
0x14006ad20  test    rax, rax
0x14006ad23  jz      short loc_14006AD39
0x14006ad25  mov     r8, [rbp+57h+Buf2]
0x14006ad29  mov     r9d, edi
0x14006ad2c  xor     edx, edx
0x14006ad2e  mov     rcx, rax; P
0x14006ad31  call    IppInitializeNeighbor
0x14006ad36  mov     r12, rax
0x14006ad39  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14006ad3d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14006ad44  nop     dword ptr [rax+rax+00h]
0x14006ad49  test    r12, r12
0x14006ad4c  jz      loc_14006AE53
0x14006ad52  cmp     [r14+8], r15
0x14006ad56  jnz     loc_14006B016
0x14006ad5c  mov     rcx, [rbx+8]
0x14006ad60  lea     rax, [rbp+57h+var_C0]
0x14006ad64  mov     qword ptr [rbp+57h+var_C0], 0
0x14006ad6c  mov     qword ptr [rbp+57h+var_C0+8], rax
0x14006ad70  mov     [rbp+57h+HashTable], rcx
0x14006ad74  mov     eax, [rcx+90h]
0x14006ad7a  test    al, 0Ch
0x14006ad7c  jz      short loc_14006AD8E
0x14006ad7e  cmp     dword ptr [rbx+100h], 1
0x14006ad85  jnz     short loc_14006AD8E
0x14006ad87  or      byte ptr [rbx+0BAh], 8
0x14006ad8e  mov     rax, [rcx+8]
0x14006ad92  mov     [rbp+57h+Buf2], rax
0x14006ad96  mov     [rbp+57h+arg_8], rax
0x14006ad9a  test    rax, rax
0x14006ad9d  jz      loc_14006AFFD
0x14006ada3  mov     rdi, [rax]
0x14006ada6  mov     qword ptr [rax], 0
0x14006adad  mov     [rcx+8], rax
0x14006adb1  mov     rcx, rbx
0x14006adb4  call    IppCreateStrongClonePacket
0x14006adb9  mov     rcx, [rbp+57h+HashTable]
0x14006adbd  mov     rdx, rax
0x14006adc0  mov     rax, [rbp+57h+arg_8]
0x14006adc4  mov     r8, [rbp+57h+Buf2]
0x14006adc8  mov     [rax], rdi
0x14006adcb  mov     [rcx+8], r8
0x14006adcf  test    rdx, rdx
0x14006add2  jz      loc_14006B142
0x14006add8  xorps   xmm0, xmm0
0x14006addb  movups  xmmword ptr [rdx+10h], xmm0
0x14006addf  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x14006ade3  mov     [rcx], rdx
0x14006ade6  mov     rcx, [rbp+57h+HashTable]
0x14006adea  mov     qword ptr [rbp+57h+var_C0+8], rdx
0x14006adee  mov     rax, [rax]
0x14006adf1  jmp     short loc_14006AD96
0x14006adf3  mov     rcx, [rbx+8]
0x14006adf7  call    IppGetPacketCount
0x14006adfc  mov     ecx, gs:1A4h
0x14006ae04  lea     rdx, [rcx+rcx*2]
0x14006ae08  shl     rdx, 6
0x14006ae0c  add     rdx, [rsi+4F28h]
0x14006ae13  mov     ecx, [rdx+98h]
0x14006ae19  add     eax, ecx
0x14006ae1b  mov     [rdx+98h], eax
  ... truncated ...
```
