# ParentQueryForInterface

- ea: `0x140022fe8`
- end: `0x14002320d`
- name: `ParentQueryForInterface`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x14000a6cc`
- `0x140014d50`
- `0x140022fe8`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400231e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400231e0`
- `ntoskrnl!KeInitializeEvent` at `0x140023089`
- `ntoskrnl!KeInitializeEvent` at `0x140023089`
- `ntoskrnl!IoFreeIrp` at `0x1400231cc`
- `ntoskrnl!IoFreeIrp` at `0x1400231cc`
- `ntoskrnl!ObfDereferenceObject` at `0x1400231ef`
- `ntoskrnl!ObfDereferenceObject` at `0x1400231ef`
- `ntoskrnl!IoAllocateIrp` at `0x14002305a`
- `ntoskrnl!IoAllocateIrp` at `0x14002305a`
- `ntoskrnl!IofCallDriver` at `0x1400230e5`
- `ntoskrnl!IofCallDriver` at `0x1400230e5`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14002303d`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14002303d`
- `ntoskrnl!ExAllocatePool2` at `0x14002301b`
- `ntoskrnl!ExAllocatePool2` at `0x14002301b`

## string_xrefs

- `0x140023101`: `event (waiting for query-interface to complete)`

## pseudocode

```c
__int64 __fastcall ParentQueryForInterface(__int64 a1)
{
  _OWORD *Pool2; // rbx
  PDEVICE_OBJECT AttachedDeviceReference; // r14
  PIRP Irp; // rax
  IRP *v6; // rbp
  NTSTATUS Status; // esi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v9; // rax
  int v10; // edx
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  Pool2 = (_OWORD *)ExAllocatePool2(256, 104, 1130525525);
  if ( !Pool2 )
    return 3221225626LL;
  AttachedDeviceReference = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)(a1 + 32));
  Irp = IoAllocateIrp(AttachedDeviceReference->StackSize + 1, 0);
  v6 = Irp;
  if ( Irp )
  {
    Irp->IoStatus.Status = -1073741637;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))USBD_SyncCompletionRoutine;
    CurrentStackLocation[-1].Context = &Event;
    CurrentStackLocation[-1].Control = -32;
    v9 = v6->Tail.Overlay.CurrentStackLocation;
    v9[-1].Parameters.WMI.ProviderId = (unsigned __int64)&USB_BUS_INTERFACE_USBC_CONFIGURATION_GUID;
    *(_WORD *)&v9[-1].MajorFunction = 2075;
    v9[-1].Parameters.Read.ByteOffset.QuadPart = (__int64)Pool2;
    v9[-1].Parameters.CreatePipe.Parameters = 0;
    v9[-1].Parameters.Create.Options = 65640;
    Status = IofCallDriver(AttachedDeviceReference, v6);
    if ( Status == 259 )
    {
      WaitForSignal(&Event, "event (waiting for query-interface to complete)", *(_QWORD *)(a1 + 1368));
      Status = v6->IoStatus.Status;
    }
    if ( Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1368),
          v10,
          8,
          73,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          Status);
      }
    }
    else if ( *((_WORD *)Pool2 + 1) == 1 && *(_WORD *)Pool2 >= 0x68u )
    {
      *(_OWORD *)(a1 + 1240) = *Pool2;
      *(_OWORD *)(a1 + 1256) = Pool2[1];
      *(_OWORD *)(a1 + 1272) = Pool2[2];
      *(_OWORD *)(a1 + 1288) = Pool2[3];
      *(_OWORD *)(a1 + 1304) = Pool2[4];
      *(_OWORD *)(a1 + 1320) = Pool2[5];
      *(_QWORD *)(a1 + 1336) = *((_QWORD *)Pool2 + 12);
      *(_DWORD *)(a1 + 1228) |= 2u;
    }
    else
    {
      Status = -1073741811;
      (*((void (__fastcall **)(_QWORD))Pool2 + 3))(*((_QWORD *)Pool2 + 1));
    }
    IoFreeIrp(v6);
  }
  else
  {
    Status = -1073741670;
  }
  ExFreePoolWithTag(Pool2, 0x43627355u);
  ObfDereferenceObject(AttachedDeviceReference);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140022fe8  push    rbx
0x140022fea  push    rbp
0x140022feb  push    rsi
0x140022fec  push    rdi
0x140022fed  push    r12
0x140022fef  push    r14
0x140022ff1  push    r15
0x140022ff3  sub     rsp, 50h
0x140022ff7  xor     eax, eax
0x140022ff9  mov     rdi, rcx
0x140022ffc  xorps   xmm0, xmm0
0x140022fff  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140023004  mov     r8d, 43627355h
0x14002300a  mov     ecx, 100h
0x14002300f  movups  xmmword ptr [rsp+88h+Event.Header.___u0], xmm0
0x140023014  lea     r15d, [rax+68h]
0x140023018  mov     edx, r15d
0x14002301b  call    cs:__imp_ExAllocatePool2
0x140023022  nop     dword ptr [rax+rax+00h]
0x140023027  mov     rbx, rax
0x14002302a  test    rax, rax
0x14002302d  jnz     short loc_140023039
0x14002302f  mov     eax, 0C000009Ah
0x140023034  jmp     loc_1400231FD
0x140023039  mov     rcx, [rdi+20h]; DeviceObject
0x14002303d  call    cs:__imp_IoGetAttachedDeviceReference
0x140023044  nop     dword ptr [rax+rax+00h]
0x140023049  mov     r12d, 1
0x14002304f  xor     edx, edx; ChargeQuota
0x140023051  mov     r14, rax
0x140023054  mov     cl, [rax+4Ch]
0x140023057  add     cl, r12b; StackSize
0x14002305a  call    cs:__imp_IoAllocateIrp
0x140023061  nop     dword ptr [rax+rax+00h]
0x140023066  mov     rbp, rax
0x140023069  test    rax, rax
0x14002306c  jnz     short loc_140023078
0x14002306e  mov     esi, 0C000009Ah
0x140023073  jmp     loc_1400231D8
0x140023078  xor     r8d, r8d; State
0x14002307b  mov     dword ptr [rax+30h], 0C00000BBh
0x140023082  xor     edx, edx; Type
0x140023084  lea     rcx, [rsp+88h+Event]; Event
0x140023089  call    cs:__imp_KeInitializeEvent
0x140023090  nop     dword ptr [rax+rax+00h]
0x140023095  mov     rax, [rbp+0B8h]
0x14002309c  lea     rcx, USBD_SyncCompletionRoutine
0x1400230a3  mov     rdx, rbp; Irp
0x1400230a6  mov     [rax-10h], rcx
0x1400230aa  lea     rcx, [rsp+88h+Event]
0x1400230af  mov     [rax-8], rcx
0x1400230b3  lea     rcx, USB_BUS_INTERFACE_USBC_CONFIGURATION_GUID
0x1400230ba  mov     byte ptr [rax-45h], 0E0h
0x1400230be  mov     rax, [rbp+0B8h]
0x1400230c5  mov     [rax-40h], rcx
0x1400230c9  mov     rcx, r14; DeviceObject
0x1400230cc  mov     word ptr [rax-48h], 81Bh
0x1400230d2  mov     [rax-30h], rbx
0x1400230d6  mov     qword ptr [rax-28h], 0
0x1400230de  mov     dword ptr [rax-38h], 10068h
0x1400230e5  call    cs:__imp_IofCallDriver
0x1400230ec  nop     dword ptr [rax+rax+00h]
0x1400230f1  mov     esi, eax
0x1400230f3  cmp     eax, 103h
0x1400230f8  jnz     short loc_140023115
0x1400230fa  mov     r8, [rdi+558h]
0x140023101  lea     rdx, aEventWaitingFo_0; "event (waiting for query-interface to c"...
0x140023108  lea     rcx, [rsp+88h+Event]; Object
0x14002310d  call    WaitForSignal
0x140023112  mov     esi, [rbp+30h]
0x140023115  test    esi, esi
0x140023117  js      short loc_140023191
0x140023119  cmp     [rbx+2], r12w
0x14002311e  jnz     short loc_14002317D
0x140023120  cmp     [rbx], r15w
0x140023124  jb      short loc_14002317D
0x140023126  movups  xmm0, xmmword ptr [rbx]
0x140023129  movups  xmmword ptr [rdi+4D8h], xmm0
0x140023130  movups  xmm1, xmmword ptr [rbx+10h]
0x140023134  movups  xmmword ptr [rdi+4E8h], xmm1
0x14002313b  movups  xmm0, xmmword ptr [rbx+20h]
0x14002313f  movups  xmmword ptr [rdi+4F8h], xmm0
0x140023146  movups  xmm1, xmmword ptr [rbx+30h]
0x14002314a  movups  xmmword ptr [rdi+508h], xmm1
0x140023151  movups  xmm0, xmmword ptr [rbx+40h]
0x140023155  movups  xmmword ptr [rdi+518h], xmm0
0x14002315c  movups  xmm1, xmmword ptr [rbx+50h]
0x140023160  movups  xmmword ptr [rdi+528h], xmm1
0x140023167  movsd   xmm0, qword ptr [rbx+60h]
0x14002316c  movsd   qword ptr [rdi+538h], xmm0
0x140023174  or      dword ptr [rdi+4CCh], 2
0x14002317b  jmp     short loc_1400231C9
0x14002317d  mov     rax, [rbx+18h]
0x140023181  mov     esi, 0C000000Dh
0x140023186  mov     rcx, [rbx+8]
0x14002318a  call    _guard_dispatch_icall
0x14002318f  jmp     short loc_1400231C9
0x140023191  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023198  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002319f  jz      short loc_1400231C9
0x1400231a1  mov     rcx, [rdi+558h]
0x1400231a8  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x1400231af  mov     r9d, 49h ; 'I'
0x1400231b5  mov     [rsp+88h+var_60], esi
0x1400231b9  mov     dl, 2
0x1400231bb  mov     [rsp+88h+var_68], rax
0x1400231c0  lea     r8d, [r9-41h]
0x1400231c4  call    WPP_RECORDER_SF_d
0x1400231c9  mov     rcx, rbp; Irp
0x1400231cc  call    cs:__imp_IoFreeIrp
0x1400231d3  nop     dword ptr [rax+rax+00h]
0x1400231d8  mov     edx, 43627355h; Tag
0x1400231dd  mov     rcx, rbx; P
0x1400231e0  call    cs:__imp_ExFreePoolWithTag
0x1400231e7  nop     dword ptr [rax+rax+00h]
0x1400231ec  mov     rcx, r14; Object
0x1400231ef  call    cs:__imp_ObfDereferenceObject
0x1400231f6  nop     dword ptr [rax+rax+00h]
0x1400231fb  mov     eax, esi
0x1400231fd  add     rsp, 50h
0x140023201  pop     r15
0x140023203  pop     r14
0x140023205  pop     r12
0x140023207  pop     rdi
0x140023208  pop     rsi
0x140023209  pop     rbp
0x14002320a  pop     rbx
0x14002320b  retn
```
