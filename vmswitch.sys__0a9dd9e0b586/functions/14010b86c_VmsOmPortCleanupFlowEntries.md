# VmsOmPortCleanupFlowEntries

- ea: `0x14010b86c`
- end: `0x14010b9d8`
- name: `VmsOmPortCleanupFlowEntries`
- size: `364`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14010e3d0`
- `0x140156fd0`
- `0x140157e80`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x14010b86c`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010b95a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010b95a`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010b99b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010b99b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010b97f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010b97f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010b8eb`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010b8eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010b96b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010b96b`
- `NDIS!NdisReleaseRWLock` at `0x14010b9b6`
- `NDIS!NdisReleaseRWLock` at `0x14010b9b6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010b8b6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010b8b6`

## pseudocode

```c
void __fastcall VmsOmPortCleanupFlowEntries(PRTL_DYNAMIC_HASH_TABLE HashTable, __int64 a2, char a3, __int64 a4)
{
  struct _NDIS_RW_LOCK_EX *v6; // rcx
  unsigned __int64 v8; // rbp
  int v9; // edx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v10; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v11; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = *(struct _NDIS_RW_LOCK_EX **)&HashTable[4].DivisorMask;
  memset(&Enumerator, 0, sizeof(Enumerator));
  NdisAcquireRWLockWrite(v6, &LockState, 1u);
  v8 = MEMORY[0xFFFFF78000000008] / 0x989680uLL;
  if ( !RtlInitEnumerationHashTable(HashTable, &Enumerator) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v9,
      19,
      103,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      "success",
      *(_OWORD *)&Enumerator.HashEntry.Linkage,
      Enumerator.HashEntry.Signature,
      Enumerator.ChainHead,
      *(_QWORD *)&Enumerator.BucketIndex);
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  while ( 1 )
  {
    v10 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
    v11 = v10;
    if ( !v10 )
      break;
    if ( (_LIST_ENTRY *)v8 >= v10[4].Linkage.Blink
      || a4 && v10[3].Signature == a4
      || a3 && (unsigned int)(LODWORD(v10[3].Linkage.Blink) - 2) > 1 )
    {
      RtlRemoveEntryHashTable(HashTable, v10, 0);
      ExFreePoolWithTag(v11, 0);
    }
  }
  RtlEndEnumerationHashTable(HashTable, &Enumerator);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)&HashTable[4].DivisorMask, &LockState);
}

```

## disassembly

```asm
0x14010b86c  mov     r11, rsp
0x14010b86f  mov     [r11+8], rbx
0x14010b873  mov     [r11+18h], rbp
0x14010b877  mov     [rsp+LockState.OldIrql], dl
0x14010b87b  push    rsi
0x14010b87c  push    rdi
0x14010b87d  push    r14
0x14010b87f  sub     rsp, 60h
0x14010b883  xor     eax, eax
0x14010b885  lea     rdx, [r11+10h]; LockState
0x14010b889  xorps   xmm0, xmm0
0x14010b88c  mov     [r11+10h], ax
0x14010b891  mov     r14b, r8b
0x14010b894  mov     [r11+12h], al
0x14010b898  mov     rdi, rcx
0x14010b89b  mov     r8b, 1; Flags
0x14010b89e  mov     rcx, [rcx+0B0h]; Lock
0x14010b8a5  mov     rsi, r9
0x14010b8a8  movups  xmmword ptr [rsp+78h+Enumerator.___u0], xmm0
0x14010b8ad  movups  xmmword ptr [rsp+78h+Enumerator.___u0+10h], xmm0
0x14010b8b2  mov     [r11-28h], rax
0x14010b8b6  call    cs:__imp_NdisAcquireRWLockWrite
0x14010b8bd  nop     dword ptr [rax+rax+00h]
0x14010b8c2  mov     rcx, 0FFFFF78000000008h
0x14010b8cc  mov     rax, 0D6BF94D5E57A42BDh
0x14010b8d6  mov     rcx, [rcx]
0x14010b8d9  mul     rcx
0x14010b8dc  mov     rcx, rdi; HashTable
0x14010b8df  mov     rbp, rdx
0x14010b8e2  lea     rdx, [rsp+78h+Enumerator]; Enumerator
0x14010b8e7  shr     rbp, 17h
0x14010b8eb  call    cs:__imp_RtlInitEnumerationHashTable
0x14010b8f2  nop     dword ptr [rax+rax+00h]
0x14010b8f7  test    al, al
0x14010b8f9  jnz     short loc_14010B977
0x14010b8fb  mov     rcx, cs:VmsIfrLog
0x14010b902  lea     rax, aSuccess; "success"
0x14010b909  mov     [rsp+78h+var_50], rax
0x14010b90e  mov     r9d, 67h ; 'g'
0x14010b914  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010b91b  mov     [rsp+78h+var_58], rax
0x14010b920  lea     r8d, [r9-54h]
0x14010b924  call    WPP_RECORDER_SF_s
0x14010b929  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14010b92e  jmp     short loc_14010B977
0x14010b930  cmp     rbp, [rbx+68h]
0x14010b934  jnb     short loc_14010B951
0x14010b936  test    rsi, rsi
0x14010b939  jz      short loc_14010B941
0x14010b93b  cmp     [rbx+58h], rsi
0x14010b93f  jz      short loc_14010B951
0x14010b941  test    r14b, r14b
0x14010b944  jz      short loc_14010B977
0x14010b946  mov     eax, [rbx+50h]
0x14010b949  sub     eax, 2
0x14010b94c  cmp     eax, 1
0x14010b94f  jbe     short loc_14010B977
0x14010b951  xor     r8d, r8d; Context
0x14010b954  mov     rdx, rbx; Entry
0x14010b957  mov     rcx, rdi; HashTable
0x14010b95a  call    cs:__imp_RtlRemoveEntryHashTable
0x14010b961  nop     dword ptr [rax+rax+00h]
0x14010b966  xor     edx, edx; Tag
0x14010b968  mov     rcx, rbx; P
0x14010b96b  call    cs:__imp_ExFreePoolWithTag
0x14010b972  nop     dword ptr [rax+rax+00h]
0x14010b977  lea     rdx, [rsp+78h+Enumerator]; Enumerator
0x14010b97c  mov     rcx, rdi; HashTable
0x14010b97f  call    cs:__imp_RtlEnumerateEntryHashTable
0x14010b986  nop     dword ptr [rax+rax+00h]
0x14010b98b  mov     rbx, rax
0x14010b98e  test    rax, rax
0x14010b991  jnz     short loc_14010B930
0x14010b993  lea     rdx, [rsp+78h+Enumerator]; Enumerator
0x14010b998  mov     rcx, rdi; HashTable
0x14010b99b  call    cs:__imp_RtlEndEnumerationHashTable
0x14010b9a2  nop     dword ptr [rax+rax+00h]
0x14010b9a7  mov     rcx, [rdi+0B0h]; Lock
0x14010b9ae  lea     rdx, [rsp+78h+LockState]; LockState
0x14010b9b6  call    cs:__imp_NdisReleaseRWLock
0x14010b9bd  nop     dword ptr [rax+rax+00h]
0x14010b9c2  lea     r11, [rsp+78h+var_18]
0x14010b9c7  mov     rbx, [r11+20h]
0x14010b9cb  mov     rbp, [r11+30h]
0x14010b9cf  mov     rsp, r11
0x14010b9d2  pop     r14
0x14010b9d4  pop     rdi
0x14010b9d5  pop     rsi
0x14010b9d6  retn
```
