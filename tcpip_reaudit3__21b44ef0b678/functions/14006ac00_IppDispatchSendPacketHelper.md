# IppDispatchSendPacketHelper

- ea: `0x14006ac00`
- end: `0x14006b57f`
- name: `IppDispatchSendPacketHelper`
- size: `2431`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400693f0`

## callees

- `0x14002f790`
- `0x140030820`
- `0x1400329e0`
- `0x140055740`
- `0x140056d90`
- `0x140058510`
- `0x14005a1d4`
- `0x14005ad28`
- `0x140068bbc`
- `0x140068fb0`
- `0x14006a6f0`
- `0x14006ac00`
- `0x14006b590`
- `0x14006bce0`
- `0x14006bf20`
- `0x140070084`
- `0x14007018c`
- `0x14009e604`
- `0x1400ebce0`
- `0x14010a1d0`
- `0x1401251fc`
- `0x14013f360`
- `0x1401bffa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14006b164`
- `ntoskrnl!KfRaiseIrql` at `0x14006b164`
- `ntoskrnl!KeLowerIrql` at `0x14006b186`
- `ntoskrnl!KeLowerIrql` at `0x14006b186`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006af32`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006af32`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006aedd`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006aedd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006ae30`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14006ae30`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006afdd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b3d1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006afdd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14006b3d1`
- `NETIO!RtlCompute37Hash` at `0x14006ae94`
- `NETIO!RtlCompute37Hash` at `0x14006aeac`
- `NETIO!RtlCompute37Hash` at `0x14006ae94`
- `NETIO!RtlCompute37Hash` at `0x14006aeac`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006add8`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006add8`

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
      if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C30 )
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
    if ( SBYTE6(WPP_MAIN_CB.Reserved) < 0 || byte_140225C30 )
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
0x14006ac00  mov     [rsp-8+arg_8], rdx
0x14006ac05  mov     [rsp-8+arg_0], rcx
0x14006ac0a  push    rbp
0x14006ac0b  push    rbx
0x14006ac0c  push    rsi
0x14006ac0d  push    rdi
0x14006ac0e  push    r12
0x14006ac10  push    r13
0x14006ac12  push    r14
0x14006ac14  push    r15
0x14006ac16  lea     rbp, [rsp-1Fh]
0x14006ac1b  sub     rsp, 0E8h
0x14006ac22  mov     rax, [rdx+0E0h]
0x14006ac29  xor     r12d, r12d
0x14006ac2c  mov     r14, [rdx+0D8h]
0x14006ac33  xorps   xmm0, xmm0
0x14006ac36  movups  [rbp+57h+var_C0], xmm0
0x14006ac3a  mov     dword ptr [rbp+57h+arg_10], r12d
0x14006ac3e  mov     rbx, rdx
0x14006ac41  xorps   xmm1, xmm1
0x14006ac44  mov     [rbp+57h+arg_18], r12d
0x14006ac48  movups  [rbp+57h+var_58], xmm1
0x14006ac4c  mov     r15, [rax+8]
0x14006ac50  mov     rsi, rcx
0x14006ac53  mov     eax, [r14]
0x14006ac56  mov     r13b, 1
0x14006ac59  cmp     eax, 656E7049h
0x14006ac5e  jz      short loc_14006AC8B
0x14006ac60  cmp     eax, 616C7049h
0x14006ac65  jz      loc_14006ACF5
0x14006ac6b  mov     rdx, rbx
0x14006ac6e  mov     rcx, rsi
0x14006ac71  call    IppFragmentPackets
0x14006ac76  add     rsp, 0E8h
0x14006ac7d  pop     r15
0x14006ac7f  pop     r14
0x14006ac81  pop     r13
0x14006ac83  pop     r12
0x14006ac85  pop     rdi
0x14006ac86  pop     rsi
0x14006ac87  pop     rbx
0x14006ac88  pop     rbp
0x14006ac89  retn
0x14006ac8b  cmp     dword ptr [r14+18h], 3
0x14006ac90  mov     r12, r14
0x14006ac93  jz      loc_14006B220
0x14006ac99  mov     r12, [r12+8]
0x14006ac9e  cmp     r12, r15
0x14006aca1  jnz     loc_14006B301
0x14006aca7  movzx   ecx, word ptr [rsi+2Ch]
0x14006acab  mov     rax, [rbx+118h]
0x14006acb2  cmp     byte ptr [rcx+rax], 0
0x14006acb6  jz      loc_14006B093
0x14006acbc  test    byte ptr [r15+18Ah], 8
0x14006acc4  jnz     loc_14006B145
0x14006acca  cmp     dword ptr [r12+28h], 1
0x14006acd0  jbe     short loc_14006AC6B
0x14006acd2  mov     eax, [rbx+100h]
0x14006acd8  sub     eax, 3
0x14006acdb  cmp     eax, 1
0x14006acde  ja      short loc_14006AC6B
0x14006ace0  lea     rdx, [rbp+57h+var_58]
0x14006ace4  mov     rcx, rbx
0x14006ace7  call    IppCreateSubInterfaceSplitList
0x14006acec  mov     rdx, qword ptr [rbp+57h+var_58]
0x14006acf0  jmp     loc_14006AC6E
0x14006acf5  mov     edi, [r14+18h]
0x14006acf9  cmp     edi, 4
0x14006acfc  jz      loc_14006AE10
0x14006ad02  cmp     edi, 3
0x14006ad05  jz      loc_14006AE03
0x14006ad0b  mov     r8, [r14+8]; int
0x14006ad0f  cmp     r8, r15
0x14006ad12  jnz     loc_14006B1AC
0x14006ad18  mov     r14, [rbx+8]
0x14006ad1c  lea     rax, [rbp+57h+var_C0]
0x14006ad20  mov     qword ptr [rbp+57h+var_C0], r12
0x14006ad24  mov     qword ptr [rbp+57h+var_C0+8], rax
0x14006ad28  mov     eax, [r14+90h]
0x14006ad2f  test    al, 0Ch
0x14006ad31  jz      short loc_14006AD43
0x14006ad33  cmp     dword ptr [rbx+100h], 1
0x14006ad3a  jnz     short loc_14006AD43
0x14006ad3c  or      byte ptr [rbx+0BAh], 8
0x14006ad43  mov     r15, [r14+8]
0x14006ad47  cmp     qword ptr [r15], 0
0x14006ad4b  jnz     loc_14006B0F8
0x14006ad51  mov     rcx, rbx
0x14006ad54  call    IppPendPacket
0x14006ad59  mov     rcx, rax
0x14006ad5c  test    rax, rax
0x14006ad5f  jz      loc_14006B384
0x14006ad65  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x14006ad69  mov     [rax], rcx
0x14006ad6c  mov     qword ptr [rbp+57h+var_C0+8], rcx
0x14006ad70  jmp     short loc_14006ADE4
0x14006ad72  mov     rdx, qword ptr [rbp+57h+var_C0]
0x14006ad76  test    rdx, rdx
0x14006ad79  jz      short loc_14006AD9F
0x14006ad7b  mov     r9d, 0E000413Fh
0x14006ad81  mov     r8d, 108h
0x14006ad87  mov     rcx, rsi
0x14006ad8a  call    IppLbLogAndDropPackets
0x14006ad8f  lea     rax, [rbp+57h+var_C0]
0x14006ad93  mov     qword ptr [rbp+57h+var_C0], 0
0x14006ad9b  mov     qword ptr [rbp+57h+var_C0+8], rax
0x14006ad9f  mov     [rbp+57h+arg_8], 0
0x14006ada7  lea     r14, [rbp+57h+arg_8]
0x14006adab  mov     rax, [rbx+8]
0x14006adaf  mov     rdi, [rbx]
0x14006adb2  test    rax, rax
0x14006adb5  jz      short loc_14006ADBD
0x14006adb7  mov     [r14], rax
0x14006adba  mov     r14, rax
0x14006adbd  mov     rcx, rbx; Entry
0x14006adc0  call    IppFreePacket
0x14006adc5  mov     rbx, rdi
0x14006adc8  test    rdi, rdi
0x14006adcb  jnz     short loc_14006ADAB
0x14006adcd  mov     rcx, [rbp+57h+arg_8]
0x14006add1  test    rcx, rcx
0x14006add4  jz      short loc_14006ADE4
0x14006add6  xor     edx, edx
0x14006add8  call    cs:__imp_NetioDereferenceNetBufferListChain
0x14006addf  nop     dword ptr [rax+rax+00h]
0x14006ade4  cmp     qword ptr [rbp+57h+var_C0], 0
0x14006ade9  jz      loc_14006AC76
0x14006adef  mov     r8b, 1
0x14006adf2  lea     rcx, [rbp+57h+var_C0]
0x14006adf6  mov     rdx, rsi
0x14006adf9  call    IppLoopbackEnqueue
0x14006adfe  jmp     loc_14006AC76
0x14006ae03  cmp     dword ptr [rcx+4CF0h], 1
0x14006ae0a  jl      loc_14006B4BE
0x14006ae10  mov     rax, [r14+10h]
0x14006ae14  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14006ae18  lea     rcx, [r15+128h]; SpinLock
0x14006ae1f  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14006ae23  mov     rax, [rax]
0x14006ae26  mov     [rbp+57h+Buf2], rax
0x14006ae2a  xor     eax, eax
0x14006ae2c  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14006ae30  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14006ae37  nop     dword ptr [rax+rax+00h]
0x14006ae3c  mov     eax, [r15+130h]
0x14006ae43  test    eax, eax
0x14006ae45  jnz     short loc_14006AE3C
0x14006ae47  mov     rdx, [rbp+57h+Buf2]
0x14006ae4b  mov     eax, 1
0x14006ae50  xorps   xmm0, xmm0
0x14006ae53  cmp     edi, 2
0x14006ae56  movups  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x14006ae5a  cmovz   edi, eax
0x14006ae5d  mov     rax, [r15+158h]
0x14006ae64  mov     [rbp+57h+SpinLock], rax
0x14006ae68  add     rax, 10h
0x14006ae6c  mov     [rbp+57h+HashTable], rax
0x14006ae70  xor     eax, eax
0x14006ae72  mov     [rbp+57h+Context.Signature], rax
0x14006ae76  mov     rax, [r15]
0x14006ae79  mov     [rbp+57h+var_94], edi
0x14006ae7c  mov     rcx, [rax+28h]
0x14006ae80  mov     rax, [rcx+10h]
0x14006ae84  mov     ecx, cs:g_37HashSeed
0x14006ae8a  movzx   eax, word ptr [rax+6]
0x14006ae8e  mov     r8d, eax
0x14006ae91  mov     [rbp+57h+var_98], eax
0x14006ae94  call    cs:__imp_RtlCompute37Hash
0x14006ae9b  nop     dword ptr [rax+rax+00h]
0x14006aea0  lea     rdx, [r15+8]
0x14006aea4  mov     r8d, 4
0x14006aeaa  mov     ecx, eax
0x14006aeac  call    cs:__imp_RtlCompute37Hash
0x14006aeb3  nop     dword ptr [rax+rax+00h]
0x14006aeb8  mov     rcx, [rbp+57h+SpinLock]; SpinLock
0x14006aebc  xorps   xmm0, xmm0
0x14006aebf  movdqu  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x14006aec4  mov     edi, eax
0x14006aec6  call    RtlAcquireReadLockAtDpcLevel
0x14006aecb  mov     rcx, [rbp+57h+HashTable]; HashTable
0x14006aecf  lea     r8, [rbp+57h+Context]; Context
0x14006aed3  mov     eax, 80000000h
0x14006aed8  mov     edx, edi
0x14006aeda  or      rdx, rax; Signature
0x14006aedd  call    cs:__imp_RtlLookupEntryHashTable
0x14006aee4  nop     dword ptr [rax+rax+00h]
0x14006aee9  test    rax, rax
0x14006aeec  jz      loc_14006AF82
0x14006aef2  mov     rsi, [rbp+57h+Buf2]
0x14006aef6  mov     rbx, [rbp+57h+HashTable]
0x14006aefa  mov     r13d, [rbp+57h+var_98]
0x14006aefe  cmp     [rax-20h], r15
0x14006af02  lea     rdi, [rax-28h]
0x14006af06  jnz     short loc_14006AF2B
0x14006af08  movzx   r8d, r13w; Size
0x14006af0c  lea     rcx, [rdi+0A8h]; Buf1
0x14006af13  mov     rdx, rsi; Buf2
0x14006af16  call    memcmp
0x14006af1b  test    eax, eax
0x14006af1d  jnz     short loc_14006AF2B
0x14006af1f  test    r12, r12
0x14006af22  jnz     loc_14006B555
0x14006af28  mov     r12, rdi
0x14006af2b  lea     rdx, [rbp+57h+Context]; Context
0x14006af2f  mov     rcx, rbx; HashTable
0x14006af32  call    cs:__imp_RtlGetNextEntryHashTable
0x14006af39  nop     dword ptr [rax+rax+00h]
0x14006af3e  test    rax, rax
0x14006af41  jnz     short loc_14006AEFE
0x14006af43  mov     rbx, [rbp+57h+arg_8]
0x14006af47  mov     r13b, 1
0x14006af4a  mov     rsi, [rbp+57h+arg_0]
0x14006af4e  test    r12, r12
0x14006af51  jz      short loc_14006AF82
0x14006af53  mov     edx, 2
0x14006af58  lock xadd [r12+60h], rdx
0x14006af5f  add     rdx, 2
0x14006af63  lea     rax, [rdx-2]
0x14006af67  cmp     rax, 1
0x14006af6b  jl      loc_14006B568
0x14006af71  mov     rax, rdx
0x14006af74  and     rax, 0FFFFFFFFFFFFFFFEh
0x14006af78  cmp     rax, 2
0x14006af7c  jz      loc_14006B3A0
0x14006af82  mov     rax, [rbp+57h+SpinLock]
0x14006af86  lock dec dword ptr [rax+8]
0x14006af8a  test    r12, r12
0x14006af8d  jnz     loc_14006B3CD
0x14006af93  mov     edi, [rbp+57h+var_94]
0x14006af96  cmp     edi, 3
0x14006af99  jnz     short loc_14006AFAB
0x14006af9b  mov     rax, [r15+30h]
0x14006af9f  mov     ecx, [rax+1Ch]
0x14006afa2  test    cl, 2
0x14006afa5  jz      loc_14006B37C
0x14006afab  mov     rax, ds:0FFFFF78000000008h
0x14006afb5  mov     rcx, r15
0x14006afb8  call    IppCreateNeighbor
0x14006afbd  mov     r12, rax
0x14006afc0  test    rax, rax
0x14006afc3  jz      short loc_14006AFD9
0x14006afc5  mov     r8, [rbp+57h+Buf2]
0x14006afc9  mov     r9d, edi
0x14006afcc  xor     edx, edx
0x14006afce  mov     rcx, rax; P
0x14006afd1  call    IppInitializeNeighbor
0x14006afd6  mov     r12, rax
0x14006afd9  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14006afdd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14006afe4  nop     dword ptr [rax+rax+00h]
0x14006afe9  test    r12, r12
0x14006afec  jz      loc_14006B0F3
0x14006aff2  cmp     [r14+8], r15
0x14006aff6  jnz     loc_14006B2B6
0x14006affc  mov     rcx, [rbx+8]
0x14006b000  lea     rax, [rbp+57h+var_C0]
0x14006b004  mov     qword ptr [rbp+57h+var_C0], 0
0x14006b00c  mov     qword ptr [rbp+57h+var_C0+8], rax
0x14006b010  mov     [rbp+57h+HashTable], rcx
0x14006b014  mov     eax, [rcx+90h]
0x14006b01a  test    al, 0Ch
0x14006b01c  jz      short loc_14006B02E
0x14006b01e  cmp     dword ptr [rbx+100h], 1
0x14006b025  jnz     short loc_14006B02E
0x14006b027  or      byte ptr [rbx+0BAh], 8
0x14006b02e  mov     rax, [rcx+8]
0x14006b032  mov     [rbp+57h+Buf2], rax
0x14006b036  mov     [rbp+57h+arg_8], rax
0x14006b03a  test    rax, rax
0x14006b03d  jz      loc_14006B29D
0x14006b043  mov     rdi, [rax]
0x14006b046  mov     qword ptr [rax], 0
0x14006b04d  mov     [rcx+8], rax
0x14006b051  mov     rcx, rbx
0x14006b054  call    IppCreateStrongClonePacket
0x14006b059  mov     rcx, [rbp+57h+HashTable]
0x14006b05d  mov     rdx, rax
0x14006b060  mov     rax, [rbp+57h+arg_8]
0x14006b064  mov     r8, [rbp+57h+Buf2]
0x14006b068  mov     [rax], rdi
0x14006b06b  mov     [rcx+8], r8
0x14006b06f  test    rdx, rdx
0x14006b072  jz      loc_14006B3E2
0x14006b078  xorps   xmm0, xmm0
0x14006b07b  movups  xmmword ptr [rdx+10h], xmm0
0x14006b07f  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x14006b083  mov     [rcx], rdx
0x14006b086  mov     rcx, [rbp+57h+HashTable]
0x14006b08a  mov     qword ptr [rbp+57h+var_C0+8], rdx
0x14006b08e  mov     rax, [rax]
0x14006b091  jmp     short loc_14006B036
0x14006b093  mov     rcx, [rbx+8]
0x14006b097  call    IppGetPacketCount
0x14006b09c  mov     ecx, gs:1A4h
0x14006b0a4  lea     rdx, [rcx+rcx*2]
0x14006b0a8  shl     rdx, 6
0x14006b0ac  add     rdx, [rsi+4F28h]
0x14006b0b3  mov     ecx, [rdx+98h]
0x14006b0b9  add     eax, ecx
0x14006b0bb  mov     [rdx+98h], eax
  ... truncated ...
```
