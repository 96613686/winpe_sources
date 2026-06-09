# TcpInsertSynTcb

- ea: `0x1400fd444`
- end: `0x1400fd963`
- name: `TcpInsertSynTcb`
- size: `1311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400fc614`

## callees

- `0x140009590`
- `0x140063db0`
- `0x1400d1120`
- `0x1400fd444`
- `0x1400fdd30`
- `0x14012970c`
- `0x140164010`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400fd73e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400fd73e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400fd75b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400fd7af`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400fd7d0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400fd75b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400fd7af`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400fd7d0`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400fd4da`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400fd512`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400fd4da`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400fd512`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd7fe`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd84e`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd8b2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd902`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd7fe`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd84e`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd8b2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400fd902`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400fd5dc`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400fd66d`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400fd6fe`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400fd5dc`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400fd66d`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400fd6fe`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400fd574`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400fd601`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400fd692`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400fd574`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400fd601`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400fd692`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd4ea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd522`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd72b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd778`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd822`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd85e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd8d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd912`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd4ea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd522`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd72b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd778`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd822`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd85e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd8d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400fd912`

## pseudocode

```c
__int64 __fastcall TcpInsertSynTcb(__int64 a1, char a2, _BYTE *a3)
{
  ULONG_PTR v3; // r15
  _WORD *v4; // r13
  char v6; // di
  ULONG_PTR v8; // rax
  unsigned int LockArray_high; // r14d
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // r8
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 v16; // rcx
  struct _LIST_ENTRY *Blink; // r8
  PRTL_DYNAMIC_HASH_TABLE_ENTRY j; // rax
  __int64 v19; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY k; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v21; // rdi
  __int64 v22; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v24; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-60h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT v33; // [rsp+38h] [rbp-48h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+50h] [rbp-30h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT v35; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v36; // [rsp+C0h] [rbp+40h]
  char v37; // [rsp+C8h] [rbp+48h]
  ULONG_PTR Signature; // [rsp+D8h] [rbp+58h]

  v37 = a2;
  v3 = *(_QWORD *)(a1 + 32);
  v4 = (_WORD *)(a1 + 134);
  v6 = a2;
  v8 = *(_QWORD *)(a1 + 56);
  memset(&LockHandle, 0, sizeof(LockHandle));
  Signature = v8;
  memset(&v33, 0, sizeof(v33));
  memset(&Context, 0, sizeof(Context));
  memset(&v35, 0, sizeof(v35));
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v36 = LockArray_high;
  while ( 2 )
  {
    v10 = TcpGetAndWriteLockPartitionAtDpcLevel(v3, &LockHandle, a3);
    v11 = v10;
    if ( v6 )
    {
      RtlRemoveEntryHashTable(
        (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v10 + 8) + 80LL),
        (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 16),
        0);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v13 = TcpGetAndWriteLockPartitionAtDpcLevel(Signature, &LockHandle, v12);
      RtlRemoveEntryHashTable(
        (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v13 + 16) + 80LL),
        (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 40),
        0);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      *(_BYTE *)(a1 + 138) &= ~1u;
      *(_BYTE *)(a1 + 136) = 2;
      v37 = 0;
      v11 = TcpGetAndWriteLockPartitionAtDpcLevel(v3, &LockHandle, v14);
    }
    else if ( LockArray_high == *(_DWORD *)(v10 + 144) )
    {
      v29 = (struct _RTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(v10 + 8) + 120LL);
      *a3 = 0;
      RtlInsertEntryHashTable(v29, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 16), v3, 0);
      TcpCountSynRcvdInPartition(v11, 0);
      *(_DWORD *)(v11 + 144) = 4096;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v31 = TcpGetAndWriteLockPartitionAtDpcLevel(Signature, &LockHandle, v30);
      RtlInsertEntryHashTable(
        (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v31 + 16) + 120LL),
        (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 40),
        Signature,
        0);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      *(_BYTE *)(a1 + 138) |= 1u;
      ++*(_DWORD *)(192LL * LockArray_high + *(_QWORD *)(*(_QWORD *)(a1 + 72) + 128LL) + 76);
      return 0;
    }
    *(_OWORD *)&Context.ChainHead = 0;
    for ( i = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v11 + 8), v3, &Context);
          i;
          i = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v11 + 8), &Context) )
    {
      if ( *v4 == HIWORD(i[2].Signature) && *(_WORD *)(a1 + 132) == WORD2(i[2].Signature) )
      {
        v16 = *(_QWORD *)(a1 + 72);
        if ( (struct _LIST_ENTRY *)v16 == i[-1].Linkage.Flink )
        {
          Blink = i[-1].Linkage.Blink;
          if ( *(struct _LIST_ENTRY **)(*(_QWORD *)(a1 + 80) + 16LL) == Blink->Flink[1].Flink )
          {
            if ( (unsigned __int8)INET_ADDR_EQUAL(*(unsigned __int16 *)(v16 + 24), a1 + 112, Blink[1].Flink) )
            {
LABEL_33:
              KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
              return 3221225994LL;
            }
          }
        }
      }
    }
    *(_OWORD *)&v33.ChainHead = 0;
    for ( j = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v11 + 8) + 120LL), v3, &v33);
          j;
          j = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v11 + 8) + 120LL), &v33) )
    {
      if ( *v4 == HIWORD(j[4].Signature) && *(_WORD *)(a1 + 132) == WORD2(j[4].Signature) )
      {
        v19 = *(_QWORD *)(a1 + 72);
        if ( (struct _LIST_ENTRY *)v19 == j[2].Linkage.Blink
          && *(_QWORD *)(*(_QWORD *)(a1 + 80) + 16LL) == *(_QWORD *)(j[2].Signature + 16)
          && (unsigned __int8)INET_ADDR_EQUAL(*(unsigned __int16 *)(v19 + 24), a1 + 112, &j[4]) )
        {
          goto LABEL_33;
        }
      }
    }
    *(_OWORD *)&v35.ChainHead = 0;
    for ( k = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v11 + 8) + 40LL), v3, &v35);
          ;
          k = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v11 + 8) + 40LL), &v35) )
    {
      v21 = k;
      if ( !k )
      {
        v25 = (struct _RTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)(v11 + 8) + 120LL);
        *a3 = 0;
        RtlInsertEntryHashTable(v25, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 16), v3, &v33);
        TcpCountSynRcvdInPartition(v11, 0);
        *(_DWORD *)(v11 + 144) = 4096;
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        v27 = TcpGetAndWriteLockPartitionAtDpcLevel(Signature, &LockHandle, v26);
        RtlInsertEntryHashTable(
          (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v27 + 16) + 120LL),
          (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 40),
          Signature,
          0);
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        LODWORD(v28) = HIDWORD(KeGetPcr()[1].LockArray);
        ++*(_DWORD *)(192 * v28 + *(_QWORD *)(*(_QWORD *)(a1 + 72) + 128LL) + 76);
        goto LABEL_39;
      }
      if ( *v4 == LOWORD(k[3].Linkage.Blink) && *(_WORD *)(a1 + 132) == HIWORD(k[3].Linkage.Flink) )
      {
        v22 = *(_QWORD *)(a1 + 72);
        if ( (struct _LIST_ENTRY *)v22 == k[2].Linkage.Flink
          && *(_QWORD *)(*(_QWORD *)(a1 + 80) + 16LL) == *(_QWORD *)(k[3].Signature + 16)
          && (unsigned __int8)INET_ADDR_EQUAL(*(unsigned __int16 *)(v22 + 24), a1 + 112, &k[4]) )
        {
          break;
        }
      }
    }
    if ( _InterlockedIncrement64((volatile signed __int64 *)&v21[2].Signature) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&v21[2].Linkage.Blink);
    if ( !BYTE1(v21[3].Linkage.Flink) )
    {
      TcpDereferenceTimeWaitTcb(v21);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v21[2].Linkage.Blink);
      v6 = v37;
      LockArray_high = v36;
      continue;
    }
    break;
  }
  if ( !(unsigned __int8)TcpCanAssassinateTimeWaitTcb(v21, *(unsigned int *)(a1 + 144), a1 + 140) )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v21[2].Linkage.Blink);
    TcpDereferenceTimeWaitTcb(v21);
    return 3221225994LL;
  }
  TcpReplaceTimeWaitTcbWithSynTcb(v24, a1);
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v21[2].Linkage.Blink);
  TcpDereferenceTimeWaitTcb(v21);
  *a3 = 1;
