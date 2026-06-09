# LockSendSetFeatureControlRequestForFunctionSuspend

- ea: `0x140009804`
- end: `0x1400099a0`
- name: `LockSendSetFeatureControlRequestForFunctionSuspend`
- size: `412`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005fc4`
- `0x140007e70`

## callees

- `0x1400054a0`
- `0x140009590`
- `0x140009804`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140009902`
- `ntoskrnl!IofCompleteRequest` at `0x140009902`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400098d8`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400098d8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009938`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009938`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009839`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009911`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009839`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009911`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000987a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000997c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000987a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400098f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000997c`
- `ntoskrnl!KeSetEvent` at `0x14000989f`
- `ntoskrnl!KeSetEvent` at `0x14000989f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009864`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009864`
- `ntoskrnl!ExAllocatePool2` at `0x1400098c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400098c4`

## pseudocode

```c
void __fastcall LockSendSetFeatureControlRequestForFunctionSuspend(__int64 a1, __int64 a2, IRP *a3, unsigned int a4)
{
  KSPIN_LOCK *v4; // rdi
  void *v9; // r12
  KIRQL v10; // si
  __int64 Pool2; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rax
  union _LARGE_INTEGER Timeout; // [rsp+68h] [rbp+10h] BYREF

  v4 = (KSPIN_LOCK *)(a2 + 456);
  Timeout.QuadPart = 0;
  v9 = (void *)(a2 + 432);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 456));
  if ( KeWaitForSingleObject(v9, Executive, 0, 0, &Timeout) )
  {
    Pool2 = ExAllocatePool2(64, 32, 1130525525);
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 8) = a4;
      *(_QWORD *)Pool2 = a3;
      v12 = *(_QWORD **)(a2 + 472);
      if ( *v12 != a2 + 464 )
        __fastfail(3u);
      v13 = (_QWORD *)(Pool2 + 16);
      v13[1] = v12;
      *v13 = a2 + 464;
      *v12 = v13;
      *(_QWORD *)(a2 + 472) = v13;
    }
    else
    {
      PoStartNextPowerIrp(a3);
      a3->IoStatus.Status = 0;
      KeReleaseSpinLock(v4, v10);
      IofCompleteRequest(a3, 0);
      v10 = KeAcquireSpinLockRaiseToDpc(v4);
      UsbcReleaseRemoveLock(a1, a3);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), a3, 0x20u);
    }
    KeReleaseSpinLock(v4, v10);
  }
  else
  {
    KeReleaseSpinLock(v4, v10);
    SendSetFeatureControlRequestForFunctionSuspend(a1, a2, a3, a4);
    KeSetEvent((PRKEVENT)(a2 + 432), 0, 0);
  }
}

