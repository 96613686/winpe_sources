# IppIsCompartmentAccessibleByThread

- ea: `0x1400665b0`
- end: `0x1400667e2`
- name: `IppIsCompartmentAccessibleByThread`
- size: `562`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400656d0`
- `0x1400801e0`
- `0x1400a2460`
- `0x1400e1a90`
- `0x1401077d0`
- `0x1401401e0`
- `0x140184c18`
- `0x140189c40`
- `0x14018a594`
- `0x14018fc80`
- `0x140190450`
- `0x14019e1b0`
- `0x1401a1b50`

## callees

- `0x1400665b0`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14006664c`
- `ntoskrnl!KfRaiseIrql` at `0x14006664c`
- `ntoskrnl!KeLowerIrql` at `0x140066700`
- `ntoskrnl!KeLowerIrql` at `0x1400667c5`
- `ntoskrnl!KeLowerIrql` at `0x140066700`
- `ntoskrnl!KeLowerIrql` at `0x1400667c5`
- `ntoskrnl!IoQueueWorkItem` at `0x1400667ac`
- `ntoskrnl!IoQueueWorkItem` at `0x1400667ac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006668e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006668e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400666a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400666a3`
- `ntoskrnl!KeTestSpinLock` at `0x140066672`
- `ntoskrnl!KeTestSpinLock` at `0x140066672`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140066766`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140066766`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140066618`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140066618`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140066635`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140066635`

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
0x1400665b0  mov     r11, rsp
0x1400665b3  push    rbp
0x1400665b4  push    r12
0x1400665b6  push    r14
0x1400665b8  sub     rsp, 90h
0x1400665bf  mov     rax, cs:__security_cookie
0x1400665c6  xor     rax, rsp
0x1400665c9  mov     [rsp+0A8h+var_48], rax
0x1400665ce  xor     eax, eax
0x1400665d0  xorps   xmm0, xmm0
0x1400665d3  movzx   r12d, r8b
0x1400665d7  mov     rbp, rdx
0x1400665da  mov     r14, rcx
0x1400665dd  movups  xmmword ptr [rsp+0A8h+var_60], xmm0
0x1400665e2  mov     [r11-50h], rax
0x1400665e6  test    rdx, rdx
0x1400665e9  jnz     loc_140066753
0x1400665ef  mov     [r11-20h], rbx
0x1400665f3  lea     r8, [r11-5Ch]
0x1400665f7  mov     rbx, [rcx+28h]
0x1400665fb  lea     rdx, [r11-60h]
0x1400665ff  mov     rcx, gs:188h
0x140066608  lea     rbp, [r11-60h]
0x14006660c  mov     [r11-28h], rsi
0x140066610  mov     [r11-30h], rdi
0x140066614  mov     [r11-38h], r15
0x140066618  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14006661f  nop     dword ptr [rax+rax+00h]
0x140066624  mov     esi, dword ptr [rsp+0A8h+var_60+4]
0x140066628  test    esi, esi
0x14006662a  jnz     short loc_140066643
0x14006662c  mov     rcx, gs:188h
0x140066635  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14006663c  nop     dword ptr [rax+rax+00h]
0x140066641  mov     esi, eax
0x140066643  mov     cl, 2; NewIrql
0x140066645  lea     rdi, [rbx+4DA8h]
0x14006664c  call    cs:__imp_KfRaiseIrql
0x140066653  nop     dword ptr [rax+rax+00h]
0x140066658  movzx   r15d, al
0x14006665c  xorps   xmm0, xmm0
0x14006665f  xor     eax, eax
0x140066661  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140066666  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14006666b  lock inc dword ptr [rdi+8]
0x14006666f  mov     rcx, rdi; SpinLock
0x140066672  call    cs:__imp_KeTestSpinLock
0x140066679  nop     dword ptr [rax+rax+00h]
0x14006667e  test    al, al
0x140066680  jnz     short loc_1400666AF
0x140066682  lock dec dword ptr [rdi+8]
0x140066686  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14006668b  mov     rcx, rdi; SpinLock
0x14006668e  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140066695  nop     dword ptr [rax+rax+00h]
0x14006669a  lock inc dword ptr [rdi+8]
0x14006669e  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x1400666a3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400666aa  nop     dword ptr [rax+rax+00h]
0x1400666af  mov     edx, [rbx+4D9Ch]
0x1400666b5  dec     edx
0x1400666b7  mov     eax, esi
0x1400666b9  and     rdx, rax
0x1400666bc  shl     rdx, 4
0x1400666c0  add     rdx, [rbx+4DA0h]
0x1400666c7  mov     rax, [rdx]
0x1400666ca  cmp     rax, rdx
0x1400666cd  jz      loc_1400667BD
0x1400666d3  cmp     [rax-30h], esi
0x1400666d6  lea     rbx, [rax-30h]
0x1400666da  jnz     loc_14006678D
0x1400666e0  mov     eax, 1
0x1400666e5  lock xadd [rbx+20h], rax
0x1400666eb  inc     rax
0x1400666ee  cmp     rax, 1
0x1400666f2  jle     loc_1400667D6
0x1400666f8  lock dec dword ptr [rdi+8]
0x1400666fc  movzx   ecx, r15b; NewIrql
0x140066700  call    cs:__imp_KeLowerIrql
0x140066707  nop     dword ptr [rax+rax+00h]
0x14006670c  test    rbx, rbx
0x14006670f  jz      short loc_140066739
0x140066711  movups  xmm0, xmmword ptr [rbx+4]
0x140066715  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14006671c  movups  xmmword ptr [rsp+0A8h+var_60+8], xmm0
0x140066721  lock xadd [rbx+20h], rax
0x140066727  sub     rax, 1
0x14006672b  jg      short loc_140066739
0x14006672d  test    rax, rax
0x140066730  jz      short loc_140066795
0x140066732  mov     ecx, 0Eh
0x140066737  int     29h; Win8: RtlFailFast(ecx)
0x140066739  mov     rdi, [rsp+0A8h+var_30]
0x14006673e  mov     rsi, [rsp+0A8h+var_28]
0x140066746  mov     rbx, [rsp+0A8h+var_20]
0x14006674e  mov     r15, [rsp+0A8h+var_38]
0x140066753  mov     ecx, [r14]
0x140066756  lea     rdx, [r14+4]
0x14006675a  mov     r9b, 1
0x14006675d  mov     [rsp+0A8h+var_88], rbp
0x140066762  movzx   r8d, r12b
0x140066766  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x14006676d  nop     dword ptr [rax+rax+00h]
0x140066772  mov     rcx, [rsp+0A8h+var_48]
0x140066777  xor     rcx, rsp; StackCookie
0x14006677a  call    __security_check_cookie
0x14006677f  add     rsp, 90h
0x140066786  pop     r14
0x140066788  pop     r12
0x14006678a  pop     rbp
0x14006678b  retn
0x14006678d  mov     rax, [rax]
0x140066790  jmp     loc_1400666CA
0x140066795  mov     rcx, [rbx+80h]; IoWorkItem
0x14006679c  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x1400667a3  mov     r9, rbx; Context
0x1400667a6  mov     r8d, 1; QueueType
0x1400667ac  call    cs:__imp_IoQueueWorkItem
0x1400667b3  nop     dword ptr [rax+rax+00h]
0x1400667b8  jmp     loc_140066739
0x1400667bd  lock dec dword ptr [rdi+8]
0x1400667c1  movzx   ecx, r15b; NewIrql
0x1400667c5  call    cs:__imp_KeLowerIrql
0x1400667cc  nop     dword ptr [rax+rax+00h]
0x1400667d1  jmp     loc_140066739
0x1400667d6  mov     ecx, 0Eh
0x1400667db  int     29h; Win8: RtlFailFast(ecx)
0x1400667dd  jmp     loc_1400666F8
```
