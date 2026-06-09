# WfpAlepTokenInformationCleanup

- ea: `0x1400bcd20`
- end: `0x1400bce98`
- name: `WfpAlepTokenInformationCleanup`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400bac20`

## callees

- `0x1400bcd20`
- `0x1400bcea0`
- `0x1400bd010`
- `0x14014ce6c`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bcdb1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bce87`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bcdb1`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1400bce87`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcd72`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcdd4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcd72`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400bcdd4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bcd38`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bce30`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bcd38`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bce30`
- `NETIO!NetioInsertWorkQueue` at `0x1400bce4e`
- `NETIO!NetioInsertWorkQueue` at `0x1400bce4e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bcd55`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400bcd55`
- `NDIS!NdisReleaseRWLock` at `0x1400bce08`
- `NDIS!NdisReleaseRWLock` at `0x1400bce08`

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
0x1400bcd20  mov     [rsp+arg_8], rbx
0x1400bcd25  push    rdi
0x1400bcd26  sub     rsp, 20h
0x1400bcd2a  xor     eax, eax
0x1400bcd2c  mov     rdi, rcx
0x1400bcd2f  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400bcd34  mov     [rsp+28h+LockState.Flags], al
0x1400bcd38  call    cs:__imp_KeGetCurrentIrql
0x1400bcd3f  nop     dword ptr [rax+rax+00h]
0x1400bcd44  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bcd4b  lea     rdx, [rsp+28h+LockState]; LockState
0x1400bcd50  xor     r8d, r8d; Flags
0x1400bcd53  mov     bl, al
0x1400bcd55  call    cs:__imp_NdisAcquireRWLockWrite
0x1400bcd5c  nop     dword ptr [rax+rax+00h]
0x1400bcd61  cmp     bl, 2
0x1400bcd64  jz      short loc_1400BCDA3
0x1400bcd66  cmp     cs:gWfpPerProContext, 0
0x1400bcd6e  jz      short loc_1400BCDA3
0x1400bcd70  xor     ecx, ecx; ProcNumber
0x1400bcd72  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bcd79  nop     dword ptr [rax+rax+00h]
0x1400bcd7e  lea     ecx, [rax+rax*8]
0x1400bcd81  mov     rax, cs:gWfpPerProContext
0x1400bcd88  shl     ecx, 3
0x1400bcd8b  mov     rcx, [rcx+rax]
0x1400bcd8f  mov     rax, ds:0FFFFF78000000008h
0x1400bcd99  mov     [rcx+8], rax
0x1400bcd9d  mov     dword ptr [rcx], 4
0x1400bcda3  lea     rdx, [rdi+50h]; Entry
0x1400bcda7  xor     r8d, r8d; Context
0x1400bcdaa  lea     rcx, gAleMasterHashTable; HashTable
0x1400bcdb1  call    cs:__imp_RtlRemoveEntryHashTable
0x1400bcdb8  nop     dword ptr [rax+rax+00h]
0x1400bcdbd  mov     eax, [rdi+1Ch]
0x1400bcdc0  test    al, 8
0x1400bcdc2  jnz     loc_1400BCE79
0x1400bcdc8  cmp     cs:gWfpPerProContext, 0
0x1400bcdd0  jz      short loc_1400BCDFC
0x1400bcdd2  xor     ecx, ecx; ProcNumber
0x1400bcdd4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400bcddb  nop     dword ptr [rax+rax+00h]
0x1400bcde0  lea     ecx, [rax+rax*8]
0x1400bcde3  mov     rax, cs:gWfpPerProContext
0x1400bcdea  shl     ecx, 3
0x1400bcded  mov     rcx, [rcx+rax]
0x1400bcdf1  cmp     dword ptr [rcx], 4
0x1400bcdf4  jnz     short loc_1400BCDFC
0x1400bcdf6  mov     dword ptr [rcx], 0
0x1400bcdfc  mov     rcx, cs:gAleHashtableLock; Lock
0x1400bce03  lea     rdx, [rsp+28h+LockState]; LockState
0x1400bce08  call    cs:__imp_NdisReleaseRWLock
0x1400bce0f  nop     dword ptr [rax+rax+00h]
0x1400bce14  mov     eax, cs:Feature_FWPS_BugFixes_25B__private_featureState
0x1400bce1a  test    al, 10h
0x1400bce1c  jnz     short loc_1400BCE74
0x1400bce1e  call    Feature_FWPS_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x1400bce23  test    eax, eax
0x1400bce25  jz      short loc_1400BCE30
0x1400bce27  mov     rcx, [rdi+14h]
0x1400bce2b  call    WfpRemoveModifiedIdCorrelationEntry
0x1400bce30  call    cs:__imp_KeGetCurrentIrql
0x1400bce37  nop     dword ptr [rax+rax+00h]
0x1400bce3c  test    al, al
0x1400bce3e  jz      short loc_1400BCE66
0x1400bce40  lea     rdx, [rdi+80h]
0x1400bce47  lea     rcx, tokenCleanupWorkQueue
0x1400bce4e  call    cs:__imp_NetioInsertWorkQueue
0x1400bce55  nop     dword ptr [rax+rax+00h]
0x1400bce5a  mov     rbx, [rsp+28h+arg_8]
0x1400bce5f  add     rsp, 20h
0x1400bce63  pop     rdi
0x1400bce64  retn
0x1400bce66  lea     rcx, [rdi+80h]
0x1400bce6d  call    WfpAleTokenCleanupWorkQueueRoutine
0x1400bce72  jmp     short loc_1400BCE5A
0x1400bce74  and     eax, 1
0x1400bce77  jmp     short loc_1400BCE23
0x1400bce79  lea     rdx, [rdi+68h]; Entry
0x1400bce7d  xor     r8d, r8d; Context
0x1400bce80  lea     rcx, gAleMasterHashTable; HashTable
0x1400bce87  call    cs:__imp_RtlRemoveEntryHashTable
0x1400bce8e  nop     dword ptr [rax+rax+00h]
0x1400bce93  jmp     loc_1400BCDC8
```
