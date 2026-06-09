# TcpCleanupPartitionModule

- ea: `0x1401624f0`
- end: `0x1401626ae`
- name: `TcpCleanupPartitionModule`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14014bd10`
- `0x140162a20`

## callees

- `0x14005e920`
- `0x1401624f0`
- `0x140169c30`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x140162545`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162555`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162565`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162575`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016258f`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625aa`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625ba`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625ca`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625da`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162545`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162555`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162565`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162575`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016258f`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625aa`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625ba`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625ca`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401625da`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14016263f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14016263f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162658`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162669`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016268b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162658`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162669`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016268b`
- `NETIO!RtlCleanupTimerWheel` at `0x1401625f5`
- `NETIO!RtlCleanupTimerWheel` at `0x140162608`
- `NETIO!RtlCleanupTimerWheel` at `0x14016261b`
- `NETIO!RtlCleanupTimerWheel` at `0x1401625f5`
- `NETIO!RtlCleanupTimerWheel` at `0x140162608`
- `NETIO!RtlCleanupTimerWheel` at `0x14016261b`

## pseudocode

```c
void __fastcall TcpCleanupPartitionModule(unsigned int a1)
{
  unsigned int v1; // ebp
  __int64 v3; // r14
  struct _RTL_DYNAMIC_HASH_TABLE *v4; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v5; // rbx
  char *v6; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  v1 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a1 )
  {
    v3 = 0;
    do
    {
      RtlAcquireWriteLock(*((_QWORD *)PartitionTable + 24 * v3), &LockHandle);
      v4 = (struct _RTL_DYNAMIC_HASH_TABLE *)*((_QWORD *)PartitionTable + 24 * v3 + 1);
      RtlDeleteHashTable(v4);
      RtlDeleteHashTable(v4 + 2);
      RtlDeleteHashTable(v4 + 3);
      RtlDeleteHashTable(v4 + 1);
      RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)((char *)PartitionTable + 192 * v3 + 24));
      v5 = (struct _RTL_DYNAMIC_HASH_TABLE *)*((_QWORD *)PartitionTable + 24 * v3 + 2);
      RtlDeleteHashTable(v5);
      RtlDeleteHashTable(v5 + 2);
      RtlDeleteHashTable(v5 + 3);
      RtlDeleteHashTable(v5 + 1);
      v6 = (char *)*((_QWORD *)PartitionTable + 24 * v3 + 8);
      RtlCleanupTimerWheel(v6);
      RtlCleanupTimerWheel(v6 + 1592);
      RtlCleanupTimerWheel(v6 + 4720);
      RngUninitializeRngPool((char *)PartitionTable + 192 * v3 + 80);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      ExFreePoolWithTag(*((PVOID *)PartitionTable + 24 * v3), 0);
      ExFreePoolWithTag(v6, 0);
      ++v1;
      ++v3;
    }
    while ( v1 < a1 );
  }
  ExFreePoolWithTag(PartitionTable, 0);
  PartitionTable = 0;
}

```

## disassembly

