# USBDInternal_BuildAndSendQueryInterfaceSynchronously

- ea: `0x1400428a8`
- end: `0x140042a06`
- name: `USBDInternal_BuildAndSendQueryInterfaceSynchronously`
- size: `350`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400430c0`

## callees

- `0x1400428a8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400429af`
- `ntoskrnl!IofCallDriver` at `0x1400429af`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400429da`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400429da`
- `ntoskrnl!KeInitializeEvent` at `0x1400428d8`
- `ntoskrnl!KeInitializeEvent` at `0x1400428d8`
- `ntoskrnl!DbgPrintEx` at `0x140042914`
- `ntoskrnl!DbgPrintEx` at `0x140042914`
- `ntoskrnl!IoFreeIrp` at `0x1400429ec`
- `ntoskrnl!IoFreeIrp` at `0x1400429ec`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14004297a`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14004297a`
- `ntoskrnl!IoAllocateIrp` at `0x1400428e9`
- `ntoskrnl!IoAllocateIrp` at `0x1400428e9`

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
  unsigned int Status; // edi
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  _IO_STACK_LOCATION *v12; // rax
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
      v12 = v9->Tail.Overlay.CurrentStackLocation;
      v12[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))USBD_SyncCompletionRoutine;
      v12[-1].Context = &Event;
      v12[-1].Control = -32;
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
0x1400428a8  push    rbx
0x1400428aa  push    rbp
0x1400428ab  push    rsi
0x1400428ac  push    rdi
0x1400428ad  push    r14
0x1400428af  sub     rsp, 60h
0x1400428b3  mov     rbp, r8
0x1400428b6  mov     rdi, rdx
0x1400428b9  mov     r14, rcx
0x1400428bc  xorps   xmm0, xmm0
0x1400428bf  xor     eax, eax
0x1400428c1  lea     rcx, [rsp+88h+Event]; Event
0x1400428c6  xor     r8d, r8d; State
0x1400428c9  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1400428ce  xor     edx, edx; Type
0x1400428d0  mov     rsi, r9
0x1400428d3  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x1400428d8  call    cs:__imp_KeInitializeEvent
0x1400428df  nop     dword ptr [rax+rax+00h]
0x1400428e4  mov     cl, [rdi+4Ch]; StackSize
0x1400428e7  xor     edx, edx; ChargeQuota
0x1400428e9  call    cs:__imp_IoAllocateIrp
0x1400428f0  nop     dword ptr [rax+rax+00h]
0x1400428f5  mov     rbx, rax
0x1400428f8  test    rax, rax
0x1400428fb  jnz     short loc_14004292A
0x1400428fd  cmp     cs:g_EnableDbgPrints, al
0x140042903  jz      short loc_140042920
0x140042905  mov     r9, rdi
0x140042908  lea     r8, aFailedToAlloca; "Failed to allocate Query Interface Irp "...
0x14004290f  xor     edx, edx; Level
0x140042911  lea     ecx, [rax+4Dh]; ComponentId
0x140042914  call    cs:__imp_DbgPrintEx
0x14004291b  nop     dword ptr [rax+rax+00h]
0x140042920  mov     edi, 0C000009Ah
0x140042925  jmp     loc_1400429F8
0x14004292a  mov     rcx, [rax+0B8h]
0x140042931  lea     r9, [rsp+88h+Event]; Context
0x140042936  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14004293b  mov     rdx, rbx; Irp
0x14004293e  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x140042943  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140042948  mov     [rcx-30h], rsi
0x14004294c  mov     word ptr [rcx-48h], 81Bh
0x140042952  mov     qword ptr [rcx-28h], 0
0x14004295a  mov     [rcx-40h], rbp
0x14004295e  movzx   eax, word ptr [rsi]
0x140042961  mov     [rcx-38h], ax
0x140042965  movzx   eax, word ptr [rsi+2]
0x140042969  lea     rsi, USBD_SyncCompletionRoutine
0x140042970  mov     [rcx-36h], ax
0x140042974  mov     r8, rsi; CompletionRoutine
0x140042977  mov     rcx, r14; DeviceObject
0x14004297a  call    cs:__imp_IoSetCompletionRoutineEx
0x140042981  nop     dword ptr [rax+rax+00h]
0x140042986  test    eax, eax
0x140042988  jns     short loc_1400429A2
0x14004298a  mov     rax, [rbx+0B8h]
0x140042991  lea     rcx, [rsp+88h+Event]
0x140042996  mov     [rax-10h], rsi
0x14004299a  mov     [rax-8], rcx
0x14004299e  mov     byte ptr [rax-45h], 0E0h
0x1400429a2  mov     rdx, rbx; Irp
0x1400429a5  mov     dword ptr [rbx+30h], 0C00000BBh
0x1400429ac  mov     rcx, rdi; DeviceObject
0x1400429af  call    cs:__imp_IofCallDriver
0x1400429b6  nop     dword ptr [rax+rax+00h]
0x1400429bb  mov     edi, eax
0x1400429bd  cmp     eax, 103h
0x1400429c2  jnz     short loc_1400429E9
0x1400429c4  xor     r9d, r9d; Alertable
0x1400429c7  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x1400429d0  xor     r8d, r8d; WaitMode
0x1400429d3  lea     rcx, [rsp+88h+Event]; Object
0x1400429d8  xor     edx, edx; WaitReason
0x1400429da  call    cs:__imp_KeWaitForSingleObject
0x1400429e1  nop     dword ptr [rax+rax+00h]
0x1400429e6  mov     edi, [rbx+30h]
0x1400429e9  mov     rcx, rbx; Irp
0x1400429ec  call    cs:__imp_IoFreeIrp
0x1400429f3  nop     dword ptr [rax+rax+00h]
0x1400429f8  mov     eax, edi
0x1400429fa  add     rsp, 60h
0x1400429fe  pop     r14
0x140042a00  pop     rdi
0x140042a01  pop     rsi
0x140042a02  pop     rbp
0x140042a03  pop     rbx
0x140042a04  retn
```
