# HandlePdoDeviceUsageNotification

- ea: `0x1400259e4`
- end: `0x140025bc8`
- name: `HandlePdoDeviceUsageNotification`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x1400259e4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140025a7a`
- `ntoskrnl!KeInitializeEvent` at `0x140025a7a`
- `ntoskrnl!IofCompleteRequest` at `0x140025b7f`
- `ntoskrnl!IofCompleteRequest` at `0x140025b7f`
- `ntoskrnl!IoFreeIrp` at `0x140025b0a`
- `ntoskrnl!IoFreeIrp` at `0x140025b0a`
- `ntoskrnl!IoAllocateIrp` at `0x140025a3b`
- `ntoskrnl!IoAllocateIrp` at `0x140025a3b`
- `ntoskrnl!IofCallDriver` at `0x140025acc`
- `ntoskrnl!IofCallDriver` at `0x140025ba6`
- `ntoskrnl!IofCallDriver` at `0x140025acc`
- `ntoskrnl!IofCallDriver` at `0x140025ba6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025af7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140025af7`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140025b5b`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140025b5b`
- `ntoskrnl!IoGetAttachedDevice` at `0x140025a27`
- `ntoskrnl!IoGetAttachedDevice` at `0x140025a27`

## pseudocode

```c
__int64 __fastcall HandlePdoDeviceUsageNotification(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int Options; // ebp
  __int64 v6; // r15
  unsigned __int8 Lock; // r12
  PDEVICE_OBJECT AttachedDevice; // r13
  PIRP Irp; // rax
  IRP *v10; // r14
  int Status; // esi
  _IO_STACK_LOCATION *v12; // rax
  _IO_STACK_LOCATION *v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-68h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( (unsigned int)(Options - 1) > 3 )
  {
    ++a2->CurrentLocation;
    a2->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
    return (unsigned int)IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 232) + 32LL), a2);
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 224);
    Lock = CurrentStackLocation->Parameters.SetLock.Lock;
    AttachedDevice = IoGetAttachedDevice(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 232) + 32LL));
    Irp = IoAllocateIrp(AttachedDevice->StackSize, 0);
    v10 = Irp;
    if ( Irp )
    {
      Irp->IoStatus.Status = -1073741637;
      memset(&Event, 0, sizeof(Event));
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v12 = v10->Tail.Overlay.CurrentStackLocation;
      v12[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))USBD_SyncCompletionRoutine;
      v12[-1].Context = &Event;
      v12[-1].Control = -32;
      v13 = v10->Tail.Overlay.CurrentStackLocation;
      v13[-1].MajorFunction = CurrentStackLocation->MajorFunction;
      v13[-1].MinorFunction = CurrentStackLocation->MinorFunction;
      v13[-1].FileObject = CurrentStackLocation->FileObject;
      v13[-1].Parameters.SetLock.Lock = Lock;
      v13[-1].Parameters.Create.Options = Options;
      if ( IofCallDriver(AttachedDevice, v10) == 259 )
        KeWaitForSingleObject(&Event, Suspended, 0, 0, 0);
      Status = v10->IoStatus.Status;
      IoFreeIrp(v10);
      if ( Status >= 0 )
      {
        if ( Options <= 3 )
        {
          if ( Lock )
            _InterlockedIncrement((volatile signed __int32 *)(a1 + 400));
          else
            _InterlockedDecrement((volatile signed __int32 *)(a1 + 400));
          v14 = *(_DWORD *)(v6 + 48);
          if ( *(_DWORD *)(a1 + 400) )
            v15 = v14 & 0xFFFFDFFF;
          else
            v15 = v14 | 0x2000;
          *(_DWORD *)(v6 + 48) = v15;
        }
        if ( RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT") < 0 && Options == 4 )
          *(_BYTE *)(a1 + 404) = 1;
      }
    }
    else
    {
      Status = -1073741670;
    }
    a2->IoStatus.Status = Status;
    IofCompleteRequest(a2, 0);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400259e4  push    rbx
