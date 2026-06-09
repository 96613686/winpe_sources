# ReportStartFailData

- ea: `0x140010d14`
- end: `0x140010e4d`
- name: `ReportStartFailData`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x140010d14`
- `0x140014e00`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010e2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010e2b`
- `ntoskrnl!KeInitializeEvent` at `0x140010d90`
- `ntoskrnl!KeInitializeEvent` at `0x140010d90`
- `ntoskrnl!IofCallDriver` at `0x140010df8`
- `ntoskrnl!IofCallDriver` at `0x140010df8`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140010dd5`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140010dd5`
- `ntoskrnl!ExAllocatePool2` at `0x140010d5c`
- `ntoskrnl!ExAllocatePool2` at `0x140010d5c`

## string_xrefs

- `0x140010e12`: `event (waiting for IOCTL_INTERNAL_USB_RECORD_FAILURE to complete)`

## pseudocode

```c
void __fastcall ReportStartFailData(__int64 a1)
{
  unsigned int *v2; // rax
  unsigned int v3; // esi
  void *Pool2; // rax
  void *v5; // rdi
  PIRP v6; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  v2 = *(unsigned int **)(a1 + 1144);
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  if ( v2 )
  {
    v3 = *v2;
    Pool2 = (void *)ExAllocatePool2(64, *v2, 1130525525);
    v5 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, *(const void **)(a1 + 1144), v3);
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v6 = IoBuildDeviceIoControlRequest(
             0x22002Bu,
             *(PDEVICE_OBJECT *)(a1 + 40),
             0,
             0,
             0,
             0,
             1u,
             &Event,
             &IoStatusBlock);
      if ( v6 )
      {
        v6->Tail.Overlay.CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)v5;
        if ( IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), v6) == 259 )
          WaitForSignal(
            &Event,
            "event (waiting for IOCTL_INTERNAL_USB_RECORD_FAILURE to complete)",
            *(_QWORD *)(a1 + 1368));
      }
      ExFreePoolWithTag(v5, 0x43627355u);
    }
  }
}

```

## disassembly

```asm
0x140010d14  mov     [rsp+arg_0], rbx
0x140010d19  mov     [rsp+arg_8], rsi
0x140010d1e  push    rdi
0x140010d1f  sub     rsp, 80h
0x140010d26  xor     eax, eax
0x140010d28  xorps   xmm0, xmm0
0x140010d2b  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140010d30  mov     rbx, rcx
0x140010d33  mov     rax, [rcx+478h]
0x140010d3a  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x140010d3f  movups  xmmword ptr [rsp+88h+var_38.___u0], xmm0
0x140010d44  test    rax, rax
0x140010d47  jz      loc_140010E37
0x140010d4d  mov     esi, [rax]
0x140010d4f  mov     r8d, 43627355h
0x140010d55  mov     edx, esi
0x140010d57  mov     ecx, 40h ; '@'
0x140010d5c  call    cs:__imp_ExAllocatePool2
0x140010d63  nop     dword ptr [rax+rax+00h]
0x140010d68  mov     rdi, rax
0x140010d6b  test    rax, rax
0x140010d6e  jz      loc_140010E37
0x140010d74  mov     rdx, [rbx+478h]; Src
0x140010d7b  mov     r8d, esi; Size
0x140010d7e  mov     rcx, rax; void *
0x140010d81  call    memmove
0x140010d86  xor     r8d, r8d; State
0x140010d89  lea     rcx, [rsp+88h+Event]; Event
0x140010d8e  xor     edx, edx; Type
0x140010d90  call    cs:__imp_KeInitializeEvent
0x140010d97  nop     dword ptr [rax+rax+00h]
0x140010d9c  mov     rdx, [rbx+28h]; DeviceObject
0x140010da0  lea     rax, [rsp+88h+var_38]
0x140010da5  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x140010daa  xor     r9d, r9d; InputBufferLength
0x140010dad  lea     rax, [rsp+88h+Event]
0x140010db2  xor     r8d, r8d; InputBuffer
0x140010db5  mov     [rsp+88h+var_50], rax; Event
0x140010dba  mov     ecx, 22002Bh; IoControlCode
0x140010dbf  mov     [rsp+88h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x140010dc4  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x140010dcc  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x140010dd5  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140010ddc  nop     dword ptr [rax+rax+00h]
0x140010de1  test    rax, rax
0x140010de4  jz      short loc_140010E23
0x140010de6  mov     rcx, [rax+0B8h]
0x140010ded  mov     rdx, rax; Irp
0x140010df0  mov     [rcx-40h], rdi
0x140010df4  mov     rcx, [rbx+28h]; DeviceObject
0x140010df8  call    cs:__imp_IofCallDriver
0x140010dff  nop     dword ptr [rax+rax+00h]
0x140010e04  cmp     eax, 103h
0x140010e09  jnz     short loc_140010E23
0x140010e0b  mov     r8, [rbx+558h]
0x140010e12  lea     rdx, aEventWaitingFo_4; "event (waiting for IOCTL_INTERNAL_USB_R"...
0x140010e19  lea     rcx, [rsp+88h+Event]; Object
0x140010e1e  call    WaitForSignal
0x140010e23  mov     edx, 43627355h; Tag
0x140010e28  mov     rcx, rdi; P
0x140010e2b  call    cs:__imp_ExFreePoolWithTag
0x140010e32  nop     dword ptr [rax+rax+00h]
0x140010e37  lea     r11, [rsp+88h+var_8]
0x140010e3f  mov     rbx, [r11+10h]
0x140010e43  mov     rsi, [r11+18h]
0x140010e47  mov     rsp, r11
0x140010e4a  pop     rdi
0x140010e4b  retn
```