```asm
0x1401624f0  push    rbx
0x1401624f2  push    rbp
0x1401624f3  push    rsi
0x1401624f4  push    rdi
0x1401624f5  push    r14
0x1401624f7  sub     rsp, 40h
0x1401624fb  xor     eax, eax
0x1401624fd  xor     ebp, ebp
0x1401624ff  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140162504  xorps   xmm0, xmm0
0x140162507  mov     esi, ecx
0x140162509  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14016250e  test    ecx, ecx
0x140162510  jz      loc_140162682
0x140162516  xor     r14d, r14d
0x140162519  mov     rcx, cs:PartitionTable
0x140162520  lea     rdi, [r14+r14*2]
0x140162524  shl     rdi, 6
0x140162528  lea     rdx, [rsp+68h+LockHandle]
0x14016252d  mov     rcx, [rdi+rcx]
0x140162531  call    RtlAcquireWriteLock
0x140162536  mov     rax, cs:PartitionTable
0x14016253d  mov     rbx, [rdi+rax+8]
0x140162542  mov     rcx, rbx; HashTable
0x140162545  call    cs:__imp_RtlDeleteHashTable
0x14016254c  nop     dword ptr [rax+rax+00h]
0x140162551  lea     rcx, [rbx+50h]; HashTable
0x140162555  call    cs:__imp_RtlDeleteHashTable
0x14016255c  nop     dword ptr [rax+rax+00h]
0x140162561  lea     rcx, [rbx+78h]; HashTable
0x140162565  call    cs:__imp_RtlDeleteHashTable
0x14016256c  nop     dword ptr [rax+rax+00h]
0x140162571  lea     rcx, [rbx+28h]; HashTable
0x140162575  call    cs:__imp_RtlDeleteHashTable
0x14016257c  nop     dword ptr [rax+rax+00h]
0x140162581  mov     rcx, cs:PartitionTable
0x140162588  add     rcx, 18h
0x14016258c  add     rcx, rdi; HashTable
0x14016258f  call    cs:__imp_RtlDeleteHashTable
0x140162596  nop     dword ptr [rax+rax+00h]
0x14016259b  mov     rax, cs:PartitionTable
0x1401625a2  mov     rbx, [rdi+rax+10h]
0x1401625a7  mov     rcx, rbx; HashTable
0x1401625aa  call    cs:__imp_RtlDeleteHashTable
0x1401625b1  nop     dword ptr [rax+rax+00h]
0x1401625b6  lea     rcx, [rbx+50h]; HashTable
0x1401625ba  call    cs:__imp_RtlDeleteHashTable
0x1401625c1  nop     dword ptr [rax+rax+00h]
0x1401625c6  lea     rcx, [rbx+78h]; HashTable
0x1401625ca  call    cs:__imp_RtlDeleteHashTable
0x1401625d1  nop     dword ptr [rax+rax+00h]
0x1401625d6  lea     rcx, [rbx+28h]; HashTable
0x1401625da  call    cs:__imp_RtlDeleteHashTable
0x1401625e1  nop     dword ptr [rax+rax+00h]
0x1401625e6  mov     rax, cs:PartitionTable
0x1401625ed  mov     rbx, [rdi+rax+40h]
0x1401625f2  mov     rcx, rbx
0x1401625f5  call    cs:__imp_RtlCleanupTimerWheel
0x1401625fc  nop     dword ptr [rax+rax+00h]
0x140162601  lea     rcx, [rbx+638h]
0x140162608  call    cs:__imp_RtlCleanupTimerWheel
0x14016260f  nop     dword ptr [rax+rax+00h]
0x140162614  lea     rcx, [rbx+1270h]
0x14016261b  call    cs:__imp_RtlCleanupTimerWheel
0x140162622  nop     dword ptr [rax+rax+00h]
0x140162627  mov     rcx, cs:PartitionTable
0x14016262e  add     rcx, 50h ; 'P'
0x140162632  add     rcx, rdi
0x140162635  call    RngUninitializeRngPool
0x14016263a  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x14016263f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140162646  nop     dword ptr [rax+rax+00h]
0x14016264b  mov     rcx, cs:PartitionTable
0x140162652  xor     edx, edx; Tag
0x140162654  mov     rcx, [rdi+rcx]; P
0x140162658  call    cs:__imp_ExFreePoolWithTag
0x14016265f  nop     dword ptr [rax+rax+00h]
0x140162664  xor     edx, edx; Tag
0x140162666  mov     rcx, rbx; P
0x140162669  call    cs:__imp_ExFreePoolWithTag
0x140162670  nop     dword ptr [rax+rax+00h]
0x140162675  inc     ebp
0x140162677  inc     r14
0x14016267a  cmp     ebp, esi
0x14016267c  jb      loc_140162519
0x140162682  mov     rcx, cs:PartitionTable; P
0x140162689  xor     edx, edx; Tag
0x14016268b  call    cs:__imp_ExFreePoolWithTag
0x140162692  nop     dword ptr [rax+rax+00h]
0x140162697  mov     cs:PartitionTable, 0
0x1401626a2  add     rsp, 40h
0x1401626a6  pop     r14
0x1401626a8  pop     rdi
0x1401626a9  pop     rsi
0x1401626aa  pop     rbp
0x1401626ab  pop     rbx
0x1401626ac  retn
```
