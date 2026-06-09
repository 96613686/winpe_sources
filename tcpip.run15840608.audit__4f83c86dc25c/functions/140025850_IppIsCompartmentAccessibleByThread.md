# IppIsCompartmentAccessibleByThread

- ea: `0x140025850`
- end: `0x140025a82`
- name: `IppIsCompartmentAccessibleByThread`
- size: `562`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140024970`
- `0x140095190`
- `0x1400c1410`
- `0x140119180`
- `0x14011edf0`
- `0x140143f10`
- `0x1401866f8`
- `0x14018b770`
- `0x14018c0c4`
- `0x140191920`
- `0x1401920f0`
- `0x14019fe30`
- `0x1401a37d0`

## callees

- `0x140025850`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400258ec`
- `ntoskrnl!KfRaiseIrql` at `0x1400258ec`
- `ntoskrnl!KeLowerIrql` at `0x1400259a0`
- `ntoskrnl!KeLowerIrql` at `0x140025a65`
- `ntoskrnl!KeLowerIrql` at `0x1400259a0`
- `ntoskrnl!KeLowerIrql` at `0x140025a65`
- `ntoskrnl!IoQueueWorkItem` at `0x140025a4c`
- `ntoskrnl!IoQueueWorkItem` at `0x140025a4c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14002592e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14002592e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140025943`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140025943`
- `ntoskrnl!KeTestSpinLock` at `0x140025912`
- `ntoskrnl!KeTestSpinLock` at `0x140025912`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140025a06`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140025a06`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x1400258b8`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x1400258b8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400258d5`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400258d5`

## pseudocode

```c
__int64 __fastcall IppIsCompartmentAccessibleByThread(unsigned int *a1, __int64 a2, unsigned __int8 a3)
{
  __int64 v5; // rbx
  int ThreadObjectCompartmentId; // esi
  __int64 v7; // rdi
  KIRQL v8; // r15
  _QWORD **v9; // rdx
  _QWORD *i; // rax
  _QWORD *v11; // rbx
  signed __int64 v12; // rax
  bool v13; // cc
  signed __int64 v14; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-60h] BYREF

  memset(v17, 0, sizeof(v17));
  if ( !a2 )
  {
    v5 = *((_QWORD *)a1 + 5);
    NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), v17, (char *)v17 + 4);
    ThreadObjectCompartmentId = HIDWORD(v17[0]);
    if ( !HIDWORD(v17[0]) )
      ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    v7 = v5 + 19880;
    v8 = KfRaiseIrql(2u);
    memset(&LockHandle, 0, sizeof(LockHandle));
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 19888));
    if ( !KeTestSpinLock((PKSPIN_LOCK)(v5 + 19880)) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v5 + 19888));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v5 + 19880), &LockHandle);
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 19888));
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    }
    v9 = (_QWORD **)(*(_QWORD *)(v5 + 19872)
                   + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(v5 + 19868) - 1)));
    for ( i = *v9; ; i = (_QWORD *)*i )
    {
      if ( i == v9 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v7 + 8));
        KeLowerIrql(v8);
        return NetioIsCompartmentAccessibleByThread(*a1, a1 + 1, a3);
      }
      v11 = i - 6;
      if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
        break;
    }
    if ( _InterlockedIncrement64(v11 + 4) <= 1 )
      __fastfail(0xEu);
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 8));
    KeLowerIrql(v8);
    if ( v11 )
    {
      *(_OWORD *)&v17[1] = *(_OWORD *)((char *)v11 + 4);
      v12 = _InterlockedExchangeAdd64(v11 + 4, 0xFFFFFFFFFFFFFFFFuLL);
      v13 = v12 <= 1;
      v14 = v12 - 1;
      if ( v13 )
      {
        if ( v14 )
          __fastfail(0xEu);
        IoQueueWorkItem((PIO_WORKITEM)v11[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v11);
      }
    }
  }
  return NetioIsCompartmentAccessibleByThread(*a1, a1 + 1, a3);
}

```

## disassembly

