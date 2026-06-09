# SqospLimiterProcessQueue

- ea: `0x140006e98`
- end: `0x14000702b`
- name: `SqospLimiterProcessQueue`
- size: `403`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140001940`
- `0x140007238`

## callees

- `0x140003de0`
- `0x140006ce4`
- `0x140006d40`
- `0x140006e98`
- `0x140007034`
- `0x140007094`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140006f33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007001`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007001`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006f15`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006fed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006f15`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006fed`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140006edc`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140006edc`

## pseudocode

```c
void __fastcall SqospLimiterProcessQueue(KSPIN_LOCK *Context, __int64 a2)
{
  struct _FLT_CALLBACK_DATA_QUEUE *v4; // rax
  unsigned __int64 v5; // r13
  PFLT_CALLBACK_DATA v6; // rax
  _QWORD *v7; // rsi
  __int64 v8; // r14
  KIRQL v9; // bl
  _QWORD *v10; // rcx
  _QWORD **v11; // rax
  _QWORD *v12; // rcx
  _QWORD **v13; // rdx
  _QWORD **v14; // rbx
  KIRQL v15; // al
  int v16; // ebx
  _QWORD *v17; // [rsp+20h] [rbp-18h] BYREF
  _QWORD **v18; // [rsp+28h] [rbp-10h]

  v18 = &v17;
  v17 = &v17;
  v4 = (struct _FLT_CALLBACK_DATA_QUEUE *)(Context + 84);
  v5 = MEMORY[0xFFFFF78000000008];
  while ( 1 )
  {
    v6 = FltCbdqRemoveNextIo(v4, 0);
    if ( !v6 )
      break;
    v7 = v6->QueueContext[0];
    if ( !v7 )
      break;
    v8 = v7[5];
    if ( v5 >= *(_QWORD *)(v8 + 496) )
    {
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 480));
      SqospLimiterReplenishQuota(v8, v5);
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 480), v9);
    }
    if ( (unsigned __int8)SqospDecrementFlowQuota(v8, v7) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 520));
      SqospQueueJobForDispatch(v7, a2);
    }
    else
    {
      v10 = v18;
      if ( *v18 != &v17 )
LABEL_16:
        __fastfail(3u);
      v7[13] = v18;
      v7[12] = &v17;
      *v10 = v7 + 12;
      v18 = (_QWORD **)(v7 + 12);
    }
    v4 = (struct _FLT_CALLBACK_DATA_QUEUE *)(Context + 84);
  }
  while ( v17 != &v17 )
  {
    v11 = v18;
    if ( *v18 != &v17 )
      goto LABEL_16;
    v12 = v18[1];
    if ( (_QWORD **)*v12 != v18 )
      goto LABEL_16;
    v13 = &v17;
    v18 = (_QWORD **)v18[1];
    *v12 = &v17;
    v14 = v11 - 12;
    LOBYTE(v13) = 1;
    if ( !(unsigned __int8)SqospLimiterQueueJob(v11 - 12, v13) )
      SqospQueueJobForDispatch(v14, a2);
  }
  v15 = KeAcquireSpinLockRaiseToDpc(Context + 80);
  v16 = *((_DWORD *)Context + 166);
  KeReleaseSpinLock(Context + 80, v15);
  if ( v16 )
    SqospQueueDeviceWorkItem(Context);
}

```

## disassembly