```

## disassembly

```asm
0x140009804  mov     [rsp+arg_0], rbx
0x140009809  mov     [rsp+arg_10], rbp
0x14000980e  push    rsi
0x14000980f  push    rdi
0x140009810  push    r12
0x140009812  push    r14
0x140009814  push    r15
0x140009816  sub     rsp, 30h
0x14000981a  lea     rdi, [rdx+1C8h]
0x140009821  mov     qword ptr [rsp+58h+arg_8], 0
0x14000982a  mov     r15, rcx
0x14000982d  mov     r14d, r9d
0x140009830  mov     rcx, rdi; SpinLock
0x140009833  mov     rbx, r8
0x140009836  mov     rbp, rdx
0x140009839  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009840  nop     dword ptr [rax+rax+00h]
0x140009845  lea     r12, [rbp+1B0h]
0x14000984c  xor     r9d, r9d; Alertable
0x14000984f  mov     sil, al
0x140009852  xor     r8d, r8d; WaitMode
0x140009855  lea     rax, [rsp+58h+arg_8]
0x14000985a  xor     edx, edx; WaitReason
0x14000985c  mov     rcx, r12; Object
0x14000985f  mov     [rsp+58h+Timeout], rax; Timeout
0x140009864  call    cs:__imp_KeWaitForSingleObject
0x14000986b  nop     dword ptr [rax+rax+00h]
0x140009870  test    eax, eax
0x140009872  jnz     short loc_1400098B0
0x140009874  mov     dl, sil; NewIrql
0x140009877  mov     rcx, rdi; SpinLock
0x14000987a  call    cs:__imp_KeReleaseSpinLock
0x140009881  nop     dword ptr [rax+rax+00h]
0x140009886  mov     r9d, r14d
0x140009889  mov     r8, rbx
0x14000988c  mov     rdx, rbp
0x14000988f  mov     rcx, r15
0x140009892  call    SendSetFeatureControlRequestForFunctionSuspend
0x140009897  xor     r8d, r8d; Wait
0x14000989a  xor     edx, edx; Increment
0x14000989c  mov     rcx, r12; Event
0x14000989f  call    cs:__imp_KeSetEvent
0x1400098a6  nop     dword ptr [rax+rax+00h]
0x1400098ab  jmp     loc_140009988
0x1400098b0  mov     r12d, 20h ; ' '
0x1400098b6  mov     r8d, 43627355h
0x1400098bc  mov     edx, r12d
0x1400098bf  lea     ecx, [r12+20h]
0x1400098c4  call    cs:__imp_ExAllocatePool2
0x1400098cb  nop     dword ptr [rax+rax+00h]
0x1400098d0  test    rax, rax
0x1400098d3  jnz     short loc_140009946
0x1400098d5  mov     rcx, rbx; Irp
0x1400098d8  call    cs:__imp_PoStartNextPowerIrp
0x1400098df  nop     dword ptr [rax+rax+00h]
0x1400098e4  mov     dl, sil; NewIrql
0x1400098e7  mov     dword ptr [rbx+30h], 0
0x1400098ee  mov     rcx, rdi; SpinLock
0x1400098f1  call    cs:__imp_KeReleaseSpinLock
0x1400098f8  nop     dword ptr [rax+rax+00h]
0x1400098fd  xor     edx, edx; PriorityBoost
0x1400098ff  mov     rcx, rbx; Irp
0x140009902  call    cs:__imp_IofCompleteRequest
0x140009909  nop     dword ptr [rax+rax+00h]
0x14000990e  mov     rcx, rdi; SpinLock
0x140009911  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009918  nop     dword ptr [rax+rax+00h]
0x14000991d  mov     rdx, rbx
0x140009920  mov     rcx, r15
0x140009923  mov     sil, al
0x140009926  call    UsbcReleaseRemoveLock
0x14000992b  lea     rcx, [r15+0C8h]; RemoveLock
0x140009932  mov     r8d, r12d; RemlockSize
0x140009935  mov     rdx, rbx; Tag
0x140009938  call    cs:__imp_IoReleaseRemoveLockEx
0x14000993f  nop     dword ptr [rax+rax+00h]
0x140009944  jmp     short loc_140009976
0x140009946  lea     rcx, [rbp+1D0h]
0x14000994d  mov     [rax+8], r14d
0x140009951  mov     [rax], rbx
0x140009954  mov     rdx, [rcx+8]
0x140009958  cmp     [rdx], rcx
0x14000995b  jz      short loc_140009964
0x14000995d  mov     ecx, 3
0x140009962  int     29h; Win8: RtlFailFast(ecx)
0x140009964  add     rax, 10h
0x140009968  mov     [rax+8], rdx
0x14000996c  mov     [rax], rcx
0x14000996f  mov     [rdx], rax
0x140009972  mov     [rcx+8], rax
0x140009976  mov     dl, sil; NewIrql
0x140009979  mov     rcx, rdi; SpinLock
0x14000997c  call    cs:__imp_KeReleaseSpinLock
0x140009983  nop     dword ptr [rax+rax+00h]
0x140009988  mov     rbx, [rsp+58h+arg_0]
0x14000998d  mov     rbp, [rsp+58h+arg_10]
0x140009992  add     rsp, 30h
0x140009996  pop     r15
0x140009998  pop     r14
0x14000999a  pop     r12
0x14000999c  pop     rdi
0x14000999d  pop     rsi
0x14000999e  retn
```