0x1400259e6  push    rbp
0x1400259e7  push    rsi
0x1400259e8  push    rdi
0x1400259e9  push    r12
0x1400259eb  push    r13
0x1400259ed  push    r14
0x1400259ef  push    r15
0x1400259f1  sub     rsp, 58h
0x1400259f5  mov     rsi, [rdx+0B8h]
0x1400259fc  mov     rdi, rdx
0x1400259ff  mov     rbx, rcx
0x140025a02  mov     ebp, [rsi+10h]
0x140025a05  lea     eax, [rbp-1]
0x140025a08  cmp     eax, 3
0x140025a0b  ja      loc_140025B8D
0x140025a11  mov     r15, [rcx+0E0h]
0x140025a18  mov     rcx, [rcx+0E8h]
0x140025a1f  mov     r12b, [rsi+8]
0x140025a23  mov     rcx, [rcx+20h]; DeviceObject
0x140025a27  call    cs:__imp_IoGetAttachedDevice
0x140025a2e  nop     dword ptr [rax+rax+00h]
0x140025a33  xor     edx, edx; ChargeQuota
0x140025a35  mov     r13, rax
0x140025a38  mov     cl, [rax+4Ch]; StackSize
0x140025a3b  call    cs:__imp_IoAllocateIrp
0x140025a42  nop     dword ptr [rax+rax+00h]
0x140025a47  mov     r14, rax
0x140025a4a  test    rax, rax
0x140025a4d  jnz     short loc_140025A59
0x140025a4f  mov     esi, 0C000009Ah
0x140025a54  jmp     loc_140025B77
0x140025a59  xorps   xmm0, xmm0
0x140025a5c  mov     dword ptr [r14+30h], 0C00000BBh
0x140025a64  xor     eax, eax
0x140025a66  lea     rcx, [rsp+98h+Event]; Event
0x140025a6b  xor     r8d, r8d; State
0x140025a6e  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140025a73  xor     edx, edx; Type
0x140025a75  movups  xmmword ptr [rsp+98h+Event.Header.___u0], xmm0
0x140025a7a  call    cs:__imp_KeInitializeEvent
0x140025a81  nop     dword ptr [rax+rax+00h]
0x140025a86  mov     rax, [r14+0B8h]
0x140025a8d  lea     rcx, USBD_SyncCompletionRoutine
0x140025a94  mov     rdx, r14; Irp
0x140025a97  mov     [rax-10h], rcx
0x140025a9b  lea     rcx, [rsp+98h+Event]
0x140025aa0  mov     [rax-8], rcx
0x140025aa4  mov     byte ptr [rax-45h], 0E0h
0x140025aa8  mov     al, [rsi]
0x140025aaa  mov     rcx, [r14+0B8h]
0x140025ab1  mov     [rcx-48h], al
0x140025ab4  mov     al, [rsi+1]
0x140025ab7  mov     [rcx-47h], al
0x140025aba  mov     rax, [rsi+30h]
0x140025abe  mov     [rcx-18h], rax
0x140025ac2  mov     [rcx-40h], r12b
0x140025ac6  mov     [rcx-38h], ebp
0x140025ac9  mov     rcx, r13; DeviceObject
0x140025acc  call    cs:__imp_IofCallDriver
0x140025ad3  nop     dword ptr [rax+rax+00h]
0x140025ad8  cmp     eax, 103h
0x140025add  jnz     short loc_140025B03
0x140025adf  xor     r9d, r9d; Alertable
0x140025ae2  mov     [rsp+98h+Timeout], 0; Timeout
0x140025aeb  xor     r8d, r8d; WaitMode
0x140025aee  lea     rcx, [rsp+98h+Event]; Object
0x140025af3  lea     edx, [r9+5]; WaitReason
0x140025af7  call    cs:__imp_KeWaitForSingleObject
0x140025afe  nop     dword ptr [rax+rax+00h]
0x140025b03  mov     esi, [r14+30h]
0x140025b07  mov     rcx, r14; Irp
0x140025b0a  call    cs:__imp_IoFreeIrp
0x140025b11  nop     dword ptr [rax+rax+00h]
0x140025b16  test    esi, esi
0x140025b18  js      short loc_140025B77
0x140025b1a  cmp     ebp, 3
0x140025b1d  jg      short loc_140025B4F
0x140025b1f  test    r12b, r12b
0x140025b22  jz      short loc_140025B2D
0x140025b24  lock inc dword ptr [rbx+190h]
0x140025b2b  jmp     short loc_140025B34
0x140025b2d  lock dec dword ptr [rbx+190h]
0x140025b34  cmp     dword ptr [rbx+190h], 0
0x140025b3b  mov     eax, [r15+30h]
0x140025b3f  jz      short loc_140025B47
0x140025b41  btr     eax, 0Dh
0x140025b45  jmp     short loc_140025B4B
0x140025b47  bts     eax, 0Dh
0x140025b4b  mov     [r15+30h], eax
0x140025b4f  lea     rdx, Path; "MiniNT"
0x140025b56  mov     ecx, 2; RelativeTo
0x140025b5b  call    cs:__imp_RtlCheckRegistryKey
0x140025b62  nop     dword ptr [rax+rax+00h]
0x140025b67  test    eax, eax
0x140025b69  jns     short loc_140025B77
0x140025b6b  cmp     ebp, 4
0x140025b6e  jnz     short loc_140025B77
0x140025b70  mov     byte ptr [rbx+194h], 1
0x140025b77  xor     edx, edx; PriorityBoost
0x140025b79  mov     [rdi+30h], esi
0x140025b7c  mov     rcx, rdi; Irp
0x140025b7f  call    cs:__imp_IofCompleteRequest
0x140025b86  nop     dword ptr [rax+rax+00h]
0x140025b8b  jmp     short loc_140025BB4
0x140025b8d  inc     byte ptr [rdx+43h]
0x140025b90  lea     rax, [rsi+48h]
0x140025b94  mov     [rdx+0B8h], rax
0x140025b9b  mov     rcx, [rcx+0E8h]
0x140025ba2  mov     rcx, [rcx+20h]; DeviceObject
0x140025ba6  call    cs:__imp_IofCallDriver
0x140025bad  nop     dword ptr [rax+rax+00h]
0x140025bb2  mov     esi, eax
0x140025bb4  mov     eax, esi
0x140025bb6  add     rsp, 58h
0x140025bba  pop     r15
0x140025bbc  pop     r14
0x140025bbe  pop     r13
0x140025bc0  pop     r12
0x140025bc2  pop     rdi
0x140025bc3  pop     rsi
0x140025bc4  pop     rbp
0x140025bc5  pop     rbx
0x140025bc6  retn
```
