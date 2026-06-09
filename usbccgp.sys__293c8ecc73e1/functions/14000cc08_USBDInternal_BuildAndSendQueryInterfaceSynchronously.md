# USBDInternal_BuildAndSendQueryInterfaceSynchronously

- ea: `0x14000cc08`
- end: `0x14000cd72`
- name: `USBDInternal_BuildAndSendQueryInterfaceSynchronously`
- size: `362`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c7e8`

## callees

- `0x14000cc08`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000cc38`
- `ntoskrnl!KeInitializeEvent` at `0x14000cc38`
- `ntoskrnl!IoFreeIrp` at `0x14000cce6`
- `ntoskrnl!IoFreeIrp` at `0x14000cce6`
- `ntoskrnl!IoAllocateIrp` at `0x14000cc49`
- `ntoskrnl!IoAllocateIrp` at `0x14000cc49`
- `ntoskrnl!IofCallDriver` at `0x14000ccce`
- `ntoskrnl!IofCallDriver` at `0x14000ccce`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cd5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cd5e`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000ccb1`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000ccb1`
- `ntoskrnl!DbgPrintEx` at `0x14000cd18`
- `ntoskrnl!DbgPrintEx` at `0x14000cd18`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildAndSendQueryInterfaceSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        unsigned __int64 a3,
        unsigned __int16 *a4)
{
  PIRP Irp; // rax
  IRP *v9; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int Status; // edi
  _IO_STACK_LOCATION *v13; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v9 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (__int64)a4;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a3;
    CurrentStackLocation[-1].Parameters.QueryInterface.Size = *a4;
    CurrentStackLocation[-1].Parameters.QueryInterface.Version = a4[1];
    if ( IoSetCompletionRoutineEx(DeviceObject, Irp, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v13 = v9->Tail.Overlay.CurrentStackLocation;
      v13[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))USBD_SyncCompletionRoutine;
      v13[-1].Context = &Event;
      v13[-1].Control = -32;
    }
    v9->IoStatus.Status = -1073741637;
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
      DbgPrintEx(0x4Du, 0, "Failed to allocate Query Interface Irp for Target Device Ojbect 0x%p\n", a2);
    return (unsigned int)-1073741670;
  }
  return Status;
}

```

## disassembly

```asm
0x14000cc08  push    rbx
0x14000cc0a  push    rbp
0x14000cc0b  push    rsi
0x14000cc0c  push    rdi
0x14000cc0d  push    r14
0x14000cc0f  sub     rsp, 60h
0x14000cc13  mov     rbp, r8
0x14000cc16  mov     rdi, rdx
0x14000cc19  mov     r14, rcx
0x14000cc1c  xorps   xmm0, xmm0
0x14000cc1f  xor     eax, eax
0x14000cc21  lea     rcx, [rsp+88h+Event]; Event
0x14000cc26  xor     r8d, r8d; State
0x14000cc29  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000cc2e  xor     edx, edx; Type
0x14000cc30  mov     rsi, r9
0x14000cc33  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x14000cc38  call    cs:__imp_KeInitializeEvent
0x14000cc3f  nop     dword ptr [rax+rax+00h]
0x14000cc44  mov     cl, [rdi+4Ch]; StackSize
0x14000cc47  xor     edx, edx; ChargeQuota
0x14000cc49  call    cs:__imp_IoAllocateIrp
0x14000cc50  nop     dword ptr [rax+rax+00h]
0x14000cc55  mov     rbx, rax
0x14000cc58  test    rax, rax
0x14000cc5b  jz      loc_14000CD00
0x14000cc61  mov     rcx, [rax+0B8h]
0x14000cc68  lea     r9, [rsp+88h+Event]; Context
0x14000cc6d  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000cc72  mov     rdx, rbx; Irp
0x14000cc75  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000cc7a  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000cc7f  mov     [rcx-30h], rsi
0x14000cc83  mov     word ptr [rcx-48h], 81Bh
0x14000cc89  mov     qword ptr [rcx-28h], 0
0x14000cc91  mov     [rcx-40h], rbp
0x14000cc95  movzx   eax, word ptr [rsi]
0x14000cc98  mov     [rcx-38h], ax
0x14000cc9c  movzx   eax, word ptr [rsi+2]
0x14000cca0  lea     rsi, USBD_SyncCompletionRoutine
0x14000cca7  mov     [rcx-36h], ax
0x14000ccab  mov     r8, rsi; CompletionRoutine
0x14000ccae  mov     rcx, r14; DeviceObject
0x14000ccb1  call    cs:__imp_IoSetCompletionRoutineEx
0x14000ccb8  nop     dword ptr [rax+rax+00h]
0x14000ccbd  test    eax, eax
0x14000ccbf  js      short loc_14000CD2B
0x14000ccc1  mov     rdx, rbx; Irp
0x14000ccc4  mov     dword ptr [rbx+30h], 0C00000BBh
0x14000cccb  mov     rcx, rdi; DeviceObject
0x14000ccce  call    cs:__imp_IofCallDriver
0x14000ccd5  nop     dword ptr [rax+rax+00h]
0x14000ccda  mov     edi, eax
0x14000ccdc  cmp     eax, 103h
0x14000cce1  jz      short loc_14000CD48
0x14000cce3  mov     rcx, rbx; Irp
0x14000cce6  call    cs:__imp_IoFreeIrp
0x14000cced  nop     dword ptr [rax+rax+00h]
0x14000ccf2  mov     eax, edi
0x14000ccf4  add     rsp, 60h
0x14000ccf8  pop     r14
0x14000ccfa  pop     rdi
0x14000ccfb  pop     rsi
0x14000ccfc  pop     rbp
0x14000ccfd  pop     rbx
0x14000ccfe  retn
0x14000cd00  cmp     cs:g_EnableDbgPrints, 0
0x14000cd07  jz      short loc_14000CD24
0x14000cd09  xor     edx, edx; Level
0x14000cd0b  lea     r8, aFailedToAlloca; "Failed to allocate Query Interface Irp "...
0x14000cd12  mov     r9, rdi
0x14000cd15  lea     ecx, [rdx+4Dh]; ComponentId
0x14000cd18  call    cs:__imp_DbgPrintEx
0x14000cd1f  nop     dword ptr [rax+rax+00h]
0x14000cd24  mov     edi, 0C000009Ah
0x14000cd29  jmp     short loc_14000CCF2
0x14000cd2b  mov     rax, [rbx+0B8h]
0x14000cd32  lea     rcx, [rsp+88h+Event]
0x14000cd37  mov     [rax-10h], rsi
0x14000cd3b  mov     [rax-8], rcx
0x14000cd3f  mov     byte ptr [rax-45h], 0E0h
0x14000cd43  jmp     loc_14000CCC1
0x14000cd48  xor     r9d, r9d; Alertable
0x14000cd4b  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000cd54  xor     r8d, r8d; WaitMode
0x14000cd57  lea     rcx, [rsp+88h+Event]; Object
0x14000cd5c  xor     edx, edx; WaitReason
0x14000cd5e  call    cs:__imp_KeWaitForSingleObject
0x14000cd65  nop     dword ptr [rax+rax+00h]
0x14000cd6a  mov     edi, [rbx+30h]
0x14000cd6d  jmp     loc_14000CCE3
```
