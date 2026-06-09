# TcpCleanupPartitionModule

- ea: `0x1401623b0`
- end: `0x14016256e`
- name: `TcpCleanupPartitionModule`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14014bb80`
- `0x1401628e0`

## callees

- `0x14005e680`
- `0x1401623b0`
- `0x140169af0`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x140162405`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162415`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162425`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162435`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016244f`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016246a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016247a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016248a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016249a`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162405`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162415`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162425`
- `ntoskrnl!RtlDeleteHashTable` at `0x140162435`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016244f`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016246a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016247a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016248a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016249a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401624ff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401624ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162518`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162529`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016254b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162518`
- `ntoskrnl!ExFreePoolWithTag` at `0x140162529`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016254b`
- `NETIO!RtlCleanupTimerWheel` at `0x1401624b5`
- `NETIO!RtlCleanupTimerWheel` at `0x1401624c8`
- `NETIO!RtlCleanupTimerWheel` at `0x1401624db`
- `NETIO!RtlCleanupTimerWheel` at `0x1401624b5`
- `NETIO!RtlCleanupTimerWheel` at `0x1401624c8`
- `NETIO!RtlCleanupTimerWheel` at `0x1401624db`

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
0x1401623b0  push    rbx
0x1401623b2  push    rbp
0x1401623b3  push    rsi
0x1401623b4  push    rdi
0x1401623b5  push    r14
0x1401623b7  sub     rsp, 40h
0x1401623bb  xor     eax, eax
0x1401623bd  xor     ebp, ebp
0x1401623bf  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x1401623c4  xorps   xmm0, xmm0
0x1401623c7  mov     esi, ecx
0x1401623c9  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x1401623ce  test    ecx, ecx
0x1401623d0  jz      loc_140162542
0x1401623d6  xor     r14d, r14d
0x1401623d9  mov     rcx, cs:PartitionTable
0x1401623e0  lea     rdi, [r14+r14*2]
0x1401623e4  shl     rdi, 6
0x1401623e8  lea     rdx, [rsp+68h+LockHandle]
0x1401623ed  mov     rcx, [rdi+rcx]
0x1401623f1  call    RtlAcquireWriteLock
0x1401623f6  mov     rax, cs:PartitionTable
0x1401623fd  mov     rbx, [rdi+rax+8]
0x140162402  mov     rcx, rbx; HashTable
0x140162405  call    cs:__imp_RtlDeleteHashTable
0x14016240c  nop     dword ptr [rax+rax+00h]
0x140162411  lea     rcx, [rbx+50h]; HashTable
0x140162415  call    cs:__imp_RtlDeleteHashTable
0x14016241c  nop     dword ptr [rax+rax+00h]
0x140162421  lea     rcx, [rbx+78h]; HashTable
0x140162425  call    cs:__imp_RtlDeleteHashTable
0x14016242c  nop     dword ptr [rax+rax+00h]
0x140162431  lea     rcx, [rbx+28h]; HashTable
0x140162435  call    cs:__imp_RtlDeleteHashTable
0x14016243c  nop     dword ptr [rax+rax+00h]
0x140162441  mov     rcx, cs:PartitionTable
0x140162448  add     rcx, 18h
0x14016244c  add     rcx, rdi; HashTable
0x14016244f  call    cs:__imp_RtlDeleteHashTable
0x140162456  nop     dword ptr [rax+rax+00h]
0x14016245b  mov     rax, cs:PartitionTable
0x140162462  mov     rbx, [rdi+rax+10h]
0x140162467  mov     rcx, rbx; HashTable
0x14016246a  call    cs:__imp_RtlDeleteHashTable
0x140162471  nop     dword ptr [rax+rax+00h]
0x140162476  lea     rcx, [rbx+50h]; HashTable
0x14016247a  call    cs:__imp_RtlDeleteHashTable
0x140162481  nop     dword ptr [rax+rax+00h]
0x140162486  lea     rcx, [rbx+78h]; HashTable
0x14016248a  call    cs:__imp_RtlDeleteHashTable
0x140162491  nop     dword ptr [rax+rax+00h]
0x140162496  lea     rcx, [rbx+28h]; HashTable
0x14016249a  call    cs:__imp_RtlDeleteHashTable
0x1401624a1  nop     dword ptr [rax+rax+00h]
0x1401624a6  mov     rax, cs:PartitionTable
0x1401624ad  mov     rbx, [rdi+rax+40h]
0x1401624b2  mov     rcx, rbx
0x1401624b5  call    cs:__imp_RtlCleanupTimerWheel
0x1401624bc  nop     dword ptr [rax+rax+00h]
0x1401624c1  lea     rcx, [rbx+638h]
0x1401624c8  call    cs:__imp_RtlCleanupTimerWheel
0x1401624cf  nop     dword ptr [rax+rax+00h]
0x1401624d4  lea     rcx, [rbx+1270h]
0x1401624db  call    cs:__imp_RtlCleanupTimerWheel
0x1401624e2  nop     dword ptr [rax+rax+00h]
0x1401624e7  mov     rcx, cs:PartitionTable
0x1401624ee  add     rcx, 50h ; 'P'
0x1401624f2  add     rcx, rdi
0x1401624f5  call    RngUninitializeRngPool
0x1401624fa  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1401624ff  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140162506  nop     dword ptr [rax+rax+00h]
0x14016250b  mov     rcx, cs:PartitionTable
0x140162512  xor     edx, edx; Tag
0x140162514  mov     rcx, [rdi+rcx]; P
0x140162518  call    cs:__imp_ExFreePoolWithTag
0x14016251f  nop     dword ptr [rax+rax+00h]
0x140162524  xor     edx, edx; Tag
0x140162526  mov     rcx, rbx; P
0x140162529  call    cs:__imp_ExFreePoolWithTag
0x140162530  nop     dword ptr [rax+rax+00h]
0x140162535  inc     ebp
0x140162537  inc     r14
0x14016253a  cmp     ebp, esi
0x14016253c  jb      loc_1401623D9
0x140162542  mov     rcx, cs:PartitionTable; P
0x140162549  xor     edx, edx; Tag
0x14016254b  call    cs:__imp_ExFreePoolWithTag
0x140162552  nop     dword ptr [rax+rax+00h]
0x140162557  mov     cs:PartitionTable, 0
0x140162562  add     rsp, 40h
0x140162566  pop     r14
0x140162568  pop     rdi
0x140162569  pop     rsi
0x14016256a  pop     rbp
0x14016256b  pop     rbx
0x14016256c  retn
```
