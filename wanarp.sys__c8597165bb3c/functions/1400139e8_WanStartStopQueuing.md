# WanStartStopQueuing

- ea: `0x1400139e8`
- end: `0x140013c7b`
- name: `WanStartStopQueuing`
- size: `659`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400172d0`

## callees

- `0x140003830`
- `0x1400139e8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013a9c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013b5f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013c4e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013a9c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013b5f`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140013c4e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140013a30`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140013a30`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013a83`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013a83`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013b05`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013b4a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013c07`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013c3e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013b05`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013b4a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013c07`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013c3e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013acb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013af2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013ba4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013acb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013af2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013ba4`

## pseudocode

```c
__int64 __fastcall WanStartStopQueuing(__int64 a1, unsigned int a2, unsigned int a3, char a4)
{
  __int64 v6; // rsi
  _DWORD *v8; // r14
  __int64 *v9; // rbx
  __int64 *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  unsigned int v14; // r15d
  __int64 v15; // rbx
  unsigned int v16; // r12d
  unsigned __int64 v17; // rdi
  __int64 v18; // rax
  _DWORD *v19; // rdx
  __int64 v20; // rcx
  KIRQL Irql; // [rsp+58h] [rbp+10h] BYREF

  Irql = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v6 = a1;
  if ( a2 < 8 )
    return 3221225507LL;
  v8 = *(_DWORD **)(a1 + 24);
  IoAcquireCancelSpinLock(&Irql);
  v9 = (__int64 *)&g_lePendingV4NotificationList;
  if ( !a4 )
    v9 = &g_lePendingV6NotificationList;
  if ( *v8 )
  {
    if ( a3 >= 8 )
    {
      KeAcquireSpinLockAtDpcLevel(&g_rwlAdapterLock);
      if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
        KeAcquireSpinLockAtDpcLevel(&SpinLock);
      KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
      v14 = 32 * g_ulNumDialOutInterfaces + 8;
      v8[1] = g_ulNumDialOutInterfaces;
      if ( a3 >= v14 )
      {
        v15 = g_leMappedAdapterList;
        v16 = 0;
        if ( (__int64 *)g_leMappedAdapterList != &g_leMappedAdapterList )
        {
          v17 = -(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFF8uLL;
          do
          {
            KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v15 + 120));
            v18 = *(_QWORD *)(v17 + v15 + 176);
            if ( v18 )
            {
              v19 = *(_DWORD **)(v18 + 40);
              if ( v19 )
              {
                if ( v19[25] == 1 )
                {
                  v20 = 8LL * v16++;
                  *(_OWORD *)&v8[v20 + 2] = *(_OWORD *)(v18 + 68);
                  v8[v20 + 6] = *(_DWORD *)(v15 + 360);
                  v8[v20 + 7] = v19[6];
                  v8[v20 + 8] = v19[7];
                  v8[v20 + 9] = v19[8];
                }
              }
            }
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v15 + 120));
            v15 = *(_QWORD *)v15;
          }
          while ( (__int64 *)v15 != &g_leMappedAdapterList );
          v6 = a1;
        }
        g_bQueueNotifications = 1;
        if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
          KeReleaseSpinLockFromDpcLevel(&SpinLock);
        IoReleaseCancelSpinLock(Irql);
        *(_QWORD *)(v6 + 56) = v14;
        return 0;
      }
      *(_QWORD *)(v6 + 56) = 8;
      if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
        KeReleaseSpinLockFromDpcLevel(&SpinLock);
      v13 = 261;
    }
    else
    {
      v13 = -1073741789;
    }
    IoReleaseCancelSpinLock(Irql);
    return v13;
  }
  g_bQueueNotifications = 0;
  while ( 1 )
  {
    v10 = (__int64 *)*v9;
    if ( (__int64 *)*v9 == v9 )
      break;
    if ( (__int64 *)v10[1] != v9 || (v11 = *v10, *(__int64 **)(*v10 + 8) != v10) )
      __fastfail(3u);
    *v9 = v11;
    *(_QWORD *)(v11 + 8) = v9;
    ExFreeToNPagedLookasideList(&g_llNotificationBlocks, v10);
  }
  IoReleaseCancelSpinLock(Irql);
  LOBYTE(v12) = a4;
  WanpClearPendingIrps(v12);
  return 0;
}

```

