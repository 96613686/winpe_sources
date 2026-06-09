# VmpSendDeviceControl

- ea: `0x140002db0`
- end: `0x140002e93`
- name: `VmpSendDeviceControl`
- size: `227`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x140004028`
- `0x14000f3b0`
- `0x14000f56c`
- `0x14000f820`
- `0x140010ad8`
- `0x140010d7c`
- `0x140011d94`
- `0x14001203c`
- `0x14001256c`
- `0x1400129d0`
- `0x140012db4`
- `0x1400130b0`
- `0x140013ba0`
- `0x140013e00`
- `0x140015800`
- `0x140015900`
- `0x140015a70`

## callees

- `0x140002db0`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140002e2d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140002e2d`
- `ntoskrnl!IofCallDriver` at `0x140002e44`
- `ntoskrnl!IofCallDriver` at `0x140002e44`
- `ntoskrnl!KeInitializeEvent` at `0x140002de5`
- `ntoskrnl!KeInitializeEvent` at `0x140002de5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002e81`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002e81`

## pseudocode

```c
NTSTATUS __fastcall VmpSendDeviceControl(
        PDEVICE_OBJECT DeviceObject,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  IRP *v10; // rax
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v10 = IoBuildDeviceIoControlRequest(
          IoControlCode,
          DeviceObject,
          InputBuffer,
          InputBufferLength,
          OutputBuffer,
          OutputBufferLength,
          0,
          &Event,
          &IoStatusBlock);
  if ( !v10 )
    return -1073741670;
  result = IofCallDriver(DeviceObject, v10);
  if ( result == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    return IoStatusBlock.Status;
  }
  return result;
}

```

## disassembly

```asm
0x140002db0  push    rbx
0x140002db2  push    rbp
0x140002db3  push    rsi
0x140002db4  push    rdi
0x140002db5  sub     rsp, 88h
0x140002dbc  xorps   xmm0, xmm0
0x140002dbf  mov     rdi, r8
0x140002dc2  mov     esi, edx
0x140002dc4  mov     rbp, rcx
0x140002dc7  xor     eax, eax
0x140002dc9  lea     rcx, [rsp+0A8h+Event]; Event
0x140002dce  xor     r8d, r8d; State
0x140002dd1  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x140002dd6  xor     edx, edx; Type
0x140002dd8  mov     ebx, r9d
0x140002ddb  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x140002de0  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140002de5  call    cs:__imp_KeInitializeEvent
0x140002dec  nop     dword ptr [rax+rax+00h]
0x140002df1  lea     rax, [rsp+0A8h+var_58]
0x140002df6  mov     r9d, ebx; InputBufferLength
0x140002df9  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x140002dfe  mov     r8, rdi; InputBuffer
0x140002e01  lea     rax, [rsp+0A8h+Event]
0x140002e06  mov     rdx, rbp; DeviceObject
0x140002e09  mov     [rsp+0A8h+var_70], rax; Event
0x140002e0e  mov     ecx, esi; IoControlCode
0x140002e10  mov     eax, [rsp+0A8h+arg_28]
0x140002e17  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140002e1c  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x140002e20  mov     rax, [rsp+0A8h+arg_20]
0x140002e28  mov     [rsp+0A8h+OutputBuffer], rax; OutputBuffer
0x140002e2d  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140002e34  nop     dword ptr [rax+rax+00h]
0x140002e39  test    rax, rax
0x140002e3c  jz      short loc_140002E64
0x140002e3e  mov     rdx, rax; Irp
0x140002e41  mov     rcx, rbp; DeviceObject
0x140002e44  call    cs:__imp_IofCallDriver
0x140002e4b  nop     dword ptr [rax+rax+00h]
0x140002e50  cmp     eax, 103h
0x140002e55  jz      short loc_140002E6B
0x140002e57  add     rsp, 88h
0x140002e5e  pop     rdi
0x140002e5f  pop     rsi
0x140002e60  pop     rbp
0x140002e61  pop     rbx
0x140002e62  retn
0x140002e64  mov     eax, 0C000009Ah
0x140002e69  jmp     short loc_140002E57
0x140002e6b  xor     r9d, r9d; Alertable
0x140002e6e  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x140002e77  xor     r8d, r8d; WaitMode
0x140002e7a  lea     rcx, [rsp+0A8h+Event]; Object
0x140002e7f  xor     edx, edx; WaitReason
0x140002e81  call    cs:__imp_KeWaitForSingleObject
0x140002e88  nop     dword ptr [rax+rax+00h]
0x140002e8d  mov     eax, dword ptr [rsp+0A8h+var_58]
0x140002e91  jmp     short loc_140002E57
```
