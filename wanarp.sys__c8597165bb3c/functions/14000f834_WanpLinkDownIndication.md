# WanpLinkDownIndication

- ea: `0x14000f834`
- end: `0x14000f9a3`
- name: `WanpLinkDownIndication`
- size: `367`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400022c0`
- `0x1400033f4`
- `0x14000d010`

## callees

- `0x14000f728`
- `0x14000f834`
- `0x14000f9c8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f857`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f857`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f898`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000f898`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000f885`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000f885`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f8e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f957`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f984`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f8e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f957`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f984`
- `ntoskrnl!ExQueueWorkItem` at `0x14000f942`
- `ntoskrnl!ExQueueWorkItem` at `0x14000f942`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f8f5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f8f5`

## pseudocode

```c
__int64 __fastcall WanpLinkDownIndication(__int64 a1, unsigned int a2)
{
  KIRQL v4; // al
  KIRQL v5; // si
  __int64 v6; // rbx
  int v7; // eax

  if ( a1 )
    a2 = *(_DWORD *)(a1 + 8);
  v4 = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock);
  v5 = v4;
  v6 = *((_QWORD *)g_puipConnTable + a2);
  if ( v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 96));
    KeAcquireSpinLockAtDpcLevel(*(PKSPIN_LOCK *)(v6 + 80));
    KeReleaseSpinLockFromDpcLevel(&g_rlConnTableLock);
    v7 = *(_DWORD *)(v6 + 124);
    if ( v7 && (unsigned int)(v7 - 3) > 1 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 96), 0xFFFFFFFF) == 1 )
        WanpDeleteConnEntry((char *)v6);
      *(_QWORD *)(v6 + 240) = a1;
      *(_DWORD *)(v6 + 124) = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 96));
      KeReleaseSpinLock(*(PKSPIN_LOCK *)(v6 + 80), v5);
      if ( KeGetCurrentIrql() )
      {
        if ( a1 )
          *(_BYTE *)(a1 + 12) = 1;
        *(_QWORD *)(v6 + 232) = v6;
        *(_QWORD *)(v6 + 224) = WanpLinkDownIndicationWorkItem;
        *(_QWORD *)(v6 + 208) = 0;
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(v6 + 208), CriticalWorkQueue);
      }
      else
      {
        WanpLinkDownIndicationWorkItemImpl((PVOID)v6, 0);
        if ( a1 )
          *(_BYTE *)(a1 + 12) = 0;
      }
    }
    else
    {
      KeReleaseSpinLock(*(PKSPIN_LOCK *)(v6 + 80), v5);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 96), 0xFFFFFFFF) == 1 )
        WanpDeleteConnEntry((char *)v6);
    }
  }
  else
  {
    KeReleaseSpinLock(&g_rlConnTableLock, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x14000f834  mov     [rsp+arg_0], rbx
0x14000f839  mov     [rsp+arg_8], rsi
0x14000f83e  push    rdi
0x14000f83f  sub     rsp, 20h
0x14000f843  mov     ebx, edx
0x14000f845  mov     rdi, rcx
0x14000f848  test    rcx, rcx
0x14000f84b  jz      short loc_14000F850
0x14000f84d  mov     ebx, [rcx+8]
0x14000f850  lea     rcx, g_rlConnTableLock; SpinLock
0x14000f857  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f85e  nop     dword ptr [rax+rax+00h]
0x14000f863  mov     rdx, cs:g_puipConnTable
0x14000f86a  mov     sil, al
0x14000f86d  mov     r8d, ebx
0x14000f870  mov     rbx, [rdx+r8*8]
0x14000f874  test    rbx, rbx
0x14000f877  jz      loc_14000F97A
0x14000f87d  lock inc dword ptr [rbx+60h]
0x14000f881  mov     rcx, [rbx+50h]; SpinLock
0x14000f885  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000f88c  nop     dword ptr [rax+rax+00h]
0x14000f891  lea     rcx, g_rlConnTableLock; SpinLock
0x14000f898  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000f89f  nop     dword ptr [rax+rax+00h]
0x14000f8a4  mov     eax, [rbx+7Ch]
0x14000f8a7  test    eax, eax
0x14000f8a9  jz      loc_14000F950
0x14000f8af  add     eax, 0FFFFFFFDh
0x14000f8b2  cmp     eax, 1
0x14000f8b5  jbe     loc_14000F950
0x14000f8bb  or      eax, 0FFFFFFFFh
0x14000f8be  lock xadd [rbx+60h], eax
0x14000f8c3  cmp     eax, 1
0x14000f8c6  jnz     short loc_14000F8D0
0x14000f8c8  mov     rcx, rbx; Entry
0x14000f8cb  call    WanpDeleteConnEntry
0x14000f8d0  mov     [rbx+0F0h], rdi
0x14000f8d7  mov     dword ptr [rbx+7Ch], 0
0x14000f8de  lock inc dword ptr [rbx+60h]
0x14000f8e2  mov     rcx, [rbx+50h]; SpinLock
0x14000f8e6  mov     dl, sil; NewIrql
0x14000f8e9  call    cs:__imp_KeReleaseSpinLock
0x14000f8f0  nop     dword ptr [rax+rax+00h]
0x14000f8f5  call    cs:__imp_KeGetCurrentIrql
0x14000f8fc  nop     dword ptr [rax+rax+00h]
0x14000f901  test    al, al
0x14000f903  jnz     short loc_14000F91A
0x14000f905  xor     edx, edx
0x14000f907  mov     rcx, rbx; Entry
0x14000f90a  call    WanpLinkDownIndicationWorkItemImpl
0x14000f90f  test    rdi, rdi
0x14000f912  jz      short loc_14000F990
0x14000f914  mov     byte ptr [rdi+0Ch], 0
0x14000f918  jmp     short loc_14000F990
0x14000f91a  test    rdi, rdi
0x14000f91d  jz      short loc_14000F923
0x14000f91f  mov     byte ptr [rdi+0Ch], 1
0x14000f923  lea     rcx, [rbx+0D0h]; WorkItem
0x14000f92a  xor     edx, edx; QueueType
0x14000f92c  lea     rax, WanpLinkDownIndicationWorkItem
0x14000f933  mov     [rcx+18h], rbx
0x14000f937  mov     [rcx+10h], rax
0x14000f93b  mov     qword ptr [rcx], 0
0x14000f942  call    cs:__imp_ExQueueWorkItem
0x14000f949  nop     dword ptr [rax+rax+00h]
0x14000f94e  jmp     short loc_14000F990
0x14000f950  mov     rcx, [rbx+50h]; SpinLock
0x14000f954  mov     dl, sil; NewIrql
0x14000f957  call    cs:__imp_KeReleaseSpinLock
0x14000f95e  nop     dword ptr [rax+rax+00h]
0x14000f963  or      eax, 0FFFFFFFFh
0x14000f966  lock xadd [rbx+60h], eax
0x14000f96b  cmp     eax, 1
0x14000f96e  jnz     short loc_14000F990
0x14000f970  mov     rcx, rbx; Entry
0x14000f973  call    WanpDeleteConnEntry
0x14000f978  jmp     short loc_14000F990
0x14000f97a  mov     dl, sil; NewIrql
0x14000f97d  lea     rcx, g_rlConnTableLock; SpinLock
0x14000f984  call    cs:__imp_KeReleaseSpinLock
0x14000f98b  nop     dword ptr [rax+rax+00h]
0x14000f990  mov     rbx, [rsp+28h+arg_0]
0x14000f995  xor     eax, eax
0x14000f997  mov     rsi, [rsp+28h+arg_8]
0x14000f99c  add     rsp, 20h
0x14000f9a0  pop     rdi
0x14000f9a1  retn
```
