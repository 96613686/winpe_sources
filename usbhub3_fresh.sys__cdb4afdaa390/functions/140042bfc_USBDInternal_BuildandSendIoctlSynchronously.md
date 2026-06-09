# USBDInternal_BuildandSendIoctlSynchronously

- ea: `0x140042bfc`
- end: `0x140042d41`
- name: `USBDInternal_BuildandSendIoctlSynchronously`
- size: `325`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT, _IRP *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400434e0`

## callees

- `0x140042bfc`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140042cea`
- `ntoskrnl!IofCallDriver` at `0x140042cea`
- `ntoskrnl!KeWaitForSingleObject` at `0x140042d15`
- `ntoskrnl!KeWaitForSingleObject` at `0x140042d15`
- `ntoskrnl!KeInitializeEvent` at `0x140042c2c`
- `ntoskrnl!KeInitializeEvent` at `0x140042c2c`
- `ntoskrnl!DbgPrintEx` at `0x140042c68`
- `ntoskrnl!DbgPrintEx` at `0x140042c68`
- `ntoskrnl!IoFreeIrp` at `0x140042d27`
- `ntoskrnl!IoFreeIrp` at `0x140042d27`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140042cbc`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140042cbc`
- `ntoskrnl!IoAllocateIrp` at `0x140042c3d`
- `ntoskrnl!IoAllocateIrp` at `0x140042c3d`

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
  unsigned int Status; // ebx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v12; // rax
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
    if ( IoSetCompletionRoutineEx(
           DeviceObject,
           v9,
           (PIO_COMPLETION_ROUTINE)USBD_SyncCompletionRoutine,
           &Event,
           1u,
           1u,
           1u) < 0 )
    {
      v12 = v9->Tail.Overlay.CurrentStackLocation;
      v12[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))USBD_SyncCompletionRoutine;
      v12[-1].Context = &Event;
      v12[-1].Control = -32;
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
0x140042bfc  push    rbx
0x140042bfe  push    rbp
0x140042bff  push    rsi
0x140042c00  push    rdi
0x140042c01  push    r14
0x140042c03  sub     rsp, 60h
0x140042c07  mov     rbp, r8
0x140042c0a  mov     rbx, rdx
0x140042c0d  mov     r14, rcx
0x140042c10  xorps   xmm0, xmm0
0x140042c13  xor     eax, eax
0x140042c15  lea     rcx, [rsp+88h+Event]; Event
0x140042c1a  xor     r8d, r8d; State
0x140042c1d  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140042c22  xor     edx, edx; Type
0x140042c24  mov     rsi, r9
0x140042c27  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x140042c2c  call    cs:__imp_KeInitializeEvent
0x140042c33  nop     dword ptr [rax+rax+00h]
0x140042c38  mov     cl, [rbx+4Ch]; StackSize
0x140042c3b  xor     edx, edx; ChargeQuota
0x140042c3d  call    cs:__imp_IoAllocateIrp
0x140042c44  nop     dword ptr [rax+rax+00h]
0x140042c49  mov     rdi, rax
0x140042c4c  test    rax, rax
0x140042c4f  jnz     short loc_140042C7E
0x140042c51  cmp     cs:g_EnableDbgPrints, al
0x140042c57  jz      short loc_140042C74
0x140042c59  mov     r9, rbx
0x140042c5c  lea     r8, aFailedToAlloca_0; "Failed to allocate Irp for Target Devic"...
0x140042c63  xor     edx, edx; Level
0x140042c65  lea     ecx, [rax+4Dh]; ComponentId
0x140042c68  call    cs:__imp_DbgPrintEx
0x140042c6f  nop     dword ptr [rax+rax+00h]
0x140042c74  mov     ebx, 0C000009Ah
0x140042c79  jmp     loc_140042D33
0x140042c7e  mov     [rax+18h], rbp
0x140042c82  lea     r9, [rsp+88h+Event]; Context
0x140042c87  mov     rax, [rax+0B8h]
0x140042c8e  mov     rdx, rdi; Irp
0x140042c91  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x140042c96  mov     rcx, r14; DeviceObject
0x140042c99  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x140042c9e  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140042ca3  mov     [rax-40h], rsi
0x140042ca7  lea     rsi, USBD_SyncCompletionRoutine
0x140042cae  mov     r8, rsi; CompletionRoutine
0x140042cb1  mov     byte ptr [rax-48h], 0Fh
0x140042cb5  mov     dword ptr [rax-30h], 49104Bh
0x140042cbc  call    cs:__imp_IoSetCompletionRoutineEx
0x140042cc3  nop     dword ptr [rax+rax+00h]
0x140042cc8  test    eax, eax
0x140042cca  jns     short loc_140042CE4
0x140042ccc  mov     rax, [rdi+0B8h]
0x140042cd3  lea     rcx, [rsp+88h+Event]
0x140042cd8  mov     [rax-10h], rsi
0x140042cdc  mov     [rax-8], rcx
0x140042ce0  mov     byte ptr [rax-45h], 0E0h
0x140042ce4  mov     rdx, rdi; Irp
0x140042ce7  mov     rcx, rbx; DeviceObject
0x140042cea  call    cs:__imp_IofCallDriver
0x140042cf1  nop     dword ptr [rax+rax+00h]
0x140042cf6  mov     ebx, eax
0x140042cf8  cmp     eax, 103h
0x140042cfd  jnz     short loc_140042D24
0x140042cff  xor     r9d, r9d; Alertable
0x140042d02  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x140042d0b  xor     r8d, r8d; WaitMode
0x140042d0e  lea     rcx, [rsp+88h+Event]; Object
0x140042d13  xor     edx, edx; WaitReason
0x140042d15  call    cs:__imp_KeWaitForSingleObject
0x140042d1c  nop     dword ptr [rax+rax+00h]
0x140042d21  mov     ebx, [rdi+30h]
0x140042d24  mov     rcx, rdi; Irp
0x140042d27  call    cs:__imp_IoFreeIrp
0x140042d2e  nop     dword ptr [rax+rax+00h]
0x140042d33  mov     eax, ebx
0x140042d35  add     rsp, 60h
0x140042d39  pop     r14
0x140042d3b  pop     rdi
0x140042d3c  pop     rsi
0x140042d3d  pop     rbp
0x140042d3e  pop     rbx
0x140042d3f  retn
```
