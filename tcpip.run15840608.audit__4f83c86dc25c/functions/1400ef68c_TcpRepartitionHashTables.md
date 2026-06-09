# TcpRepartitionHashTables

- ea: `0x1400ef68c`
- end: `0x1400ef93b`
- name: `TcpRepartitionHashTables`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400eeb60`

## callees

- `0x140009410`
- `0x1400a2910`
- `0x1400ef68c`
- `0x1400ef944`
- `0x1400efa38`
- `0x1400efb38`
- `0x1400efc88`
- `0x1400fdd30`
- `0x14012e1d0`

## import_xrefs

- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400ef76b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400ef7d9`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400ef83f`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400ef76b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400ef7d9`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400ef83f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400ef704`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400ef7ba`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400ef820`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400ef704`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400ef7ba`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400ef820`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400ef6f1`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400ef7a7`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400ef80d`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400ef6f1`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400ef7a7`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400ef80d`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400ef73c`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400ef90c`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401d3243`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400ef73c`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400ef90c`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401d3243`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400ef756`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400ef92a`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401d3261`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400ef756`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1400ef92a`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401d3261`

## pseudocode

```c
__int64 __fastcall TcpRepartitionHashTables(unsigned __int16 a1)
{
  unsigned __int16 v1; // di
  __int64 result; // rax
  __int64 v4; // r13
  __int64 v5; // r15
  struct _RTL_DYNAMIC_HASH_TABLE *v6; // rsi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v7; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rbx
  PRTL_DYNAMIC_HASH_TABLE *PartitionFromKey; // r14
  struct _RTL_DYNAMIC_HASH_TABLE *v10; // r14
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v11; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v12; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v13; // rsi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v14; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  _QWORD *v19; // rsi
  _QWORD *v20; // r14
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+20h] [rbp-58h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR v22; // [rsp+48h] [rbp-30h] BYREF

  v1 = 0;
  result = 0;
  if ( a1 )
  {
    v4 = 0;
    do
    {
      TcpRepartitionTcbHashTable(v1, 0);
      v5 = 192 * v4;
      memset(&Enumerator, 0, sizeof(Enumerator));
      v6 = (struct _RTL_DYNAMIC_HASH_TABLE *)*((_QWORD *)PartitionTable + 24 * v4 + 2);
      RtlInitEnumerationHashTable(v6, &Enumerator);
      while ( 1 )
      {
        v7 = RtlEnumerateEntryHashTable(v6, &Enumerator);
        v8 = v7;
        if ( !v7 )
          break;
        PartitionFromKey = (PRTL_DYNAMIC_HASH_TABLE *)TcpGetPartitionFromKey(v7->Signature);
        if ( PartitionFromKey != (PRTL_DYNAMIC_HASH_TABLE *)((char *)PartitionTable + v5) )
        {
          RtlRemoveEntryHashTable(v6, v8, 0);
          RtlInsertEntryHashTable(PartitionFromKey[2], v8, v8->Signature, 0);
        }
      }
      RtlEndEnumerationHashTable(v6, &Enumerator);
      TcpRepartitionTupleTable(v1);
      memset(&Enumerator, 0, sizeof(Enumerator));
      v10 = (struct _RTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)((char *)PartitionTable + v5 + 8) + 120LL);
      RtlInitEnumerationHashTable(v10, &Enumerator);
      while ( 1 )
      {
        v11 = RtlEnumerateEntryHashTable(v10, &Enumerator);
        v12 = v11;
        if ( !v11 )
          break;
        v19 = (_QWORD *)TcpGetPartitionFromKey(v11->Signature);
        if ( v19 != (_QWORD *)((char *)PartitionTable + v5) )
        {
          LOBYTE(v18) = BYTE3(v12[5].Linkage.Flink) & 1;
          TcpDropSynRcvdFromPartition((char *)PartitionTable + v5, v18, 0);
          TcpCountSynRcvdInPartition(v19, 0);
          if ( (BYTE3(v12[5].Linkage.Flink) & 1) != 0 )
            TcpCountSynRcvdRetryInPartition(v19);
          RtlRemoveEntryHashTable(v10, v12, 0);
          RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v19[1] + 120LL), v12, v12->Signature, 0);
        }
      }
      RtlEndEnumerationHashTable(v10, &Enumerator);
      memset(&v22, 0, sizeof(v22));
      v13 = (struct _RTL_DYNAMIC_HASH_TABLE *)(*(_QWORD *)((char *)PartitionTable + v5 + 16) + 120LL);
      RtlInitEnumerationHashTable(v13, &v22);
      while ( 1 )
      {
        v14 = RtlEnumerateEntryHashTable(v13, &v22);
        v15 = v14;
        if ( !v14 )
          break;
        v20 = (_QWORD *)TcpGetPartitionFromKey(v14->Signature);
        if ( v20 != (_QWORD *)((char *)PartitionTable + v5) )
        {
          RtlRemoveEntryHashTable(v13, v15, 0);
          RtlInsertEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v20[2] + 120LL), v15, v15->Signature, 0);
        }
      }
      RtlEndEnumerationHashTable(v13, &v22);
      TcpRepartitionStandbyTcbHashTable(v1, 0);
      LOBYTE(v16) = 1;
      TcpRepartitionStandbyTcbHashTable(v1, v16);
      TcpRepartitionTimeWaitTcbHashTable(v1, 0);
      LOBYTE(v17) = 1;
      result = TcpRepartitionTimeWaitTcbHashTable(v1++, v17);
      ++v4;
    }
    while ( v1 < a1 );
  }
  return result;
}

```

