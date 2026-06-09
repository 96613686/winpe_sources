# RaidAdapterResetBus

- ea: `0x140038afc`
- end: `0x140038e41`
- name: `RaidAdapterResetBus`
- size: `837`
- prototype: ``
- caller_count: `7`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000e510`
- `0x140038120`
- `0x140038808`
- `0x140064200`
- `0x1400c4830`
- `0x1400c9338`
- `0x1400ca754`

## callees

- `0x140025440`
- `0x140030b30`
- `0x140031330`
- `0x140038afc`
- `0x140046c60`
- `0x140054800`
- `0x140071670`
- `0x1400872f4`
- `0x14008dca8`
- `0x140093144`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140038c15`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140038c3b`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140038c15`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140038c3b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140038bb7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140038c75`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140038bb7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140038c75`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140038bd0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140038ca0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140038bd0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140038ca0`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140038b81`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140038c5f`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140038b81`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140038c5f`
- `ntoskrnl!KeLowerIrql` at `0x140038d1e`
- `ntoskrnl!KeLowerIrql` at `0x140038d1e`
- `ntoskrnl!KfRaiseIrql` at `0x140038d06`
- `ntoskrnl!KfRaiseIrql` at `0x140038d06`
- `ntoskrnl!InitializeSListHead` at `0x140038b98`
- `ntoskrnl!InitializeSListHead` at `0x140038b98`

## pseudocode

```c
__int64 __fastcall RaidAdapterResetBus(__int64 a1, unsigned __int8 a2)
{
  int v5; // r14d
  unsigned int v6; // esi
  unsigned int i; // ebx
  struct _SLIST_ENTRY *v8; // rax
  int OutstandingIoCount; // r13d
  ULONGLONG UnbiasedInterruptTime; // rax
  __int64 v11; // rdx
  ULONGLONG v12; // rsi
  unsigned int v13; // r14d
  ULONGLONG v14; // rax
  bool v15; // cc
  ULONGLONG v16; // r12
  int v17; // esi
  unsigned int v18; // ebx
  PSLIST_ENTRY v19; // rax
  unsigned int v20; // ecx
  __int64 v21; // r9
  __int64 v22; // rcx
  KIRQL v23; // bl
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  unsigned __int8 v27; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+34h] [rbp-CCh] BYREF
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v30; // [rsp+3Ch] [rbp-C4h] BYREF
  ULONGLONG v31; // [rsp+40h] [rbp-C0h] BYREF
  ULONGLONG v32; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h]
  union _SLIST_HEADER SListHead; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36[18]; // [rsp+80h] [rbp-80h] BYREF

  v33 = 0;
  v34 = 0;
  SListHead = 0;
  if ( a2 >= *(_BYTE *)(a1 + 440) )
    return 3221225485LL;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 308), 1, 0) == 1 )
    return 3221226614LL;
  RaidPauseAdapterQueue(a1);
  if ( *(int *)(a1 + 4728) > 1 )
  {
    v5 = 0;
    v6 = KeQueryHighestNodeNumber() + 1;
    InitializeSListHead(&SListHead);
    do
    {
      for ( i = 0; i < v6; ++i )
      {
        v8 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 4736) + ((unsigned __int64)i << 6)));
        if ( v8 )
        {
          ExpInterlockedPushEntrySList(&SListHead, v8);
          ++v5;
        }
        else
        {
          _mm_pause();
        }
      }
    }
    while ( v5 < *(_DWORD *)(a1 + 4728) );
  }
  RaidAdapterAcquireStartIoLock(a1, &v33);
  *(_DWORD *)(a1 + 5152) = 0;
  OutstandingIoCount = StorGetOutstandingIoCount(a1);
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  LOBYTE(v11) = a2;
  v12 = UnbiasedInterruptTime;
  v31 = UnbiasedInterruptTime;
  v13 = RaCallMiniportResetBus(a1 + 360, v11);
  v14 = KeQueryUnbiasedInterruptTime();
  v15 = *(_DWORD *)(a1 + 4728) <= 1;
  v16 = v14;
  v28 = *(_DWORD *)(a1 + 5152);
  if ( !v15 )
  {
    v17 = 0;
    v18 = KeQueryHighestNodeNumber() + 1;
    do
    {
      v19 = ExpInterlockedPopEntrySList(&SListHead);
      if ( v19 )
      {
        ExpInterlockedPushEntrySList(
          (PSLIST_HEADER)(*(_QWORD *)(a1 + 4736) + ((unsigned __int64)(HIDWORD(v19[1].Next) % v18) << 6)),
          v19);
        ++v17;
      }
    }
    while ( v17 < *(_DWORD *)(a1 + 4728) );
    v12 = v31;
  }
  RaidAdapterReleaseStartIoLock(a1, &v33);
  v20 = *(_DWORD *)(a1 + 584);
  if ( v20 )
  {
    v21 = v20 / 0xF4240 + 1;
    if ( v20 == 1000000 * (v20 / 0xF4240) )
      v21 = v20 / 0xF4240;
    RaidAdapterSetPauseTimer(a1, a1 + 4200, a1 + 4264, v21);
  }
  else
  {
    v23 = KfRaiseIrql(2u);
    RaidResumeAndRestartAdapterQueues(a1);
    KeLowerIrql(v23);
  }
  if ( (unsigned int)dword_140176178 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v22, 0x400000000000LL) )
    {
      v36[5] = 16;
      v36[4] = a1 + 5128;
      v29 = *(_DWORD *)(a1 + 56);
      v36[6] = (__int64)&v29;
      v36[8] = (__int64)&v27;
      v36[10] = (__int64)&v30;
      v36[12] = (__int64)&v32;
      v36[14] = (__int64)&v31;
      v36[16] = (__int64)&v28;
      v36[7] = 4;
      v27 = a2;
      v36[9] = 1;
      v30 = v13;
      v36[11] = 4;
      v32 = v16 - v12;
      v36[13] = 8;
      LODWORD(v31) = OutstandingIoCount;
      v36[15] = 4;
      v36[17] = 4;
      tlgWriteTransfer_EtwWriteTransfer(v24, (int)&byte_140163E99, v25, v26, 9u, (__int64)v36);
    }
  }
  *(_DWORD *)(a1 + 308) = 0;
  return v13;
}

