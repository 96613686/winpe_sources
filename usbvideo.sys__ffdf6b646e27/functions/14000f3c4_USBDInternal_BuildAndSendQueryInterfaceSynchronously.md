# USBDInternal_BuildAndSendQueryInterfaceSynchronously

- ea: `0x14000f3c4`
- end: `0x14000f522`
- name: `USBDInternal_BuildAndSendQueryInterfaceSynchronously`
- size: `350`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000efa4`

## callees

- `0x14000f3c4`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000f496`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000f496`
- `ntoskrnl!KeInitializeEvent` at `0x14000f3f4`
- `ntoskrnl!KeInitializeEvent` at `0x14000f3f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f4f6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f4f6`
- `ntoskrnl!IofCallDriver` at `0x14000f4cb`
- `ntoskrnl!IofCallDriver` at `0x14000f4cb`
- `ntoskrnl!IoAllocateIrp` at `0x14000f405`
- `ntoskrnl!IoAllocateIrp` at `0x14000f405`
- `ntoskrnl!IoFreeIrp` at `0x14000f508`
- `ntoskrnl!IoFreeIrp` at `0x14000f508`
- `ntoskrnl!DbgPrintEx` at `0x14000f430`
- `ntoskrnl!DbgPrintEx` at `0x14000f430`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildAndSendQueryInterfaceSynchronously(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT a2,
        ULONG_PTR a3,
        USHORT *a4)
{
  PIRP Irp; // rax
  IRP *v9; // rbx
  unsigned int Status; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v12; // rax
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  Irp = IoAllocateIrp(a2->StackSize, 0);
  v9 = Irp;
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)a4;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
    CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = a3;
    CurrentStackLocation[-1].Parameters.QueryInterface.Size = *a4;
    CurrentStackLocation[-1].Parameters.QueryInterface.Version = a4[1];
    if ( IoSetCompletionRoutineEx(DeviceObject, Irp, USBD_SyncCompletionRoutine, &Event, 1u, 1u, 1u) < 0 )
    {
      v12 = v9->Tail.Overlay.CurrentStackLocation;
      v12[-1].CompletionRoutine = USBD_SyncCompletionRoutine;
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
0x14000f3c4  push    rbx
0x14000f3c6  push    rbp
0x14000f3c7  push    rsi
0x14000f3c8  push    rdi
0x14000f3c9  push    r14
0x14000f3cb  sub     rsp, 60h
0x14000f3cf  mov     rbp, r8
0x14000f3d2  mov     rdi, rdx
0x14000f3d5  mov     r14, rcx
0x14000f3d8  xorps   xmm0, xmm0
0x14000f3db  xor     eax, eax
0x14000f3dd  lea     rcx, [rsp+88h+Event]; Event
0x14000f3e2  xor     r8d, r8d; State
0x14000f3e5  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000f3ea  xor     edx, edx; Type
0x14000f3ec  mov     rsi, r9
0x14000f3ef  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000f3f4  call    cs:__imp_KeInitializeEvent
0x14000f3fb  nop     dword ptr [rax+rax+00h]
0x14000f400  mov     cl, [rdi+4Ch]; StackSize
0x14000f403  xor     edx, edx; ChargeQuota
0x14000f405  call    cs:__imp_IoAllocateIrp
0x14000f40c  nop     dword ptr [rax+rax+00h]
0x14000f411  mov     rbx, rax
0x14000f414  test    rax, rax
0x14000f417  jnz     short loc_14000F446
0x14000f419  cmp     cs:g_EnableDbgPrints, al
0x14000f41f  jz      short loc_14000F43C
0x14000f421  mov     r9, rdi
0x14000f424  lea     r8, aFailedToAlloca; "Failed to allocate Query Interface Irp "...
0x14000f42b  xor     edx, edx; Level
0x14000f42d  lea     ecx, [rax+4Dh]; ComponentId
0x14000f430  call    cs:__imp_DbgPrintEx
0x14000f437  nop     dword ptr [rax+rax+00h]
0x14000f43c  mov     edi, 0C000009Ah
0x14000f441  jmp     loc_14000F514
0x14000f446  mov     rcx, [rax+0B8h]
0x14000f44d  lea     r9, [rsp+88h+Event]; Context
0x14000f452  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x14000f457  mov     rdx, rbx; Irp
0x14000f45a  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x14000f45f  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x14000f464  mov     [rcx-30h], rsi
0x14000f468  mov     word ptr [rcx-48h], 81Bh
0x14000f46e  mov     qword ptr [rcx-28h], 0
0x14000f476  mov     [rcx-40h], rbp
0x14000f47a  movzx   eax, word ptr [rsi]
0x14000f47d  mov     [rcx-38h], ax
0x14000f481  movzx   eax, word ptr [rsi+2]
0x14000f485  lea     rsi, USBD_SyncCompletionRoutine
0x14000f48c  mov     [rcx-36h], ax
0x14000f490  mov     r8, rsi; CompletionRoutine
0x14000f493  mov     rcx, r14; DeviceObject
0x14000f496  call    cs:__imp_IoSetCompletionRoutineEx
0x14000f49d  nop     dword ptr [rax+rax+00h]
0x14000f4a2  test    eax, eax
0x14000f4a4  jns     short loc_14000F4BE
0x14000f4a6  mov     rax, [rbx+0B8h]
0x14000f4ad  lea     rcx, [rsp+88h+Event]
0x14000f4b2  mov     [rax-10h], rsi
0x14000f4b6  mov     [rax-8], rcx
0x14000f4ba  mov     byte ptr [rax-45h], 0E0h
0x14000f4be  mov     rdx, rbx; Irp
0x14000f4c1  mov     dword ptr [rbx+30h], 0C00000BBh
0x14000f4c8  mov     rcx, rdi; DeviceObject
0x14000f4cb  call    cs:__imp_IofCallDriver
0x14000f4d2  nop     dword ptr [rax+rax+00h]
0x14000f4d7  mov     edi, eax
0x14000f4d9  cmp     eax, 103h
0x14000f4de  jnz     short loc_14000F505
0x14000f4e0  xor     r9d, r9d; Alertable
0x14000f4e3  mov     qword ptr [rsp+88h+InvokeOnSuccess], 0; Timeout
0x14000f4ec  xor     r8d, r8d; WaitMode
0x14000f4ef  lea     rcx, [rsp+88h+Event]; Object
0x14000f4f4  xor     edx, edx; WaitReason
0x14000f4f6  call    cs:__imp_KeWaitForSingleObject
0x14000f4fd  nop     dword ptr [rax+rax+00h]
0x14000f502  mov     edi, [rbx+30h]
0x14000f505  mov     rcx, rbx; Irp
0x14000f508  call    cs:__imp_IoFreeIrp
0x14000f50f  nop     dword ptr [rax+rax+00h]
0x14000f514  mov     eax, edi
0x14000f516  add     rsp, 60h
0x14000f51a  pop     r14
0x14000f51c  pop     rdi
0x14000f51d  pop     rsi
0x14000f51e  pop     rbp
0x14000f51f  pop     rbx
0x14000f520  retn
```
