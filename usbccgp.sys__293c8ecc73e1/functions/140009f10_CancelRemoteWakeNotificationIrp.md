# CancelRemoteWakeNotificationIrp

- ea: `0x140009f10`
- end: `0x14000a060`
- name: `CancelRemoteWakeNotificationIrp`
- size: `336`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004b08`
- `0x140005fc4`
- `0x140009210`
- `0x14000d81c`

## callees

- `0x1400054a0`
- `0x140008eac`
- `0x140009f10`
- `0x14000c4d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000a011`
- `ntoskrnl!IofCompleteRequest` at `0x14000a011`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a043`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000a043`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009f2f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009f2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009f4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009fb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009f4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009fb4`
- `ntoskrnl!IoCancelIrp` at `0x140009fa3`
- `ntoskrnl!IoCancelIrp` at `0x140009fa3`

## pseudocode

```c
void __fastcall CancelRemoteWakeNotificationIrp(_QWORD *a1, IRP *a2)
{
  __int64 v2; // rbx
  KIRQL v5; // al
  int v6; // edx
  int v7; // edx

  v2 = a1[48];
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v2);
  if ( *(_BYTE *)(v2 + 56) )
  {
    *(_QWORD *)(v2 + 48) = a2;
    KeReleaseSpinLock((PKSPIN_LOCK)v2, v5);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_qq(
        a1[49],
        v6,
        3,
        73,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        a1[28],
        *(_QWORD *)(v2 + 40));
    }
    IoCancelIrp(*(PIRP *)(v2 + 40));
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)v2, v5);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_qqd(
        a1[49],
        v7,
        3,
        74,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        (char)a2,
        a1[28],
        a2->IoStatus.Status);
    }
    IofCompleteRequest(a2, 0);
    UsbcReleaseRemoveLock(a1[29], a2);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1[29] + 200LL), a2, 0x20u);
  }
}

```

## disassembly

```asm
0x140009f10  mov     [rsp+arg_0], rbx
0x140009f15  mov     [rsp+arg_8], rsi
0x140009f1a  push    rdi
0x140009f1b  sub     rsp, 40h
0x140009f1f  mov     rbx, [rcx+180h]
0x140009f26  mov     rdi, rcx
0x140009f29  mov     rcx, rbx; SpinLock
0x140009f2c  mov     rsi, rdx
0x140009f2f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009f36  nop     dword ptr [rax+rax+00h]
0x140009f3b  cmp     byte ptr [rbx+38h], 0
0x140009f3f  mov     rcx, rbx; SpinLock
0x140009f42  mov     dl, al; NewIrql
0x140009f44  jz      short loc_140009FB4
0x140009f46  mov     [rbx+30h], rsi
0x140009f4a  call    cs:__imp_KeReleaseSpinLock
0x140009f51  nop     dword ptr [rax+rax+00h]
0x140009f56  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009f5d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009f64  jz      short loc_140009F9F
0x140009f66  mov     rax, [rbx+28h]
0x140009f6a  mov     r9d, 49h ; 'I'
0x140009f70  mov     rcx, [rdi+188h]
0x140009f77  mov     dl, 4
0x140009f79  mov     [rsp+48h+var_18], rax
0x140009f7e  mov     rax, [rdi+0E0h]
0x140009f85  mov     [rsp+48h+var_20], rax
0x140009f8a  lea     r8d, [r9-46h]
0x140009f8e  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140009f95  mov     [rsp+48h+var_28], rax
0x140009f9a  call    WPP_RECORDER_SF_qq
0x140009f9f  mov     rcx, [rbx+28h]; Irp
0x140009fa3  call    cs:__imp_IoCancelIrp
0x140009faa  nop     dword ptr [rax+rax+00h]
0x140009faf  jmp     loc_14000A04F
0x140009fb4  call    cs:__imp_KeReleaseSpinLock
0x140009fbb  nop     dword ptr [rax+rax+00h]
0x140009fc0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009fc7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009fce  jz      short loc_14000A00C
0x140009fd0  mov     eax, [rsi+30h]
0x140009fd3  mov     r9d, 4Ah ; 'J'
0x140009fd9  mov     rcx, [rdi+188h]
0x140009fe0  mov     dl, 4
0x140009fe2  mov     [rsp+48h+var_10], eax
0x140009fe6  mov     rax, [rdi+0E0h]
0x140009fed  mov     [rsp+48h+var_18], rax
0x140009ff2  lea     r8d, [r9-47h]
0x140009ff6  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140009ffd  mov     [rsp+48h+var_20], rsi
0x14000a002  mov     [rsp+48h+var_28], rax
0x14000a007  call    WPP_RECORDER_SF_qqd
0x14000a00c  xor     edx, edx; PriorityBoost
0x14000a00e  mov     rcx, rsi; Irp
0x14000a011  call    cs:__imp_IofCompleteRequest
0x14000a018  nop     dword ptr [rax+rax+00h]
0x14000a01d  mov     rcx, [rdi+0E8h]
0x14000a024  mov     rdx, rsi
0x14000a027  call    UsbcReleaseRemoveLock
0x14000a02c  mov     rcx, [rdi+0E8h]
0x14000a033  mov     r8d, 20h ; ' '; RemlockSize
0x14000a039  add     rcx, 0C8h; RemoveLock
0x14000a040  mov     rdx, rsi; Tag
0x14000a043  call    cs:__imp_IoReleaseRemoveLockEx
0x14000a04a  nop     dword ptr [rax+rax+00h]
0x14000a04f  mov     rbx, [rsp+48h+arg_0]
0x14000a054  mov     rsi, [rsp+48h+arg_8]
0x14000a059  add     rsp, 40h
0x14000a05d  pop     rdi
0x14000a05e  retn
```
