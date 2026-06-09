# TmSinglePhaseRejectExt

- ea: `0x1400106c0`
- end: `0x1400107f3`
- name: `TmSinglePhaseRejectExt`
- size: `307`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013f20`

## callees

- `0x1400106c0`
- `0x14001b338`
- `0x14001eb30`
- `0x1400209fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140010744`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010744`
- `ntoskrnl!KeReleaseMutex` at `0x140010761`
- `ntoskrnl!KeReleaseMutex` at `0x14001078c`
- `ntoskrnl!KeReleaseMutex` at `0x1400107db`
- `ntoskrnl!KeReleaseMutex` at `0x140010761`
- `ntoskrnl!KeReleaseMutex` at `0x14001078c`
- `ntoskrnl!KeReleaseMutex` at `0x1400107db`
- `ntoskrnl!DbgPrintEx` at `0x1400106f1`
- `ntoskrnl!DbgPrintEx` at `0x1400106f1`

## string_xrefs

- `0x1400106d0`: `KTM:  TmRollbackCompleteExt for tx %lx\n`

## pseudocode

```c
NTSTATUS __stdcall TmSinglePhaseRejectExt(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  __int64 v2; // rdi
  __int64 v3; // rbx
  _QWORD *v6; // rcx
  struct _KMUTANT *v8; // rcx
  NTSTATUS v9; // ebx

  v2 = *((_QWORD *)Enlistment + 20);
  v3 = *((_QWORD *)Enlistment + 19);
  DbgPrintEx(0x6Cu, 0x80000020, "KTM:  TmRollbackCompleteExt for tx %lx\n", v2);
  v6 = (_QWORD *)(v3 + 360);
  if ( TmVirtualClock && !*v6 )
    return -1072103342;
  TmpAdjustVirtualClock(*v6, TmVirtualClock);
  TmpAcquireTransactionMutex(v2);
  KeWaitForSingleObject((char *)Enlistment + 64, Executive, 0, 0, 0);
  v8 = (struct _KMUTANT *)((char *)Enlistment + 64);
  if ( *((_DWORD *)Enlistment + 42) == 264 )
  {
    *((_DWORD *)Enlistment + 42) = 256;
    --*(_DWORD *)(v2 + 236);
    *((_DWORD *)Enlistment + 44) &= ~0x200u;
    KeReleaseMutex(v8, 0);
    if ( (*(_DWORD *)(*(_QWORD *)(v2 + 512) + 128LL) & 0x10) != 0 )
      _InterlockedOr((volatile signed __int32 *)(v2 + 196), 0x10000u);
    _InterlockedOr((volatile signed __int32 *)(v2 + 196), 4u);
    *(_DWORD *)(v2 + 192) = 1;
    TmpTxActionDoPrePrepare(v2);
    v9 = 0;
  }
  else
  {
    KeReleaseMutex(v8, 0);
    v9 = -1072103404;
  }
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v2 + 88) + 32LL), 0);
  return v9;
}

```

## disassembly

```asm
0x1400106c0  push    rbx
0x1400106c2  push    rbp
0x1400106c3  push    rsi
0x1400106c4  push    rdi
0x1400106c5  sub     rsp, 38h
0x1400106c9  mov     rdi, [rcx+0A0h]
0x1400106d0  lea     r8, aKtmTmrollbackc; "KTM:  TmRollbackCompleteExt for tx %lx"...
0x1400106d7  mov     rbx, [rcx+98h]
0x1400106de  mov     rbp, rdx
0x1400106e1  mov     rsi, rcx
0x1400106e4  mov     r9, rdi
0x1400106e7  mov     edx, 80000020h; Level
0x1400106ec  mov     ecx, 6Ch ; 'l'; ComponentId
0x1400106f1  call    cs:__imp_DbgPrintEx
0x1400106f8  nop     dword ptr [rax+rax+00h]
0x1400106fd  lea     rcx, [rbx+168h]
0x140010704  test    rbp, rbp
0x140010707  jz      short loc_140010719
0x140010709  cmp     qword ptr [rcx], 0
0x14001070d  jnz     short loc_140010719
0x14001070f  mov     eax, 0C0190052h
0x140010714  jmp     loc_1400107E9
0x140010719  mov     rcx, [rcx]
0x14001071c  mov     rdx, rbp
0x14001071f  call    TmpAdjustVirtualClock
0x140010724  mov     rcx, rdi
0x140010727  call    TmpAcquireTransactionMutex
0x14001072c  lea     rbx, [rsi+40h]
0x140010730  mov     [rsp+58h+Timeout], 0; Timeout
0x140010739  mov     rcx, rbx; Object
0x14001073c  xor     r9d, r9d; Alertable
0x14001073f  xor     r8d, r8d; WaitMode
0x140010742  xor     edx, edx; WaitReason
0x140010744  call    cs:__imp_KeWaitForSingleObject
0x14001074b  nop     dword ptr [rax+rax+00h]
0x140010750  xor     edx, edx; Wait
0x140010752  mov     rcx, rbx; Mutex
0x140010755  cmp     dword ptr [rsi+0A8h], 108h
0x14001075f  jz      short loc_140010774
0x140010761  call    cs:__imp_KeReleaseMutex
0x140010768  nop     dword ptr [rax+rax+00h]
0x14001076d  mov     ebx, 0C0190014h
0x140010772  jmp     short loc_1400107D1
0x140010774  mov     dword ptr [rsi+0A8h], 100h
0x14001077e  dec     dword ptr [rdi+0ECh]
0x140010784  btr     dword ptr [rsi+0B0h], 9
0x14001078c  call    cs:__imp_KeReleaseMutex
0x140010793  nop     dword ptr [rax+rax+00h]
0x140010798  mov     rax, [rdi+200h]
0x14001079f  mov     ecx, [rax+80h]
0x1400107a5  test    cl, 10h
0x1400107a8  jz      short loc_1400107B5
0x1400107aa  lock or dword ptr [rdi+0C4h], 10000h
0x1400107b5  lock or dword ptr [rdi+0C4h], 4
0x1400107bd  mov     rcx, rdi; int
0x1400107c0  mov     dword ptr [rdi+0C0h], 1
0x1400107ca  call    TmpTxActionDoPrePrepare
0x1400107cf  xor     ebx, ebx
0x1400107d1  mov     rcx, [rdi+58h]
0x1400107d5  xor     edx, edx; Wait
0x1400107d7  add     rcx, 20h ; ' '; Mutex
0x1400107db  call    cs:__imp_KeReleaseMutex
0x1400107e2  nop     dword ptr [rax+rax+00h]
0x1400107e7  mov     eax, ebx
0x1400107e9  add     rsp, 38h
0x1400107ed  pop     rdi
0x1400107ee  pop     rsi
0x1400107ef  pop     rbp
0x1400107f0  pop     rbx
0x1400107f1  retn
```
