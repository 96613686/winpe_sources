# UsbcGetTopologyAddress

- ea: `0x14000deb8`
- end: `0x14000dfa5`
- name: `UsbcGetTopologyAddress`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140025bd0`
- `0x14002db28`

## callees

- `0x14000deb8`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000def3`
- `ntoskrnl!KeInitializeEvent` at `0x14000def3`
- `ntoskrnl!IofCallDriver` at `0x14000df5b`
- `ntoskrnl!IofCallDriver` at `0x14000df5b`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000df38`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000df38`

## string_xrefs

- `0x14000df8e`: `event (waiting for IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS to complete)`

## pseudocode

```c
NTSTATUS __fastcall UsbcGetTopologyAddress(__int64 a1, _OWORD *a2)
{
  PIRP v4; // rax
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  *a2 = 0;
  a2[1] = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v4 = IoBuildDeviceIoControlRequest(0x22043Fu, *(PDEVICE_OBJECT *)(a1 + 40), 0, 0, 0, 0, 1u, &Event, &IoStatusBlock);
  if ( !v4 )
    return -1073741670;
  v4->Tail.Overlay.CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)a2;
  result = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), v4);
  if ( result == 259 )
  {
    WaitForSignal(
      &Event,
      "event (waiting for IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS to complete)",
      *(_QWORD *)(a1 + 1368));
    return IoStatusBlock.Status;
  }
  return result;
}

```

## disassembly

```asm
0x14000deb8  mov     [rsp+arg_0], rbx
0x14000debd  push    rdi
0x14000debe  sub     rsp, 80h
0x14000dec5  xorps   xmm1, xmm1
0x14000dec8  xorps   xmm0, xmm0
0x14000decb  movups  xmmword ptr [rdx], xmm1
0x14000dece  mov     rdi, rdx
0x14000ded1  mov     rbx, rcx
0x14000ded4  movups  xmmword ptr [rdx+10h], xmm1
0x14000ded8  xor     eax, eax
0x14000deda  lea     rcx, [rsp+88h+Event]; Event
0x14000dedf  xor     edx, edx; Type
0x14000dee1  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000dee6  xor     r8d, r8d; State
0x14000dee9  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x14000deee  movups  xmmword ptr [rsp+88h+var_38.___u0], xmm0
0x14000def3  call    cs:__imp_KeInitializeEvent
0x14000defa  nop     dword ptr [rax+rax+00h]
0x14000deff  mov     rdx, [rbx+28h]; DeviceObject
0x14000df03  lea     rax, [rsp+88h+var_38]
0x14000df08  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x14000df0d  xor     r9d, r9d; InputBufferLength
0x14000df10  lea     rax, [rsp+88h+Event]
0x14000df15  xor     r8d, r8d; InputBuffer
0x14000df18  mov     [rsp+88h+var_50], rax; Event
0x14000df1d  mov     ecx, 22043Fh; IoControlCode
0x14000df22  mov     [rsp+88h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x14000df27  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x14000df2f  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x14000df38  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000df3f  nop     dword ptr [rax+rax+00h]
0x14000df44  mov     rdx, rax; Irp
0x14000df47  test    rax, rax
0x14000df4a  jz      short loc_14000DF80
0x14000df4c  mov     rax, [rax+0B8h]
0x14000df53  mov     [rax-40h], rdi
0x14000df57  mov     rcx, [rbx+28h]; DeviceObject
0x14000df5b  call    cs:__imp_IofCallDriver
0x14000df62  nop     dword ptr [rax+rax+00h]
0x14000df67  cmp     eax, 103h
0x14000df6c  jz      short loc_14000DF87
0x14000df6e  mov     rbx, [rsp+88h+arg_0]
0x14000df76  add     rsp, 80h
0x14000df7d  pop     rdi
0x14000df7e  retn
0x14000df80  mov     eax, 0C000009Ah
0x14000df85  jmp     short loc_14000DF6E
0x14000df87  mov     r8, [rbx+558h]
0x14000df8e  lea     rdx, aEventWaitingFo_3; "event (waiting for IOCTL_INTERNAL_USB_G"...
0x14000df95  lea     rcx, [rsp+88h+Event]; Object
0x14000df9a  call    WaitForSignal
0x14000df9f  mov     eax, dword ptr [rsp+88h+var_38.___u0]
0x14000dfa3  jmp     short loc_14000DF6E
```