## disassembly

```asm
0x1400ef68c  push    rbp
0x1400ef68e  push    rbx
0x1400ef68f  push    rsi
0x1400ef690  push    rdi
0x1400ef691  push    r12
0x1400ef693  push    r13
0x1400ef695  push    r14
0x1400ef697  push    r15
0x1400ef699  mov     rbp, rsp
0x1400ef69c  sub     rsp, 78h
0x1400ef6a0  xor     edi, edi
0x1400ef6a2  xor     eax, eax
0x1400ef6a4  movzx   r12d, cx
0x1400ef6a8  cmp     ax, cx
0x1400ef6ab  jnb     loc_1400EF883
0x1400ef6b1  xor     r13d, r13d
0x1400ef6b4  xor     edx, edx
0x1400ef6b6  movzx   ecx, di
0x1400ef6b9  call    TcpRepartitionTcbHashTable
0x1400ef6be  xor     eax, eax
0x1400ef6c0  lea     r15, ds:0[r13*2]
0x1400ef6c8  xorps   xmm0, xmm0
0x1400ef6cb  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x1400ef6cf  mov     rax, cs:PartitionTable
0x1400ef6d6  lea     rdx, [rbp+Enumerator]; Enumerator
0x1400ef6da  add     r15, r13
0x1400ef6dd  shl     r15, 6
0x1400ef6e1  movups  xmmword ptr [rbp+Enumerator], xmm0
0x1400ef6e5  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x1400ef6e9  mov     rsi, [r15+rax+10h]
0x1400ef6ee  mov     rcx, rsi; HashTable
0x1400ef6f1  call    cs:__imp_RtlInitEnumerationHashTable
0x1400ef6f8  nop     dword ptr [rax+rax+00h]
0x1400ef6fd  lea     rdx, [rbp+Enumerator]; Enumerator
0x1400ef701  mov     rcx, rsi; HashTable
0x1400ef704  call    cs:__imp_RtlEnumerateEntryHashTable
0x1400ef70b  nop     dword ptr [rax+rax+00h]
0x1400ef710  mov     rbx, rax
0x1400ef713  test    rax, rax
0x1400ef716  jz      short loc_1400EF764
0x1400ef718  mov     rcx, [rax+10h]
0x1400ef71c  call    TcpGetPartitionFromKey
0x1400ef721  mov     rdx, cs:PartitionTable
0x1400ef728  mov     r14, rax
0x1400ef72b  add     rdx, r15
0x1400ef72e  cmp     rax, rdx
0x1400ef731  jz      short loc_1400EF6FD
0x1400ef733  xor     r8d, r8d; Context
0x1400ef736  mov     rdx, rbx; Entry
0x1400ef739  mov     rcx, rsi; HashTable
0x1400ef73c  call    cs:__imp_RtlRemoveEntryHashTable
0x1400ef743  nop     dword ptr [rax+rax+00h]
0x1400ef748  mov     r8, [rbx+10h]; Signature
0x1400ef74c  xor     r9d, r9d; Context
0x1400ef74f  mov     rcx, [r14+10h]; HashTable
0x1400ef753  mov     rdx, rbx; Entry
0x1400ef756  call    cs:__imp_RtlInsertEntryHashTable
0x1400ef75d  nop     dword ptr [rax+rax+00h]
0x1400ef762  jmp     short loc_1400EF6FD
0x1400ef764  lea     rdx, [rbp+Enumerator]; Enumerator
0x1400ef768  mov     rcx, rsi; HashTable
0x1400ef76b  call    cs:__imp_RtlEndEnumerationHashTable
0x1400ef772  nop     dword ptr [rax+rax+00h]
0x1400ef777  movzx   ecx, di
0x1400ef77a  call    TcpRepartitionTupleTable
0x1400ef77f  xor     eax, eax
0x1400ef781  lea     rdx, [rbp+Enumerator]; Enumerator
0x1400ef785  xorps   xmm0, xmm0
0x1400ef788  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x1400ef78c  mov     rax, cs:PartitionTable
0x1400ef793  movups  xmmword ptr [rbp+Enumerator], xmm0
0x1400ef797  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x1400ef79b  mov     r14, [r15+rax+8]
0x1400ef7a0  add     r14, 78h ; 'x'
0x1400ef7a4  mov     rcx, r14; HashTable
0x1400ef7a7  call    cs:__imp_RtlInitEnumerationHashTable
0x1400ef7ae  nop     dword ptr [rax+rax+00h]
0x1400ef7b3  lea     rdx, [rbp+Enumerator]; Enumerator
0x1400ef7b7  mov     rcx, r14; HashTable
0x1400ef7ba  call    cs:__imp_RtlEnumerateEntryHashTable
0x1400ef7c1  nop     dword ptr [rax+rax+00h]
0x1400ef7c6  mov     rbx, rax
0x1400ef7c9  test    rax, rax
0x1400ef7cc  jnz     loc_1400EF895
0x1400ef7d2  lea     rdx, [rbp+Enumerator]; Enumerator
0x1400ef7d6  mov     rcx, r14; HashTable
0x1400ef7d9  call    cs:__imp_RtlEndEnumerationHashTable
0x1400ef7e0  nop     dword ptr [rax+rax+00h]
0x1400ef7e5  xor     eax, eax
0x1400ef7e7  lea     rdx, [rbp+var_30]; Enumerator
0x1400ef7eb  xorps   xmm0, xmm0
0x1400ef7ee  mov     qword ptr [rbp+var_30.BucketIndex], rax
0x1400ef7f2  mov     rax, cs:PartitionTable
0x1400ef7f9  movups  xmmword ptr [rbp+var_30], xmm0
0x1400ef7fd  movups  xmmword ptr [rbp+var_30+10h], xmm0
0x1400ef801  mov     rsi, [r15+rax+10h]
0x1400ef806  add     rsi, 78h ; 'x'
0x1400ef80a  mov     rcx, rsi; HashTable
0x1400ef80d  call    cs:__imp_RtlInitEnumerationHashTable
0x1400ef814  nop     dword ptr [rax+rax+00h]
0x1400ef819  lea     rdx, [rbp+var_30]; Enumerator
0x1400ef81d  mov     rcx, rsi; HashTable
0x1400ef820  call    cs:__imp_RtlEnumerateEntryHashTable
0x1400ef827  nop     dword ptr [rax+rax+00h]
0x1400ef82c  mov     rbx, rax
0x1400ef82f  test    rax, rax
0x1400ef832  jnz     loc_1400EF8E4
0x1400ef838  lea     rdx, [rbp+var_30]; Enumerator
0x1400ef83c  mov     rcx, rsi; HashTable
0x1400ef83f  call    cs:__imp_RtlEndEnumerationHashTable
0x1400ef846  nop     dword ptr [rax+rax+00h]
0x1400ef84b  xor     edx, edx
0x1400ef84d  movzx   ecx, di
0x1400ef850  call    TcpRepartitionStandbyTcbHashTable
0x1400ef855  mov     dl, 1
0x1400ef857  movzx   ecx, di
0x1400ef85a  call    TcpRepartitionStandbyTcbHashTable
0x1400ef85f  xor     edx, edx
0x1400ef861  movzx   ecx, di
0x1400ef864  call    TcpRepartitionTimeWaitTcbHashTable
0x1400ef869  mov     dl, 1
0x1400ef86b  movzx   ecx, di
0x1400ef86e  call    TcpRepartitionTimeWaitTcbHashTable
0x1400ef873  inc     di
0x1400ef876  inc     r13
0x1400ef879  cmp     di, r12w
0x1400ef87d  jb      loc_1400EF6B4
0x1400ef883  add     rsp, 78h
0x1400ef887  pop     r15
0x1400ef889  pop     r14
0x1400ef88b  pop     r13
0x1400ef88d  pop     r12
0x1400ef88f  pop     rdi
0x1400ef890  pop     rsi
0x1400ef891  pop     rbx
0x1400ef892  pop     rbp
0x1400ef893  retn
0x1400ef895  mov     rcx, [rbx+10h]
0x1400ef899  call    TcpGetPartitionFromKey
0x1400ef89e  mov     rcx, cs:PartitionTable
0x1400ef8a5  mov     rsi, rax
0x1400ef8a8  add     rcx, r15
0x1400ef8ab  cmp     rax, rcx
0x1400ef8ae  jz      loc_1400EF7B3
0x1400ef8b4  mov     dl, [rbx+7Bh]
0x1400ef8b7  xor     r8d, r8d
0x1400ef8ba  and     dl, 1
0x1400ef8bd  call    TcpDropSynRcvdFromPartition
0x1400ef8c2  xor     edx, edx
0x1400ef8c4  mov     rcx, rsi
0x1400ef8c7  call    TcpCountSynRcvdInPartition
0x1400ef8cc  test    byte ptr [rbx+7Bh], 1
0x1400ef8d0  jz      loc_1401D323A
0x1400ef8d6  mov     rcx, rsi
0x1400ef8d9  call    TcpCountSynRcvdRetryInPartition
0x1400ef8de  nop
0x1400ef8df  jmp     loc_1401D323A
0x1400ef8e4  mov     rcx, [rbx+10h]
0x1400ef8e8  call    TcpGetPartitionFromKey
0x1400ef8ed  mov     rdx, cs:PartitionTable
0x1400ef8f4  mov     r14, rax
0x1400ef8f7  add     rdx, r15
0x1400ef8fa  cmp     rax, rdx
0x1400ef8fd  jz      loc_1400EF819
0x1400ef903  xor     r8d, r8d; Context
0x1400ef906  mov     rdx, rbx; Entry
0x1400ef909  mov     rcx, rsi; HashTable
0x1400ef90c  call    cs:__imp_RtlRemoveEntryHashTable
0x1400ef913  nop     dword ptr [rax+rax+00h]
0x1400ef918  mov     rcx, [r14+10h]
0x1400ef91c  xor     r9d, r9d; Context
0x1400ef91f  mov     r8, [rbx+10h]; Signature
0x1400ef923  add     rcx, 78h ; 'x'; HashTable
0x1400ef927  mov     rdx, rbx; Entry
0x1400ef92a  call    cs:__imp_RtlInsertEntryHashTable
0x1400ef931  nop     dword ptr [rax+rax+00h]
0x1400ef936  jmp     loc_1400EF819
0x1401d323a  xor     r8d, r8d; Context
0x1401d323d  mov     rdx, rbx; Entry
0x1401d3240  mov     rcx, r14; HashTable
0x1401d3243  call    cs:__imp_RtlRemoveEntryHashTable
0x1401d324a  nop     dword ptr [rax+rax+00h]
0x1401d324f  mov     rcx, [rsi+8]
0x1401d3253  xor     r9d, r9d; Context
0x1401d3256  mov     r8, [rbx+10h]; Signature
0x1401d325a  add     rcx, 78h ; 'x'; HashTable
0x1401d325e  mov     rdx, rbx; Entry
0x1401d3261  call    cs:__imp_RtlInsertEntryHashTable
0x1401d3268  nop     dword ptr [rax+rax+00h]
0x1401d326d  nop
0x1401d326e  jmp     loc_1400EF7B3
```
