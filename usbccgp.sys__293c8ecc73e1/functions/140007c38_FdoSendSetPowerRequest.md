# FdoSendSetPowerRequest

- ea: `0x140007c38`
- end: `0x140007e61`
- name: `FdoSendSetPowerRequest`
- size: `553`
- prototype: `__int64 __fastcall(POWER_STATE PowerState, PREQUEST_POWER_COMPLETE CompletionFunction)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140006630`
- `0x140007170`
- `0x1400084c0`
- `0x140008980`
- `0x1400145e0`

## callees

- `0x14000476c`
- `0x1400054a0`
- `0x140005854`
- `0x140005bb0`
- `0x140007c38`
- `0x1400083c8`
- `0x14000b4bc`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007e50`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007e50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007cc4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007cc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d51`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d13`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007d51`
- `ntoskrnl!KeResetEvent` at `0x140007cfa`
- `ntoskrnl!KeResetEvent` at `0x140007cfa`
- `ntoskrnl!PoRequestPowerIrp` at `0x140007c8d`
- `ntoskrnl!PoRequestPowerIrp` at `0x140007c8d`

## pseudocode

```c
__int64 __fastcall FdoSendSetPowerRequest(
        POWER_STATE PowerState,
        PREQUEST_POWER_COMPLETE CompletionFunction,
        void *a3,
        __int64 a4)
{
  char v4; // r13
  NTSTATUS v8; // eax
  int v9; // edx
  unsigned int v10; // ebp
  KSPIN_LOCK *v12; // rbp
  KIRQL v13; // al
  int v14; // edx
  KIRQL v15; // r15
  int v16; // edx

  v4 = 0;
  if ( PowerState.SystemState != PowerSystemWorking )
  {
LABEL_2:
    v8 = PoRequestPowerIrp(*(PDEVICE_OBJECT *)(a4 + 32), 2u, PowerState, CompletionFunction, a3, 0);
    v10 = v8;
    if ( v8 != 259 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_qD(
          *(_QWORD *)(a4 + 1368),
          v9,
          8,
          72,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *(_QWORD *)(a4 + 32),
          v8);
      }
      if ( PowerState.SystemState == PowerSystemWorking
        && (int)AllocateWorkerIfNeeded(a4, UnblockWorkBlockedOnPendingParentD0) < 0 )
      {
        UnblockWorkBlockedOnPendingParentD0((PVOID)a4);
      }
      if ( v4 )
      {
        UsbcReleaseRemoveLock(a4, gSetD0Tag);
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a4 + 200), gSetD0Tag, 0x20u);
      }
    }
    return v10;
  }
  v12 = (KSPIN_LOCK *)(a4 + 344);
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a4 + 344));
  v15 = v13;
  if ( !*(_DWORD *)(a4 + 336) )
  {
    *(_DWORD *)(a4 + 336) = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 4;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a4 + 1368),
        v14,
        3,
        71,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a4 + 32));
    }
    KeResetEvent((PRKEVENT)(a4 + 312));
    *(_BYTE *)(a4 + 352) = 1;
    KeReleaseSpinLock(v12, v15);
    if ( !CompletionFunction )
    {
      UsbcAcquireRemoveLock(a4, 1601662800, gSetD0Tag);
      CompletionFunction = (PREQUEST_POWER_COMPLETE)CallbackFdoDeviceSetD0;
      v4 = 1;
    }
    goto LABEL_2;
  }
  KeReleaseSpinLock(v12, v13);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_q(
      *(_QWORD *)(a4 + 1368),
      v16,
      3,
      70,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *(_QWORD *)(a4 + 32));
  }
  return 2147483665LL;
}

```

## disassembly

