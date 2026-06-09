# VmbusSendInterfaceQuery

- ea: `0x14000a9bc`
- end: `0x14000ab4a`
- name: `VmbusSendInterfaceQuery`
- size: `398`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000afe8`
- `0x14000e4e0`
- `0x14001c758`

## callees

- `0x14000a9bc`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000ab31`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ab31`
- `ntoskrnl!KeInitializeEvent` at `0x14000aa02`
- `ntoskrnl!KeInitializeEvent` at `0x14000aa02`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000aae4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000aae4`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14000aa2e`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14000aa2e`
- `ntoskrnl!IofCallDriver` at `0x14000aab9`
- `ntoskrnl!IofCallDriver` at `0x14000aab9`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000a9e7`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000a9e7`

## pseudocode

```c
__int64 __fastcall VmbusSendInterfaceQuery(__int64 a1)
{
  struct _DEVICE_OBJECT *v2; // rcx
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rsi
  PIRP v4; // rax
  IRP *v5; // rdx
  NTSTATUS Status; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rcx
  void (__fastcall *v9)(_QWORD); // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  v2 = *(struct _DEVICE_OBJECT **)(a1 + 2720);
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  AttachedDeviceReference = IoGetAttachedDeviceReference(v2);
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v4 = IoBuildAsynchronousFsdRequest(0x1Bu, AttachedDeviceReference, 0, 0, 0, &IoStatusBlock);
  v5 = v4;
  if ( v4 )
  {
    CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmbusSendInterfaceQueryCompletionRoutine;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    v8 = v5->Tail.Overlay.CurrentStackLocation;
    v8[-1].Parameters.WMI.ProviderId = (ULONG_PTR)&GUID_VMBUS_INTERFACE_STANDARD;
    v8[-1].Parameters.Read.ByteOffset.QuadPart = a1 + 2360;
    v8[-1].MinorFunction = 8;
    v8[-1].Parameters.Create.Options = 852288;
    v8[-1].Parameters.CreatePipe.Parameters = *(PNAMED_PIPE_CREATE_PARAMETERS *)(a1 + 2728);
    v8[-1].FileObject = *(PFILE_OBJECT *)(a1 + 2728);
    v5->IoStatus.Status = -1073741637;
    Status = IofCallDriver(AttachedDeviceReference, v5);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
    {
      if ( *(_WORD *)(a1 + 2362) == 13 )
      {
        Status = 0;
      }
      else
      {
        v9 = *(void (__fastcall **)(_QWORD))(a1 + 2384);
        if ( v9 )
        {
          v9(*(_QWORD *)(a1 + 2368));
          *(_QWORD *)(a1 + 2384) = 0;
        }
        Status = -1073741735;
      }
    }
  }
  else
  {
    Status = -1073741670;
  }
  ObfDereferenceObject(AttachedDeviceReference);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000a9bc  push    rbx
0x14000a9be  push    rsi
0x14000a9bf  push    rdi
0x14000a9c0  push    r14
0x14000a9c2  sub     rsp, 68h
0x14000a9c6  mov     rdi, rcx
0x14000a9c9  xorps   xmm0, xmm0
0x14000a9cc  mov     rcx, [rcx+0AA0h]; DeviceObject
0x14000a9d3  xorps   xmm1, xmm1
0x14000a9d6  xor     eax, eax
0x14000a9d8  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x14000a9dd  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000a9e2  movups  xmmword ptr [rsp+88h+Event.Header], xmm1
0x14000a9e7  call    cs:__imp_IoGetAttachedDeviceReference
0x14000a9ee  nop     dword ptr [rax+rax+00h]
0x14000a9f3  xor     r8d, r8d; State
0x14000a9f6  lea     rcx, [rsp+88h+Event]; Event
0x14000a9fb  mov     rsi, rax
0x14000a9fe  lea     edx, [r8+1]; Type
0x14000aa02  call    cs:__imp_KeInitializeEvent
0x14000aa09  nop     dword ptr [rax+rax+00h]
0x14000aa0e  xor     r9d, r9d; Length
0x14000aa11  lea     rax, [rsp+88h+var_58]
0x14000aa16  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x14000aa1b  xor     r8d, r8d; Buffer
0x14000aa1e  mov     rdx, rsi; DeviceObject
0x14000aa21  mov     [rsp+88h+StartingOffset], 0; StartingOffset
0x14000aa2a  lea     ecx, [r9+1Bh]; MajorFunction
0x14000aa2e  call    cs:__imp_IoBuildAsynchronousFsdRequest
0x14000aa35  nop     dword ptr [rax+rax+00h]
0x14000aa3a  mov     rdx, rax; Irp
0x14000aa3d  test    rax, rax
0x14000aa40  jnz     short loc_14000AA4C
0x14000aa42  mov     ebx, 0C000009Ah
0x14000aa47  jmp     loc_14000AB2E
0x14000aa4c  mov     rax, [rax+0B8h]
0x14000aa53  lea     rcx, VmbusSendInterfaceQueryCompletionRoutine
0x14000aa5a  mov     r14d, 0Dh
0x14000aa60  mov     [rax-10h], rcx
0x14000aa64  lea     rcx, [rsp+88h+Event]
0x14000aa69  mov     [rax-8], rcx
0x14000aa6d  mov     byte ptr [rax-45h], 0E0h
0x14000aa71  lea     rax, GUID_VMBUS_INTERFACE_STANDARD
0x14000aa78  mov     rcx, [rdx+0B8h]
0x14000aa7f  mov     [rcx-40h], rax
0x14000aa83  lea     rax, [rdi+938h]
0x14000aa8a  mov     [rcx-30h], rax
0x14000aa8e  mov     byte ptr [rcx-47h], 8
0x14000aa92  mov     dword ptr [rcx-38h], 0D0140h
0x14000aa99  mov     rax, [rdi+0AA8h]
0x14000aaa0  mov     [rcx-28h], rax
0x14000aaa4  mov     rax, [rdi+0AA8h]
0x14000aaab  mov     [rcx-18h], rax
0x14000aaaf  mov     rcx, rsi; DeviceObject
0x14000aab2  mov     dword ptr [rdx+30h], 0C00000BBh
0x14000aab9  call    cs:__imp_IofCallDriver
0x14000aac0  nop     dword ptr [rax+rax+00h]
0x14000aac5  mov     ebx, eax
0x14000aac7  cmp     eax, 103h
0x14000aacc  jnz     short loc_14000AAF4
0x14000aace  xor     r9d, r9d; Alertable
0x14000aad1  mov     [rsp+88h+StartingOffset], 0; Timeout
0x14000aada  xor     r8d, r8d; WaitMode
0x14000aadd  lea     rcx, [rsp+88h+Event]; Object
0x14000aae2  xor     edx, edx; WaitReason
0x14000aae4  call    cs:__imp_KeWaitForSingleObject
0x14000aaeb  nop     dword ptr [rax+rax+00h]
0x14000aaf0  mov     ebx, dword ptr [rsp+88h+var_58]
0x14000aaf4  test    ebx, ebx
0x14000aaf6  js      short loc_14000AB2E
0x14000aaf8  cmp     [rdi+93Ah], r14w
0x14000ab00  jz      short loc_14000AB2C
0x14000ab02  mov     rax, [rdi+950h]
0x14000ab09  test    rax, rax
0x14000ab0c  jz      short loc_14000AB25
0x14000ab0e  mov     rcx, [rdi+940h]
0x14000ab15  call    _guard_dispatch_icall
0x14000ab1a  mov     qword ptr [rdi+950h], 0
0x14000ab25  mov     ebx, 0C0000059h
0x14000ab2a  jmp     short loc_14000AB2E
0x14000ab2c  xor     ebx, ebx
0x14000ab2e  mov     rcx, rsi; Object
0x14000ab31  call    cs:__imp_ObfDereferenceObject
0x14000ab38  nop     dword ptr [rax+rax+00h]
0x14000ab3d  mov     eax, ebx
0x14000ab3f  add     rsp, 68h
0x14000ab43  pop     r14
0x14000ab45  pop     rdi
0x14000ab46  pop     rsi
0x14000ab47  pop     rbx
0x14000ab48  retn
```
