# TcpRepartitionHashTables

- ea: `0x140104924`
- end: `0x140104bd3`
- name: `TcpRepartitionHashTables`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140103e2c`

## callees

- `0x14001c170`
- `0x1400b03d0`
- `0x1400b23a0`
- `0x140104924`
- `0x140104bdc`
- `0x140104cd0`
- `0x140104dd0`
- `0x140104f20`
- `0x1401242ac`

## import_xrefs

- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104a03`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104a71`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104ad7`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104a03`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104a71`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104ad7`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010499c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104a52`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104ab8`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010499c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104a52`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104ab8`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104989`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104a3f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104aa5`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104989`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104a3f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104aa5`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401049d4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140104ba4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401d20a9`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401049d4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140104ba4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401d20a9`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401049ee`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140104bc2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401d20c7`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401049ee`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140104bc2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401d20c7`

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
0x140104924  push    rbp
0x140104926  push    rbx
0x140104927  push    rsi
0x140104928  push    rdi
0x140104929  push    r12
0x14010492b  push    r13
0x14010492d  push    r14
0x14010492f  push    r15
0x140104931  mov     rbp, rsp
0x140104934  sub     rsp, 78h
0x140104938  xor     edi, edi
0x14010493a  xor     eax, eax
0x14010493c  movzx   r12d, cx
0x140104940  cmp     ax, cx
0x140104943  jnb     loc_140104B1B
0x140104949  xor     r13d, r13d
0x14010494c  xor     edx, edx
0x14010494e  movzx   ecx, di
0x140104951  call    TcpRepartitionTcbHashTable
0x140104956  xor     eax, eax
0x140104958  lea     r15, ds:0[r13*2]
0x140104960  xorps   xmm0, xmm0
0x140104963  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x140104967  mov     rax, cs:PartitionTable
0x14010496e  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104972  add     r15, r13
0x140104975  shl     r15, 6
0x140104979  movups  xmmword ptr [rbp+Enumerator], xmm0
0x14010497d  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x140104981  mov     rsi, [r15+rax+10h]
0x140104986  mov     rcx, rsi; HashTable
0x140104989  call    cs:__imp_RtlInitEnumerationHashTable
0x140104990  nop     dword ptr [rax+rax+00h]
0x140104995  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104999  mov     rcx, rsi; HashTable
0x14010499c  call    cs:__imp_RtlEnumerateEntryHashTable
0x1401049a3  nop     dword ptr [rax+rax+00h]
0x1401049a8  mov     rbx, rax
0x1401049ab  test    rax, rax
0x1401049ae  jz      short loc_1401049FC
0x1401049b0  mov     rcx, [rax+10h]
0x1401049b4  call    TcpGetPartitionFromKey
0x1401049b9  mov     rdx, cs:PartitionTable
0x1401049c0  mov     r14, rax
0x1401049c3  add     rdx, r15
0x1401049c6  cmp     rax, rdx
0x1401049c9  jz      short loc_140104995
0x1401049cb  xor     r8d, r8d; Context
0x1401049ce  mov     rdx, rbx; Entry
0x1401049d1  mov     rcx, rsi; HashTable
0x1401049d4  call    cs:__imp_RtlRemoveEntryHashTable
0x1401049db  nop     dword ptr [rax+rax+00h]
0x1401049e0  mov     r8, [rbx+10h]; Signature
0x1401049e4  xor     r9d, r9d; Context
0x1401049e7  mov     rcx, [r14+10h]; HashTable
0x1401049eb  mov     rdx, rbx; Entry
0x1401049ee  call    cs:__imp_RtlInsertEntryHashTable
0x1401049f5  nop     dword ptr [rax+rax+00h]
0x1401049fa  jmp     short loc_140104995
0x1401049fc  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104a00  mov     rcx, rsi; HashTable
0x140104a03  call    cs:__imp_RtlEndEnumerationHashTable
0x140104a0a  nop     dword ptr [rax+rax+00h]
0x140104a0f  movzx   ecx, di
0x140104a12  call    TcpRepartitionTupleTable
0x140104a17  xor     eax, eax
0x140104a19  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104a1d  xorps   xmm0, xmm0
0x140104a20  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x140104a24  mov     rax, cs:PartitionTable
0x140104a2b  movups  xmmword ptr [rbp+Enumerator], xmm0
0x140104a2f  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x140104a33  mov     r14, [r15+rax+8]
0x140104a38  add     r14, 78h ; 'x'
0x140104a3c  mov     rcx, r14; HashTable
0x140104a3f  call    cs:__imp_RtlInitEnumerationHashTable
0x140104a46  nop     dword ptr [rax+rax+00h]
0x140104a4b  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104a4f  mov     rcx, r14; HashTable
0x140104a52  call    cs:__imp_RtlEnumerateEntryHashTable
0x140104a59  nop     dword ptr [rax+rax+00h]
0x140104a5e  mov     rbx, rax
0x140104a61  test    rax, rax
0x140104a64  jnz     loc_140104B2D
0x140104a6a  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104a6e  mov     rcx, r14; HashTable
0x140104a71  call    cs:__imp_RtlEndEnumerationHashTable
0x140104a78  nop     dword ptr [rax+rax+00h]
0x140104a7d  xor     eax, eax
0x140104a7f  lea     rdx, [rbp+var_30]; Enumerator
0x140104a83  xorps   xmm0, xmm0
0x140104a86  mov     qword ptr [rbp+var_30.BucketIndex], rax
0x140104a8a  mov     rax, cs:PartitionTable
0x140104a91  movups  xmmword ptr [rbp+var_30], xmm0
0x140104a95  movups  xmmword ptr [rbp+var_30+10h], xmm0
0x140104a99  mov     rsi, [r15+rax+10h]
0x140104a9e  add     rsi, 78h ; 'x'
0x140104aa2  mov     rcx, rsi; HashTable
0x140104aa5  call    cs:__imp_RtlInitEnumerationHashTable
0x140104aac  nop     dword ptr [rax+rax+00h]
0x140104ab1  lea     rdx, [rbp+var_30]; Enumerator
0x140104ab5  mov     rcx, rsi; HashTable
0x140104ab8  call    cs:__imp_RtlEnumerateEntryHashTable
0x140104abf  nop     dword ptr [rax+rax+00h]
0x140104ac4  mov     rbx, rax
0x140104ac7  test    rax, rax
0x140104aca  jnz     loc_140104B7C
0x140104ad0  lea     rdx, [rbp+var_30]; Enumerator
0x140104ad4  mov     rcx, rsi; HashTable
0x140104ad7  call    cs:__imp_RtlEndEnumerationHashTable
0x140104ade  nop     dword ptr [rax+rax+00h]
0x140104ae3  xor     edx, edx
0x140104ae5  movzx   ecx, di
0x140104ae8  call    TcpRepartitionStandbyTcbHashTable
0x140104aed  mov     dl, 1
0x140104aef  movzx   ecx, di
0x140104af2  call    TcpRepartitionStandbyTcbHashTable
0x140104af7  xor     edx, edx
0x140104af9  movzx   ecx, di
0x140104afc  call    TcpRepartitionTimeWaitTcbHashTable
0x140104b01  mov     dl, 1
0x140104b03  movzx   ecx, di
0x140104b06  call    TcpRepartitionTimeWaitTcbHashTable
0x140104b0b  inc     di
0x140104b0e  inc     r13
0x140104b11  cmp     di, r12w
0x140104b15  jb      loc_14010494C
0x140104b1b  add     rsp, 78h
0x140104b1f  pop     r15
0x140104b21  pop     r14
0x140104b23  pop     r13
0x140104b25  pop     r12
0x140104b27  pop     rdi
0x140104b28  pop     rsi
0x140104b29  pop     rbx
0x140104b2a  pop     rbp
0x140104b2b  retn
0x140104b2d  mov     rcx, [rbx+10h]
0x140104b31  call    TcpGetPartitionFromKey
0x140104b36  mov     rcx, cs:PartitionTable
0x140104b3d  mov     rsi, rax
0x140104b40  add     rcx, r15
0x140104b43  cmp     rax, rcx
0x140104b46  jz      loc_140104A4B
0x140104b4c  mov     dl, [rbx+7Bh]
0x140104b4f  xor     r8d, r8d
0x140104b52  and     dl, 1
0x140104b55  call    TcpDropSynRcvdFromPartition
0x140104b5a  xor     edx, edx
0x140104b5c  mov     rcx, rsi
0x140104b5f  call    TcpCountSynRcvdInPartition
0x140104b64  test    byte ptr [rbx+7Bh], 1
0x140104b68  jz      loc_1401D20A0
0x140104b6e  mov     rcx, rsi
0x140104b71  call    TcpCountSynRcvdRetryInPartition
0x140104b76  nop
0x140104b77  jmp     loc_1401D20A0
0x140104b7c  mov     rcx, [rbx+10h]
0x140104b80  call    TcpGetPartitionFromKey
0x140104b85  mov     rdx, cs:PartitionTable
0x140104b8c  mov     r14, rax
0x140104b8f  add     rdx, r15
0x140104b92  cmp     rax, rdx
0x140104b95  jz      loc_140104AB1
0x140104b9b  xor     r8d, r8d; Context
0x140104b9e  mov     rdx, rbx; Entry
0x140104ba1  mov     rcx, rsi; HashTable
0x140104ba4  call    cs:__imp_RtlRemoveEntryHashTable
0x140104bab  nop     dword ptr [rax+rax+00h]
0x140104bb0  mov     rcx, [r14+10h]
0x140104bb4  xor     r9d, r9d; Context
0x140104bb7  mov     r8, [rbx+10h]; Signature
0x140104bbb  add     rcx, 78h ; 'x'; HashTable
0x140104bbf  mov     rdx, rbx; Entry
0x140104bc2  call    cs:__imp_RtlInsertEntryHashTable
0x140104bc9  nop     dword ptr [rax+rax+00h]
0x140104bce  jmp     loc_140104AB1
0x1401d20a0  xor     r8d, r8d; Context
0x1401d20a3  mov     rdx, rbx; Entry
0x1401d20a6  mov     rcx, r14; HashTable
0x1401d20a9  call    cs:__imp_RtlRemoveEntryHashTable
0x1401d20b0  nop     dword ptr [rax+rax+00h]
0x1401d20b5  mov     rcx, [rsi+8]
0x1401d20b9  xor     r9d, r9d; Context
0x1401d20bc  mov     r8, [rbx+10h]; Signature
0x1401d20c0  add     rcx, 78h ; 'x'; HashTable
0x1401d20c4  mov     rdx, rbx; Entry
0x1401d20c7  call    cs:__imp_RtlInsertEntryHashTable
0x1401d20ce  nop     dword ptr [rax+rax+00h]
0x1401d20d3  nop
0x1401d20d4  jmp     loc_140104A4B
```
