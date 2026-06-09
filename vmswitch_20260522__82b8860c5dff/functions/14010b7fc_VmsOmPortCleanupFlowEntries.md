# VmsOmPortCleanupFlowEntries

- ea: `0x14010b7fc`
- end: `0x14010b968`
- name: `VmsOmPortCleanupFlowEntries`
- size: `364`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14010e360`
- `0x140156f60`
- `0x140157e10`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x14010b7fc`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010b8ea`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010b8ea`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010b92b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010b92b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010b90f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010b90f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010b87b`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010b87b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010b8fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010b8fb`
- `NDIS!NdisReleaseRWLock` at `0x14010b946`
- `NDIS!NdisReleaseRWLock` at `0x14010b946`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010b846`
- `NDIS!NdisAcquireRWLockWrite` at `0x14010b846`

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
0x14010b7fc  mov     r11, rsp
0x14010b7ff  mov     [r11+8], rbx
0x14010b803  mov     [r11+18h], rbp
0x14010b807  mov     [rsp+LockState.OldIrql], dl
0x14010b80b  push    rsi
0x14010b80c  push    rdi
0x14010b80d  push    r14
0x14010b80f  sub     rsp, 60h
0x14010b813  xor     eax, eax
0x14010b815  lea     rdx, [r11+10h]; LockState
0x14010b819  xorps   xmm0, xmm0
0x14010b81c  mov     [r11+10h], ax
0x14010b821  mov     r14b, r8b
0x14010b824  mov     [r11+12h], al
0x14010b828  mov     rdi, rcx
0x14010b82b  mov     r8b, 1; Flags
0x14010b82e  mov     rcx, [rcx+0B0h]; Lock
0x14010b835  mov     rsi, r9
0x14010b838  movups  xmmword ptr [rsp+78h+Enumerator.___u0], xmm0
0x14010b83d  movups  xmmword ptr [rsp+78h+Enumerator.___u0+10h], xmm0
0x14010b842  mov     [r11-28h], rax
0x14010b846  call    cs:__imp_NdisAcquireRWLockWrite
0x14010b84d  nop     dword ptr [rax+rax+00h]
0x14010b852  mov     rcx, 0FFFFF78000000008h
0x14010b85c  mov     rax, 0D6BF94D5E57A42BDh
0x14010b866  mov     rcx, [rcx]
0x14010b869  mul     rcx
0x14010b86c  mov     rcx, rdi; HashTable
0x14010b86f  mov     rbp, rdx
0x14010b872  lea     rdx, [rsp+78h+Enumerator]; Enumerator
0x14010b877  shr     rbp, 17h
0x14010b87b  call    cs:__imp_RtlInitEnumerationHashTable
0x14010b882  nop     dword ptr [rax+rax+00h]
0x14010b887  test    al, al
0x14010b889  jnz     short loc_14010B907
0x14010b88b  mov     rcx, cs:VmsIfrLog
0x14010b892  lea     rax, aSuccess; "success"
0x14010b899  mov     [rsp+78h+var_50], rax
0x14010b89e  mov     r9d, 67h ; 'g'
0x14010b8a4  lea     rax, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010b8ab  mov     [rsp+78h+var_58], rax
0x14010b8b0  lea     r8d, [r9-54h]
0x14010b8b4  call    WPP_RECORDER_SF_s
0x14010b8b9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14010b8be  jmp     short loc_14010B907
0x14010b8c0  cmp     rbp, [rbx+68h]
0x14010b8c4  jnb     short loc_14010B8E1
0x14010b8c6  test    rsi, rsi
0x14010b8c9  jz      short loc_14010B8D1
0x14010b8cb  cmp     [rbx+58h], rsi
0x14010b8cf  jz      short loc_14010B8E1
0x14010b8d1  test    r14b, r14b
0x14010b8d4  jz      short loc_14010B907
0x14010b8d6  mov     eax, [rbx+50h]
0x14010b8d9  sub     eax, 2
0x14010b8dc  cmp     eax, 1
0x14010b8df  jbe     short loc_14010B907
0x14010b8e1  xor     r8d, r8d; Context
0x14010b8e4  mov     rdx, rbx; Entry
0x14010b8e7  mov     rcx, rdi; HashTable
0x14010b8ea  call    cs:__imp_RtlRemoveEntryHashTable
0x14010b8f1  nop     dword ptr [rax+rax+00h]
0x14010b8f6  xor     edx, edx; Tag
0x14010b8f8  mov     rcx, rbx; P
0x14010b8fb  call    cs:__imp_ExFreePoolWithTag
0x14010b902  nop     dword ptr [rax+rax+00h]
0x14010b907  lea     rdx, [rsp+78h+Enumerator]; Enumerator
0x14010b90c  mov     rcx, rdi; HashTable
0x14010b90f  call    cs:__imp_RtlEnumerateEntryHashTable
0x14010b916  nop     dword ptr [rax+rax+00h]
0x14010b91b  mov     rbx, rax
0x14010b91e  test    rax, rax
0x14010b921  jnz     short loc_14010B8C0
0x14010b923  lea     rdx, [rsp+78h+Enumerator]; Enumerator
0x14010b928  mov     rcx, rdi; HashTable
0x14010b92b  call    cs:__imp_RtlEndEnumerationHashTable
0x14010b932  nop     dword ptr [rax+rax+00h]
0x14010b937  mov     rcx, [rdi+0B0h]; Lock
0x14010b93e  lea     rdx, [rsp+78h+LockState]; LockState
0x14010b946  call    cs:__imp_NdisReleaseRWLock
0x14010b94d  nop     dword ptr [rax+rax+00h]
0x14010b952  lea     r11, [rsp+78h+var_18]
0x14010b957  mov     rbx, [r11+20h]
0x14010b95b  mov     rbp, [r11+30h]
0x14010b95f  mov     rsp, r11
0x14010b962  pop     r14
0x14010b964  pop     rdi
0x14010b965  pop     rsi
0x14010b966  retn
```