## disassembly

```asm
0x1400139e8  mov     rax, rsp
0x1400139eb  mov     [rax+18h], rbx
0x1400139ef  mov     [rax+20h], rbp
0x1400139f3  mov     [rax+8], rcx
0x1400139f7  push    rsi
0x1400139f8  push    rdi
0x1400139f9  push    r12
0x1400139fb  push    r14
0x1400139fd  push    r15
0x1400139ff  sub     rsp, 20h
0x140013a03  mov     byte ptr [rax+10h], 0
0x140013a07  mov     dil, r9b
0x140013a0a  mov     qword ptr [rcx+38h], 0
0x140013a12  mov     ebp, r8d
0x140013a15  mov     rsi, rcx
0x140013a18  cmp     edx, 8
0x140013a1b  jnb     short loc_140013A27
0x140013a1d  mov     eax, 0C0000023h
0x140013a22  jmp     loc_140013C63
0x140013a27  mov     r14, [rcx+18h]
0x140013a2b  lea     rcx, [rsp+48h+Irql]; Irql
0x140013a30  call    cs:__imp_IoAcquireCancelSpinLock
0x140013a37  nop     dword ptr [rax+rax+00h]
0x140013a3c  test    dil, dil
0x140013a3f  lea     rax, g_lePendingV6NotificationList
0x140013a46  lea     rbx, g_lePendingV4NotificationList
0x140013a4d  cmovz   rbx, rax
0x140013a51  cmp     dword ptr [r14], 0
0x140013a55  jnz     short loc_140013AB5
0x140013a57  mov     cs:g_bQueueNotifications, 0
0x140013a5e  mov     rdx, [rbx]; Entry
0x140013a61  cmp     rdx, rbx
0x140013a64  jz      short loc_140013A98
0x140013a66  cmp     [rdx+8], rbx
0x140013a6a  jnz     short loc_140013A91
0x140013a6c  mov     rax, [rdx]
0x140013a6f  cmp     [rax+8], rdx
0x140013a73  jnz     short loc_140013A91
0x140013a75  mov     [rbx], rax
0x140013a78  lea     rcx, g_llNotificationBlocks; Lookaside
0x140013a7f  mov     [rax+8], rbx
0x140013a83  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013a8a  nop     dword ptr [rax+rax+00h]
0x140013a8f  jmp     short loc_140013A5E
0x140013a91  mov     ecx, 3
0x140013a96  int     29h; Win8: RtlFailFast(ecx)
0x140013a98  mov     cl, [rsp+48h+Irql]; Irql
0x140013a9c  call    cs:__imp_IoReleaseCancelSpinLock
0x140013aa3  nop     dword ptr [rax+rax+00h]
0x140013aa8  mov     cl, dil
0x140013aab  call    WanpClearPendingIrps
0x140013ab0  jmp     loc_140013C61
0x140013ab5  cmp     ebp, 8
0x140013ab8  jnb     short loc_140013AC4
0x140013aba  mov     ebx, 0C0000023h
0x140013abf  jmp     loc_140013B5B
0x140013ac4  lea     rcx, g_rwlAdapterLock; SpinLock
0x140013acb  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140013ad2  nop     dword ptr [rax+rax+00h]
0x140013ad7  mov     eax, 1
0x140013adc  lock xadd cs:dword_140009CB0, eax
0x140013ae4  inc     eax
0x140013ae6  cmp     eax, 1
0x140013ae9  jnz     short loc_140013AFE
0x140013aeb  lea     rcx, SpinLock; SpinLock
0x140013af2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140013af9  nop     dword ptr [rax+rax+00h]
0x140013afe  lea     rcx, g_rwlAdapterLock; SpinLock
0x140013b05  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140013b0c  nop     dword ptr [rax+rax+00h]
0x140013b11  mov     edx, cs:g_ulNumDialOutInterfaces
0x140013b17  mov     r15d, edx
0x140013b1a  shl     r15d, 5
0x140013b1e  add     r15d, 8
0x140013b22  mov     [r14+4], edx
0x140013b26  cmp     ebp, r15d
0x140013b29  jnb     short loc_140013B72
0x140013b2b  mov     qword ptr [rsi+38h], 8
0x140013b33  or      eax, 0FFFFFFFFh
0x140013b36  lock xadd cs:dword_140009CB0, eax
0x140013b3e  cmp     eax, 1
0x140013b41  jnz     short loc_140013B56
0x140013b43  lea     rcx, SpinLock; SpinLock
0x140013b4a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140013b51  nop     dword ptr [rax+rax+00h]
0x140013b56  mov     ebx, 105h
0x140013b5b  mov     cl, [rsp+48h+Irql]; Irql
0x140013b5f  call    cs:__imp_IoReleaseCancelSpinLock
0x140013b66  nop     dword ptr [rax+rax+00h]
0x140013b6b  mov     eax, ebx
0x140013b6d  jmp     loc_140013C63
0x140013b72  mov     rbx, cs:g_leMappedAdapterList
0x140013b79  lea     rax, g_leMappedAdapterList
0x140013b80  xor     r12d, r12d
0x140013b83  cmp     rbx, rax
0x140013b86  jz      loc_140013C20
0x140013b8c  neg     dil
0x140013b8f  lea     rsi, g_leMappedAdapterList
0x140013b96  sbb     rdi, rdi
0x140013b99  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140013b9d  lea     rbp, [rbx+78h]
0x140013ba1  mov     rcx, rbp; SpinLock
0x140013ba4  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140013bab  nop     dword ptr [rax+rax+00h]
0x140013bb0  mov     rax, [rdi+rbx+0B0h]
0x140013bb8  test    rax, rax
0x140013bbb  jz      short loc_140013C04
0x140013bbd  mov     rdx, [rax+28h]
0x140013bc1  test    rdx, rdx
0x140013bc4  jz      short loc_140013C04
0x140013bc6  cmp     dword ptr [rdx+64h], 1
0x140013bca  jnz     short loc_140013C04
0x140013bcc  movups  xmm0, xmmword ptr [rax+44h]
0x140013bd0  mov     ecx, r12d
0x140013bd3  shl     rcx, 5
0x140013bd7  inc     r12d
0x140013bda  movdqu  xmmword ptr [rcx+r14+8], xmm0
0x140013be1  mov     eax, [rbx+168h]
0x140013be7  mov     [rcx+r14+18h], eax
0x140013bec  mov     eax, [rdx+18h]
0x140013bef  mov     [rcx+r14+1Ch], eax
0x140013bf4  mov     eax, [rdx+1Ch]
0x140013bf7  mov     [rcx+r14+20h], eax
0x140013bfc  mov     eax, [rdx+20h]
0x140013bff  mov     [rcx+r14+24h], eax
0x140013c04  mov     rcx, rbp; SpinLock
0x140013c07  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140013c0e  nop     dword ptr [rax+rax+00h]
0x140013c13  mov     rbx, [rbx]
0x140013c16  cmp     rbx, rsi
0x140013c19  jnz     short loc_140013B9D
0x140013c1b  mov     rsi, [rsp+48h+arg_0]
0x140013c20  mov     cs:g_bQueueNotifications, 1
0x140013c27  or      eax, 0FFFFFFFFh
0x140013c2a  lock xadd cs:dword_140009CB0, eax
0x140013c32  cmp     eax, 1
0x140013c35  jnz     short loc_140013C4A
0x140013c37  lea     rcx, SpinLock; SpinLock
0x140013c3e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140013c45  nop     dword ptr [rax+rax+00h]
0x140013c4a  mov     cl, [rsp+48h+Irql]; Irql
0x140013c4e  call    cs:__imp_IoReleaseCancelSpinLock
0x140013c55  nop     dword ptr [rax+rax+00h]
0x140013c5a  mov     eax, r15d
0x140013c5d  mov     [rsi+38h], rax
0x140013c61  xor     eax, eax
0x140013c63  mov     rbx, [rsp+48h+arg_10]
0x140013c68  mov     rbp, [rsp+48h+arg_18]
0x140013c6d  add     rsp, 20h
0x140013c71  pop     r15
0x140013c73  pop     r14
0x140013c75  pop     r12
0x140013c77  pop     rdi
0x140013c78  pop     rsi
0x140013c79  retn
```
