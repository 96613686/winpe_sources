# WinNatLibCreateStaticBindingEntry

- ea: `0x14001b9ec`
- end: `0x14001bcb5`
- name: `WinNatLibCreateStaticBindingEntry`
- size: `713`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011778`
- `0x1400319dc`

## callees

- `0x1400061d0`
- `0x140006b40`
- `0x14000a638`
- `0x14000ae68`
- `0x14000caa0`
- `0x14001a878`
- `0x14001b9ec`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bc50`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001bc50`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001ba7d`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x14001ba7d`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001baa1`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14001baa1`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001bc03`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14001bc03`

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
  __int64 v8; // r15
  char v9; // bl
  int v10; // r12d
  bool v11; // zf
  bool v13; // r13
  char v14; // si
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // rax
  __int64 **v16; // rdi
  __int64 v17; // rbx
  _WORD *v18; // rsi
  __int16 v19; // ax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // di
  __int64 **v24; // rax
  __int64 *v25; // rcx
  __int64 *v26; // rax
  __int64 *v28; // [rsp+58h] [rbp-51h] BYREF
  __int64 **v29; // [rsp+60h] [rbp-49h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-41h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+80h] [rbp-29h] BYREF
  char v34; // [rsp+108h] [rbp+5Fh]

  v8 = (__int64)(a1 + 16);
  v9 = 0;
  v10 = 0;
  v34 = 0;
  v11 = *(_WORD *)a3 == 2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&Enumerator, 0, sizeof(Enumerator));
  v13 = v11 && !*(_DWORD *)(a3 + 4);
  v29 = &v28;
  v28 = (__int64 *)&v28;
  RtlAcquireScalableWriteLock((__int64)(a1 + 24), &LockHandle);
  RtlInitWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v8 + 384), &Enumerator);
  v14 = a6;
  while ( 1 )
  {
    v15 = RtlWeaklyEnumerateEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v8 + 384), &Enumerator);
    v16 = (__int64 **)v15;
    if ( !v15 )
      break;
    v17 = (__int64)&v15[-7];
    if ( LODWORD(v15[-2].Linkage.Flink) != a5 )
      goto LABEL_7;
    v18 = *(_WORD **)(v17 + 104);
    if ( (unsigned __int8)WinNatCompareTransportAndSockAddr(v18, a3, 0) )
      goto LABEL_41;
    if ( !v13 || *v18 != 2 )
    {
      v14 = a6;
      goto LABEL_7;
    }
    v19 = v18[1];
    v14 = a6;
    if ( *(_WORD *)(a3 + 2) == v19 )
    {
LABEL_41:
      if ( !(unsigned __int8)WinNatCompareTransportAndSockAddr(*(_QWORD *)(v17 + 88), a2, 0)
        || (v21 = a4, *(_DWORD *)(v17 + 8) != a4) )
      {
        v14 = a6;
        if ( a6 && (*(_BYTE *)(*(_QWORD *)(v17 + 80) + 88LL) & 8) != 0 )
          goto LABEL_7;
        if ( (*(_BYTE *)(v17 + 132) & 1) != 0 )
LABEL_26:
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v21, v20, v22);
LABEL_27:
        *(_BYTE *)(v17 + 132) |= 1u;
        WinNatDeleteSessionEntryUnderLock(v8, v17);
        v24 = v29;
        if ( *v29 != (__int64 *)&v28 )
LABEL_37:
          __fastfail(3u);
        *v16 = (__int64 *)&v28;
        v16[1] = (__int64 *)v24;
        *v24 = (__int64 *)v16;
        v29 = v16;
        goto LABEL_7;
      }
      v20 = *(_QWORD *)(v17 + 80);
      v14 = a6;
      if ( ((*(_BYTE *)(v20 + 88) & 8) != 0) != a6 || v13 )
      {
        if ( (*(_BYTE *)(v17 + 132) & 1) != 0 )
          goto LABEL_26;
        goto LABEL_27;
      }
      v9 = v34;
      if ( !v34 )
      {
        v23 = a5;
        v9 = 1;
        v10 = WinNatLibReserveBinding(a1, v20, (__int16 *)a3, a2, a4, a5, a6, a7, a8);
        v34 = 1;
        if ( v10 < 0 )
          goto LABEL_30;
      }
    }
    else
    {
LABEL_7:
      v9 = v34;
    }
  }
  v23 = a5;
LABEL_30:
  RtlEndWeakEnumerationHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v8 + 384), &Enumerator);
  if ( !v9 )
    v10 = WinNatLibReserveBinding(a1, 0, (__int16 *)a3, a2, a4, v23, v14, a7, a8);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v25 = v28;
    if ( v28 == (__int64 *)&v28 )
      return (unsigned int)v10;
    if ( (__int64 **)v28[1] != &v28 )
      goto LABEL_37;
    v26 = (__int64 *)*v28;
    if ( *(__int64 **)(*v28 + 8) != v28 )
      goto LABEL_37;
    v28 = (__int64 *)*v28;
    v26[1] = (__int64)&v28;
    WinNatLibDereferenceSession(v25 - 21);
  }
}

```

