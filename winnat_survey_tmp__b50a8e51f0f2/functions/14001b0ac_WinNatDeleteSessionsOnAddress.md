# WinNatDeleteSessionsOnAddress

- ea: `0x14001b0ac`
- end: `0x14001b1f6`
- name: `WinNatDeleteSessionsOnAddress`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140018c7c`
- `0x140018e40`
- `0x140018f48`
- `0x1400195fc`

## callees

- `0x140006b40`
- `0x14000a638`
- `0x14000ae68`
- `0x14000caa0`
- `0x14001b0ac`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b19d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b19d`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001b101`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001b101`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001b16e`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001b16e`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001b18d`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001b18d`

## pseudocode

```c
__int64 **__fastcall WinNatDeleteSessionsOnAddress(__int64 a1, struct _LIST_ENTRY *a2)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v4; // rdi
  struct _LIST_ENTRY *Blink; // rcx
  __int64 **v6; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v7; // rax
  __int64 v8; // rdx
  __int64 **v9; // rbx
  __int64 *v10; // rcx
  __int64 **result; // rax
  __int64 *v12; // rax
  __int64 *v13; // [rsp+20h] [rbp-50h] BYREF
  __int64 **v14; // [rsp+28h] [rbp-48h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-40h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+48h] [rbp-28h] BYREF

  v14 = &v13;
  v13 = (__int64 *)&v13;
  memset(&Enumerator, 0, sizeof(Enumerator));
  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLock(a1 + 64, &LockHandle);
  RtlInitWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
  while ( 1 )
  {
    v7 = RtlWeaklyEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
    v9 = (__int64 **)v7;
    if ( !v7 )
      break;
    v4 = v7 - 7;
    Blink = v7[-4].Linkage.Blink;
    if ( Blink[4].Blink == a2 )
    {
      if ( (BYTE4(v4[5].Linkage.Blink) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(Blink, v8);
      BYTE4(v4[5].Linkage.Blink) |= 1u;
      WinNatDeleteSessionEntryUnderLock(a1, (__int64)(v9 - 21));
      v6 = v14;
      if ( *v14 != (__int64 *)&v13 )
LABEL_13:
        __fastfail(3u);
      v9[1] = (__int64 *)v14;
      *v9 = (__int64 *)&v13;
      *v6 = (__int64 *)v9;
      v14 = v9;
    }
  }
  RtlEndWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 384), &Enumerator);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v10 = v13;
    result = &v13;
    if ( v13 == (__int64 *)&v13 )
      return result;
    if ( (__int64 **)v13[1] != &v13 )
      goto LABEL_13;
    v12 = (__int64 *)*v13;
    if ( *(__int64 **)(*v13 + 8) != v13 )
      goto LABEL_13;
    v13 = (__int64 *)*v13;
    v12[1] = (__int64)&v13;
    WinNatLibDereferenceSession(v10 - 21);
  }
}

```

## disassembly

```asm
0x14001b0ac  push    rbp
0x14001b0ae  push    rbx
0x14001b0af  push    rsi
0x14001b0b0  push    rdi
0x14001b0b1  push    r14
0x14001b0b3  mov     rbp, rsp
0x14001b0b6  sub     rsp, 70h
0x14001b0ba  xor     eax, eax
0x14001b0bc  xorps   xmm0, xmm0
0x14001b0bf  mov     qword ptr [rbp+Enumerator.BucketIndex], rax
0x14001b0c3  mov     r14, rdx
0x14001b0c6  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14001b0ca  lea     rdx, [rbp+LockHandle]
0x14001b0ce  lea     rax, [rbp+var_50]
0x14001b0d2  mov     rsi, rcx
0x14001b0d5  mov     [rbp+var_48], rax
0x14001b0d9  add     rcx, 40h ; '@'
0x14001b0dd  lea     rax, [rbp+var_50]
0x14001b0e1  mov     [rbp+var_50], rax
0x14001b0e5  movups  xmmword ptr [rbp+Enumerator], xmm0
0x14001b0e9  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14001b0ed  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14001b0f1  call    RtlAcquireScalableWriteLock
0x14001b0f6  mov     rcx, [rsi+180h]; HashTable
0x14001b0fd  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001b101  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14001b108  nop     dword ptr [rax+rax+00h]
0x14001b10d  jmp     short loc_14001B163
0x14001b10f  lea     rdi, [rbx-0A8h]
0x14001b116  mov     rcx, [rdi+50h]
0x14001b11a  cmp     [rcx+48h], r14
0x14001b11e  jnz     short loc_14001B163
0x14001b120  test    byte ptr [rdi+84h], 1
0x14001b127  jz      short loc_14001B12E
0x14001b129  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b12e  or      byte ptr [rdi+84h], 1
0x14001b135  mov     rdx, rdi
0x14001b138  mov     rcx, rsi
0x14001b13b  call    WinNatDeleteSessionEntryUnderLock
0x14001b140  mov     rax, [rbp+var_48]
0x14001b144  lea     rcx, [rbp+var_50]
0x14001b148  cmp     [rax], rcx
0x14001b14b  jnz     loc_14001B1E3
0x14001b151  mov     [rbx+8], rax
0x14001b155  lea     rcx, [rbp+var_50]
0x14001b159  mov     [rbx], rcx
0x14001b15c  mov     [rax], rbx
0x14001b15f  mov     [rbp+var_48], rbx
0x14001b163  mov     rcx, [rsi+180h]; HashTable
0x14001b16a  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001b16e  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
0x14001b175  nop     dword ptr [rax+rax+00h]
0x14001b17a  mov     rbx, rax
0x14001b17d  test    rax, rax
0x14001b180  jnz     short loc_14001B10F
0x14001b182  mov     rcx, [rsi+180h]; HashTable
0x14001b189  lea     rdx, [rbp+Enumerator]; Enumerator
0x14001b18d  call    cs:__imp_RtlEndWeakEnumerationHashTable
0x14001b194  nop     dword ptr [rax+rax+00h]
0x14001b199  lea     rcx, [rbp+LockHandle]; LockHandle
0x14001b19d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b1a4  nop     dword ptr [rax+rax+00h]
0x14001b1a9  mov     rcx, [rbp+var_50]
0x14001b1ad  lea     rax, [rbp+var_50]
0x14001b1b1  cmp     rcx, rax
0x14001b1b4  jz      short loc_14001B1EA
0x14001b1b6  lea     rax, [rbp+var_50]
0x14001b1ba  cmp     [rcx+8], rax
0x14001b1be  jnz     short loc_14001B1E3
0x14001b1c0  mov     rax, [rcx]
0x14001b1c3  cmp     [rax+8], rcx
0x14001b1c7  jnz     short loc_14001B1E3
0x14001b1c9  lea     rdx, [rbp+var_50]
0x14001b1cd  mov     [rbp+var_50], rax
0x14001b1d1  add     rcx, 0FFFFFFFFFFFFFF58h
0x14001b1d8  mov     [rax+8], rdx
0x14001b1dc  call    WinNatLibDereferenceSession
0x14001b1e1  jmp     short loc_14001B1A9
0x14001b1e3  mov     ecx, 3
0x14001b1e8  int     29h; Win8: RtlFailFast(ecx)
0x14001b1ea  add     rsp, 70h
0x14001b1ee  pop     r14
0x14001b1f0  pop     rdi
0x14001b1f1  pop     rsi
0x14001b1f2  pop     rbx
0x14001b1f3  pop     rbp
0x14001b1f4  retn
```