```

## disassembly

```asm
0x140038afc  mov     [rsp-8+arg_10], rbx
0x140038b01  push    rbp
0x140038b02  push    rsi
0x140038b03  push    rdi
0x140038b04  push    r12
0x140038b06  push    r13
0x140038b08  push    r14
0x140038b0a  push    r15
0x140038b0c  lea     rbp, [rsp-20h]
0x140038b11  sub     rsp, 120h
0x140038b18  mov     rax, cs:__security_cookie
0x140038b1f  xor     rax, rsp
0x140038b22  mov     [rbp+50h+var_40], rax
0x140038b26  xor     eax, eax
0x140038b28  xorps   xmm0, xmm0
0x140038b2b  mov     r15b, dl
0x140038b2e  mov     rdi, rcx
0x140038b31  movups  [rsp+150h+var_100], xmm0
0x140038b36  mov     [rsp+150h+var_F0], rax
0x140038b3b  movups  xmmword ptr [rsp+150h+SListHead], xmm0
0x140038b40  cmp     dl, [rcx+1B8h]
0x140038b46  jb      short loc_140038B52
0x140038b48  mov     eax, 0C000000Dh
0x140038b4d  jmp     loc_140038E19
0x140038b52  mov     r12d, 1
0x140038b58  lock cmpxchg [rcx+134h], r12d
0x140038b61  cmp     eax, r12d
0x140038b64  jnz     short loc_140038B70
0x140038b66  mov     eax, 0C0000476h
0x140038b6b  jmp     loc_140038E19
0x140038b70  call    RaidPauseAdapterQueue
0x140038b75  cmp     [rdi+1278h], r12d
0x140038b7c  jle     short loc_140038BF3
0x140038b7e  xor     r14d, r14d
0x140038b81  call    cs:__imp_KeQueryHighestNodeNumber
0x140038b88  nop     dword ptr [rax+rax+00h]
0x140038b8d  movzx   esi, ax
0x140038b90  lea     rcx, [rsp+150h+SListHead]; SListHead
0x140038b95  add     esi, r12d
0x140038b98  call    cs:__imp_InitializeSListHead
0x140038b9f  nop     dword ptr [rax+rax+00h]
0x140038ba4  xor     ebx, ebx
0x140038ba6  test    esi, esi
0x140038ba8  jz      short loc_140038BEA
0x140038baa  mov     ecx, ebx
0x140038bac  shl     rcx, 6
0x140038bb0  add     rcx, [rdi+1280h]; ListHead
0x140038bb7  call    cs:__imp_ExpInterlockedPopEntrySList
0x140038bbe  nop     dword ptr [rax+rax+00h]
0x140038bc3  test    rax, rax
0x140038bc6  jz      short loc_140038BE1
0x140038bc8  mov     rdx, rax; ListEntry
0x140038bcb  lea     rcx, [rsp+150h+SListHead]; ListHead
0x140038bd0  call    cs:__imp_ExpInterlockedPushEntrySList
0x140038bd7  nop     dword ptr [rax+rax+00h]
0x140038bdc  add     r14d, r12d
0x140038bdf  jmp     short loc_140038BE3
0x140038be1  pause
0x140038be3  add     ebx, r12d
0x140038be6  cmp     ebx, esi
0x140038be8  jb      short loc_140038BAA
0x140038bea  cmp     r14d, [rdi+1278h]
0x140038bf1  jl      short loc_140038BA4
0x140038bf3  lea     rdx, [rsp+150h+var_100]
0x140038bf8  mov     rcx, rdi
0x140038bfb  call    RaidAdapterAcquireStartIoLock
0x140038c00  mov     rcx, rdi
0x140038c03  mov     dword ptr [rdi+1420h], 0
0x140038c0d  call    StorGetOutstandingIoCount
0x140038c12  mov     r13d, eax
0x140038c15  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140038c1c  nop     dword ptr [rax+rax+00h]
0x140038c21  lea     rcx, [rdi+168h]
0x140038c28  mov     dl, r15b
0x140038c2b  mov     rsi, rax
0x140038c2e  mov     [rsp+150h+var_110], rax
0x140038c33  call    RaCallMiniportResetBus
0x140038c38  mov     r14d, eax
0x140038c3b  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140038c42  nop     dword ptr [rax+rax+00h]
0x140038c47  cmp     dword ptr [rdi+1278h], 1
0x140038c4e  mov     r12, rax
0x140038c51  mov     eax, [rdi+1420h]
0x140038c57  mov     [rsp+150h+var_11C], eax
0x140038c5b  jle     short loc_140038CBB
0x140038c5d  xor     esi, esi
0x140038c5f  call    cs:__imp_KeQueryHighestNodeNumber
0x140038c66  nop     dword ptr [rax+rax+00h]
0x140038c6b  movzx   ebx, ax
0x140038c6e  inc     ebx
0x140038c70  lea     rcx, [rsp+150h+SListHead]; ListHead
0x140038c75  call    cs:__imp_ExpInterlockedPopEntrySList
0x140038c7c  nop     dword ptr [rax+rax+00h]
0x140038c81  mov     r8, rax
0x140038c84  test    rax, rax
0x140038c87  jz      short loc_140038CAE
0x140038c89  mov     eax, [rax+14h]
0x140038c8c  xor     edx, edx
0x140038c8e  div     ebx
0x140038c90  mov     ecx, edx
0x140038c92  mov     rdx, r8; ListEntry
0x140038c95  shl     rcx, 6
0x140038c99  add     rcx, [rdi+1280h]; ListHead
0x140038ca0  call    cs:__imp_ExpInterlockedPushEntrySList
0x140038ca7  nop     dword ptr [rax+rax+00h]
0x140038cac  inc     esi
0x140038cae  cmp     esi, [rdi+1278h]
0x140038cb4  jl      short loc_140038C70
0x140038cb6  mov     rsi, [rsp+150h+var_110]
0x140038cbb  lea     rdx, [rsp+150h+var_100]
0x140038cc0  mov     rcx, rdi
0x140038cc3  call    RaidAdapterReleaseStartIoLock
0x140038cc8  mov     ecx, [rdi+248h]
0x140038cce  test    ecx, ecx
0x140038cd0  jz      short loc_140038D04
0x140038cd2  mov     eax, 431BDE83h
0x140038cd7  lea     r8, [rdi+10A8h]
0x140038cde  mul     ecx
0x140038ce0  shr     edx, 12h
0x140038ce3  imul    eax, edx, 0F4240h
0x140038ce9  lea     r9d, [rdx+1]
0x140038ced  cmp     ecx, eax
0x140038cef  mov     rcx, rdi
0x140038cf2  cmovz   r9d, edx
0x140038cf6  lea     rdx, [rdi+1068h]
0x140038cfd  call    RaidAdapterSetPauseTimer
0x140038d02  jmp     short loc_140038D2A
0x140038d04  mov     cl, 2; NewIrql
0x140038d06  call    cs:__imp_KfRaiseIrql
0x140038d0d  nop     dword ptr [rax+rax+00h]
0x140038d12  mov     rcx, rdi
0x140038d15  mov     bl, al
0x140038d17  call    RaidResumeAndRestartAdapterQueues
0x140038d1c  mov     cl, bl; NewIrql
0x140038d1e  call    cs:__imp_KeLowerIrql
0x140038d25  nop     dword ptr [rax+rax+00h]
0x140038d2a  mov     eax, cs:dword_140176178
0x140038d30  cmp     eax, 5
0x140038d33  jbe     loc_140038E0C
0x140038d39  mov     rdx, 400000000000h
0x140038d43  call    _tlgKeywordOn
0x140038d48  test    al, al
0x140038d4a  jz      loc_140038E0C
0x140038d50  lea     rax, [rdi+1408h]
0x140038d57  mov     [rbp+50h+var_A8], 10h
0x140038d5f  mov     [rbp+50h+var_B0], rax
0x140038d63  lea     rdx, byte_140163E99; int
0x140038d6a  mov     eax, [rdi+38h]
0x140038d6d  sub     r12, rsi
0x140038d70  mov     [rsp+150h+var_118], eax
0x140038d74  lea     rax, [rsp+150h+var_118]
0x140038d79  mov     [rbp+50h+var_A0], rax
0x140038d7d  lea     rax, [rsp+150h+var_120]
0x140038d82  mov     [rbp+50h+var_90], rax
0x140038d86  lea     rax, [rsp+150h+var_114]
0x140038d8b  mov     [rbp+50h+var_80], rax
0x140038d8f  lea     rax, [rsp+150h+var_108]
0x140038d94  mov     [rbp+50h+var_70], rax
0x140038d98  lea     rax, [rsp+150h+var_110]
0x140038d9d  mov     [rbp+50h+var_60], rax
0x140038da1  mov     eax, [rsp+150h+var_11C]
0x140038da5  mov     [rsp+150h+var_11C], eax
0x140038da9  lea     rax, [rsp+150h+var_11C]
0x140038dae  mov     [rbp+50h+var_50], rax
0x140038db2  lea     rax, [rbp+50h+var_D0]
0x140038db6  mov     [rsp+150h+var_128], rax; __int64
0x140038dbb  mov     [rsp+150h+var_130], 9; ULONG
0x140038dc3  mov     [rbp+50h+var_98], 4
0x140038dcb  mov     [rsp+150h+var_120], r15b
0x140038dd0  mov     [rbp+50h+var_88], 1
0x140038dd8  mov     [rsp+150h+var_114], r14d
0x140038ddd  mov     [rbp+50h+var_78], 4
0x140038de5  mov     [rsp+150h+var_108], r12
0x140038dea  mov     [rbp+50h+var_68], 8
0x140038df2  mov     dword ptr [rsp+150h+var_110], r13d
0x140038df7  mov     [rbp+50h+var_58], 4
0x140038dff  mov     [rbp+50h+var_48], 4
0x140038e07  call    _tlgWriteTransfer_EtwWriteTransfer
0x140038e0c  mov     dword ptr [rdi+134h], 0
0x140038e16  mov     eax, r14d
0x140038e19  mov     rcx, [rbp+50h+var_40]
0x140038e1d  xor     rcx, rsp; StackCookie
0x140038e20  call    __security_check_cookie
0x140038e25  mov     rbx, [rsp+150h+arg_10]
0x140038e2d  add     rsp, 120h
0x140038e34  pop     r15
0x140038e36  pop     r14
0x140038e38  pop     r13
0x140038e3a  pop     r12
0x140038e3c  pop     rdi
0x140038e3d  pop     rsi
0x140038e3e  pop     rbp
0x140038e3f  retn
```
