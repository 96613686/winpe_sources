# WinNatLibCreateStaticBindingEntry

- ea: `0x14001b50c`
- end: `0x14001b7d5`
- name: `WinNatLibCreateStaticBindingEntry`
- size: `713`
- prototype: `__int64 __fastcall(_QWORD *, __int16 *, __int64, unsigned int, unsigned __int8, char, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011718`
- `0x1400308ac`

## callees

- `0x1400061d0`
- `0x140006b40`
- `0x14000a638`
- `0x14000ae68`
- `0x14000caa0`
- `0x14001a398`
- `0x14001b50c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b770`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b770`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001b59d`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001b59d`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001b5c1`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001b5c1`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001b723`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001b723`

## pseudocode

```c
__int64 __fastcall WinNatLibCreateStaticBindingEntry(
        _QWORD *a1,
        __int16 *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        char a6,
        unsigned __int8 *a7,
        int a8)
{
  _QWORD *v8; // r15
  char v9; // bl
  int v10; // r12d
  bool v11; // zf
  bool v13; // r13
  char v14; // si
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // rax
  __int64 **v16; // rdi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v17; // rbx
  struct _LIST_ENTRY *Blink; // rsi
  __int16 v19; // ax
  __int64 v20; // rdx
  __int64 v21; // rcx
  char v22; // di
  __int64 **v23; // rax
  __int64 *v24; // rcx
  __int64 *v25; // rax
  __int64 *v27; // [rsp+58h] [rbp-51h] BYREF
  __int64 **v28; // [rsp+60h] [rbp-49h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-41h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+80h] [rbp-29h] BYREF
  char v33; // [rsp+108h] [rbp+5Fh]

  v8 = a1 + 16;
  v9 = 0;
  v10 = 0;
  v33 = 0;
  v11 = *(_WORD *)a3 == 2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&Enumerator, 0, sizeof(Enumerator));
  v13 = v11 && !*(_DWORD *)(a3 + 4);
  v28 = &v27;
  v27 = (__int64 *)&v27;
  RtlAcquireScalableWriteLock(a1 + 24, &LockHandle);
  RtlInitWeakEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)v8[48], &Enumerator);
  v14 = a6;
  while ( 1 )
  {
    v15 = RtlWeaklyEnumerateEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)v8[48], &Enumerator);
    v16 = (__int64 **)v15;
    if ( !v15 )
      break;
    v17 = v15 - 7;
    if ( LODWORD(v15[-2].Linkage.Flink) != a5 )
      goto LABEL_7;
    Blink = v17[4].Linkage.Blink;
    if ( (unsigned __int8)WinNatCompareTransportAndSockAddr(Blink, a3, 0) )
      goto LABEL_41;
    if ( !v13 || LOWORD(Blink->Flink) != 2 )
    {
      v14 = a6;
      goto LABEL_7;
    }
    v19 = WORD1(Blink->Flink);
    v14 = a6;
    if ( *(_WORD *)(a3 + 2) == v19 )
    {
LABEL_41:
      if ( !(unsigned __int8)WinNatCompareTransportAndSockAddr(v17[3].Signature, a2, 0)
        || (v21 = a4, LODWORD(v17->Linkage.Blink) != a4) )
      {
        v14 = a6;
        if ( a6 && ((__int64)v17[3].Linkage.Blink[5].Blink & 8) != 0 )
          goto LABEL_7;
        if ( (BYTE4(v17[5].Linkage.Blink) & 1) != 0 )
LABEL_26:
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v20);
LABEL_27:
        BYTE4(v17[5].Linkage.Blink) |= 1u;
        WinNatDeleteSessionEntryUnderLock(v8, v17);
        v23 = v28;
        if ( *v28 != (__int64 *)&v27 )
LABEL_37:
          __fastfail(3u);
        *v16 = (__int64 *)&v27;
        v16[1] = (__int64 *)v23;
        *v23 = (__int64 *)v16;
        v28 = v16;
        goto LABEL_7;
      }
      v20 = (__int64)v17[3].Linkage.Blink;
      v14 = a6;
      if ( ((*(_BYTE *)(v20 + 88) & 8) != 0) != a6 || v13 )
      {
        if ( (BYTE4(v17[5].Linkage.Blink) & 1) != 0 )
          goto LABEL_26;
        goto LABEL_27;
      }
      v9 = v33;
      if ( !v33 )
      {
        v22 = a5;
        v9 = 1;
        v10 = WinNatLibReserveBinding(a1, v20, (__int16 *)a3, a2, a4, a5, a6, a7, a8);
        v33 = 1;
        if ( v10 < 0 )
          goto LABEL_30;
      }
    }
    else
    {
LABEL_7:
      v9 = v33;
    }
  }
  v22 = a5;
