# WfpAlepTokenInformationCleanup

- ea: `0x1400bccf0`
- end: `0x1400bce68`
- name: `WfpAlepTokenInformationCleanup`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400bb000`

## callees

- `0x1400bccf0`
- `0x1400bce70`
- `0x1400bcfe0`
- `0x14014ccdc`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bcd81`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bce57`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bcd81`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bce57`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcd42`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcda4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcd42`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcda4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bcd08`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bce00`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bcd08`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bce00`
- `NETIO!NetioInsertWorkQueue` at `0x1400bce1e`
- `NETIO!NetioInsertWorkQueue` at `0x1400bce1e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bcd25`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bcd25`
- `NDIS!NdisReleaseRWLock` at `0x1400bcdd8`
- `NDIS!NdisReleaseRWLock` at `0x1400bcdd8`

## pseudocode

```c
__int64 __fastcall WfpAlepTokenInformationCleanup(__int64 a1)
{
  KIRQL CurrentIrql; // bl
  __int64 v3; // rcx
  _DWORD *v4; // rcx
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
    IsEnabledDeviceUsageNoInline = Feature_FWPS_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
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
0x1400bccf0  mov     [rsp+arg_8], rbx
0x1400bccf5  push    rdi
0x1400bccf6  sub     rsp, 20h
0x1400bccfa  xor     eax, eax
0x1400bccfc  mov     rdi, rcx
0x1400bccff  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400bcd04  mov     [rsp+28h+LockState.Flags], al
0x1400bcd08  call    cs:__imp_KeGetCurrentIrql
0x1400bcd0f  nop     dword ptr [rax+rax+00h]
0x1400bcd14  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bcd1b  lea     rdx, [rsp+28h+LockState]; LockState
0x1400bcd20  xor     r8d, r8d; Flags
0x1400bcd23  mov     bl, al
0x1400bcd25  call    cs:__imp_NdisAcquireRWLockWrite
0x1400bcd2c  nop     dword ptr [rax+rax+00h]
0x1400bcd31  cmp     bl, 2
0x1400bcd34  jz      short loc_1400BCD73
0x1400bcd36  cmp     cs:gWfpPerProContext, 0
0x1400bcd3e  jz      short loc_1400BCD73
0x1400bcd40  xor     ecx, ecx; ProcNumber
0x1400bcd42  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bcd49  nop     dword ptr [rax+rax+00h]
0x1400bcd4e  lea     ecx, [rax+rax*8]
0x1400bcd51  mov     rax, cs:gWfpPerProContext
0x1400bcd58  shl     ecx, 3
0x1400bcd5b  mov     rcx, [rcx+rax]
0x1400bcd5f  mov     rax, ds:0FFFFF78000000008h
0x1400bcd69  mov     [rcx+8], rax
0x1400bcd6d  mov     dword ptr [rcx], 4
0x1400bcd73  lea     rdx, [rdi+50h]; Entry
0x1400bcd77  xor     r8d, r8d; Context
0x1400bcd7a  lea     rcx, gAleMasterHashTable; HashTable
0x1400bcd81  call    cs:__imp_RtlRemoveEntryHashTable
0x1400bcd88  nop     dword ptr [rax+rax+00h]
0x1400bcd8d  mov     eax, [rdi+1Ch]
0x1400bcd90  test    al, 8
0x1400bcd92  jnz     loc_1400BCE49
0x1400bcd98  cmp     cs:gWfpPerProContext, 0
0x1400bcda0  jz      short loc_1400BCDCC
0x1400bcda2  xor     ecx, ecx; ProcNumber
0x1400bcda4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bcdab  nop     dword ptr [rax+rax+00h]
0x1400bcdb0  lea     ecx, [rax+rax*8]
0x1400bcdb3  mov     rax, cs:gWfpPerProContext
0x1400bcdba  shl     ecx, 3
0x1400bcdbd  mov     rcx, [rcx+rax]
0x1400bcdc1  cmp     dword ptr [rcx], 4
0x1400bcdc4  jnz     short loc_1400BCDCC
0x1400bcdc6  mov     dword ptr [rcx], 0
0x1400bcdcc  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bcdd3  lea     rdx, [rsp+28h+LockState]; LockState
0x1400bcdd8  call    cs:__imp_NdisReleaseRWLock
0x1400bcddf  nop     dword ptr [rax+rax+00h]
0x1400bcde4  mov     eax, cs:Feature_FWPS_BugFixes_25B__private_featureState
0x1400bcdea  test    al, 10h
0x1400bcdec  jnz     short loc_1400BCE44
0x1400bcdee  call    Feature_FWPS_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1400bcdf3  test    eax, eax
0x1400bcdf5  jz      short loc_1400BCE00
0x1400bcdf7  mov     rcx, [rdi+14h]
0x1400bcdfb  call    WfpRemoveModifiedIdCorrelationEntry
0x1400bce00  call    cs:__imp_KeGetCurrentIrql
0x1400bce07  nop     dword ptr [rax+rax+00h]
0x1400bce0c  test    al, al
0x1400bce0e  jz      short loc_1400BCE36
0x1400bce10  lea     rdx, [rdi+80h]
0x1400bce17  lea     rcx, tokenCleanupWorkQueue
0x1400bce1e  call    cs:__imp_NetioInsertWorkQueue
0x1400bce25  nop     dword ptr [rax+rax+00h]
0x1400bce2a  mov     rbx, [rsp+28h+arg_8]
0x1400bce2f  add     rsp, 20h
0x1400bce33  pop     rdi
0x1400bce34  retn
0x1400bce36  lea     rcx, [rdi+80h]
0x1400bce3d  call    WfpAleTokenCleanupWorkQueueRoutine
0x1400bce42  jmp     short loc_1400BCE2A
0x1400bce44  and     eax, 1
0x1400bce47  jmp     short loc_1400BCDF3
0x1400bce49  lea     rdx, [rdi+68h]; Entry
0x1400bce4d  xor     r8d, r8d; Context
0x1400bce50  lea     rcx, gAleMasterHashTable; HashTable
0x1400bce57  call    cs:__imp_RtlRemoveEntryHashTable
0x1400bce5e  nop     dword ptr [rax+rax+00h]
0x1400bce63  jmp     loc_1400BCD98
```