```asm
0x140025850  mov     r11, rsp
0x140025853  push    rbp
0x140025854  push    r12
0x140025856  push    r14
0x140025858  sub     rsp, 90h
0x14002585f  mov     rax, cs:__security_cookie
0x140025866  xor     rax, rsp
0x140025869  mov     [rsp+0A8h+var_48], rax
0x14002586e  xor     eax, eax
0x140025870  xorps   xmm0, xmm0
0x140025873  movzx   r12d, r8b
0x140025877  mov     rbp, rdx
0x14002587a  mov     r14, rcx
0x14002587d  movups  xmmword ptr [rsp+0A8h+var_60], xmm0
0x140025882  mov     [r11-50h], rax
0x140025886  test    rdx, rdx
0x140025889  jnz     loc_1400259F3
0x14002588f  mov     [r11-20h], rbx
0x140025893  lea     r8, [r11-5Ch]
0x140025897  mov     rbx, [rcx+28h]
0x14002589b  lea     rdx, [r11-60h]
0x14002589f  mov     rcx, gs:188h
0x1400258a8  lea     rbp, [r11-60h]
0x1400258ac  mov     [r11-28h], rsi
0x1400258b0  mov     [r11-30h], rdi
0x1400258b4  mov     [r11-38h], r15
0x1400258b8  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x1400258bf  nop     dword ptr [rax+rax+00h]
0x1400258c4  mov     esi, dword ptr [rsp+0A8h+var_60+4]
0x1400258c8  test    esi, esi
0x1400258ca  jnz     short loc_1400258E3
0x1400258cc  mov     rcx, gs:188h
0x1400258d5  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400258dc  nop     dword ptr [rax+rax+00h]
0x1400258e1  mov     esi, eax
0x1400258e3  mov     cl, 2; NewIrql
0x1400258e5  lea     rdi, [rbx+4DA8h]
0x1400258ec  call    cs:__imp_KfRaiseIrql
0x1400258f3  nop     dword ptr [rax+rax+00h]
0x1400258f8  movzx   r15d, al
0x1400258fc  xorps   xmm0, xmm0
0x1400258ff  xor     eax, eax
0x140025901  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140025906  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14002590b  lock inc dword ptr [rdi+8]
0x14002590f  mov     rcx, rdi; SpinLock
0x140025912  call    cs:__imp_KeTestSpinLock
0x140025919  nop     dword ptr [rax+rax+00h]
0x14002591e  test    al, al
0x140025920  jnz     short loc_14002594F
0x140025922  lock dec dword ptr [rdi+8]
0x140025926  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14002592b  mov     rcx, rdi; SpinLock
0x14002592e  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140025935  nop     dword ptr [rax+rax+00h]
0x14002593a  lock inc dword ptr [rdi+8]
0x14002593e  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140025943  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14002594a  nop     dword ptr [rax+rax+00h]
0x14002594f  mov     edx, [rbx+4D9Ch]
0x140025955  dec     edx
0x140025957  mov     eax, esi
0x140025959  and     rdx, rax
0x14002595c  shl     rdx, 4
0x140025960  add     rdx, [rbx+4DA0h]
0x140025967  mov     rax, [rdx]
0x14002596a  cmp     rax, rdx
0x14002596d  jz      loc_140025A5D
0x140025973  cmp     [rax-30h], esi
0x140025976  lea     rbx, [rax-30h]
0x14002597a  jnz     loc_140025A2D
0x140025980  mov     eax, 1
0x140025985  lock xadd [rbx+20h], rax
0x14002598b  inc     rax
0x14002598e  cmp     rax, 1
0x140025992  jle     loc_140025A76
0x140025998  lock dec dword ptr [rdi+8]
0x14002599c  movzx   ecx, r15b; NewIrql
0x1400259a0  call    cs:__imp_KeLowerIrql
0x1400259a7  nop     dword ptr [rax+rax+00h]
0x1400259ac  test    rbx, rbx
0x1400259af  jz      short loc_1400259D9
0x1400259b1  movups  xmm0, xmmword ptr [rbx+4]
0x1400259b5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400259bc  movups  xmmword ptr [rsp+0A8h+var_60+8], xmm0
0x1400259c1  lock xadd [rbx+20h], rax
0x1400259c7  sub     rax, 1
0x1400259cb  jg      short loc_1400259D9
0x1400259cd  test    rax, rax
0x1400259d0  jz      short loc_140025A35
0x1400259d2  mov     ecx, 0Eh
0x1400259d7  int     29h; Win8: RtlFailFast(ecx)
0x1400259d9  mov     rdi, [rsp+0A8h+var_30]
0x1400259de  mov     rsi, [rsp+0A8h+var_28]
0x1400259e6  mov     rbx, [rsp+0A8h+var_20]
0x1400259ee  mov     r15, [rsp+0A8h+var_38]
0x1400259f3  mov     ecx, [r14]
0x1400259f6  lea     rdx, [r14+4]
0x1400259fa  mov     r9b, 1
0x1400259fd  mov     [rsp+0A8h+var_88], rbp
0x140025a02  movzx   r8d, r12b
0x140025a06  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140025a0d  nop     dword ptr [rax+rax+00h]
0x140025a12  mov     rcx, [rsp+0A8h+var_48]
0x140025a17  xor     rcx, rsp; StackCookie
0x140025a1a  call    __security_check_cookie
0x140025a1f  add     rsp, 90h
0x140025a26  pop     r14
0x140025a28  pop     r12
0x140025a2a  pop     rbp
0x140025a2b  retn
0x140025a2d  mov     rax, [rax]
0x140025a30  jmp     loc_14002596A
0x140025a35  mov     rcx, [rbx+80h]; IoWorkItem
0x140025a3c  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140025a43  mov     r9, rbx; Context
0x140025a46  mov     r8d, 1; QueueType
0x140025a4c  call    cs:__imp_IoQueueWorkItem
0x140025a53  nop     dword ptr [rax+rax+00h]
0x140025a58  jmp     loc_1400259D9
0x140025a5d  lock dec dword ptr [rdi+8]
0x140025a61  movzx   ecx, r15b; NewIrql
0x140025a65  call    cs:__imp_KeLowerIrql
0x140025a6c  nop     dword ptr [rax+rax+00h]
0x140025a71  jmp     loc_1400259D9
0x140025a76  mov     ecx, 0Eh
0x140025a7b  int     29h; Win8: RtlFailFast(ecx)
0x140025a7d  jmp     loc_140025998
```
