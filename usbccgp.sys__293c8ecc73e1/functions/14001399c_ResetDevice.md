# ResetDevice

- ea: `0x14001399c`
- end: `0x140013a66`
- name: `ResetDevice`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x14001399c`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400139c9`
- `ntoskrnl!KeInitializeEvent` at `0x1400139c9`
- `ntoskrnl!IofCallDriver` at `0x140013a2d`
- `ntoskrnl!IofCallDriver` at `0x140013a2d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140013a0e`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140013a0e`

## string_xrefs

- `0x140013a47`: `event (waiting for IOCTL_INTERNAL_USB_RESET_PORT to complete)`

## pseudocode

```c
__int64 __fastcall ResetDevice(__int64 a1)
{
  IRP *v2; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v2 = IoBuildDeviceIoControlRequest(0x220007u, *(PDEVICE_OBJECT *)(a1 + 40), 0, 0, 0, 0, 1u, &Event, &IoStatusBlock);
  if ( !v2 )
    return 3221225626LL;
  if ( IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), v2) == 259 )
    WaitForSignal(&Event, "event (waiting for IOCTL_INTERNAL_USB_RESET_PORT to complete)", *(_QWORD *)(a1 + 1368));
  return (unsigned int)IoStatusBlock.Status;
}

```

## disassembly

```asm
0x14001399c  push    rbx
0x14001399e  sub     rsp, 80h
0x1400139a5  mov     rbx, rcx
0x1400139a8  xorps   xmm0, xmm0
0x1400139ab  xorps   xmm1, xmm1
0x1400139ae  lea     rcx, [rsp+88h+Event]; Event
0x1400139b3  xor     eax, eax
0x1400139b5  xor     r8d, r8d; State
0x1400139b8  xor     edx, edx; Type
0x1400139ba  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1400139bf  movups  xmmword ptr [rsp+88h+var_38.___u0], xmm0
0x1400139c4  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm1
0x1400139c9  call    cs:__imp_KeInitializeEvent
0x1400139d0  nop     dword ptr [rax+rax+00h]
0x1400139d5  mov     rdx, [rbx+28h]; DeviceObject
0x1400139d9  lea     rax, [rsp+88h+var_38]
0x1400139de  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x1400139e3  xor     r9d, r9d; InputBufferLength
0x1400139e6  lea     rax, [rsp+88h+Event]
0x1400139eb  xor     r8d, r8d; InputBuffer
0x1400139ee  mov     [rsp+88h+var_50], rax; Event
0x1400139f3  mov     ecx, 220007h; IoControlCode
0x1400139f8  mov     [rsp+88h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x1400139fd  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x140013a05  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x140013a0e  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140013a15  nop     dword ptr [rax+rax+00h]
0x140013a1a  test    rax, rax
0x140013a1d  jnz     short loc_140013A26
0x140013a1f  mov     eax, 0C000009Ah
0x140013a24  jmp     short loc_140013A5C
0x140013a26  mov     rcx, [rbx+28h]; DeviceObject
0x140013a2a  mov     rdx, rax; Irp
0x140013a2d  call    cs:__imp_IofCallDriver
0x140013a34  nop     dword ptr [rax+rax+00h]
0x140013a39  cmp     eax, 103h
0x140013a3e  jnz     short loc_140013A58
0x140013a40  mov     r8, [rbx+558h]
0x140013a47  lea     rdx, aEventWaitingFo_2; "event (waiting for IOCTL_INTERNAL_USB_R"...
0x140013a4e  lea     rcx, [rsp+88h+Event]; Object
0x140013a53  call    WaitForSignal
0x140013a58  mov     eax, dword ptr [rsp+88h+var_38.___u0]
0x140013a5c  add     rsp, 80h
0x140013a63  pop     rbx
0x140013a64  retn
```
