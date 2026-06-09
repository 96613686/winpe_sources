# SendIoctlToBus

- ea: `0x1400053c8`
- end: `0x140005628`
- name: `SendIoctlToBus`
- size: `608`
- prototype: `__int64 __fastcall(PUNICODE_STRING ObjectName, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID, ULONG)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1400033f0`
- `0x140004c50`
- `0x140005108`
- `0x14000df0c`

## callees

- `0x1400053c8`
- `0x14000d8ec`
- `0x14000d91c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400054c0`
- `ntoskrnl!IofCallDriver` at `0x1400054c0`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400054a4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400054a4`
- `ntoskrnl!KeInitializeEvent` at `0x140005465`
- `ntoskrnl!KeInitializeEvent` at `0x140005465`
- `ntoskrnl!ObfReferenceObject` at `0x14000544f`
- `ntoskrnl!ObfReferenceObject` at `0x14000544f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140005435`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140005435`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000559d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000559d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400054e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400054f7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400054e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400054f7`

## pseudocode

```c
__int64 __fastcall SendIoctlToBus(
        PUNICODE_STRING ObjectName,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  NTSTATUS DeviceObjectPointer; // eax
  unsigned int Status; // ebx
  IRP *v12; // rax
  PDEVICE_OBJECT v14; // rcx
  unsigned __int16 v15; // dx
  NTSTATUS v16; // r9d
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-29h] BYREF
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-19h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-9h] BYREF

  IoStatusBlock = 0;
  FileObject = 0;
  memset(&Event, 0, sizeof(Event));
  DeviceObject = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x14u,
      (__int64)WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  DeviceObjectPointer = IoGetDeviceObjectPointer(ObjectName, 0x1F01FFu, &FileObject, &DeviceObject);
  Status = DeviceObjectPointer;
  if ( DeviceObjectPointer )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v15 = 21;
      v16 = DeviceObjectPointer;
LABEL_23:
      WPP_SF_d((__int64)v14->AttachedDevice, v15, (__int64)WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids, v16);
    }
  }
  else
  {
    ObfReferenceObject(DeviceObject);
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    v12 = IoBuildDeviceIoControlRequest(
            IoControlCode,
            DeviceObject,
            InputBuffer,
            InputBufferLength,
            OutputBuffer,
            OutputBufferLength,
            0,
            &Event,
            &IoStatusBlock);
    if ( v12 )
    {
      Status = IofCallDriver(DeviceObject, v12);
      if ( Status == 259 )
      {
        Status = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( !Status )
        {
          Status = IoStatusBlock.Status;
          if ( IoStatusBlock.Status )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v15 = 23;
              v16 = IoStatusBlock.Status;
              goto LABEL_23;
            }
          }
        }
      }
    }
    else
    {
      Status = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x16u,
          (__int64)WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
    }
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( DeviceObject )
    ObfDereferenceObject(DeviceObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x18u,
      (__int64)WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids,
      Status);
  return Status;
}

