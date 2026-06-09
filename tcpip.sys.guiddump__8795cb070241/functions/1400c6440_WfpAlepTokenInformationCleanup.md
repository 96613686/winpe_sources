# WfpAlepTokenInformationCleanup

- ea: `0x1400c6440`
- end: `0x1400c65b8`
- name: `WfpAlepTokenInformationCleanup`
- size: `376`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400c4750`

## callees

- `0x1400c6440`
- `0x1400c65c0`
- `0x1400c6730`
- `0x14014ea14`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400c64d1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400c65a7`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400c64d1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400c65a7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c6492`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c64f4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c6492`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400c64f4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c6458`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c6550`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c6458`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c6550`
- `NETIO!NetioInsertWorkQueue` at `0x1400c656e`
- `NETIO!NetioInsertWorkQueue` at `0x1400c656e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400c6475`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400c6475`
- `NDIS!NdisReleaseRWLock` at `0x1400c6528`
- `NDIS!NdisReleaseRWLock` at `0x1400c6528`

## pseudocode

```c
__int64 __fastcall WfpAlepTokenInformationCleanup(__int64 a1)
{
  KIRQL CurrentIrql; // bl
  __int64 v3; // rcx
  _DWORD *v4; // rcx
  __int64 v5; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockWrite(gAleHashtableLock, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v3 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v3 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v3 = 4;
  }
  RtlRemoveEntryHashTable(&gAleMasterHashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 80), 0);
  if ( (*(_DWORD *)(a1 + 28) & 8) != 0 )
    RtlRemoveEntryHashTable(&gAleMasterHashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a1 + 104), 0);
  if ( gWfpPerProContext )
  {
    v4 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v4 == 4 )
      *v4 = 0;
  }
  NdisReleaseRWLock(gAleHashtableLock, &LockState);
  if ( (Feature_FWPS_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_FWPS_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_FWPS_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v5);
  if ( IsEnabledDeviceUsageNoInline )
    WfpRemoveModifiedIdCorrelationEntry(*(_QWORD *)(a1 + 20));
  if ( KeGetCurrentIrql() )
    return NetioInsertWorkQueue(tokenCleanupWorkQueue, a1 + 128);
  else
    return WfpAleTokenCleanupWorkQueueRoutine(a1 + 128);
}

```

## disassembly

```asm
0x1400c6440  mov     [rsp+arg_8], rbx
0x1400c6445  push    rdi
0x1400c6446  sub     rsp, 20h
0x1400c644a  xor     eax, eax
0x1400c644c  mov     rdi, rcx
0x1400c644f  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400c6454  mov     [rsp+28h+LockState.Flags], al
0x1400c6458  call    cs:__imp_KeGetCurrentIrql
0x1400c645f  nop     dword ptr [rax+rax+00h]
0x1400c6464  mov     rcx, cs:gAleHashtableLock; Lock
0x1400c646b  lea     rdx, [rsp+28h+LockState]; LockState
0x1400c6470  xor     r8d, r8d; Flags
0x1400c6473  mov     bl, al
0x1400c6475  call    cs:__imp_NdisAcquireRWLockWrite
0x1400c647c  nop     dword ptr [rax+rax+00h]
0x1400c6481  cmp     bl, 2
0x1400c6484  jz      short loc_1400C64C3
0x1400c6486  cmp     cs:gWfpPerProContext, 0
0x1400c648e  jz      short loc_1400C64C3
0x1400c6490  xor     ecx, ecx; ProcNumber
0x1400c6492  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c6499  nop     dword ptr [rax+rax+00h]
0x1400c649e  lea     ecx, [rax+rax*8]
0x1400c64a1  mov     rax, cs:gWfpPerProContext
0x1400c64a8  shl     ecx, 3
0x1400c64ab  mov     rcx, [rcx+rax]
0x1400c64af  mov     rax, ds:0FFFFF78000000008h
0x1400c64b9  mov     [rcx+8], rax
0x1400c64bd  mov     dword ptr [rcx], 4
0x1400c64c3  lea     rdx, [rdi+50h]; Entry
0x1400c64c7  xor     r8d, r8d; Context
0x1400c64ca  lea     rcx, gAleMasterHashTable; HashTable
0x1400c64d1  call    cs:__imp_RtlRemoveEntryHashTable
0x1400c64d8  nop     dword ptr [rax+rax+00h]
0x1400c64dd  mov     eax, [rdi+1Ch]
0x1400c64e0  test    al, 8
0x1400c64e2  jnz     loc_1400C6599
0x1400c64e8  cmp     cs:gWfpPerProContext, 0
0x1400c64f0  jz      short loc_1400C651C
0x1400c64f2  xor     ecx, ecx; ProcNumber
0x1400c64f4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400c64fb  nop     dword ptr [rax+rax+00h]
0x1400c6500  lea     ecx, [rax+rax*8]
0x1400c6503  mov     rax, cs:gWfpPerProContext
0x1400c650a  shl     ecx, 3
0x1400c650d  mov     rcx, [rcx+rax]
0x1400c6511  cmp     dword ptr [rcx], 4
0x1400c6514  jnz     short loc_1400C651C
0x1400c6516  mov     dword ptr [rcx], 0
0x1400c651c  mov     rcx, cs:gAleHashtableLock; Lock
0x1400c6523  lea     rdx, [rsp+28h+LockState]; LockState
0x1400c6528  call    cs:__imp_NdisReleaseRWLock
0x1400c652f  nop     dword ptr [rax+rax+00h]
0x1400c6534  mov     eax, cs:Feature_FWPS_BugFixes_25B__private_featureState
0x1400c653a  test    al, 10h
0x1400c653c  jnz     short loc_1400C6594
0x1400c653e  call    Feature_FWPS_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1400c6543  test    eax, eax
0x1400c6545  jz      short loc_1400C6550
0x1400c6547  mov     rcx, [rdi+14h]
0x1400c654b  call    WfpRemoveModifiedIdCorrelationEntry
0x1400c6550  call    cs:__imp_KeGetCurrentIrql
0x1400c6557  nop     dword ptr [rax+rax+00h]
0x1400c655c  test    al, al
0x1400c655e  jz      short loc_1400C6586
0x1400c6560  lea     rdx, [rdi+80h]
0x1400c6567  lea     rcx, tokenCleanupWorkQueue
0x1400c656e  call    cs:__imp_NetioInsertWorkQueue
0x1400c6575  nop     dword ptr [rax+rax+00h]
0x1400c657a  mov     rbx, [rsp+28h+arg_8]
0x1400c657f  add     rsp, 20h
0x1400c6583  pop     rdi
0x1400c6584  retn
0x1400c6586  lea     rcx, [rdi+80h]
0x1400c658d  call    WfpAleTokenCleanupWorkQueueRoutine
0x1400c6592  jmp     short loc_1400C657A
0x1400c6594  and     eax, 1
0x1400c6597  jmp     short loc_1400C6543
0x1400c6599  lea     rdx, [rdi+68h]; Entry
0x1400c659d  xor     r8d, r8d; Context
0x1400c65a0  lea     rcx, gAleMasterHashTable; HashTable
0x1400c65a7  call    cs:__imp_RtlRemoveEntryHashTable
0x1400c65ae  nop     dword ptr [rax+rax+00h]
0x1400c65b3  jmp     loc_1400C64E8
```
