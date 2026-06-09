# FinishWaitWakeCompletionForFunctionSuspend

- ea: `0x140013eb0`
- end: `0x14001402e`
- name: `FinishWaitWakeCompletionForFunctionSuspend`
- size: `382`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140005bb0`
- `0x140008980`
- `0x140014560`

## callees

- `0x1400054a0`
- `0x1400059e4`
- `0x140005eb0`
- `0x1400083c8`
- `0x140008d58`
- `0x140013eb0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140014014`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140014014`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013ed1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013f64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013ed1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013f64`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013fba`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013fba`
- `ntoskrnl!KeSetEvent` at `0x140013f7f`
- `ntoskrnl!KeSetEvent` at `0x140013f7f`

## pseudocode

```c
void __fastcall FinishWaitWakeCompletionForFunctionSuspend(char *Context)
{
  KSPIN_LOCK *v1; // r14
  void *v3; // rdi
  char v4; // bp
  __int64 v5; // rsi
  int v6; // edx
  KIRQL v7; // r15
  void *v8; // rax
  KIRQL v9; // r15
  int v10; // edx

  v1 = (KSPIN_LOCK *)(Context + 400);
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 50);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)Context + 171),
      v6,
      3,
      24,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *((_QWORD *)Context + 4));
  }
  v8 = (void *)*((_QWORD *)Context + 48);
  Context[440] = 0;
  if ( v8 )
  {
    v3 = v8;
    *((_QWORD *)Context + 48) = 0;
  }
  _InterlockedExchange((volatile __int32 *)Context + 98, 0);
  _InterlockedExchange((volatile __int32 *)Context + 99, 0);
  KeReleaseSpinLock(v1, v7);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 43);
  KeSetEvent((PRKEVENT)(Context + 416), 0, 0);
  v10 = *((_DWORD *)Context + 307);
  if ( (v10 & 0x20) != 0 )
  {
    v5 = *((_QWORD *)Context + 154);
    *((_DWORD *)Context + 307) = v10 & 0xFFFFFFDF;
    v4 = 1;
    *((_QWORD *)Context + 154) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 43, v9);
  if ( v4 && (int)AllocateWorker(Context, IdleFinishCompletionWorker, v5) < 0 )
    IdleFinishCompletionWorker(Context, v5);
  CheckParentWaitWake(Context);
  if ( v3 )
  {
    UsbcReleaseRemoveLock(Context, v3);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), v3, 0x20u);
  }
}

```

## disassembly

```asm
0x140013eb0  push    rbx
0x140013eb2  push    rbp
0x140013eb3  push    rsi
0x140013eb4  push    rdi
0x140013eb5  push    r14
0x140013eb7  push    r15
0x140013eb9  sub     rsp, 38h
0x140013ebd  lea     r14, [rcx+190h]
0x140013ec4  mov     rbx, rcx
0x140013ec7  mov     rcx, r14; SpinLock
0x140013eca  xor     edi, edi
0x140013ecc  xor     bpl, bpl
0x140013ecf  xor     esi, esi
0x140013ed1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013ed8  nop     dword ptr [rax+rax+00h]
0x140013edd  mov     r15b, al
0x140013ee0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140013ee7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013eee  jz      short loc_140013F1B
0x140013ef0  mov     rcx, [rbx+20h]
0x140013ef4  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140013efb  mov     [rsp+68h+var_40], rcx
0x140013f00  lea     r9d, [rdi+18h]
0x140013f04  mov     rcx, [rbx+558h]
0x140013f0b  lea     r8d, [rdi+3]
0x140013f0f  mov     dl, 4
0x140013f11  mov     [rsp+68h+var_48], rax
0x140013f16  call    WPP_RECORDER_SF_q
0x140013f1b  mov     rax, [rbx+180h]
0x140013f22  mov     [rbx+1B8h], sil
0x140013f29  test    rax, rax
0x140013f2c  jz      short loc_140013F38
0x140013f2e  mov     rdi, rax
0x140013f31  mov     [rbx+180h], rsi
0x140013f38  xor     eax, eax
0x140013f3a  mov     dl, r15b; NewIrql
0x140013f3d  xchg    eax, [rbx+188h]
0x140013f43  xor     eax, eax
0x140013f45  mov     rcx, r14; SpinLock
0x140013f48  xchg    eax, [rbx+18Ch]
0x140013f4e  call    cs:__imp_KeReleaseSpinLock
0x140013f55  nop     dword ptr [rax+rax+00h]
0x140013f5a  lea     r14, [rbx+158h]
0x140013f61  mov     rcx, r14; SpinLock
0x140013f64  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013f6b  nop     dword ptr [rax+rax+00h]
0x140013f70  lea     rcx, [rbx+1A0h]; Event
0x140013f77  xor     r8d, r8d; Wait
0x140013f7a  xor     edx, edx; Increment
0x140013f7c  mov     r15b, al
0x140013f7f  call    cs:__imp_KeSetEvent
0x140013f86  nop     dword ptr [rax+rax+00h]
0x140013f8b  mov     edx, [rbx+4CCh]
0x140013f91  test    dl, 20h
0x140013f94  jz      short loc_140013FB4
0x140013f96  mov     rsi, [rbx+4D0h]
0x140013f9d  and     edx, 0FFFFFFDFh
0x140013fa0  mov     [rbx+4CCh], edx
0x140013fa6  mov     bpl, 1
0x140013fa9  mov     qword ptr [rbx+4D0h], 0
0x140013fb4  mov     dl, r15b; NewIrql
0x140013fb7  mov     rcx, r14; SpinLock
0x140013fba  call    cs:__imp_KeReleaseSpinLock
0x140013fc1  nop     dword ptr [rax+rax+00h]
0x140013fc6  test    bpl, bpl
0x140013fc9  jz      short loc_140013FEC
0x140013fcb  mov     r8, rsi
0x140013fce  lea     rdx, IdleFinishCompletionWorker
0x140013fd5  mov     rcx, rbx
0x140013fd8  call    AllocateWorker
0x140013fdd  test    eax, eax
0x140013fdf  jns     short loc_140013FEC
0x140013fe1  mov     rdx, rsi
0x140013fe4  mov     rcx, rbx
0x140013fe7  call    IdleFinishCompletionWorker
0x140013fec  mov     rcx, rbx; Context
0x140013fef  call    CheckParentWaitWake
0x140013ff4  test    rdi, rdi
0x140013ff7  jz      short loc_140014020
0x140013ff9  mov     rdx, rdi
0x140013ffc  mov     rcx, rbx
0x140013fff  call    UsbcReleaseRemoveLock
0x140014004  lea     rcx, [rbx+0C8h]; RemoveLock
0x14001400b  mov     r8d, 20h ; ' '; RemlockSize
0x140014011  mov     rdx, rdi; Tag
0x140014014  call    cs:__imp_IoReleaseRemoveLockEx
0x14001401b  nop     dword ptr [rax+rax+00h]
0x140014020  add     rsp, 38h
0x140014024  pop     r15
0x140014026  pop     r14
0x140014028  pop     rdi
0x140014029  pop     rsi
0x14001402a  pop     rbp
0x14001402b  pop     rbx
0x14001402c  retn
```
