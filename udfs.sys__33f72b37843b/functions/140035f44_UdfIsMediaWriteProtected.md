# UdfIsMediaWriteProtected

- ea: `0x140035f44`
- end: `0x140036043`
- name: `UdfIsMediaWriteProtected`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x140035f44`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140035fd5`
- `ntoskrnl!ExRaiseStatus` at `0x140035fd5`
- `ntoskrnl!IofCallDriver` at `0x140035ff0`
- `ntoskrnl!IofCallDriver` at `0x140035ff0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140036019`
- `ntoskrnl!KeWaitForSingleObject` at `0x140036019`
- `ntoskrnl!KeInitializeEvent` at `0x140035f75`
- `ntoskrnl!KeInitializeEvent` at `0x140035f75`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140035fb9`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140035fb9`

## pseudocode

```c
bool __fastcall UdfIsMediaWriteProtected(__int64 a1, struct _DEVICE_OBJECT *a2)
{
  PIRP v4; // rax
  NTSTATUS Status; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v4 = IoBuildDeviceIoControlRequest(0x70024u, a2, 0, 0, 0, 0, 0, &Event, &IoStatusBlock);
  if ( !v4 )
  {
    *(_DWORD *)(a1 + 24) = -1073741670;
    ExRaiseStatus(-1073741670);
  }
  v4->Tail.Overlay.CurrentStackLocation[-1].Flags |= 2u;
  Status = IofCallDriver(a2, v4);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  return Status == -1073741662;
}

```

## disassembly

```asm
0x140035f44  mov     [rsp+arg_0], rbx
0x140035f49  push    rdi
0x140035f4a  sub     rsp, 80h
0x140035f51  xorps   xmm0, xmm0
0x140035f54  mov     rdi, rdx
0x140035f57  mov     rbx, rcx
0x140035f5a  xor     eax, eax
0x140035f5c  xor     edx, edx; Type
0x140035f5e  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140035f63  lea     rcx, [rsp+88h+Event]; Event
0x140035f68  xor     r8d, r8d; State
0x140035f6b  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x140035f70  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x140035f75  call    cs:__imp_KeInitializeEvent
0x140035f7c  nop     dword ptr [rax+rax+00h]
0x140035f81  lea     rax, [rsp+88h+var_38]
0x140035f86  xor     r9d, r9d; InputBufferLength
0x140035f89  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x140035f8e  xor     r8d, r8d; InputBuffer
0x140035f91  lea     rax, [rsp+88h+Event]
0x140035f96  mov     rdx, rdi; DeviceObject
0x140035f99  mov     [rsp+88h+var_50], rax; Event
0x140035f9e  mov     ecx, 70024h; IoControlCode
0x140035fa3  mov     [rsp+88h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140035fa8  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x140035fb0  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x140035fb9  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140035fc0  nop     dword ptr [rax+rax+00h]
0x140035fc5  mov     rdx, rax; Irp
0x140035fc8  test    rax, rax
0x140035fcb  jnz     short loc_140035FE2
0x140035fcd  mov     ecx, 0C000009Ah; Status
0x140035fd2  mov     [rbx+18h], ecx
0x140035fd5  call    cs:__imp_ExRaiseStatus
0x140035fe2  mov     rax, [rax+0B8h]
0x140035fe9  mov     rcx, rdi; DeviceObject
0x140035fec  or      byte ptr [rax-46h], 2
0x140035ff0  call    cs:__imp_IofCallDriver
0x140035ff7  nop     dword ptr [rax+rax+00h]
0x140035ffc  cmp     eax, 103h
0x140036001  jnz     short loc_140036029
0x140036003  xor     r9d, r9d; Alertable
0x140036006  mov     [rsp+88h+OutputBuffer], 0; Timeout
0x14003600f  xor     r8d, r8d; WaitMode
0x140036012  lea     rcx, [rsp+88h+Event]; Object
0x140036017  xor     edx, edx; WaitReason
0x140036019  call    cs:__imp_KeWaitForSingleObject
0x140036020  nop     dword ptr [rax+rax+00h]
0x140036025  mov     eax, dword ptr [rsp+88h+var_38]
0x140036029  mov     rbx, [rsp+88h+arg_0]
0x140036031  cmp     eax, 0C00000A2h
0x140036036  setz    al
0x140036039  add     rsp, 80h
0x140036040  pop     rdi
0x140036041  retn
```