LABEL_30:
  RtlEndWeakEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)v8[48], &Enumerator);
  if ( !v9 )
    v10 = WinNatLibReserveBinding(a1, 0, (__int16 *)a3, a2, a4, v22, v14, a7, a8);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v24 = v27;
    if ( v27 == (__int64 *)&v27 )
      return (unsigned int)v10;
    if ( (__int64 **)v27[1] != &v27 )
      goto LABEL_37;
    v25 = (__int64 *)*v27;
    if ( *(__int64 **)(*v27 + 8) != v27 )
      goto LABEL_37;
    v27 = (__int64 *)*v27;
    v25[1] = (__int64)&v27;
    WinNatLibDereferenceSession(v24 - 21);
  }
}

```

## disassembly

```asm
0x14001b50c  mov     rax, rsp
0x14001b50f  mov     [rax+20h], r9d
0x14001b513  mov     [rax+10h], rdx
0x14001b517  mov     [rax+8], rcx
0x14001b51b  push    rbp
0x14001b51c  push    rbx
0x14001b51d  push    rsi
0x14001b51e  push    rdi
0x14001b51f  push    r12
0x14001b521  push    r13
0x14001b523  push    r14
0x14001b525  push    r15
0x14001b527  lea     rbp, [rax-47h]
0x14001b52b  sub     rsp, 0A8h
0x14001b532  xor     eax, eax
0x14001b534  lea     r15, [rcx+80h]
0x14001b53b  xor     bl, bl
0x14001b53d  mov     qword ptr [rbp+3Fh+LockHandle.OldIrql], rax
0x14001b541  xorps   xmm1, xmm1
0x14001b544  mov     qword ptr [rbp+3Fh+Enumerator.BucketIndex], rax
0x14001b548  xor     r12d, r12d
0x14001b54b  mov     [rbp+3Fh+arg_10], bl
0x14001b54e  cmp     word ptr [r8], 2
0x14001b553  xorps   xmm0, xmm0
0x14001b556  mov     r14, r8
0x14001b559  movups  xmmword ptr [rbp+3Fh+LockHandle.LockQueue.Next], xmm0
0x14001b55d  movups  xmmword ptr [rbp+3Fh+Enumerator], xmm1
0x14001b561  movups  xmmword ptr [rbp+3Fh+Enumerator+10h], xmm1
0x14001b565  jnz     short loc_14001B572
0x14001b567  cmp     [r8+4], eax
0x14001b56b  jnz     short loc_14001B572
0x14001b56d  mov     r13b, 1
0x14001b570  jmp     short loc_14001B575
0x14001b572  xor     r13b, r13b
0x14001b575  lea     rax, [rbp+3Fh+var_90]
0x14001b579  mov     [rbp+3Fh+var_88], rax
0x14001b57d  lea     rcx, [r15+40h]
0x14001b581  lea     rax, [rbp+3Fh+var_90]
0x14001b585  lea     rdx, [rbp+3Fh+LockHandle]
0x14001b589  mov     [rbp+3Fh+var_90], rax
0x14001b58d  call    RtlAcquireScalableWriteLock
0x14001b592  mov     rcx, [r15+180h]; HashTable
0x14001b599  lea     rdx, [rbp+3Fh+Enumerator]; Enumerator
0x14001b59d  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14001b5a4  nop     dword ptr [rax+rax+00h]
0x14001b5a9  mov     sil, [rbp+3Fh+arg_28]
0x14001b5ad  jmp     short loc_14001B5B6
0x14001b5af  mov     sil, [rbp+3Fh+arg_28]
0x14001b5b3  mov     bl, [rbp+3Fh+arg_10]
0x14001b5b6  mov     rcx, [r15+180h]; HashTable
0x14001b5bd  lea     rdx, [rbp+3Fh+Enumerator]; Enumerator
0x14001b5c1  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
0x14001b5c8  nop     dword ptr [rax+rax+00h]
0x14001b5cd  mov     rdi, rax
0x14001b5d0  test    rax, rax
0x14001b5d3  jz      loc_14001B714
0x14001b5d9  lea     rbx, [rax-0A8h]
0x14001b5e0  movzx   eax, [rbp+3Fh+arg_20]
0x14001b5e4  cmp     [rbx+78h], eax
0x14001b5e7  jnz     short loc_14001B5B3
0x14001b5e9  mov     rsi, [rbx+68h]
0x14001b5ed  xor     r8d, r8d
0x14001b5f0  mov     rcx, rsi
0x14001b5f3  mov     rdx, r14
0x14001b5f6  call    WinNatCompareTransportAndSockAddr
0x14001b5fb  test    al, al
0x14001b5fd  jnz     short loc_14001B619
0x14001b5ff  test    r13b, r13b
0x14001b602  jz      short loc_14001B5AF
0x14001b604  cmp     word ptr [rsi], 2
0x14001b608  jnz     short loc_14001B5AF
0x14001b60a  movzx   eax, word ptr [rsi+2]
0x14001b60e  mov     sil, [rbp+3Fh+arg_28]
0x14001b612  cmp     [r14+2], ax
0x14001b617  jnz     short loc_14001B5B3
0x14001b619  mov     rdx, [rbp+3Fh+arg_8]
0x14001b61d  xor     r8d, r8d
0x14001b620  mov     rcx, [rbx+58h]
0x14001b624  call    WinNatCompareTransportAndSockAddr
0x14001b629  test    al, al
0x14001b62b  jz      loc_14001B6B5
0x14001b631  mov     ecx, [rbp+3Fh+arg_18]
0x14001b634  cmp     [rbx+8], ecx
0x14001b637  jnz     short loc_14001B6B5
0x14001b639  mov     rdx, [rbx+50h]
0x14001b63d  mov     sil, [rbp+3Fh+arg_28]
0x14001b641  mov     al, [rdx+58h]
0x14001b644  shr     al, 3
0x14001b647  and     al, 1
0x14001b649  cmp     al, sil
0x14001b64c  jnz     short loc_14001B6A5
0x14001b64e  test    r13b, r13b
0x14001b651  jnz     short loc_14001B6A5
0x14001b653  mov     bl, [rbp+3Fh+arg_10]
0x14001b656  test    bl, bl
0x14001b658  jnz     loc_14001B5B6
0x14001b65e  mov     eax, [rbp+3Fh+arg_38]
0x14001b664  mov     r8, r14
0x14001b667  mov     dil, [rbp+3Fh+arg_20]
0x14001b66b  mov     r9, [rbp+3Fh+arg_8]
0x14001b66f  mov     [rsp+40h], eax
0x14001b673  mov     rax, [rbp+3Fh+arg_30]
0x14001b677  mov     qword ptr [rsp+0E0h+var_A8], rax
0x14001b67c  mov     byte ptr [rsp+0E0h+var_B0], sil
0x14001b681  mov     [rsp+0E0h+var_B8], dil
0x14001b686  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x14001b68a  mov     rcx, [rbp+3Fh+arg_0]
0x14001b68e  call    WinNatLibReserveBinding
0x14001b693  mov     bl, 1
0x14001b695  mov     r12d, eax
0x14001b698  mov     [rbp+3Fh+arg_10], bl
0x14001b69b  test    eax, eax
0x14001b69d  jns     loc_14001B5B6
0x14001b6a3  jmp     short loc_14001B718
0x14001b6a5  test    byte ptr [rbx+84h], 1
0x14001b6ac  jz      short loc_14001B6DA
0x14001b6ae  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b6b3  jmp     short loc_14001B6DA
0x14001b6b5  mov     sil, [rbp+3Fh+arg_28]
0x14001b6b9  test    sil, sil
0x14001b6bc  jz      short loc_14001B6CC
0x14001b6be  mov     rax, [rbx+50h]
0x14001b6c2  test    byte ptr [rax+58h], 8
0x14001b6c6  jnz     loc_14001B5B3
0x14001b6cc  test    byte ptr [rbx+84h], 1
0x14001b6d3  jz      short loc_14001B6DA
0x14001b6d5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001b6da  or      byte ptr [rbx+84h], 1
0x14001b6e1  mov     rdx, rbx
0x14001b6e4  mov     rcx, r15
0x14001b6e7  call    WinNatDeleteSessionEntryUnderLock
0x14001b6ec  mov     rax, [rbp+3Fh+var_88]
0x14001b6f0  lea     rcx, [rbp+3Fh+var_90]
0x14001b6f4  cmp     [rax], rcx
0x14001b6f7  jnz     loc_14001B7B6
0x14001b6fd  lea     rcx, [rbp+3Fh+var_90]
0x14001b701  mov     [rdi], rcx
0x14001b704  mov     [rdi+8], rax
0x14001b708  mov     [rax], rdi
0x14001b70b  mov     [rbp+3Fh+var_88], rdi
0x14001b70f  jmp     loc_14001B5B3
0x14001b714  mov     dil, [rbp+3Fh+arg_20]
0x14001b718  mov     rcx, [r15+180h]; HashTable
0x14001b71f  lea     rdx, [rbp+3Fh+Enumerator]; Enumerator
0x14001b723  call    cs:__imp_RtlEndWeakEnumerationHashTable
0x14001b72a  nop     dword ptr [rax+rax+00h]
0x14001b72f  test    bl, bl
0x14001b731  jnz     short loc_14001B76C
0x14001b733  mov     eax, [rbp+3Fh+arg_38]
0x14001b739  mov     r8, r14
0x14001b73c  mov     r9, [rbp+3Fh+arg_8]
0x14001b740  xor     edx, edx
0x14001b742  mov     rcx, [rbp+3Fh+arg_0]
0x14001b746  mov     [rsp+40h], eax
0x14001b74a  mov     rax, [rbp+3Fh+arg_30]
0x14001b74e  mov     qword ptr [rsp+0E0h+var_A8], rax
0x14001b753  mov     eax, [rbp+3Fh+arg_18]
0x14001b756  mov     byte ptr [rsp+0E0h+var_B0], sil
0x14001b75b  mov     [rsp+0E0h+var_B8], dil
0x14001b760  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14001b764  call    WinNatLibReserveBinding
0x14001b769  mov     r12d, eax
0x14001b76c  lea     rcx, [rbp+3Fh+LockHandle]; LockHandle
0x14001b770  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001b777  nop     dword ptr [rax+rax+00h]
0x14001b77c  mov     rcx, [rbp+3Fh+var_90]
0x14001b780  lea     rax, [rbp+3Fh+var_90]
0x14001b784  cmp     rcx, rax
0x14001b787  jz      short loc_14001B7BD
0x14001b789  lea     rax, [rbp+3Fh+var_90]
0x14001b78d  cmp     [rcx+8], rax
0x14001b791  jnz     short loc_14001B7B6
0x14001b793  mov     rax, [rcx]
0x14001b796  cmp     [rax+8], rcx
0x14001b79a  jnz     short loc_14001B7B6
0x14001b79c  lea     rdx, [rbp+3Fh+var_90]
0x14001b7a0  mov     [rbp+3Fh+var_90], rax
0x14001b7a4  add     rcx, 0FFFFFFFFFFFFFF58h
0x14001b7ab  mov     [rax+8], rdx
0x14001b7af  call    WinNatLibDereferenceSession
0x14001b7b4  jmp     short loc_14001B77C
0x14001b7b6  mov     ecx, 3
0x14001b7bb  int     29h; Win8: RtlFailFast(ecx)
0x14001b7bd  mov     eax, r12d
0x14001b7c0  add     rsp, 0A8h
0x14001b7c7  pop     r15
0x14001b7c9  pop     r14
0x14001b7cb  pop     r13
0x14001b7cd  pop     r12
0x14001b7cf  pop     rdi
0x14001b7d0  pop     rsi
0x14001b7d1  pop     rbx
0x14001b7d2  pop     rbp
0x14001b7d3  retn
```
