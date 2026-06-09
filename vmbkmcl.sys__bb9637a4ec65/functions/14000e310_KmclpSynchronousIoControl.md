# KmclpSynchronousIoControl

- ea: `0x14000e310`
- end: `0x14000e40c`
- name: `KmclpSynchronousIoControl`
- size: `252`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b3d8`
- `0x14000e4e0`
- `0x14001c758`

## callees

- `0x14000e310`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000e346`
- `ntoskrnl!KeInitializeEvent` at `0x14000e346`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e3ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e3ef`
- `ntoskrnl!IofCallDriver` at `0x14000e3c6`
- `ntoskrnl!IofCallDriver` at `0x14000e3c6`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000e392`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000e392`

## pseudocode

```c
NTSTATUS __fastcall KmclpSynchronousIoControl(
        __int64 a1,
        ULONG a2,
        void *a3,
        ULONG a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  PIRP v10; // rax
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v10 = IoBuildDeviceIoControlRequest(
          a2,
          *(PDEVICE_OBJECT *)(a1 + 2720),
          a3,
          a4,
          OutputBuffer,
          OutputBufferLength,
          0,
          &Event,
          &IoStatusBlock);
  if ( !v10 )
    return -1073741670;
  v10->Tail.Overlay.CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(a1 + 2728);
  result = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 2720), v10);
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
0x14000e310  push    rbx
0x14000e312  push    rbp
0x14000e313  push    rsi
0x14000e314  push    rdi
0x14000e315  sub     rsp, 88h
0x14000e31c  xor     eax, eax
0x14000e31e  xorps   xmm0, xmm0
0x14000e321  mov     rdi, r8
0x14000e324  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14000e329  mov     esi, edx
0x14000e32b  mov     rbp, rcx
0x14000e32e  xor     r8d, r8d; State
0x14000e331  lea     rcx, [rsp+0A8h+Event]; Event
0x14000e336  lea     edx, [rax+1]; Type
0x14000e339  mov     ebx, r9d
0x14000e33c  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14000e341  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x14000e346  call    cs:__imp_KeInitializeEvent
0x14000e34d  nop     dword ptr [rax+rax+00h]
0x14000e352  mov     rdx, [rbp+0AA0h]; DeviceObject
0x14000e359  lea     rax, [rsp+0A8h+var_58]
0x14000e35e  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x14000e363  mov     r9d, ebx; InputBufferLength
0x14000e366  lea     rax, [rsp+0A8h+Event]
0x14000e36b  mov     r8, rdi; InputBuffer
0x14000e36e  mov     [rsp+0A8h+var_70], rax; Event
0x14000e373  mov     ecx, esi; IoControlCode
0x14000e375  mov     eax, [rsp+0A8h+arg_28]
0x14000e37c  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14000e381  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x14000e385  mov     rax, [rsp+0A8h+arg_20]
0x14000e38d  mov     [rsp+0A8h+OutputBuffer], rax; OutputBuffer
0x14000e392  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000e399  nop     dword ptr [rax+rax+00h]
0x14000e39e  mov     rdx, rax; Irp
0x14000e3a1  test    rax, rax
0x14000e3a4  jnz     short loc_14000E3AD
0x14000e3a6  mov     eax, 0C000009Ah
0x14000e3ab  jmp     short loc_14000E3FF
0x14000e3ad  mov     rcx, [rax+0B8h]
0x14000e3b4  mov     rax, [rbp+0AA8h]
0x14000e3bb  mov     [rcx-18h], rax
0x14000e3bf  mov     rcx, [rbp+0AA0h]; DeviceObject
0x14000e3c6  call    cs:__imp_IofCallDriver
0x14000e3cd  nop     dword ptr [rax+rax+00h]
0x14000e3d2  cmp     eax, 103h
0x14000e3d7  jnz     short loc_14000E3FF
0x14000e3d9  xor     r9d, r9d; Alertable
0x14000e3dc  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x14000e3e5  xor     r8d, r8d; WaitMode
0x14000e3e8  lea     rcx, [rsp+0A8h+Event]; Object
0x14000e3ed  xor     edx, edx; WaitReason
0x14000e3ef  call    cs:__imp_KeWaitForSingleObject
0x14000e3f6  nop     dword ptr [rax+rax+00h]
0x14000e3fb  mov     eax, dword ptr [rsp+0A8h+var_58]
0x14000e3ff  add     rsp, 88h
0x14000e406  pop     rdi
0x14000e407  pop     rsi
0x14000e408  pop     rbp
0x14000e409  pop     rbx
0x14000e40a  retn
```
