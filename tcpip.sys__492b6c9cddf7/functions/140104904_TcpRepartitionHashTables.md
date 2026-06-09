# TcpRepartitionHashTables

- ea: `0x140104904`
- end: `0x140104bb3`
- name: `TcpRepartitionHashTables`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140103e0c`

## callees

- `0x14001bed0`
- `0x1400b07b0`
- `0x1400b2780`
- `0x140104904`
- `0x140104bbc`
- `0x140104cb0`
- `0x140104db0`
- `0x140104f00`
- `0x14012416c`

## import_xrefs

- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401049e3`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104a51`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104ab7`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401049e3`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104a51`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140104ab7`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010497c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104a32`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104a98`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010497c`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104a32`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x140104a98`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104969`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104a1f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104a85`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104969`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104a1f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140104a85`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401049b4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140104b84`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401d1f69`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401049b4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140104b84`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1401d1f69`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401049ce`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140104ba2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401d1f87`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401049ce`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140104ba2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1401d1f87`

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
0x140104904  push    rbp
0x140104906  push    rbx
0x140104907  push    rsi
0x140104908  push    rdi
0x140104909  push    r12
0x14010490b  push    r13
0x14010490d  push    r14
0x14010490f  push    r15
0x140104911  mov     rbp, rsp
0x140104914  sub     rsp, 78h
0x140104918  xor     edi, edi
0x14010491a  xor     eax, eax
0x14010491c  movzx   r12d, cx
0x140104920  cmp     ax, cx
0x140104923  jnb     loc_140104AFB
0x140104929  xor     r13d, r13d
0x14010492c  xor     edx, edx
0x14010492e  movzx   ecx, di
0x140104931  call    TcpRepartitionTcbHashTable
0x140104936  xor     eax, eax
0x140104938  lea     r15, ds:0[r13*2]
0x140104940  xorps   xmm0, xmm0
0x140104943  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x140104947  mov     rax, cs:PartitionTable
0x14010494e  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104952  add     r15, r13
0x140104955  shl     r15, 6
0x140104959  movups  xmmword ptr [rbp+Enumerator], xmm0
0x14010495d  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x140104961  mov     rsi, [r15+rax+10h]
0x140104966  mov     rcx, rsi; HashTable
0x140104969  call    cs:__imp_RtlInitEnumerationHashTable
0x140104970  nop     dword ptr [rax+rax+00h]
0x140104975  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104979  mov     rcx, rsi; HashTable
0x14010497c  call    cs:__imp_RtlEnumerateEntryHashTable
0x140104983  nop     dword ptr [rax+rax+00h]
0x140104988  mov     rbx, rax
0x14010498b  test    rax, rax
0x14010498e  jz      short loc_1401049DC
0x140104990  mov     rcx, [rax+10h]
0x140104994  call    TcpGetPartitionFromKey
0x140104999  mov     rdx, cs:PartitionTable
0x1401049a0  mov     r14, rax
0x1401049a3  add     rdx, r15
0x1401049a6  cmp     rax, rdx
0x1401049a9  jz      short loc_140104975
0x1401049ab  xor     r8d, r8d; Context
0x1401049ae  mov     rdx, rbx; Entry
0x1401049b1  mov     rcx, rsi; HashTable
0x1401049b4  call    cs:__imp_RtlRemoveEntryHashTable
0x1401049bb  nop     dword ptr [rax+rax+00h]
0x1401049c0  mov     r8, [rbx+10h]; Signature
0x1401049c4  xor     r9d, r9d; Context
0x1401049c7  mov     rcx, [r14+10h]; HashTable
0x1401049cb  mov     rdx, rbx; Entry
0x1401049ce  call    cs:__imp_RtlInsertEntryHashTable
0x1401049d5  nop     dword ptr [rax+rax+00h]
0x1401049da  jmp     short loc_140104975
0x1401049dc  lea     rdx, [rbp+Enumerator]; Enumerator
0x1401049e0  mov     rcx, rsi; HashTable
0x1401049e3  call    cs:__imp_RtlEndEnumerationHashTable
0x1401049ea  nop     dword ptr [rax+rax+00h]
0x1401049ef  movzx   ecx, di
0x1401049f2  call    TcpRepartitionTupleTable
0x1401049f7  xor     eax, eax
0x1401049f9  lea     rdx, [rbp+Enumerator]; Enumerator
0x1401049fd  xorps   xmm0, xmm0
0x140104a00  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x140104a04  mov     rax, cs:PartitionTable
0x140104a0b  movups  xmmword ptr [rbp+Enumerator], xmm0
0x140104a0f  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x140104a13  mov     r14, [r15+rax+8]
0x140104a18  add     r14, 78h ; 'x'
0x140104a1c  mov     rcx, r14; HashTable
0x140104a1f  call    cs:__imp_RtlInitEnumerationHashTable
0x140104a26  nop     dword ptr [rax+rax+00h]
0x140104a2b  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104a2f  mov     rcx, r14; HashTable
0x140104a32  call    cs:__imp_RtlEnumerateEntryHashTable
0x140104a39  nop     dword ptr [rax+rax+00h]
0x140104a3e  mov     rbx, rax
0x140104a41  test    rax, rax
0x140104a44  jnz     loc_140104B0D
0x140104a4a  lea     rdx, [rbp+Enumerator]; Enumerator
0x140104a4e  mov     rcx, r14; HashTable
0x140104a51  call    cs:__imp_RtlEndEnumerationHashTable
0x140104a58  nop     dword ptr [rax+rax+00h]
0x140104a5d  xor     eax, eax
0x140104a5f  lea     rdx, [rbp+var_30]; Enumerator
0x140104a63  xorps   xmm0, xmm0
0x140104a66  mov     qword ptr [rbp+var_30.BucketIndex], rax
0x140104a6a  mov     rax, cs:PartitionTable
0x140104a71  movups  xmmword ptr [rbp+var_30], xmm0
0x140104a75  movups  xmmword ptr [rbp+var_30+10h], xmm0
0x140104a79  mov     rsi, [r15+rax+10h]
0x140104a7e  add     rsi, 78h ; 'x'
0x140104a82  mov     rcx, rsi; HashTable
0x140104a85  call    cs:__imp_RtlInitEnumerationHashTable
0x140104a8c  nop     dword ptr [rax+rax+00h]
0x140104a91  lea     rdx, [rbp+var_30]; Enumerator
0x140104a95  mov     rcx, rsi; HashTable
0x140104a98  call    cs:__imp_RtlEnumerateEntryHashTable
0x140104a9f  nop     dword ptr [rax+rax+00h]
0x140104aa4  mov     rbx, rax
0x140104aa7  test    rax, rax
0x140104aaa  jnz     loc_140104B5C
0x140104ab0  lea     rdx, [rbp+var_30]; Enumerator
0x140104ab4  mov     rcx, rsi; HashTable
0x140104ab7  call    cs:__imp_RtlEndEnumerationHashTable
0x140104abe  nop     dword ptr [rax+rax+00h]
0x140104ac3  xor     edx, edx
0x140104ac5  movzx   ecx, di
0x140104ac8  call    TcpRepartitionStandbyTcbHashTable
0x140104acd  mov     dl, 1
0x140104acf  movzx   ecx, di
0x140104ad2  call    TcpRepartitionStandbyTcbHashTable
0x140104ad7  xor     edx, edx
0x140104ad9  movzx   ecx, di
0x140104adc  call    TcpRepartitionTimeWaitTcbHashTable
0x140104ae1  mov     dl, 1
0x140104ae3  movzx   ecx, di
0x140104ae6  call    TcpRepartitionTimeWaitTcbHashTable
0x140104aeb  inc     di
0x140104aee  inc     r13
0x140104af1  cmp     di, r12w
0x140104af5  jb      loc_14010492C
0x140104afb  add     rsp, 78h
0x140104aff  pop     r15
0x140104b01  pop     r14
0x140104b03  pop     r13
0x140104b05  pop     r12
0x140104b07  pop     rdi
0x140104b08  pop     rsi
0x140104b09  pop     rbx
0x140104b0a  pop     rbp
0x140104b0b  retn
0x140104b0d  mov     rcx, [rbx+10h]
0x140104b11  call    TcpGetPartitionFromKey
0x140104b16  mov     rcx, cs:PartitionTable
0x140104b1d  mov     rsi, rax
0x140104b20  add     rcx, r15
0x140104b23  cmp     rax, rcx
0x140104b26  jz      loc_140104A2B
0x140104b2c  mov     dl, [rbx+7Bh]
0x140104b2f  xor     r8d, r8d
0x140104b32  and     dl, 1
0x140104b35  call    TcpDropSynRcvdFromPartition
0x140104b3a  xor     edx, edx
0x140104b3c  mov     rcx, rsi
0x140104b3f  call    TcpCountSynRcvdInPartition
0x140104b44  test    byte ptr [rbx+7Bh], 1
0x140104b48  jz      loc_1401D1F60
0x140104b4e  mov     rcx, rsi
0x140104b51  call    TcpCountSynRcvdRetryInPartition
0x140104b56  nop
0x140104b57  jmp     loc_1401D1F60
0x140104b5c  mov     rcx, [rbx+10h]
0x140104b60  call    TcpGetPartitionFromKey
0x140104b65  mov     rdx, cs:PartitionTable
0x140104b6c  mov     r14, rax
0x140104b6f  add     rdx, r15
0x140104b72  cmp     rax, rdx
0x140104b75  jz      loc_140104A91
0x140104b7b  xor     r8d, r8d; Context
0x140104b7e  mov     rdx, rbx; Entry
0x140104b81  mov     rcx, rsi; HashTable
0x140104b84  call    cs:__imp_RtlRemoveEntryHashTable
0x140104b8b  nop     dword ptr [rax+rax+00h]
0x140104b90  mov     rcx, [r14+10h]
0x140104b94  xor     r9d, r9d; Context
0x140104b97  mov     r8, [rbx+10h]; Signature
0x140104b9b  add     rcx, 78h ; 'x'; HashTable
0x140104b9f  mov     rdx, rbx; Entry
0x140104ba2  call    cs:__imp_RtlInsertEntryHashTable
0x140104ba9  nop     dword ptr [rax+rax+00h]
0x140104bae  jmp     loc_140104A91
0x1401d1f60  xor     r8d, r8d; Context
0x1401d1f63  mov     rdx, rbx; Entry
0x1401d1f66  mov     rcx, r14; HashTable
0x1401d1f69  call    cs:__imp_RtlRemoveEntryHashTable
0x1401d1f70  nop     dword ptr [rax+rax+00h]
0x1401d1f75  mov     rcx, [rsi+8]
0x1401d1f79  xor     r9d, r9d; Context
0x1401d1f7c  mov     r8, [rbx+10h]; Signature
0x1401d1f80  add     rcx, 78h ; 'x'; HashTable
0x1401d1f84  mov     rdx, rbx; Entry
0x1401d1f87  call    cs:__imp_RtlInsertEntryHashTable
0x1401d1f8e  nop     dword ptr [rax+rax+00h]
0x1401d1f93  nop
0x1401d1f94  jmp     loc_140104A2B
```
