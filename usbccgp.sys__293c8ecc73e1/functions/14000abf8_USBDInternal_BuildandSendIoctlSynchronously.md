# USBDInternal_BuildandSendIoctlSynchronously

- ea: `0x14000abf8`
- end: `0x14000ad48`
- name: `USBDInternal_BuildandSendIoctlSynchronously`
- size: `336`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a938`

## callees

- `0x14000abf8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000ac28`
- `ntoskrnl!KeInitializeEvent` at `0x14000ac28`
- `ntoskrnl!IoFreeIrp` at `0x14000ace6`
- `ntoskrnl!IoFreeIrp` at `0x14000ace6`
- `ntoskrnl!IoAllocateIrp` at `0x14000ac39`
- `ntoskrnl!IoAllocateIrp` at `0x14000ac39`
- `ntoskrnl!IofCallDriver` at `0x14000aca9`
- `ntoskrnl!IofCallDriver` at `0x14000aca9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000acd4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000acd4`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000ac8f`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000ac8f`
- `ntoskrnl!DbgPrintEx` at `0x14000ad18`
- `ntoskrnl!DbgPrintEx` at `0x14000ad18`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildandSendIoctlSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        _IRP *a3,
        unsigned __int64 a4)
{
  PIRP Irp; // rax
  IRP *v9; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int Status; // ebx
  _IO_STACK_LOCATION *v13; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v9 = Irp;
  if ( Irp )
  {
    Irp->AssociatedIrp.MasterIrp = a3;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a4;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4788299;
    if ( IoSetCompletionRoutineEx(DeviceObject, v9, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v13 = v9->Tail.Overlay.CurrentStackLocation;
      v13[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))USBD_SyncCompletionRoutine;
      v13[-1].Context = &Event;
      v13[-1].Control = -32;
    }
    Status = IofCallDriver(a2, v9);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v9->IoStatus.Status;
    }
    IoFreeIrp(v9);
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Failed to allocate Irp for Target Device Object 0x%p\n", a2);
    return (unsigned int)-1073741670;
  }
  return Status;
}

```

## disassembly

```asm
0x14000abf8  push    rbx
0x14000abfa  push    rbp
0x14000abfb  push    rsi
0x14000abfc  push    rdi
0x14000abfd  push    r14
0x14000abff  sub     rsp, 60h
0x14000ac03  mov     rbp, r8
0x14000ac06  mov     rbx, rdx
0x14000ac09  mov     r14, rcx
0x14000ac0c  xorps   xmm0, xmm0
0x14000ac0f  xor     eax, eax
0x14000ac11  lea     rcx, [rsp+88h+Event]; Event
0x14000ac16  xor     r8d, r8d; State
0x14000ac19  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000ac1e  xor     edx, edx; Type
0x14000ac20  mov     rsi, r9
0x14000ac23  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x14000ac28  call    cs:__imp_KeInitializeEvent
0x14000ac2f  nop     dword ptr [rax+rax+00h]
0x14000ac34  mov     cl, [rbx+4Ch]; StackSize
0x14000ac37  xor     edx, edx; ChargeQuota
0x14000ac39  call    cs:__imp_IoAllocateIrp
0x14000ac40  nop     dword ptr [rax+rax+00h]
0x14000ac45  mov     rdi, rax
0x14000ac48  test    rax, rax
0x14000ac4b  jz      loc_14000AD00
0x14000ac51  mov     [rax+18h], rbp
0x14000ac55  lea     r9, [rsp+88h+Event]; Context
0x14000ac5a  mov     rax, [rax+0B8h]
0x14000ac61  mov     rdx, rdi; Irp
0x14000ac64  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000ac69  mov     rcx, r14; DeviceObject
0x14000ac6c  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000ac71  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000ac76  mov     [rax-40h], rsi
0x14000ac7a  lea     rsi, USBD_SyncCompletionRoutine
0x14000ac81  mov     r8, rsi; CompletionRoutine
0x14000ac84  mov     byte ptr [rax-48h], 0Fh
0x14000ac88  mov     dword ptr [rax-30h], 49104Bh
0x14000ac8f  call    cs:__imp_IoSetCompletionRoutineEx
0x14000ac96  nop     dword ptr [rax+rax+00h]
0x14000ac9b  test    eax, eax
0x14000ac9d  js      loc_14000AD2B
0x14000aca3  mov     rdx, rdi; Irp
0x14000aca6  mov     rcx, rbx; DeviceObject
0x14000aca9  call    cs:__imp_IofCallDriver
0x14000acb0  nop     dword ptr [rax+rax+00h]
0x14000acb5  mov     ebx, eax
0x14000acb7  cmp     eax, 103h
0x14000acbc  jnz     short loc_14000ACE3
0x14000acbe  xor     r9d, r9d; Alertable
0x14000acc1  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000acca  xor     r8d, r8d; WaitMode
0x14000accd  lea     rcx, [rsp+88h+Event]; Object
0x14000acd2  xor     edx, edx; WaitReason
0x14000acd4  call    cs:__imp_KeWaitForSingleObject
0x14000acdb  nop     dword ptr [rax+rax+00h]
0x14000ace0  mov     ebx, [rdi+30h]
0x14000ace3  mov     rcx, rdi; Irp
0x14000ace6  call    cs:__imp_IoFreeIrp
0x14000aced  nop     dword ptr [rax+rax+00h]
0x14000acf2  mov     eax, ebx
0x14000acf4  add     rsp, 60h
0x14000acf8  pop     r14
0x14000acfa  pop     rdi
0x14000acfb  pop     rsi
0x14000acfc  pop     rbp
0x14000acfd  pop     rbx
0x14000acfe  retn
0x14000ad00  cmp     cs:g_EnableDbgPrints, 0
0x14000ad07  jz      short loc_14000AD24
0x14000ad09  xor     edx, edx; Level
0x14000ad0b  lea     r8, aFailedToAlloca_0; "Failed to allocate Irp for Target Devic"...
0x14000ad12  mov     r9, rbx
0x14000ad15  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ad18  call    cs:__imp_DbgPrintEx
0x14000ad1f  nop     dword ptr [rax+rax+00h]
0x14000ad24  mov     ebx, 0C000009Ah
0x14000ad29  jmp     short loc_14000ACF2
0x14000ad2b  mov     rax, [rdi+0B8h]
0x14000ad32  lea     rcx, [rsp+88h+Event]
0x14000ad37  mov     [rax-10h], rsi
0x14000ad3b  mov     [rax-8], rcx
0x14000ad3f  mov     byte ptr [rax-45h], 0E0h
0x14000ad43  jmp     loc_14000ACA3
```