## disassembly

```asm
0x14001b9ec  mov     rax, rsp
0x14001b9ef  mov     [rax+20h], r9d
0x14001b9f3  mov     [rax+10h], rdx
0x14001b9f7  mov     [rax+8], rcx
0x14001b9fb  push    rbp
0x14001b9fc  push    rbx
0x14001b9fd  push    rsi
0x14001b9fe  push    rdi
0x14001b9ff  push    r12
0x14001ba01  push    r13
0x14001ba03  push    r14
0x14001ba05  push    r15
0x14001ba07  lea     rbp, [rax-47h]
0x14001ba0b  sub     rsp, 0A8h
0x14001ba12  xor     eax, eax
0x14001ba14  lea     r15, [rcx+80h]
0x14001ba1b  xor     bl, bl
0x14001ba1d  mov     qword ptr [rbp+3Fh+LockHandle.OldIrql], rax
0x14001ba21  xorps   xmm1, xmm1
0x14001ba24  mov     qword ptr [rbp+3Fh+Enumerator.BucketIndex], rax
0x14001ba28  xor     r12d, r12d
0x14001ba2b  mov     [rbp+3Fh+arg_10], bl
0x14001ba2e  cmp     word ptr [r8], 2
0x14001ba33  xorps   xmm0, xmm0
0x14001ba36  mov     r14, r8
0x14001ba39  movups  xmmword ptr [rbp+3Fh+LockHandle.LockQueue.Next], xmm0
0x14001ba3d  movups  xmmword ptr [rbp+3Fh+Enumerator], xmm1
0x14001ba41  movups  xmmword ptr [rbp+3Fh+Enumerator+10h], xmm1
0x14001ba45  jnz     short loc_14001BA52
0x14001ba47  cmp     [r8+4], eax
0x14001ba4b  jnz     short loc_14001BA52
0x14001ba4d  mov     r13b, 1
0x14001ba50  jmp     short loc_14001BA55
0x14001ba52  xor     r13b, r13b
0x14001ba55  lea     rax, [rbp+3Fh+var_90]
0x14001ba59  mov     [rbp+3Fh+var_88], rax
0x14001ba5d  lea     rcx, [r15+40h]
0x14001ba61  lea     rax, [rbp+3Fh+var_90]
0x14001ba65  lea     rdx, [rbp+3Fh+LockHandle]
0x14001ba69  mov     [rbp+3Fh+var_90], rax
0x14001ba6d  call    RtlAcquireScalableWriteLock
0x14001ba72  mov     rcx, [r15+180h]; HashTable
0x14001ba79  lea     rdx, [rbp+3Fh+Enumerator]; Enumerator
0x14001ba7d  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14001ba84  nop     dword ptr [rax+rax+00h]
0x14001ba89  mov     sil, [rbp+3Fh+arg_28]
0x14001ba8d  jmp     short loc_14001BA96
0x14001ba8f  mov     sil, [rbp+3Fh+arg_28]
0x14001ba93  mov     bl, [rbp+3Fh+arg_10]
0x14001ba96  mov     rcx, [r15+180h]; HashTable
0x14001ba9d  lea     rdx, [rbp+3Fh+Enumerator]; Enumerator
0x14001baa1  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
0x14001baa8  nop     dword ptr [rax+rax+00h]
0x14001baad  mov     rdi, rax
0x14001bab0  test    rax, rax
0x14001bab3  jz      loc_14001BBF4
0x14001bab9  lea     rbx, [rax-0A8h]
0x14001bac0  movzx   eax, [rbp+3Fh+arg_20]
0x14001bac4  cmp     [rbx+78h], eax
0x14001bac7  jnz     short loc_14001BA93
0x14001bac9  mov     rsi, [rbx+68h]
0x14001bacd  xor     r8d, r8d
0x14001bad0  mov     rcx, rsi
0x14001bad3  mov     rdx, r14
0x14001bad6  call    WinNatCompareTransportAndSockAddr
0x14001badb  test    al, al
0x14001badd  jnz     short loc_14001BAF9
0x14001badf  test    r13b, r13b
0x14001bae2  jz      short loc_14001BA8F
0x14001bae4  cmp     word ptr [rsi], 2
0x14001bae8  jnz     short loc_14001BA8F
0x14001baea  movzx   eax, word ptr [rsi+2]
0x14001baee  mov     sil, [rbp+3Fh+arg_28]
0x14001baf2  cmp     [r14+2], ax
0x14001baf7  jnz     short loc_14001BA93
0x14001baf9  mov     rdx, [rbp+3Fh+arg_8]
0x14001bafd  xor     r8d, r8d
0x14001bb00  mov     rcx, [rbx+58h]
0x14001bb04  call    WinNatCompareTransportAndSockAddr
0x14001bb09  test    al, al
0x14001bb0b  jz      loc_14001BB95
0x14001bb11  mov     ecx, [rbp+3Fh+arg_18]
0x14001bb14  cmp     [rbx+8], ecx
0x14001bb17  jnz     short loc_14001BB95
0x14001bb19  mov     rdx, [rbx+50h]
0x14001bb1d  mov     sil, [rbp+3Fh+arg_28]
0x14001bb21  mov     al, [rdx+58h]
0x14001bb24  shr     al, 3
0x14001bb27  and     al, 1
0x14001bb29  cmp     al, sil
0x14001bb2c  jnz     short loc_14001BB85
0x14001bb2e  test    r13b, r13b
0x14001bb31  jnz     short loc_14001BB85
0x14001bb33  mov     bl, [rbp+3Fh+arg_10]
0x14001bb36  test    bl, bl
0x14001bb38  jnz     loc_14001BA96
0x14001bb3e  mov     eax, [rbp+3Fh+arg_38]
0x14001bb44  mov     r8, r14
0x14001bb47  mov     dil, [rbp+3Fh+arg_20]
0x14001bb4b  mov     r9, [rbp+3Fh+arg_8]
0x14001bb4f  mov     [rsp+40h], eax
0x14001bb53  mov     rax, [rbp+3Fh+arg_30]
0x14001bb57  mov     qword ptr [rsp+0E0h+var_A8], rax
0x14001bb5c  mov     byte ptr [rsp+0E0h+var_B0], sil
0x14001bb61  mov     [rsp+0E0h+var_B8], dil
0x14001bb66  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x14001bb6a  mov     rcx, [rbp+3Fh+arg_0]
0x14001bb6e  call    WinNatLibReserveBinding
0x14001bb73  mov     bl, 1
0x14001bb75  mov     r12d, eax
0x14001bb78  mov     [rbp+3Fh+arg_10], bl
0x14001bb7b  test    eax, eax
0x14001bb7d  jns     loc_14001BA96
0x14001bb83  jmp     short loc_14001BBF8
0x14001bb85  test    byte ptr [rbx+84h], 1
0x14001bb8c  jz      short loc_14001BBBA
0x14001bb8e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bb93  jmp     short loc_14001BBBA
0x14001bb95  mov     sil, [rbp+3Fh+arg_28]
0x14001bb99  test    sil, sil
0x14001bb9c  jz      short loc_14001BBAC
0x14001bb9e  mov     rax, [rbx+50h]
0x14001bba2  test    byte ptr [rax+58h], 8
0x14001bba6  jnz     loc_14001BA93
0x14001bbac  test    byte ptr [rbx+84h], 1
0x14001bbb3  jz      short loc_14001BBBA
0x14001bbb5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001bbba  or      byte ptr [rbx+84h], 1
0x14001bbc1  mov     rdx, rbx
0x14001bbc4  mov     rcx, r15
0x14001bbc7  call    WinNatDeleteSessionEntryUnderLock
0x14001bbcc  mov     rax, [rbp+3Fh+var_88]
0x14001bbd0  lea     rcx, [rbp+3Fh+var_90]
0x14001bbd4  cmp     [rax], rcx
0x14001bbd7  jnz     loc_14001BC96
0x14001bbdd  lea     rcx, [rbp+3Fh+var_90]
0x14001bbe1  mov     [rdi], rcx
0x14001bbe4  mov     [rdi+8], rax
0x14001bbe8  mov     [rax], rdi
0x14001bbeb  mov     [rbp+3Fh+var_88], rdi
0x14001bbef  jmp     loc_14001BA93
0x14001bbf4  mov     dil, [rbp+3Fh+arg_20]
0x14001bbf8  mov     rcx, [r15+180h]; HashTable
0x14001bbff  lea     rdx, [rbp+3Fh+Enumerator]; Enumerator
0x14001bc03  call    cs:__imp_RtlEndWeakEnumerationHashTable
0x14001bc0a  nop     dword ptr [rax+rax+00h]
0x14001bc0f  test    bl, bl
0x14001bc11  jnz     short loc_14001BC4C
0x14001bc13  mov     eax, [rbp+3Fh+arg_38]
0x14001bc19  mov     r8, r14
0x14001bc1c  mov     r9, [rbp+3Fh+arg_8]
0x14001bc20  xor     edx, edx
0x14001bc22  mov     rcx, [rbp+3Fh+arg_0]
0x14001bc26  mov     [rsp+40h], eax
0x14001bc2a  mov     rax, [rbp+3Fh+arg_30]
0x14001bc2e  mov     qword ptr [rsp+0E0h+var_A8], rax
0x14001bc33  mov     eax, [rbp+3Fh+arg_18]
0x14001bc36  mov     byte ptr [rsp+0E0h+var_B0], sil
0x14001bc3b  mov     [rsp+0E0h+var_B8], dil
0x14001bc40  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14001bc44  call    WinNatLibReserveBinding
0x14001bc49  mov     r12d, eax
0x14001bc4c  lea     rcx, [rbp+3Fh+LockHandle]; LockHandle
0x14001bc50  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001bc57  nop     dword ptr [rax+rax+00h]
0x14001bc5c  mov     rcx, [rbp+3Fh+var_90]
0x14001bc60  lea     rax, [rbp+3Fh+var_90]
0x14001bc64  cmp     rcx, rax
0x14001bc67  jz      short loc_14001BC9D
0x14001bc69  lea     rax, [rbp+3Fh+var_90]
0x14001bc6d  cmp     [rcx+8], rax
0x14001bc71  jnz     short loc_14001BC96
0x14001bc73  mov     rax, [rcx]
0x14001bc76  cmp     [rax+8], rcx
0x14001bc7a  jnz     short loc_14001BC96
0x14001bc7c  lea     rdx, [rbp+3Fh+var_90]
0x14001bc80  mov     [rbp+3Fh+var_90], rax
0x14001bc84  add     rcx, 0FFFFFFFFFFFFFF58h
0x14001bc8b  mov     [rax+8], rdx
0x14001bc8f  call    WinNatLibDereferenceSession
0x14001bc94  jmp     short loc_14001BC5C
0x14001bc96  mov     ecx, 3
0x14001bc9b  int     29h; Win8: RtlFailFast(ecx)
0x14001bc9d  mov     eax, r12d
0x14001bca0  add     rsp, 0A8h
0x14001bca7  pop     r15
0x14001bca9  pop     r14
0x14001bcab  pop     r13
0x14001bcad  pop     r12
0x14001bcaf  pop     rdi
0x14001bcb0  pop     rsi
0x14001bcb1  pop     rbx
0x14001bcb2  pop     rbp
0x14001bcb3  retn
```
