# USBDInternal_BuildandSendIoctlSynchronously

- ea: `0x140013dc8`
- end: `0x140013f0a`
- name: `USBDInternal_BuildandSendIoctlSynchronously`
- size: `322`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14003be34`

## callees

- `0x140013dc8`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140013e87`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140013e87`
- `ntoskrnl!KeInitializeEvent` at `0x140013df3`
- `ntoskrnl!KeInitializeEvent` at `0x140013df3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013ee0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013ee0`
- `ntoskrnl!IofCallDriver` at `0x140013eb5`
- `ntoskrnl!IofCallDriver` at `0x140013eb5`
- `ntoskrnl!IoAllocateIrp` at `0x140013e04`
- `ntoskrnl!IoAllocateIrp` at `0x140013e04`
- `ntoskrnl!IoFreeIrp` at `0x140013ef2`
- `ntoskrnl!IoFreeIrp` at `0x140013ef2`
- `ntoskrnl!DbgPrintEx` at `0x140013e2f`
- `ntoskrnl!DbgPrintEx` at `0x140013e2f`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildandSendIoctlSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        __int64 a3,
        ULONG_PTR a4)
{
  PIRP Irp; // rax
  IRP *v8; // rbx
  unsigned int Status; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v11; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v8 = Irp;
  if ( Irp )
  {
    Irp->AssociatedIrp.MasterIrp = 0;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a4;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4788299;
    if ( IoSetCompletionRoutineEx(DeviceObject, v8, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v11 = v8->Tail.Overlay.CurrentStackLocation;
      v11[-1].CompletionRoutine = USBD_SyncCompletionRoutine;
      v11[-1].Context = &Event;
      v11[-1].Control = -32;
    }
    Status = IofCallDriver(a2, v8);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v8->IoStatus.Status;
    }
    IoFreeIrp(v8);
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
0x140013dc8  push    rbx
0x140013dca  push    rbp
0x140013dcb  push    rsi
0x140013dcc  push    rdi
0x140013dcd  sub     rsp, 68h
0x140013dd1  mov     rdi, rdx
0x140013dd4  mov     rbp, rcx
0x140013dd7  xorps   xmm0, xmm0
0x140013dda  lea     rcx, [rsp+88h+Event]; Event
0x140013ddf  xor     eax, eax
0x140013de1  xor     edx, edx; Type
0x140013de3  xor     r8d, r8d; State
0x140013de6  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140013deb  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x140013df0  mov     rsi, r9
0x140013df3  call    cs:__imp_KeInitializeEvent
0x140013dfa  nop     dword ptr [rax+rax+00h]
0x140013dff  mov     cl, [rdi+4Ch]; StackSize
0x140013e02  xor     edx, edx; ChargeQuota
0x140013e04  call    cs:__imp_IoAllocateIrp
0x140013e0b  nop     dword ptr [rax+rax+00h]
0x140013e10  mov     rbx, rax
0x140013e13  test    rax, rax
0x140013e16  jnz     short loc_140013E45
0x140013e18  cmp     cs:g_EnableDbgPrints, al
0x140013e1e  jz      short loc_140013E3B
0x140013e20  mov     r9, rdi
0x140013e23  lea     r8, aFailedToAlloca_0; "Failed to allocate Irp for Target Devic"...
0x140013e2a  xor     edx, edx; Level
0x140013e2c  lea     ecx, [rax+4Dh]; ComponentId
0x140013e2f  call    cs:__imp_DbgPrintEx
0x140013e36  nop     dword ptr [rax+rax+00h]
0x140013e3b  mov     edi, 0C000009Ah
0x140013e40  jmp     loc_140013EFE
0x140013e45  mov     qword ptr [rax+18h], 0
0x140013e4d  lea     r9, [rsp+88h+Event]; Context
0x140013e52  mov     rax, [rax+0B8h]
0x140013e59  mov     rdx, rbx; Irp
0x140013e5c  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x140013e61  mov     rcx, rbp; DeviceObject
0x140013e64  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x140013e69  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140013e6e  mov     [rax-40h], rsi
0x140013e72  lea     rsi, USBD_SyncCompletionRoutine
0x140013e79  mov     r8, rsi; CompletionRoutine
0x140013e7c  mov     byte ptr [rax-48h], 0Fh
0x140013e80  mov     dword ptr [rax-30h], 49104Bh
0x140013e87  call    cs:__imp_IoSetCompletionRoutineEx
0x140013e8e  nop     dword ptr [rax+rax+00h]
0x140013e93  test    eax, eax
0x140013e95  jns     short loc_140013EAF
0x140013e97  mov     rax, [rbx+0B8h]
0x140013e9e  lea     rcx, [rsp+88h+Event]
0x140013ea3  mov     [rax-10h], rsi
0x140013ea7  mov     [rax-8], rcx
0x140013eab  mov     byte ptr [rax-45h], 0E0h
0x140013eaf  mov     rdx, rbx; Irp
0x140013eb2  mov     rcx, rdi; DeviceObject
0x140013eb5  call    cs:__imp_IofCallDriver
0x140013ebc  nop     dword ptr [rax+rax+00h]
0x140013ec1  mov     edi, eax
0x140013ec3  cmp     eax, 103h
0x140013ec8  jnz     short loc_140013EEF
0x140013eca  xor     r9d, r9d; Alertable
0x140013ecd  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x140013ed6  xor     r8d, r8d; WaitMode
0x140013ed9  lea     rcx, [rsp+88h+Event]; Object
0x140013ede  xor     edx, edx; WaitReason
0x140013ee0  call    cs:__imp_KeWaitForSingleObject
0x140013ee7  nop     dword ptr [rax+rax+00h]
0x140013eec  mov     edi, [rbx+30h]
0x140013eef  mov     rcx, rbx; Irp
0x140013ef2  call    cs:__imp_IoFreeIrp
0x140013ef9  nop     dword ptr [rax+rax+00h]
0x140013efe  mov     eax, edi
0x140013f00  add     rsp, 68h
0x140013f04  pop     rdi
0x140013f05  pop     rsi
0x140013f06  pop     rbp
0x140013f07  pop     rbx
0x140013f08  retn
```
