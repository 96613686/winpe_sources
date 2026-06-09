# WinNatDeleteSessionsOnAddress

- ea: `0x14001b58c`
- end: `0x14001b6d6`
- name: `WinNatDeleteSessionsOnAddress`
- size: `330`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001915c`
- `0x140019320`
- `0x140019428`
- `0x140019adc`

## callees

- `0x140006b40`
- `0x14000a638`
- `0x14000ae68`
- `0x14000caa0`
- `0x14001b58c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b67d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b67d`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001b5e1`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001b5e1`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001b64e`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001b64e`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001b66d`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001b66d`

## pseudocode

```c
__int64 **__fastcall WinNatDeleteSessionsOnAddress(__int64 a1, struct _LIST_ENTRY *a2)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v4; // rdi
  struct _LIST_ENTRY *Blink; // rcx
  __int64 **v6; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 **v10; // rbx
  __int64 *v11; // rcx
  __int64 **result; // rax
  __int64 *v13; // rax
  __int64 *v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 **v15; // [rsp+28h] [rbp-48h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-40h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+48h] [rbp-28h] BYREF

  v15 = &v14;
  v14 = (__int64 *)&v14;
  memset(&Enumerator, 0, sizeof(Enumerator));
  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  RtlInitWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
  while ( 1 )
  {
    v7 = RtlWeaklyEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
    v10 = (__int64 **)v7;
    if ( !v7 )
      break;
    v4 = v7 - 7;
    Blink = v7[-4].Linkage.Blink;
    if ( Blink[4].Blink == a2 )
    {
      if ( (BYTE4(v4[5].Linkage.Blink) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(Blink, v8, v9);
      BYTE4(v4[5].Linkage.Blink) |= 1u;
      WinNatDeleteSessionEntryUnderLock(a1, (__int64)(v10 - 21));
      v6 = v15;
      if ( *v15 != (__int64 *)&v14 )
LABEL_13:
        __fastfail(3u);
      v10[1] = (__int64 *)v15;
      *v10 = (__int64 *)&v14;
      *v6 = (__int64 *)v10;
      v15 = v10;
    }
  }
  RtlEndWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v11 = v14;
    result = &v14;
    if ( v14 == (__int64 *)&v14 )
      return result;
    if ( (__int64 **)v14[1] != &v14 )
      goto LABEL_13;
    v13 = (__int64 *)*v14;
    if ( *(__int64 **)(*v14 + 8) != v14 )
      goto LABEL_13;
    v14 = (__int64 *)*v14;
    v13[1] = (__int64)&v14;
    WinNatLibDereferenceSession(v11 - 21);
  }
}

```

## disassembly

```asm
0x14001b58c  push    rbp
0x14001b58e  push    rbx
0x14001b58f  push    rsi
0x14001b590  push    rdi
0x14001b591  push    r14
0x14001b593  mov     rbp, rsp
0x14001b596  sub     rsp, 70h
0x14001b59a  xor     eax, eax
0x14001b59c  xorps   xmm0, xmm0
0x14001b59f  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x14001b5a3  mov     r14, rdx
0x14001b5a6  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14001b5aa  lea     rdx, [rbp+LockHandle]
0x14001b5ae  lea     rax, [rbp+var_50]
0x14001b5b2  mov     rsi, rcx
0x14001b5b5  mov     [rbp+var_48], rax
0x14001b5b9  add     rcx, 40h ; '@'
0x14001b5bd  lea     rax, [rbp+var_50]
0x14001b5c1  mov     [rbp+var_50], rax
0x14001b5c5  movups  xmmword ptr [rbp+Enumerator], xmm0
0x14001b5c9  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14001b5cd  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14001b5d1  call    RtlAcquireScalableWriteLock
0x14001b5d6  mov     rcx, [rsi+180h]; HashTable
0x14001b5dd  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001b5e1  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14001b5e8  nop     dword ptr [rax+rax+00h]
0x14001b5ed  jmp     short loc_14001B643
0x14001b5ef  lea     rdi, [rbx-0A8h]
0x14001b5f6  mov     rcx, [rdi+50h]
0x14001b5fa  cmp     [rcx+48h], r14
0x14001b5fe  jnz     short loc_14001B643
0x14001b600  test    byte ptr [rdi+84h], 1
0x14001b607  jz      short loc_14001B60E
0x14001b609  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b60e  or      byte ptr [rdi+84h], 1
0x14001b615  mov     rdx, rdi
0x14001b618  mov     rcx, rsi
0x14001b61b  call    WinNatDeleteSessionEntryUnderLock
0x14001b620  mov     rax, [rbp+var_48]
0x14001b624  lea     rcx, [rbp+var_50]
0x14001b628  cmp     [rax], rcx
0x14001b62b  jnz     loc_14001B6C3
0x14001b631  mov     [rbx+8], rax
0x14001b635  lea     rcx, [rbp+var_50]
0x14001b639  mov     [rbx], rcx
0x14001b63c  mov     [rax], rbx
0x14001b63f  mov     [rbp+var_48], rbx
0x14001b643  mov     rcx, [rsi+180h]; HashTable
0x14001b64a  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001b64e  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
0x14001b655  nop     dword ptr [rax+rax+00h]
0x14001b65a  mov     rbx, rax
0x14001b65d  test    rax, rax
0x14001b660  jnz     short loc_14001B5EF
0x14001b662  mov     rcx, [rsi+180h]; HashTable
0x14001b669  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001b66d  call    cs:__imp_RtlEndWeakEnumerationHashTable
0x14001b674  nop     dword ptr [rax+rax+00h]
0x14001b679  lea     rcx, [rbp+LockHandle]; LockHandle
0x14001b67d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b684  nop     dword ptr [rax+rax+00h]
0x14001b689  mov     rcx, [rbp+var_50]
0x14001b68d  lea     rax, [rbp+var_50]
0x14001b691  cmp     rcx, rax
0x14001b694  jz      short loc_14001B6CA
0x14001b696  lea     rax, [rbp+var_50]
0x14001b69a  cmp     [rcx+8], rax
0x14001b69e  jnz     short loc_14001B6C3
0x14001b6a0  mov     rax, [rcx]
0x14001b6a3  cmp     [rax+8], rcx
0x14001b6a7  jnz     short loc_14001B6C3
0x14001b6a9  lea     rdx, [rbp+var_50]
0x14001b6ad  mov     [rbp+var_50], rax
0x14001b6b1  add     rcx, 0FFFFFFFFFFFFFF58h
0x14001b6b8  mov     [rax+8], rdx
0x14001b6bc  call    WinNatLibDereferenceSession
0x14001b6c1  jmp     short loc_14001B689
0x14001b6c3  mov     ecx, 3
0x14001b6c8  int     29h; Win8: RtlFailFast(ecx)
0x14001b6ca  add     rsp, 70h
0x14001b6ce  pop     r14
0x14001b6d0  pop     rdi
0x14001b6d1  pop     rsi
0x14001b6d2  pop     rbx
0x14001b6d3  pop     rbp
0x14001b6d4  retn
```
