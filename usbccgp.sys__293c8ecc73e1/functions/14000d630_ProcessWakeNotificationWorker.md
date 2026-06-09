# ProcessWakeNotificationWorker

- ea: `0x14000d630`
- end: `0x14000d813`
- name: `ProcessWakeNotificationWorker`
- size: `483`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x140006430`
- `0x140006f58`
- `0x1400083c8`
- `0x140008eac`
- `0x14000d630`
- `0x14000d81c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d71b`
- `ntoskrnl!IofCompleteRequest` at `0x14000d71b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d745`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d7f7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d745`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d7f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d6a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d6a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d70a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d75c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d70a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d75c`

## pseudocode

```c
void __fastcall ProcessWakeNotificationWorker(PDEVICE_OBJECT DeviceObject, char *Context)
{
  __int64 v2; // rsi
  char *v3; // rbx
  __int64 v4; // rdi
  KIRQL v5; // al
  int v6; // edx
  IRP *v7; // rbp
  KIRQL v8; // r14
  struct _IO_REMOVE_LOCK *v9; // rbx
  int v10; // edx
  __int64 v11; // [rsp+28h] [rbp-50h]

  v2 = *((_QWORD *)Context + 29);
  v3 = Context;
  v4 = *((_QWORD *)Context + 48);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v11 = *((_QWORD *)Context + 28);
    LOBYTE(Context) = 5;
    WPP_RECORDER_SF_q(
      *((_QWORD *)v3 + 49),
      (_DWORD)Context,
      3,
      75,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      v11);
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v4);
  v7 = *(IRP **)(v4 + 48);
  v8 = v5;
  *(_BYTE *)(v4 + 56) = 0;
  if ( v7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)v3 + 49),
        v6,
        3,
        76,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *((_QWORD *)v3 + 28),
        (char)v7);
    }
    *(_QWORD *)(v4 + 48) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)v4, v8);
    IofCompleteRequest(v7, 0);
    UsbcReleaseRemoveLock(v2, v7);
    v9 = (struct _IO_REMOVE_LOCK *)(v2 + 200);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 200), v7, 0x20u);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)v4, v5);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_q(
        *((_QWORD *)v3 + 49),
        v10,
        3,
        77,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *((_QWORD *)v3 + 28));
    }
    CompletePdoWaitWakeIrp(v3, *(_DWORD *)(*(_QWORD *)(v4 + 40) + 48LL));
    CompleteFunctionIdleIrp(v3, 0);
    SetPdoIdle(v2, (__int64)v3, 2, 0, 1);
    v9 = (struct _IO_REMOVE_LOCK *)(v2 + 200);
  }
  UsbcReleaseRemoveLock(v2, SendRemoteWakeNotificationIrp);
  IoReleaseRemoveLockEx(v9, SendRemoteWakeNotificationIrp, 0x20u);
}

