# TmThawTransactionsExt

- ea: `0x140010e70`
- end: `0x140010faa`
- name: `TmThawTransactionsExt`
- size: `314`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011a90`
- `0x140017280`
- `0x14001e810`

## callees

- `0x140010e70`
- `0x14001d510`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140010ec3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010ec3`
- `ntoskrnl!KeReleaseMutex` at `0x140010f95`
- `ntoskrnl!KeReleaseMutex` at `0x140021dc1`
- `ntoskrnl!KeReleaseMutex` at `0x140010f95`
- `ntoskrnl!KeReleaseMutex` at `0x140021dc1`
- `ntoskrnl!KeSetEvent` at `0x140010e9f`
- `ntoskrnl!KeSetEvent` at `0x140010ee0`
- `ntoskrnl!KeSetEvent` at `0x140010f1f`
- `ntoskrnl!KeSetEvent` at `0x140010e9f`
- `ntoskrnl!KeSetEvent` at `0x140010ee0`
- `ntoskrnl!KeSetEvent` at `0x140010f1f`
- `ntoskrnl!KeResetEvent` at `0x140010f45`
- `ntoskrnl!KeResetEvent` at `0x140010f45`
- `ntoskrnl!KeCancelTimer` at `0x140010f32`
- `ntoskrnl!KeCancelTimer` at `0x140010f32`

## pseudocode

```c
__int64 TmThawTransactionsExt()
{
  unsigned int v0; // ebx
  __int128 v2; // [rsp+38h] [rbp-20h] BYREF
  __int64 v3; // [rsp+48h] [rbp-10h]

  v2 = 0;
  v3 = 0;
  KeSetEvent(&TmpTransactionFreezeCancelEvent, 0, 0);
  KeWaitForSingleObject(&TmpFreezeMutex, Executive, 0, 0, 0);
  KeSetEvent(&TmpTransactionFreezeCancelEvent, 0, 0);
  if ( TmpTransactionsFreezeCancelled )
  {
    TmpTransactionsFreezeCancelled = 0;
    v0 = 0;
  }
  else if ( TmpTransactionsFrozen )
  {
    KeSetEvent(&TmpTransactionThawEvent, 0, 0);
    KeCancelTimer(&TmpTransactionThawTimer);
    KeResetEvent(&TmpTransactionFreezeCompleteEvent);
    TmpTransactionsFrozen = 0;
    LOBYTE(v2) = 0;
    *((_QWORD *)&v2 + 1) = 0;
    v0 = TmpNamespaceForEach(
           &TmpTmNamespace,
           0,
           (__int64 (__fastcall *)(_BYTE *, __int64))TmpFreezeThawTransactionManager,
           (__int64)&v2);
    TmpTransactionsCommittedActive = 0;
  }
  else
  {
    v0 = -1072103355;
  }
  KeReleaseMutex(&TmpFreezeMutex, 0);
  return v0;
}

```

## disassembly

```asm
0x140010e70  push    rbx
0x140010e72  sub     rsp, 50h
0x140010e76  mov     [rsp+58h+var_28], 0
0x140010e7b  xor     eax, eax
0x140010e7d  xorps   xmm0, xmm0
0x140010e80  movups  [rsp+58h+var_20], xmm0
0x140010e85  mov     byte ptr [rsp+58h+var_10], al
0x140010e89  movups  [rsp+58h+var_20], xmm0
0x140010e8e  mov     [rsp+58h+var_10], rax
0x140010e93  xor     r8d, r8d; Wait
0x140010e96  xor     edx, edx; Increment
0x140010e98  lea     rcx, TmpTransactionFreezeCancelEvent; Event
0x140010e9f  call    cs:__imp_KeSetEvent
0x140010ea6  nop     dword ptr [rax+rax+00h]
0x140010eab  mov     [rsp+58h+Timeout], 0; Timeout
0x140010eb4  xor     r9d, r9d; Alertable
0x140010eb7  xor     r8d, r8d; WaitMode
0x140010eba  xor     edx, edx; WaitReason
0x140010ebc  lea     rcx, TmpFreezeMutex; Object
0x140010ec3  call    cs:__imp_KeWaitForSingleObject
0x140010eca  nop     dword ptr [rax+rax+00h]
0x140010ecf  mov     [rsp+58h+var_28], 1
0x140010ed4  xor     r8d, r8d; Wait
0x140010ed7  xor     edx, edx; Increment
0x140010ed9  lea     rcx, TmpTransactionFreezeCancelEvent; Event
0x140010ee0  call    cs:__imp_KeSetEvent
0x140010ee7  nop     dword ptr [rax+rax+00h]
0x140010eec  cmp     cs:TmpTransactionsFreezeCancelled, 0
0x140010ef3  jz      short loc_140010F03
0x140010ef5  mov     cs:TmpTransactionsFreezeCancelled, 0
0x140010efc  xor     ebx, ebx
0x140010efe  jmp     loc_140010F8C
0x140010f03  cmp     cs:TmpTransactionsFrozen, 0
0x140010f0a  jnz     short loc_140010F13
0x140010f0c  mov     ebx, 0C0190045h
0x140010f11  jmp     short loc_140010F8C
0x140010f13  xor     r8d, r8d; Wait
0x140010f16  xor     edx, edx; Increment
0x140010f18  lea     rcx, TmpTransactionThawEvent; Event
0x140010f1f  call    cs:__imp_KeSetEvent
0x140010f26  nop     dword ptr [rax+rax+00h]
0x140010f2b  lea     rcx, TmpTransactionThawTimer; PKTIMER
0x140010f32  call    cs:__imp_KeCancelTimer
0x140010f39  nop     dword ptr [rax+rax+00h]
0x140010f3e  lea     rcx, TmpTransactionFreezeCompleteEvent; Event
0x140010f45  call    cs:__imp_KeResetEvent
0x140010f4c  nop     dword ptr [rax+rax+00h]
0x140010f51  mov     cs:TmpTransactionsFrozen, 0
0x140010f58  mov     byte ptr [rsp+58h+var_20], 0
0x140010f5d  mov     qword ptr [rsp+58h+var_20+8], 0
0x140010f66  lea     r9, [rsp+58h+var_20]
0x140010f6b  lea     r8, TmpFreezeThawTransactionManager
0x140010f72  xor     edx, edx
0x140010f74  lea     rcx, TmpTmNamespace; Table
0x140010f7b  call    TmpNamespaceForEach
0x140010f80  mov     ebx, eax
0x140010f82  mov     cs:TmpTransactionsCommittedActive, 0
0x140010f8c  xor     edx, edx; Wait
0x140010f8e  lea     rcx, TmpFreezeMutex; Mutex
0x140010f95  call    cs:__imp_KeReleaseMutex
0x140010f9c  nop     dword ptr [rax+rax+00h]
0x140010fa1  mov     eax, ebx
0x140010fa3  add     rsp, 50h
0x140010fa7  pop     rbx
0x140010fa8  retn
0x140021da9  push    rbp
0x140021dab  sub     rsp, 30h
0x140021daf  mov     rbp, rdx
0x140021db2  cmp     byte ptr [rbp+30h], 0
0x140021db6  jz      short loc_140021DD1
0x140021db8  xor     edx, edx; Wait
0x140021dba  lea     rcx, TmpFreezeMutex; Mutex
0x140021dc1  call    cs:__imp_KeReleaseMutex
0x140021dc8  nop     dword ptr [rax+rax+00h]
0x140021dcd  mov     byte ptr [rbp+30h], 0
0x140021dd1  add     rsp, 30h
0x140021dd5  pop     rbp
0x140021dd6  retn
```
