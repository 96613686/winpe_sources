# PdoInvokeIdleCallbackWorker

- ea: `0x14002cfb0`
- end: `0x14002d076`
- name: `PdoInvokeIdleCallbackWorker`
- size: `198`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x140008eac`
- `0x140014d50`
- `0x14002cfb0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002d060`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002d060`
- `ntoskrnl!IoCsqInsertIrp` at `0x14002d031`
- `ntoskrnl!IoCsqInsertIrp` at `0x14002d031`

## pseudocode

```c
void __fastcall PdoInvokeIdleCallbackWorker(PDEVICE_OBJECT DeviceObject, IRP *Context)
{
  _LIST_ENTRY *Flink; // rbp
  IRP *v3; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _LIST_ENTRY *Blink; // rsi
  _NAMED_PIPE_CREATE_PARAMETERS *Parameters; // rdi

  Flink = Context->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v3 = Context;
  CurrentStackLocation = Context->Tail.Overlay.CurrentStackLocation;
  Context->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  Blink = Flink[14].Blink;
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(Context) = 4;
    WPP_RECORDER_SF_qq(
      Blink[85].Blink,
      (_DWORD)Context,
      7,
      68,
      (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
      (char)Parameters,
      *(_QWORD *)&Parameters->NamedPipeType);
  }
  (*(void (__fastcall **)(_QWORD))&Parameters->NamedPipeType)(*(_QWORD *)&Parameters->CompletionMode);
  IoCsqInsertIrp((PIO_CSQ)&Flink[7].Blink, v3, 0);
  UsbcReleaseRemoveLock(Blink, PdoInvokeIdleCallbackWorker);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)&Blink[12].Blink, PdoInvokeIdleCallbackWorker, 0x20u);
}

```

## disassembly

```asm
0x14002cfb0  push    rbx
0x14002cfb2  push    rbp
0x14002cfb3  push    rsi
0x14002cfb4  push    rdi
0x14002cfb5  sub     rsp, 48h
0x14002cfb9  mov     rbp, [rdx+78h]
0x14002cfbd  mov     rbx, rdx
0x14002cfc0  mov     rax, [rdx+0B8h]
0x14002cfc7  mov     qword ptr [rdx+78h], 0
0x14002cfcf  mov     rsi, [rbp+0E8h]
0x14002cfd6  mov     rdi, [rax+20h]
0x14002cfda  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cfe1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002cfe8  jz      short loc_14002D01B
0x14002cfea  mov     rax, [rdi]
0x14002cfed  mov     r9d, 44h ; 'D'
0x14002cff3  mov     rcx, [rsi+558h]
0x14002cffa  mov     dl, 4
0x14002cffc  mov     [rsp+68h+var_38], rax
0x14002d001  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x14002d008  mov     [rsp+68h+var_40], rdi
0x14002d00d  lea     r8d, [r9-3Dh]
0x14002d011  mov     [rsp+68h+var_48], rax
0x14002d016  call    WPP_RECORDER_SF_qq
0x14002d01b  mov     rax, [rdi]
0x14002d01e  mov     rcx, [rdi+8]
0x14002d022  call    _guard_dispatch_icall
0x14002d027  lea     rcx, [rbp+78h]; Csq
0x14002d02b  xor     r8d, r8d; Context
0x14002d02e  mov     rdx, rbx; Irp
0x14002d031  call    cs:__imp_IoCsqInsertIrp
0x14002d038  nop     dword ptr [rax+rax+00h]
0x14002d03d  lea     rdx, PdoInvokeIdleCallbackWorker
0x14002d044  mov     rcx, rsi
0x14002d047  call    UsbcReleaseRemoveLock
0x14002d04c  lea     rcx, [rsi+0C8h]; RemoveLock
0x14002d053  mov     r8d, 20h ; ' '; RemlockSize
0x14002d059  lea     rdx, PdoInvokeIdleCallbackWorker; Tag
0x14002d060  call    cs:__imp_IoReleaseRemoveLockEx
0x14002d067  nop     dword ptr [rax+rax+00h]
0x14002d06c  add     rsp, 48h
0x14002d070  pop     rdi
0x14002d071  pop     rsi
0x14002d072  pop     rbp
0x14002d073  pop     rbx
0x14002d074  retn
```
