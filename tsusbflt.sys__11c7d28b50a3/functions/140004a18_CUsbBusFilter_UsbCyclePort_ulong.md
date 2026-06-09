# CUsbBusFilter::UsbCyclePort(ulong)

- ea: `0x140004a18`
- end: `0x140004c6b`
- name: `?UsbCyclePort@CUsbBusFilter@@AEAAJK@Z`
- size: `595`
- prototype: `__int64 __fastcall(CUsbBusFilter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003258`

## callees

- `0x140004a18`
- `0x140004edc`
- `0x140004f18`
- `0x140004f48`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140004ae7`
- `ntoskrnl!IoAllocateIrp` at `0x140004ae7`
- `ntoskrnl!KeInitializeEvent` at `0x140004b44`
- `ntoskrnl!KeInitializeEvent` at `0x140004b44`
- `ntoskrnl!IofCallDriver` at `0x140004bc4`
- `ntoskrnl!IofCallDriver` at `0x140004bc4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004bee`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004bee`
- `ntoskrnl!IoFreeIrp` at `0x140004c47`
- `ntoskrnl!IoFreeIrp` at `0x140004c47`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::UsbCyclePort(CUsbBusFilter *this, int a2)
{
  __int64 v3; // rdx
  __int64 v5; // rax
  int v6; // r9d
  struct _DEVICE_OBJECT *v7; // r14
  PDEVICE_OBJECT v8; // rcx
  unsigned __int16 v9; // dx
  PIRP Irp; // rax
  IRP *v11; // rdi
  NTSTATUS Status; // ebx
  char v13; // dl
  int v14; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  struct _IRP *v16; // rax
  struct _IO_STACK_LOCATION *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  PDEVICE_OBJECT v20; // rcx
  struct _KEVENT Event; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+70h] [rbp+20h] BYREF
  __int64 v24; // [rsp+80h] [rbp+30h] BYREF

  v3 = *((_QWORD *)this + 6);
  v24 = 0;
  v23 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( v3 )
  {
    v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[89].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
    v6 = *((_DWORD *)this + 14);
    v7 = (struct _DEVICE_OBJECT *)v5;
    v23 = v6;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v9 = 40;
LABEL_8:
      WPP_SF_d((__int64)v8->AttachedDevice, v9, (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids, v6);
    }
  }
  else
  {
    v7 = (struct _DEVICE_OBJECT *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[16].Flink)(
                                    WPP_MAIN_CB.Queue.ListEntry.Blink,
                                    *(_QWORD *)this);
    v23 = a2;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v9 = 41;
      v6 = a2;
      goto LABEL_8;
    }
  }
  Irp = IoAllocateIrp(v7->StackSize, 0);
  v11 = Irp;
  if ( Irp )
  {
    Irp->IoStatus.Status = -1073741637;
    Irp->IoStatus.Information = 0;
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    v13 = *((_BYTE *)this + 40);
    v14 = v24;
    CurrentStackLocation = v11->Tail.Overlay.CurrentStackLocation;
    if ( v13 )
      v14 = v23;
    LODWORD(v24) = v14;
    v16 = (struct _IRP *)&v23;
    if ( v13 )
      v16 = (struct _IRP *)&v24;
    v11->AssociatedIrp.MasterIrp = v16;
    CurrentStackLocation[-1].Parameters.Create.Options = v13 != 0 ? 8 : 4;
    CurrentStackLocation[-1].Parameters.Read.Length = v13 != 0 ? 8 : 0;
    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 14;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2229316;
    v17 = v11->Tail.Overlay.CurrentStackLocation;
    v17[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FdEvtWdmIrpGenericCompletion;
    v17[-1].Context = &Event;
    v17[-1].Control = -32;
    Status = IofCallDriver(v7, v11);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v11->IoStatus.Status;
    }
    if ( Status >= 0 )
    {
      Status = 0;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x2Bu,
          (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
          Status);
      if ( (Microsoft_Windows_TerminalServices_ClientUSBDevicesEnableBits & 0x10) != 0 )
        McTemplateK0_EtwWriteTransfer((__int64)v20, (const EVENT_DESCRIPTOR *)",", v18, v19);
    }
    IoFreeIrp(v11);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x2Au,
        (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140004a18  mov     [rsp-18h+arg_8], rbx
0x140004a1d  mov     [rsp-18h+arg_18], rsi
0x140004a22  push    rbp
0x140004a23  push    rdi
0x140004a24  push    r14
0x140004a26  mov     rbp, rsp
0x140004a29  sub     rsp, 50h
0x140004a2d  xor     eax, eax
0x140004a2f  mov     edi, edx
0x140004a31  mov     rdx, [rcx+30h]
0x140004a35  xorps   xmm0, xmm0
0x140004a38  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x140004a3c  mov     rbx, rcx
0x140004a3f  mov     [rbp+arg_10], rax
0x140004a43  mov     [rbp+arg_0], eax
0x140004a46  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004a4d  movups  xmmword ptr [rbp+Event.Header], xmm0
0x140004a51  test    rdx, rdx
0x140004a54  jz      short loc_140004A94
0x140004a56  mov     rax, [rax+590h]
0x140004a5d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004a64  call    _guard_dispatch_icall
0x140004a69  mov     r9d, [rbx+38h]
0x140004a6d  mov     r14, rax
0x140004a70  mov     [rbp+arg_0], r9d
0x140004a74  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a7b  lea     rsi, WPP_GLOBAL_Control
0x140004a82  cmp     rcx, rsi
0x140004a85  jz      short loc_140004AE1
0x140004a87  cmp     byte ptr [rcx+29h], 5
0x140004a8b  jb      short loc_140004AE1
0x140004a8d  mov     edx, 28h ; '('
0x140004a92  jmp     short loc_140004AD1
0x140004a94  mov     rdx, [rcx]
0x140004a97  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004a9e  mov     rax, [rax+100h]
0x140004aa5  call    _guard_dispatch_icall
0x140004aaa  mov     r14, rax
0x140004aad  mov     [rbp+arg_0], edi
0x140004ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ab7  lea     rsi, WPP_GLOBAL_Control
0x140004abe  cmp     rcx, rsi
0x140004ac1  jz      short loc_140004AE1
0x140004ac3  cmp     byte ptr [rcx+29h], 5
0x140004ac7  jb      short loc_140004AE1
0x140004ac9  mov     edx, 29h ; ')'
0x140004ace  mov     r9d, edi
0x140004ad1  mov     rcx, [rcx+18h]
0x140004ad5  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004adc  call    WPP_SF_d
0x140004ae1  mov     cl, [r14+4Ch]; StackSize
0x140004ae5  xor     edx, edx; ChargeQuota
0x140004ae7  call    cs:__imp_IoAllocateIrp
0x140004aee  nop     dword ptr [rax+rax+00h]
0x140004af3  mov     rdi, rax
0x140004af6  test    rax, rax
0x140004af9  jnz     short loc_140004B2A
0x140004afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b02  cmp     rcx, rsi
0x140004b05  jz      short loc_140004B20
0x140004b07  cmp     byte ptr [rcx+29h], 2
0x140004b0b  jb      short loc_140004B20
0x140004b0d  mov     rcx, [rcx+18h]
0x140004b11  lea     edx, [rax+2Ah]
0x140004b14  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004b1b  call    WPP_SF_
0x140004b20  mov     ebx, 0C000009Ah
0x140004b25  jmp     loc_140004C53
0x140004b2a  xor     r8d, r8d; State
0x140004b2d  mov     dword ptr [rax+30h], 0C00000BBh
0x140004b34  lea     rcx, [rbp+Event]; Event
0x140004b38  mov     qword ptr [rax+38h], 0
0x140004b40  lea     edx, [r8+1]; Type
0x140004b44  call    cs:__imp_KeInitializeEvent
0x140004b4b  nop     dword ptr [rax+rax+00h]
0x140004b50  mov     dl, [rbx+28h]
0x140004b53  lea     rcx, [rbp+arg_10]
0x140004b57  mov     eax, dword ptr [rbp+arg_10]
0x140004b5a  test    dl, dl
0x140004b5c  mov     r8, [rdi+0B8h]
0x140004b63  cmovnz  eax, [rbp+arg_0]
0x140004b67  mov     dword ptr [rbp+arg_10], eax
0x140004b6a  lea     rax, [rbp+arg_0]
0x140004b6e  cmovnz  rax, rcx
0x140004b72  mov     [rdi+18h], rax
0x140004b76  mov     al, dl
0x140004b78  neg     al
0x140004b7a  sbb     ecx, ecx
0x140004b7c  and     ecx, 4
0x140004b7f  add     ecx, 4
0x140004b82  mov     [r8-38h], ecx
0x140004b86  neg     dl
0x140004b88  lea     rcx, FdEvtWdmIrpGenericCompletion
0x140004b8f  mov     rdx, rdi; Irp
0x140004b92  sbb     eax, eax
0x140004b94  and     eax, 8
0x140004b97  mov     [r8-40h], eax
0x140004b9b  mov     word ptr [r8-48h], 0Eh
0x140004ba2  mov     dword ptr [r8-30h], 220444h
0x140004baa  mov     rax, [rdi+0B8h]
0x140004bb1  mov     [rax-10h], rcx
0x140004bb5  lea     rcx, [rbp+Event]
0x140004bb9  mov     [rax-8], rcx
0x140004bbd  mov     rcx, r14; DeviceObject
0x140004bc0  mov     byte ptr [rax-45h], 0E0h
0x140004bc4  call    cs:__imp_IofCallDriver
0x140004bcb  nop     dword ptr [rax+rax+00h]
0x140004bd0  mov     ebx, eax
0x140004bd2  cmp     eax, 103h
0x140004bd7  jnz     short loc_140004BFD
0x140004bd9  xor     r9d, r9d; Alertable
0x140004bdc  mov     [rsp+50h+Timeout], 0; Timeout
0x140004be5  xor     r8d, r8d; WaitMode
0x140004be8  lea     rcx, [rbp+Event]; Object
0x140004bec  xor     edx, edx; WaitReason
0x140004bee  call    cs:__imp_KeWaitForSingleObject
0x140004bf5  nop     dword ptr [rax+rax+00h]
0x140004bfa  mov     ebx, [rdi+30h]
0x140004bfd  test    ebx, ebx
0x140004bff  jns     short loc_140004C42
0x140004c01  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c08  cmp     rcx, rsi
0x140004c0b  jz      short loc_140004C2B
0x140004c0d  cmp     byte ptr [rcx+29h], 2
0x140004c11  jb      short loc_140004C2B
0x140004c13  mov     rcx, [rcx+18h]
0x140004c17  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004c1e  mov     edx, 2Bh ; '+'
0x140004c23  mov     r9d, ebx
0x140004c26  call    WPP_SF_d
0x140004c2b  test    cs:Microsoft_Windows_TerminalServices_ClientUSBDevicesEnableBits, 10h
0x140004c32  jz      short loc_140004C44
0x140004c34  lea     rdx, EVENT_PORT_CYCLE_FAILED; ","
0x140004c3b  call    McTemplateK0_EtwWriteTransfer
0x140004c40  jmp     short loc_140004C44
0x140004c42  xor     ebx, ebx
0x140004c44  mov     rcx, rdi; Irp
0x140004c47  call    cs:__imp_IoFreeIrp
0x140004c4e  nop     dword ptr [rax+rax+00h]
0x140004c53  lea     r11, [rsp+50h+var_s0]
0x140004c58  mov     eax, ebx
0x140004c5a  mov     rbx, [r11+28h]
0x140004c5e  mov     rsi, [r11+38h]
0x140004c62  mov     rsp, r11
0x140004c65  pop     r14
0x140004c67  pop     rdi
0x140004c68  pop     rbp
0x140004c69  retn
```