```asm
0x140006e98  push    rbp
0x140006e9a  push    rbx
0x140006e9b  push    rsi
0x140006e9c  push    rdi
0x140006e9d  push    r12
0x140006e9f  push    r13
0x140006ea1  push    r14
0x140006ea3  push    r15
0x140006ea5  mov     rbp, rsp
0x140006ea8  sub     rsp, 38h
0x140006eac  lea     rax, [rbp+var_18]
0x140006eb0  mov     r13, 0FFFFF78000000008h
0x140006eba  mov     [rbp+var_10], rax
0x140006ebe  mov     r12, rdx
0x140006ec1  lea     rax, [rbp+var_18]
0x140006ec5  mov     r15, rcx
0x140006ec8  mov     [rbp+var_18], rax
0x140006ecc  lea     rax, [rcx+2A0h]
0x140006ed3  mov     r13, [r13+0]
0x140006ed7  xor     edx, edx; PeekContext
0x140006ed9  mov     rcx, rax; Cbdq
0x140006edc  call    cs:__imp_FltCbdqRemoveNextIo
0x140006ee3  nop     dword ptr [rax+rax+00h]
0x140006ee8  test    rax, rax
0x140006eeb  jz      loc_140006F92
0x140006ef1  mov     rsi, [rax+40h]
0x140006ef5  test    rsi, rsi
0x140006ef8  jz      loc_140006F92
0x140006efe  mov     r14, [rsi+28h]
0x140006f02  cmp     r13, [r14+1F0h]
0x140006f09  jb      short loc_140006F3F
0x140006f0b  lea     rdi, [r14+1E0h]
0x140006f12  mov     rcx, rdi; SpinLock
0x140006f15  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006f1c  nop     dword ptr [rax+rax+00h]
0x140006f21  mov     rdx, r13
0x140006f24  mov     rcx, r14
0x140006f27  mov     bl, al
0x140006f29  call    SqospLimiterReplenishQuota
0x140006f2e  mov     dl, bl; NewIrql
0x140006f30  mov     rcx, rdi; SpinLock
0x140006f33  call    cs:__imp_KeReleaseSpinLock
0x140006f3a  nop     dword ptr [rax+rax+00h]
0x140006f3f  mov     rdx, rsi
0x140006f42  mov     rcx, r14
0x140006f45  call    SqospDecrementFlowQuota
0x140006f4a  test    al, al
0x140006f4c  jz      short loc_140006F63
0x140006f4e  lock dec dword ptr [r14+208h]
0x140006f56  mov     rdx, r12
0x140006f59  mov     rcx, rsi
0x140006f5c  call    SqospQueueJobForDispatch
0x140006f61  jmp     short loc_140006F86
0x140006f63  mov     rcx, [rbp+var_10]
0x140006f67  lea     rax, [rbp+var_18]
0x140006f6b  cmp     [rcx], rax
0x140006f6e  jnz     short loc_140006FDC
0x140006f70  lea     rax, [rsi+60h]
0x140006f74  mov     [rax+8], rcx
0x140006f78  lea     rdx, [rbp+var_18]
0x140006f7c  mov     [rax], rdx
0x140006f7f  mov     [rcx], rax
0x140006f82  mov     [rbp+var_10], rax
0x140006f86  lea     rax, [r15+2A0h]
0x140006f8d  jmp     loc_140006ED7
0x140006f92  lea     rax, [rbp+var_18]
0x140006f96  cmp     [rbp+var_18], rax
0x140006f9a  jz      short loc_140006FE3
0x140006f9c  mov     rax, [rbp+var_10]
0x140006fa0  lea     rcx, [rbp+var_18]
0x140006fa4  cmp     [rax], rcx
0x140006fa7  jnz     short loc_140006FDC
0x140006fa9  mov     rcx, [rax+8]
0x140006fad  cmp     [rcx], rax
0x140006fb0  jnz     short loc_140006FDC
0x140006fb2  lea     rdx, [rbp+var_18]
0x140006fb6  mov     [rbp+var_10], rcx
0x140006fba  mov     [rcx], rdx
0x140006fbd  lea     rbx, [rax-60h]
0x140006fc1  mov     dl, 1
0x140006fc3  mov     rcx, rbx
0x140006fc6  call    SqospLimiterQueueJob
0x140006fcb  test    al, al
0x140006fcd  jnz     short loc_140006F92
0x140006fcf  mov     rdx, r12
0x140006fd2  mov     rcx, rbx
0x140006fd5  call    SqospQueueJobForDispatch
0x140006fda  jmp     short loc_140006F92
0x140006fdc  mov     ecx, 3
0x140006fe1  int     29h; Win8: RtlFailFast(ecx)
0x140006fe3  lea     rdi, [r15+280h]
0x140006fea  mov     rcx, rdi; SpinLock
0x140006fed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006ff4  nop     dword ptr [rax+rax+00h]
0x140006ff9  mov     ebx, [rdi+18h]
0x140006ffc  mov     rcx, rdi; SpinLock
0x140006fff  mov     dl, al; NewIrql
0x140007001  call    cs:__imp_KeReleaseSpinLock
0x140007008  nop     dword ptr [rax+rax+00h]
0x14000700d  test    ebx, ebx
0x14000700f  jz      short loc_140007019
0x140007011  mov     rcx, r15; Context
0x140007014  call    SqospQueueDeviceWorkItem
0x140007019  add     rsp, 38h
0x14000701d  pop     r15
0x14000701f  pop     r14
0x140007021  pop     r13
0x140007023  pop     r12
0x140007025  pop     rdi
0x140007026  pop     rsi
0x140007027  pop     rbx
0x140007028  pop     rbp
0x140007029  retn
```
