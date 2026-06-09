# WaitWakeCancelComplete

- ea: `0x140009210`
- end: `0x1400092e3`
- name: `WaitWakeCancelComplete`
- size: `211`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x140008d58`
- `0x140008eac`
- `0x140009210`
- `0x140009f10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400092ab`
- `ntoskrnl!IofCompleteRequest` at `0x1400092ab`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400092d2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400092d2`

## pseudocode

```c
void __fastcall WaitWakeCancelComplete(char *Csq, PIRP Irp)
{
  char *v2; // rdi
  void (__fastcall *v4)(_IO_CSQ *, _IRP *); // rsi
  int v5; // edx

  v2 = Csq - 32;
  v4 = (void (__fastcall *)(_IO_CSQ *, _IRP *))*((_QWORD *)Csq + 25);
  CheckParentWaitWake(v4);
  Irp->IoStatus.Status = -1073741536;
  if ( *((_BYTE *)v4 + 1362) )
  {
    CancelRemoteWakeNotificationIrp(v2, Irp);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)v2 + 49),
        v5,
        3,
        10,
        (__int64)WPP_c22e0bd291983066d7104eda50c0b1f9_Traceguids,
        *((_QWORD *)v2 + 28),
        (char)Irp);
    }
    IofCompleteRequest(Irp, 0);
    UsbcReleaseRemoveLock(v4, Irp);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)v4 + 200), Irp, 0x20u);
  }
}

```

## disassembly

```asm
0x140009210  mov     [rsp+arg_0], rbx
0x140009215  mov     [rsp+arg_8], rsi
0x14000921a  push    rdi
0x14000921b  sub     rsp, 40h
0x14000921f  lea     rdi, [rcx-20h]
0x140009223  mov     rbx, rdx
0x140009226  mov     rsi, [rdi+0E8h]
0x14000922d  mov     rcx, rsi; Context
0x140009230  call    CheckParentWaitWake
0x140009235  mov     dword ptr [rbx+30h], 0C0000120h
0x14000923c  cmp     byte ptr [rsi+552h], 0
0x140009243  jz      short loc_140009261
0x140009245  mov     rdx, rbx
0x140009248  mov     rcx, rdi
0x14000924b  call    CancelRemoteWakeNotificationIrp
0x140009250  mov     rbx, [rsp+48h+arg_0]
0x140009255  mov     rsi, [rsp+48h+arg_8]
0x14000925a  add     rsp, 40h
0x14000925e  pop     rdi
0x14000925f  retn
0x140009261  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009268  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000926f  jz      short loc_1400092A6
0x140009271  mov     rax, [rdi+0E0h]
0x140009278  mov     r9d, 0Ah
0x14000927e  mov     rcx, [rdi+188h]
0x140009285  mov     dl, 4
0x140009287  mov     [rsp+48h+var_18], rbx
0x14000928c  mov     [rsp+48h+var_20], rax
0x140009291  lea     rax, WPP_c22e0bd291983066d7104eda50c0b1f9_Traceguids
0x140009298  lea     r8d, [r9-7]
0x14000929c  mov     [rsp+48h+var_28], rax
0x1400092a1  call    WPP_RECORDER_SF_qq
0x1400092a6  xor     edx, edx; PriorityBoost
0x1400092a8  mov     rcx, rbx; Irp
0x1400092ab  call    cs:__imp_IofCompleteRequest
0x1400092b2  nop     dword ptr [rax+rax+00h]
0x1400092b7  mov     rdx, rbx
0x1400092ba  mov     rcx, rsi
0x1400092bd  call    UsbcReleaseRemoveLock
0x1400092c2  lea     rcx, [rsi+0C8h]; RemoveLock
0x1400092c9  mov     r8d, 20h ; ' '; RemlockSize
0x1400092cf  mov     rdx, rbx; Tag
0x1400092d2  call    cs:__imp_IoReleaseRemoveLockEx
0x1400092d9  nop     dword ptr [rax+rax+00h]
0x1400092de  jmp     loc_140009250
```