LABEL_39:
  *(_BYTE *)(a1 + 138) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x1400fd444  mov     [rsp-38h+arg_10], rbx
0x1400fd449  mov     [rsp-38h+arg_8], dl
0x1400fd44d  push    rbp
0x1400fd44e  push    rsi
0x1400fd44f  push    rdi
0x1400fd450  push    r12
0x1400fd452  push    r13
0x1400fd454  push    r14
0x1400fd456  push    r15
0x1400fd458  mov     rbp, rsp
0x1400fd45b  sub     rsp, 80h
0x1400fd462  mov     r15, [rcx+20h]
0x1400fd466  lea     r13, [rcx+86h]
0x1400fd46d  xor     eax, eax
0x1400fd46f  xorps   xmm0, xmm0
0x1400fd472  xorps   xmm1, xmm1
0x1400fd475  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400fd479  mov     [rbp+var_48.Signature], rax
0x1400fd47d  mov     r12, r8
0x1400fd480  mov     [rbp+Context.Signature], rax
0x1400fd484  mov     dil, dl
0x1400fd487  mov     [rbp+var_18.Signature], rax
0x1400fd48b  mov     rbx, rcx
0x1400fd48e  mov     rax, [rcx+38h]
0x1400fd492  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400fd496  mov     [rbp+Signature], rax
0x1400fd49a  movups  xmmword ptr [rbp+var_48.ChainHead], xmm1
0x1400fd49e  movups  xmmword ptr [rbp+Context.ChainHead], xmm0
0x1400fd4a2  movups  xmmword ptr [rbp+var_18.ChainHead], xmm1
0x1400fd4a6  mov     r14d, gs:1A4h
0x1400fd4af  mov     [rbp+arg_0], r14d
0x1400fd4b3  lea     rdx, [rbp+LockHandle]
0x1400fd4b7  mov     rcx, r15
0x1400fd4ba  call    TcpGetAndWriteLockPartitionAtDpcLevel
0x1400fd4bf  mov     rsi, rax
0x1400fd4c2  test    dil, dil
0x1400fd4c5  jz      loc_1400FD551
0x1400fd4cb  mov     rcx, [rax+8]
0x1400fd4cf  lea     rdx, [rbx+10h]; Entry
0x1400fd4d3  add     rcx, 50h ; 'P'; HashTable
0x1400fd4d7  xor     r8d, r8d; Context
0x1400fd4da  call    cs:__imp_RtlRemoveEntryHashTable
0x1400fd4e1  nop     dword ptr [rax+rax+00h]
0x1400fd4e6  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd4ea  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd4f1  nop     dword ptr [rax+rax+00h]
0x1400fd4f6  mov     rcx, [rbp+Signature]
0x1400fd4fa  lea     rdx, [rbp+LockHandle]
0x1400fd4fe  call    TcpGetAndWriteLockPartitionAtDpcLevel
0x1400fd503  lea     rdx, [rbx+28h]; Entry
0x1400fd507  xor     r8d, r8d; Context
0x1400fd50a  mov     rcx, [rax+10h]
0x1400fd50e  add     rcx, 50h ; 'P'; HashTable
0x1400fd512  call    cs:__imp_RtlRemoveEntryHashTable
0x1400fd519  nop     dword ptr [rax+rax+00h]
0x1400fd51e  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd522  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd529  nop     dword ptr [rax+rax+00h]
0x1400fd52e  and     byte ptr [rbx+8Ah], 0FEh
0x1400fd535  lea     rdx, [rbp+LockHandle]
0x1400fd539  mov     rcx, r15
0x1400fd53c  mov     byte ptr [rbx+88h], 2
0x1400fd543  mov     [rbp+arg_8], 0
0x1400fd547  call    TcpGetAndWriteLockPartitionAtDpcLevel
0x1400fd54c  mov     rsi, rax
0x1400fd54f  jmp     short loc_1400FD55E
0x1400fd551  cmp     r14d, [rax+90h]
0x1400fd558  jz      loc_1400FD89B
0x1400fd55e  xorps   xmm0, xmm0
0x1400fd561  lea     r8, [rbp+Context]; Context
0x1400fd565  movdqu  xmmword ptr [rbp+Context.ChainHead], xmm0
0x1400fd56a  mov     rcx, [rsi+8]; HashTable
0x1400fd56e  mov     rdx, r15; Signature
0x1400fd571  mov     r14, r13
0x1400fd574  call    cs:__imp_RtlLookupEntryHashTable
0x1400fd57b  nop     dword ptr [rax+rax+00h]
0x1400fd580  test    rax, rax
0x1400fd583  jz      short loc_1400FD5EA
0x1400fd585  movzx   ecx, word ptr [rax+46h]
0x1400fd589  cmp     [r14], cx
0x1400fd58d  jnz     short loc_1400FD5D4
0x1400fd58f  movzx   ecx, word ptr [rax+44h]
0x1400fd593  cmp     [rbx+84h], cx
0x1400fd59a  jnz     short loc_1400FD5D4
0x1400fd59c  mov     rcx, [rbx+48h]
0x1400fd5a0  cmp     rcx, [rax-18h]
0x1400fd5a4  jnz     short loc_1400FD5D4
0x1400fd5a6  mov     r8, [rax-10h]
0x1400fd5aa  mov     r9, [rbx+50h]
0x1400fd5ae  mov     rax, [r8]
0x1400fd5b1  mov     rdx, [rax+10h]
0x1400fd5b5  cmp     [r9+10h], rdx
0x1400fd5b9  jnz     short loc_1400FD5D4
0x1400fd5bb  mov     r8, [r8+10h]
0x1400fd5bf  lea     rdx, [rbx+70h]
0x1400fd5c3  movzx   ecx, word ptr [rcx+18h]
0x1400fd5c7  call    INET_ADDR_EQUAL
0x1400fd5cc  test    al, al
0x1400fd5ce  jnz     loc_1400FD774
0x1400fd5d4  mov     rcx, [rsi+8]; HashTable
0x1400fd5d8  lea     rdx, [rbp+Context]; Context
0x1400fd5dc  call    cs:__imp_RtlGetNextEntryHashTable
0x1400fd5e3  nop     dword ptr [rax+rax+00h]
0x1400fd5e8  jmp     short loc_1400FD580
0x1400fd5ea  xorps   xmm0, xmm0
0x1400fd5ed  lea     r8, [rbp+var_48]; Context
0x1400fd5f1  movdqu  xmmword ptr [rbp+var_48.ChainHead], xmm0
0x1400fd5f6  mov     rcx, [rsi+8]
0x1400fd5fa  mov     rdx, r15; Signature
0x1400fd5fd  add     rcx, 78h ; 'x'; HashTable
0x1400fd601  call    cs:__imp_RtlLookupEntryHashTable
0x1400fd608  nop     dword ptr [rax+rax+00h]
0x1400fd60d  mov     r9, rax
0x1400fd610  test    rax, rax
0x1400fd613  jz      short loc_1400FD67B
0x1400fd615  movzx   ecx, word ptr [rax+76h]
0x1400fd619  cmp     [r14], cx
0x1400fd61d  jnz     short loc_1400FD661
0x1400fd61f  movzx   ecx, word ptr [rax+74h]
0x1400fd623  cmp     [rbx+84h], cx
0x1400fd62a  jnz     short loc_1400FD661
0x1400fd62c  mov     rcx, [rbx+48h]
0x1400fd630  cmp     rcx, [rax+38h]
0x1400fd634  jnz     short loc_1400FD661
0x1400fd636  mov     rax, [rax+40h]
0x1400fd63a  mov     r8, [rbx+50h]
0x1400fd63e  mov     rdx, [rax+10h]
0x1400fd642  cmp     [r8+10h], rdx
0x1400fd646  jnz     short loc_1400FD661
0x1400fd648  movzx   ecx, word ptr [rcx+18h]
0x1400fd64c  lea     r8, [r9+60h]
0x1400fd650  lea     rdx, [rbx+70h]
0x1400fd654  call    INET_ADDR_EQUAL
0x1400fd659  test    al, al
0x1400fd65b  jnz     loc_1400FD774
0x1400fd661  mov     rcx, [rsi+8]
0x1400fd665  lea     rdx, [rbp+var_48]; Context
0x1400fd669  add     rcx, 78h ; 'x'; HashTable
0x1400fd66d  call    cs:__imp_RtlGetNextEntryHashTable
0x1400fd674  nop     dword ptr [rax+rax+00h]
0x1400fd679  jmp     short loc_1400FD60D
0x1400fd67b  xorps   xmm0, xmm0
0x1400fd67e  lea     r8, [rbp+var_18]; Context
0x1400fd682  movdqu  xmmword ptr [rbp+var_18.ChainHead], xmm0
0x1400fd687  mov     rcx, [rsi+8]
0x1400fd68b  mov     rdx, r15; Signature
0x1400fd68e  add     rcx, 28h ; '('; HashTable
0x1400fd692  call    cs:__imp_RtlLookupEntryHashTable
0x1400fd699  nop     dword ptr [rax+rax+00h]
0x1400fd69e  mov     rdi, rax
0x1400fd6a1  test    rax, rax
0x1400fd6a4  jz      loc_1400FD7E6
0x1400fd6aa  movzx   ecx, word ptr [rax+50h]
0x1400fd6ae  cmp     [r14], cx
0x1400fd6b2  jnz     short loc_1400FD6F2
0x1400fd6b4  movzx   ecx, word ptr [rax+4Eh]
0x1400fd6b8  cmp     [rbx+84h], cx
0x1400fd6bf  jnz     short loc_1400FD6F2
0x1400fd6c1  mov     rcx, [rbx+48h]
0x1400fd6c5  cmp     rcx, [rax+30h]
0x1400fd6c9  jnz     short loc_1400FD6F2
0x1400fd6cb  mov     rax, [rax+58h]
0x1400fd6cf  mov     rdx, [rbx+50h]
0x1400fd6d3  mov     rax, [rax+10h]
0x1400fd6d7  cmp     [rdx+10h], rax
0x1400fd6db  jnz     short loc_1400FD6F2
0x1400fd6dd  movzx   ecx, word ptr [rcx+18h]
0x1400fd6e1  lea     r8, [rdi+60h]
0x1400fd6e5  lea     rdx, [rbx+70h]
0x1400fd6e9  call    INET_ADDR_EQUAL
0x1400fd6ee  test    al, al
0x1400fd6f0  jnz     short loc_1400FD70C
0x1400fd6f2  mov     rcx, [rsi+8]
0x1400fd6f6  lea     rdx, [rbp+var_18]; Context
0x1400fd6fa  add     rcx, 28h ; '('; HashTable
0x1400fd6fe  call    cs:__imp_RtlGetNextEntryHashTable
0x1400fd705  nop     dword ptr [rax+rax+00h]
0x1400fd70a  jmp     short loc_1400FD69E
0x1400fd70c  mov     eax, 1
0x1400fd711  lock xadd [rdi+40h], rax
0x1400fd717  inc     rax
0x1400fd71a  cmp     rax, 1
0x1400fd71e  jg      short loc_1400FD727
0x1400fd720  mov     ecx, 0Eh
0x1400fd725  int     29h; Win8: RtlFailFast(ecx)
0x1400fd727  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd72b  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd732  nop     dword ptr [rax+rax+00h]
0x1400fd737  lea     rsi, [rdi+38h]
0x1400fd73b  mov     rcx, rsi; SpinLock
0x1400fd73e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400fd745  nop     dword ptr [rax+rax+00h]
0x1400fd74a  cmp     byte ptr [rdi+49h], 0
0x1400fd74e  mov     rcx, rdi
0x1400fd751  jnz     short loc_1400FD78E
0x1400fd753  call    TcpDereferenceTimeWaitTcb
0x1400fd758  mov     rcx, rsi; SpinLock
0x1400fd75b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400fd762  nop     dword ptr [rax+rax+00h]
0x1400fd767  mov     dil, [rbp+arg_8]
0x1400fd76b  mov     r14d, [rbp+arg_0]
0x1400fd76f  jmp     loc_1400FD4B3
0x1400fd774  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd778  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd77f  nop     dword ptr [rax+rax+00h]
0x1400fd784  mov     eax, 0C000020Ah
0x1400fd789  jmp     loc_1400FD947
0x1400fd78e  mov     edx, [rbx+90h]
0x1400fd794  lea     r8, [rbx+8Ch]
0x1400fd79b  call    TcpCanAssassinateTimeWaitTcb
0x1400fd7a0  test    al, al
0x1400fd7a2  jz      short loc_1400FD7CD
0x1400fd7a4  mov     rdx, rbx
0x1400fd7a7  call    TcpReplaceTimeWaitTcbWithSynTcb
0x1400fd7ac  mov     rcx, rsi; SpinLock
0x1400fd7af  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400fd7b6  nop     dword ptr [rax+rax+00h]
0x1400fd7bb  mov     rcx, rdi
0x1400fd7be  call    TcpDereferenceTimeWaitTcb
0x1400fd7c3  mov     byte ptr [r12], 1
0x1400fd7c8  jmp     loc_1400FD88F
0x1400fd7cd  mov     rcx, rsi; SpinLock
0x1400fd7d0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400fd7d7  nop     dword ptr [rax+rax+00h]
0x1400fd7dc  mov     rcx, rdi
0x1400fd7df  call    TcpDereferenceTimeWaitTcb
0x1400fd7e4  jmp     short loc_1400FD784
0x1400fd7e6  mov     rcx, [rsi+8]
0x1400fd7ea  lea     rdx, [rbx+10h]; Entry
0x1400fd7ee  add     rcx, 78h ; 'x'; HashTable
0x1400fd7f2  mov     byte ptr [r12], 0
0x1400fd7f7  lea     r9, [rbp+var_48]; Context
0x1400fd7fb  mov     r8, r15; Signature
0x1400fd7fe  call    cs:__imp_RtlInsertEntryHashTable
0x1400fd805  nop     dword ptr [rax+rax+00h]
0x1400fd80a  xor     edx, edx
0x1400fd80c  mov     rcx, rsi
0x1400fd80f  call    TcpCountSynRcvdInPartition
0x1400fd814  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd818  mov     dword ptr [rsi+90h], 1000h
0x1400fd822  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd829  nop     dword ptr [rax+rax+00h]
0x1400fd82e  mov     rcx, [rbp+Signature]
0x1400fd832  lea     rdx, [rbp+LockHandle]
0x1400fd836  call    TcpGetAndWriteLockPartitionAtDpcLevel
0x1400fd83b  mov     r8, [rbp+Signature]; Signature
0x1400fd83f  lea     rdx, [rbx+28h]; Entry
0x1400fd843  xor     r9d, r9d; Context
0x1400fd846  mov     rcx, [rax+10h]
0x1400fd84a  add     rcx, 78h ; 'x'; HashTable
0x1400fd84e  call    cs:__imp_RtlInsertEntryHashTable
0x1400fd855  nop     dword ptr [rax+rax+00h]
0x1400fd85a  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd85e  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd865  nop     dword ptr [rax+rax+00h]
0x1400fd86a  mov     eax, gs:1A4h
0x1400fd872  lea     rdx, [rax+rax*2]
0x1400fd876  mov     rax, [rbx+48h]
0x1400fd87a  shl     rdx, 6
0x1400fd87e  mov     rcx, [rax+80h]
0x1400fd885  mov     eax, [rdx+rcx+4Ch]
0x1400fd889  inc     eax
0x1400fd88b  mov     [rdx+rcx+4Ch], eax
0x1400fd88f  or      byte ptr [rbx+8Ah], 1
0x1400fd896  jmp     loc_1400FD945
0x1400fd89b  mov     rcx, [rax+8]
0x1400fd89f  lea     rdx, [rbx+10h]; Entry
0x1400fd8a3  add     rcx, 78h ; 'x'; HashTable
0x1400fd8a7  mov     byte ptr [r12], 0
0x1400fd8ac  xor     r9d, r9d; Context
0x1400fd8af  mov     r8, r15; Signature
0x1400fd8b2  call    cs:__imp_RtlInsertEntryHashTable
0x1400fd8b9  nop     dword ptr [rax+rax+00h]
0x1400fd8be  xor     edx, edx
0x1400fd8c0  mov     rcx, rsi
0x1400fd8c3  call    TcpCountSynRcvdInPartition
0x1400fd8c8  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd8cc  mov     dword ptr [rsi+90h], 1000h
0x1400fd8d6  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd8dd  nop     dword ptr [rax+rax+00h]
0x1400fd8e2  mov     rcx, [rbp+Signature]
0x1400fd8e6  lea     rdx, [rbp+LockHandle]
0x1400fd8ea  call    TcpGetAndWriteLockPartitionAtDpcLevel
0x1400fd8ef  mov     r8, [rbp+Signature]; Signature
0x1400fd8f3  lea     rdx, [rbx+28h]; Entry
0x1400fd8f7  xor     r9d, r9d; Context
0x1400fd8fa  mov     rcx, [rax+10h]
0x1400fd8fe  add     rcx, 78h ; 'x'; HashTable
0x1400fd902  call    cs:__imp_RtlInsertEntryHashTable
0x1400fd909  nop     dword ptr [rax+rax+00h]
0x1400fd90e  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400fd912  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400fd919  nop     dword ptr [rax+rax+00h]
0x1400fd91e  or      byte ptr [rbx+8Ah], 1
0x1400fd925  mov     eax, r14d
0x1400fd928  lea     rdx, [rax+rax*2]
0x1400fd92c  mov     rax, [rbx+48h]
0x1400fd930  shl     rdx, 6
0x1400fd934  mov     rcx, [rax+80h]
0x1400fd93b  mov     eax, [rdx+rcx+4Ch]
  ... truncated ...
```
