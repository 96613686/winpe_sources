# TcpCleanupPartitionModule

- ea: `0x140164170`
- end: `0x14016432e`
- name: `TcpCleanupPartitionModule`
- size: `446`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14014d860`
- `0x1401646a0`

## callees

- `0x1400b4570`
- `0x140164170`
- `0x14016b730`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x1401641c5`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641d5`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641e5`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641f5`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016420f`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016422a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016423a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016424a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016425a`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641c5`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641d5`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641e5`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401641f5`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016420f`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016422a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016423a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016424a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14016425a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401642bf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401642bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401642d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401642e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016430b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401642d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401642e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016430b`
- `NETIO!RtlCleanupTimerWheel` at `0x140164275`
- `NETIO!RtlCleanupTimerWheel` at `0x140164288`
- `NETIO!RtlCleanupTimerWheel` at `0x14016429b`
- `NETIO!RtlCleanupTimerWheel` at `0x140164275`
- `NETIO!RtlCleanupTimerWheel` at `0x140164288`
- `NETIO!RtlCleanupTimerWheel` at `0x14016429b`

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
0x140164170  push    rbx
0x140164172  push    rbp
0x140164173  push    rsi
0x140164174  push    rdi
0x140164175  push    r14
0x140164177  sub     rsp, 40h
0x14016417b  xor     eax, eax
0x14016417d  xor     ebp, ebp
0x14016417f  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140164184  xorps   xmm0, xmm0
0x140164187  mov     esi, ecx
0x140164189  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14016418e  test    ecx, ecx
0x140164190  jz      loc_140164302
0x140164196  xor     r14d, r14d
0x140164199  mov     rcx, cs:PartitionTable
0x1401641a0  lea     rdi, [r14+r14*2]
0x1401641a4  shl     rdi, 6
0x1401641a8  lea     rdx, [rsp+68h+LockHandle]
0x1401641ad  mov     rcx, [rdi+rcx]
0x1401641b1  call    RtlAcquireWriteLock
0x1401641b6  mov     rax, cs:PartitionTable
0x1401641bd  mov     rbx, [rdi+rax+8]
0x1401641c2  mov     rcx, rbx; HashTable
0x1401641c5  call    cs:__imp_RtlDeleteHashTable
0x1401641cc  nop     dword ptr [rax+rax+00h]
0x1401641d1  lea     rcx, [rbx+50h]; HashTable
0x1401641d5  call    cs:__imp_RtlDeleteHashTable
0x1401641dc  nop     dword ptr [rax+rax+00h]
0x1401641e1  lea     rcx, [rbx+78h]; HashTable
0x1401641e5  call    cs:__imp_RtlDeleteHashTable
0x1401641ec  nop     dword ptr [rax+rax+00h]
0x1401641f1  lea     rcx, [rbx+28h]; HashTable
0x1401641f5  call    cs:__imp_RtlDeleteHashTable
0x1401641fc  nop     dword ptr [rax+rax+00h]
0x140164201  mov     rcx, cs:PartitionTable
0x140164208  add     rcx, 18h
0x14016420c  add     rcx, rdi; HashTable
0x14016420f  call    cs:__imp_RtlDeleteHashTable
0x140164216  nop     dword ptr [rax+rax+00h]
0x14016421b  mov     rax, cs:PartitionTable
0x140164222  mov     rbx, [rdi+rax+10h]
0x140164227  mov     rcx, rbx; HashTable
0x14016422a  call    cs:__imp_RtlDeleteHashTable
0x140164231  nop     dword ptr [rax+rax+00h]
0x140164236  lea     rcx, [rbx+50h]; HashTable
0x14016423a  call    cs:__imp_RtlDeleteHashTable
0x140164241  nop     dword ptr [rax+rax+00h]
0x140164246  lea     rcx, [rbx+78h]; HashTable
0x14016424a  call    cs:__imp_RtlDeleteHashTable
0x140164251  nop     dword ptr [rax+rax+00h]
0x140164256  lea     rcx, [rbx+28h]; HashTable
0x14016425a  call    cs:__imp_RtlDeleteHashTable
0x140164261  nop     dword ptr [rax+rax+00h]
0x140164266  mov     rax, cs:PartitionTable
0x14016426d  mov     rbx, [rdi+rax+40h]
0x140164272  mov     rcx, rbx
0x140164275  call    cs:__imp_RtlCleanupTimerWheel
0x14016427c  nop     dword ptr [rax+rax+00h]
0x140164281  lea     rcx, [rbx+638h]
0x140164288  call    cs:__imp_RtlCleanupTimerWheel
0x14016428f  nop     dword ptr [rax+rax+00h]
0x140164294  lea     rcx, [rbx+1270h]
0x14016429b  call    cs:__imp_RtlCleanupTimerWheel
0x1401642a2  nop     dword ptr [rax+rax+00h]
0x1401642a7  mov     rcx, cs:PartitionTable
0x1401642ae  add     rcx, 50h ; 'P'
0x1401642b2  add     rcx, rdi
0x1401642b5  call    RngUninitializeRngPool
0x1401642ba  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1401642bf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401642c6  nop     dword ptr [rax+rax+00h]
0x1401642cb  mov     rcx, cs:PartitionTable
0x1401642d2  xor     edx, edx; Tag
0x1401642d4  mov     rcx, [rdi+rcx]; P
0x1401642d8  call    cs:__imp_ExFreePoolWithTag
0x1401642df  nop     dword ptr [rax+rax+00h]
0x1401642e4  xor     edx, edx; Tag
0x1401642e6  mov     rcx, rbx; P
0x1401642e9  call    cs:__imp_ExFreePoolWithTag
0x1401642f0  nop     dword ptr [rax+rax+00h]
0x1401642f5  inc     ebp
0x1401642f7  inc     r14
0x1401642fa  cmp     ebp, esi
0x1401642fc  jb      loc_140164199
0x140164302  mov     rcx, cs:PartitionTable; P
0x140164309  xor     edx, edx; Tag
0x14016430b  call    cs:__imp_ExFreePoolWithTag
0x140164312  nop     dword ptr [rax+rax+00h]
0x140164317  mov     cs:PartitionTable, 0
0x140164322  add     rsp, 40h
0x140164326  pop     r14
0x140164328  pop     rdi
0x140164329  pop     rsi
0x14016432a  pop     rbp
0x14016432b  pop     rbx
0x14016432c  retn
```