```

## disassembly

```asm
0x14000d630  push    rbx
0x14000d632  push    rbp
0x14000d633  push    rsi
0x14000d634  push    rdi
0x14000d635  push    r12
0x14000d637  push    r14
0x14000d639  push    r15
0x14000d63b  sub     rsp, 40h
0x14000d63f  mov     rsi, [rdx+0E8h]
0x14000d646  mov     rbx, rdx
0x14000d649  mov     rdi, [rdx+180h]
0x14000d650  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d657  xor     r15d, r15d
0x14000d65a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000d661  lea     rcx, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000d668  jz      short loc_14000D69F
0x14000d66a  mov     rax, cs:WPP_GLOBAL_Control
0x14000d671  cmp     [rax+48h], r15w
0x14000d676  jz      short loc_14000D69F
0x14000d678  mov     rax, [rdx+0E0h]
0x14000d67f  lea     r9d, [r15+4Bh]
0x14000d683  mov     [rsp+78h+var_50], rax
0x14000d688  lea     r8d, [r15+3]
0x14000d68c  mov     [rsp+78h+var_58], rcx
0x14000d691  mov     dl, 5
0x14000d693  mov     rcx, [rbx+188h]
0x14000d69a  call    WPP_RECORDER_SF_q
0x14000d69f  mov     rcx, rdi; SpinLock
0x14000d6a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d6a9  nop     dword ptr [rax+rax+00h]
0x14000d6ae  mov     rbp, [rdi+30h]
0x14000d6b2  mov     r14b, al
0x14000d6b5  mov     [rdi+38h], r15b
0x14000d6b9  test    rbp, rbp
0x14000d6bc  jz      loc_14000D756
0x14000d6c2  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000d6c9  jz      short loc_14000D700
0x14000d6cb  mov     rax, [rbx+0E0h]
0x14000d6d2  mov     r9d, 4Ch ; 'L'
0x14000d6d8  mov     rcx, [rbx+188h]
0x14000d6df  mov     dl, 4
0x14000d6e1  mov     [rsp+78h+var_48], rbp
0x14000d6e6  mov     [rsp+78h+var_50], rax
0x14000d6eb  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000d6f2  lea     r8d, [r9-49h]
0x14000d6f6  mov     [rsp+78h+var_58], rax
0x14000d6fb  call    WPP_RECORDER_SF_qq
0x14000d700  mov     dl, r14b; NewIrql
0x14000d703  mov     [rdi+30h], r15
0x14000d707  mov     rcx, rdi; SpinLock
0x14000d70a  call    cs:__imp_KeReleaseSpinLock
0x14000d711  nop     dword ptr [rax+rax+00h]
0x14000d716  xor     edx, edx; PriorityBoost
0x14000d718  mov     rcx, rbp; Irp
0x14000d71b  call    cs:__imp_IofCompleteRequest
0x14000d722  nop     dword ptr [rax+rax+00h]
0x14000d727  mov     rdx, rbp
0x14000d72a  mov     rcx, rsi
0x14000d72d  call    UsbcReleaseRemoveLock
0x14000d732  lea     rbx, [rsi+0C8h]
0x14000d739  mov     r8d, 20h ; ' '; RemlockSize
0x14000d73f  mov     rcx, rbx; RemoveLock
0x14000d742  mov     rdx, rbp; Tag
0x14000d745  call    cs:__imp_IoReleaseRemoveLockEx
0x14000d74c  nop     dword ptr [rax+rax+00h]
0x14000d751  jmp     loc_14000D7D8
0x14000d756  mov     dl, r14b; NewIrql
0x14000d759  mov     rcx, rdi; SpinLock
0x14000d75c  call    cs:__imp_KeReleaseSpinLock
0x14000d763  nop     dword ptr [rax+rax+00h]
0x14000d768  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000d76f  jz      short loc_14000D7A1
0x14000d771  mov     rax, [rbx+0E0h]
0x14000d778  mov     r9d, 4Dh ; 'M'
0x14000d77e  mov     rcx, [rbx+188h]
0x14000d785  mov     dl, 4
0x14000d787  mov     [rsp+78h+var_50], rax
0x14000d78c  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000d793  mov     [rsp+78h+var_58], rax
0x14000d798  lea     r8d, [r9-4Ah]
0x14000d79c  call    WPP_RECORDER_SF_q
0x14000d7a1  mov     rdx, [rdi+28h]
0x14000d7a5  mov     rcx, rbx; PeekContext
0x14000d7a8  mov     edx, [rdx+30h]
0x14000d7ab  call    CompletePdoWaitWakeIrp
0x14000d7b0  xor     edx, edx
0x14000d7b2  mov     rcx, rbx; PeekContext
0x14000d7b5  call    CompleteFunctionIdleIrp
0x14000d7ba  xor     r9d, r9d
0x14000d7bd  mov     byte ptr [rsp+78h+var_58], 1
0x14000d7c2  mov     rdx, rbx
0x14000d7c5  mov     rcx, rsi
0x14000d7c8  lea     r8d, [r9+2]
0x14000d7cc  call    SetPdoIdle
0x14000d7d1  lea     rbx, [rsi+0C8h]
0x14000d7d8  lea     rdx, SendRemoteWakeNotificationIrp
0x14000d7df  mov     rcx, rsi
0x14000d7e2  call    UsbcReleaseRemoveLock
0x14000d7e7  mov     r8d, 20h ; ' '; RemlockSize
0x14000d7ed  lea     rdx, SendRemoteWakeNotificationIrp; Tag
0x14000d7f4  mov     rcx, rbx; RemoveLock
0x14000d7f7  call    cs:__imp_IoReleaseRemoveLockEx
0x14000d7fe  nop     dword ptr [rax+rax+00h]
0x14000d803  add     rsp, 40h
0x14000d807  pop     r15
0x14000d809  pop     r14
0x14000d80b  pop     r12
0x14000d80d  pop     rdi
0x14000d80e  pop     rsi
0x14000d80f  pop     rbp
0x14000d810  pop     rbx
0x14000d811  retn
```