```asm
0x140007c38  mov     [rsp+arg_10], r8
0x140007c3d  push    rbx
0x140007c3e  push    rbp
0x140007c3f  push    rsi
0x140007c40  push    rdi
0x140007c41  push    r12
0x140007c43  push    r13
0x140007c45  push    r14
0x140007c47  push    r15
0x140007c49  sub     rsp, 48h
0x140007c4d  xor     r13b, r13b
0x140007c50  lea     rsi, WPP_RECORDER_INITIALIZED
0x140007c57  lea     r14, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140007c5e  mov     rdi, r9
0x140007c61  mov     r12, rdx
0x140007c64  mov     ebx, ecx
0x140007c66  cmp     ecx, 1
0x140007c69  jz      short loc_140007CBA
0x140007c6b  mov     rax, [rsp+88h+arg_10]
0x140007c73  mov     r9, r12; CompletionFunction
0x140007c76  mov     rcx, [rdi+20h]; DeviceObject
0x140007c7a  mov     r8d, ebx; PowerState
0x140007c7d  mov     [rsp+88h+Irp], 0; Irp
0x140007c86  mov     dl, 2; MinorFunction
0x140007c88  mov     [rsp+88h+Context], rax; Context
0x140007c8d  call    cs:__imp_PoRequestPowerIrp
0x140007c94  nop     dword ptr [rax+rax+00h]
0x140007c99  mov     ebp, eax
0x140007c9b  cmp     eax, 103h
0x140007ca0  jnz     loc_140007DCF
0x140007ca6  mov     eax, ebp
0x140007ca8  add     rsp, 48h
0x140007cac  pop     r15
0x140007cae  pop     r14
0x140007cb0  pop     r13
0x140007cb2  pop     r12
0x140007cb4  pop     rdi
0x140007cb5  pop     rsi
0x140007cb6  pop     rbp
0x140007cb7  pop     rbx
0x140007cb8  retn
0x140007cba  lea     rbp, [r9+158h]
0x140007cc1  mov     rcx, rbp; SpinLock
0x140007cc4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007ccb  nop     dword ptr [rax+rax+00h]
0x140007cd0  cmp     dword ptr [rdi+150h], 0
0x140007cd7  mov     r15b, al
0x140007cda  jnz     short loc_140007D4B
0x140007cdc  mov     dword ptr [rdi+150h], 1
0x140007ce6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140007ced  jnz     loc_140007DA4
0x140007cf3  lea     rcx, [rdi+138h]; Event
0x140007cfa  call    cs:__imp_KeResetEvent
0x140007d01  nop     dword ptr [rax+rax+00h]
0x140007d06  mov     dl, r15b; NewIrql
0x140007d09  mov     byte ptr [rdi+160h], 1
0x140007d10  mov     rcx, rbp; SpinLock
0x140007d13  call    cs:__imp_KeReleaseSpinLock
0x140007d1a  nop     dword ptr [rax+rax+00h]
0x140007d1f  test    r12, r12
0x140007d22  jnz     loc_140007C6B
0x140007d28  lea     r8, gSetD0Tag; "T0DS"
0x140007d2f  mov     edx, 5F776F50h
0x140007d34  mov     rcx, rdi
0x140007d37  call    UsbcAcquireRemoveLock
0x140007d3c  lea     r12, CallbackFdoDeviceSetD0
0x140007d43  mov     r13b, 1
0x140007d46  jmp     loc_140007C6B
0x140007d4b  mov     dl, r15b; NewIrql
0x140007d4e  mov     rcx, rbp; SpinLock
0x140007d51  call    cs:__imp_KeReleaseSpinLock
0x140007d58  nop     dword ptr [rax+rax+00h]
0x140007d5d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140007d64  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140007d6b  jz      short loc_140007D9A
0x140007d6d  mov     rax, [rdi+20h]
0x140007d71  lea     r14, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140007d78  mov     rcx, [rdi+558h]
0x140007d7f  mov     r9d, 46h ; 'F'
0x140007d85  mov     [rsp+88h+Irp], rax
0x140007d8a  mov     dl, 4
0x140007d8c  mov     [rsp+88h+Context], r14
0x140007d91  lea     r8d, [r9-43h]
0x140007d95  call    WPP_RECORDER_SF_q
0x140007d9a  mov     eax, 80000011h
0x140007d9f  jmp     loc_140007CA8
0x140007da4  mov     rax, [rdi+20h]
0x140007da8  mov     r9d, 47h ; 'G'
0x140007dae  mov     rcx, [rdi+558h]
0x140007db5  mov     dl, 4
0x140007db7  mov     [rsp+88h+Irp], rax
0x140007dbc  mov     [rsp+88h+Context], r14
0x140007dc1  lea     r8d, [r9-44h]
0x140007dc5  call    WPP_RECORDER_SF_q
0x140007dca  jmp     loc_140007CF3
0x140007dcf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140007dd6  jz      short loc_140007E02
0x140007dd8  mov     rcx, [rdi+20h]
0x140007ddc  mov     r9d, 48h ; 'H'
0x140007de2  mov     [rsp+88h+var_58], ebp
0x140007de6  mov     dl, 2
0x140007de8  mov     [rsp+88h+Irp], rcx
0x140007ded  mov     rcx, [rdi+558h]
0x140007df4  lea     r8d, [r9-40h]
0x140007df8  mov     [rsp+88h+Context], r14
0x140007dfd  call    WPP_RECORDER_SF_qD
0x140007e02  cmp     ebx, 1
0x140007e05  jnz     short loc_140007E24
0x140007e07  lea     rdx, UnblockWorkBlockedOnPendingParentD0
0x140007e0e  mov     rcx, rdi
0x140007e11  call    AllocateWorkerIfNeeded
0x140007e16  test    eax, eax
0x140007e18  jns     short loc_140007E24
0x140007e1a  xor     edx, edx
0x140007e1c  mov     rcx, rdi
0x140007e1f  call    UnblockWorkBlockedOnPendingParentD0
0x140007e24  test    r13b, r13b
0x140007e27  jz      loc_140007CA6
0x140007e2d  lea     rdx, gSetD0Tag; "T0DS"
0x140007e34  mov     rcx, rdi
0x140007e37  call    UsbcReleaseRemoveLock
0x140007e3c  lea     rcx, [rdi+0C8h]; RemoveLock
0x140007e43  mov     r8d, 20h ; ' '; RemlockSize
0x140007e49  lea     rdx, gSetD0Tag; "T0DS"
0x140007e50  call    cs:__imp_IoReleaseRemoveLockEx
0x140007e57  nop     dword ptr [rax+rax+00h]
0x140007e5c  jmp     loc_140007CA6
```