```

## disassembly

```asm
0x1400053c8  push    rbp
0x1400053ca  push    rbx
0x1400053cb  push    rsi
0x1400053cc  push    rdi
0x1400053cd  push    r12
0x1400053cf  push    r13
0x1400053d1  push    r14
0x1400053d3  lea     rbp, [rsp-17h]
0x1400053d8  sub     rsp, 90h
0x1400053df  xor     eax, eax
0x1400053e1  xorps   xmm0, xmm0
0x1400053e4  xorps   xmm1, xmm1
0x1400053e7  mov     [rbp+47h+Event.Header.WaitListHead.Blink], rax
0x1400053eb  movups  xmmword ptr [rbp+47h+var_60], xmm0
0x1400053ef  mov     [rbp+47h+FileObject], rax
0x1400053f3  mov     edi, r9d
0x1400053f6  movups  xmmword ptr [rbp+47h+Event.Header], xmm1
0x1400053fa  mov     [rbp+47h+DeviceObject], rax
0x1400053fe  mov     rsi, r8
0x140005401  mov     r14d, edx
0x140005404  mov     rbx, rcx
0x140005407  mov     rcx, cs:WPP_GLOBAL_Control
0x14000540e  lea     r12, WPP_GLOBAL_Control
0x140005415  lea     r13, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x14000541c  cmp     rcx, r12
0x14000541f  jnz     loc_140005524
0x140005425  lea     r9, [rbp+47h+DeviceObject]; DeviceObject
0x140005429  mov     edx, 1F01FFh; DesiredAccess
0x14000542e  lea     r8, [rbp+47h+FileObject]; FileObject
0x140005432  mov     rcx, rbx; ObjectName
0x140005435  call    cs:__imp_IoGetDeviceObjectPointer
0x14000543c  nop     dword ptr [rax+rax+00h]
0x140005441  mov     ebx, eax
0x140005443  test    eax, eax
0x140005445  jnz     loc_140005562
0x14000544b  mov     rcx, [rbp+47h+DeviceObject]; Object
0x14000544f  call    cs:__imp_ObfReferenceObject
0x140005456  nop     dword ptr [rax+rax+00h]
0x14000545b  xor     r8d, r8d; State
0x14000545e  lea     edx, [rbx+1]; Type
0x140005461  lea     rcx, [rbp+47h+Event]; Event
0x140005465  call    cs:__imp_KeInitializeEvent
0x14000546c  nop     dword ptr [rax+rax+00h]
0x140005471  mov     rdx, [rbp+47h+DeviceObject]; DeviceObject
0x140005475  lea     rax, [rbp+47h+var_60]
0x140005479  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14000547e  mov     r9d, edi; InputBufferLength
0x140005481  lea     rax, [rbp+47h+Event]
0x140005485  mov     r8, rsi; InputBuffer
0x140005488  mov     [rsp+0C0h+var_88], rax; Event
0x14000548d  mov     ecx, r14d; IoControlCode
0x140005490  mov     eax, [rbp+47h+arg_28]
0x140005493  mov     [rsp+0C0h+InternalDeviceIoControl], bl; InternalDeviceIoControl
0x140005497  mov     [rsp+0C0h+OutputBufferLength], eax; OutputBufferLength
0x14000549b  mov     rax, [rbp+47h+arg_20]
0x14000549f  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x1400054a4  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400054ab  nop     dword ptr [rax+rax+00h]
0x1400054b0  test    rax, rax
0x1400054b3  jz      loc_1400055F2
0x1400054b9  mov     rcx, [rbp+47h+DeviceObject]; DeviceObject
0x1400054bd  mov     rdx, rax; Irp
0x1400054c0  call    cs:__imp_IofCallDriver
0x1400054c7  nop     dword ptr [rax+rax+00h]
0x1400054cc  mov     ebx, eax
0x1400054ce  cmp     eax, 103h
0x1400054d3  jz      loc_140005588
0x1400054d9  mov     rcx, [rbp+47h+FileObject]; Object
0x1400054dd  test    rcx, rcx
0x1400054e0  jz      short loc_1400054EE
0x1400054e2  call    cs:__imp_ObfDereferenceObject
0x1400054e9  nop     dword ptr [rax+rax+00h]
0x1400054ee  mov     rcx, [rbp+47h+DeviceObject]; Object
0x1400054f2  test    rcx, rcx
0x1400054f5  jz      short loc_140005503
0x1400054f7  call    cs:__imp_ObfDereferenceObject
0x1400054fe  nop     dword ptr [rax+rax+00h]
0x140005503  mov     rcx, cs:WPP_GLOBAL_Control
0x14000550a  cmp     rcx, r12
0x14000550d  jnz     short loc_140005545
0x14000550f  mov     eax, ebx
0x140005511  add     rsp, 90h
0x140005518  pop     r14
0x14000551a  pop     r13
0x14000551c  pop     r12
0x14000551e  pop     rdi
0x14000551f  pop     rsi
0x140005520  pop     rbx
0x140005521  pop     rbp
0x140005522  retn
0x140005524  mov     eax, [rcx+2Ch]
0x140005527  test    al, 20h
0x140005529  jz      loc_140005425
0x14000552f  mov     rcx, [rcx+18h]
0x140005533  mov     edx, 14h
0x140005538  mov     r8, r13
0x14000553b  call    WPP_SF_
0x140005540  jmp     loc_140005425
0x140005545  mov     eax, [rcx+2Ch]
0x140005548  test    al, 20h
0x14000554a  jz      short loc_14000550F
0x14000554c  mov     rcx, [rcx+18h]
0x140005550  mov     edx, 18h
0x140005555  mov     r9d, ebx
0x140005558  mov     r8, r13
0x14000555b  call    WPP_SF_d
0x140005560  jmp     short loc_14000550F
0x140005562  mov     rcx, cs:WPP_GLOBAL_Control
0x140005569  cmp     rcx, r12
0x14000556c  jz      loc_1400054D9
0x140005572  mov     edx, [rcx+2Ch]
0x140005575  test    dl, 1
0x140005578  jz      loc_1400054D9
0x14000557e  mov     edx, 15h
0x140005583  mov     r9d, eax
0x140005586  jmp     short loc_1400055E1
0x140005588  xor     r9d, r9d; Alertable
0x14000558b  mov     [rsp+0C0h+OutputBuffer], 0; Timeout
0x140005594  xor     r8d, r8d; WaitMode
0x140005597  lea     rcx, [rbp+47h+Event]; Object
0x14000559b  xor     edx, edx; WaitReason
0x14000559d  call    cs:__imp_KeWaitForSingleObject
0x1400055a4  nop     dword ptr [rax+rax+00h]
0x1400055a9  mov     ebx, eax
0x1400055ab  test    eax, eax
0x1400055ad  jnz     loc_1400054D9
0x1400055b3  mov     ebx, dword ptr [rbp+47h+var_60]
0x1400055b6  test    ebx, ebx
0x1400055b8  jz      loc_1400054D9
0x1400055be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055c5  cmp     rcx, r12
0x1400055c8  jz      loc_1400054D9
0x1400055ce  mov     eax, [rcx+2Ch]
0x1400055d1  test    al, 1
0x1400055d3  jz      loc_1400054D9
0x1400055d9  mov     edx, 17h
0x1400055de  mov     r9d, ebx
0x1400055e1  mov     rcx, [rcx+18h]
0x1400055e5  mov     r8, r13
0x1400055e8  call    WPP_SF_d
0x1400055ed  jmp     loc_1400054D9
0x1400055f2  mov     ebx, 0C000009Ah
0x1400055f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055fe  cmp     rcx, r12
0x140005601  jz      loc_1400054D9
0x140005607  mov     eax, [rcx+2Ch]
0x14000560a  test    al, 1
0x14000560c  jz      loc_1400054D9
0x140005612  mov     rcx, [rcx+18h]
0x140005616  mov     edx, 16h
0x14000561b  mov     r8, r13
0x14000561e  call    WPP_SF_
0x140005623  jmp     loc_1400054D9
```
