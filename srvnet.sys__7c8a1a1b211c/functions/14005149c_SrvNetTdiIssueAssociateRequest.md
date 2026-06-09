# SrvNetTdiIssueAssociateRequest

- ea: `0x14005149c`
- end: `0x140051707`
- name: `SrvNetTdiIssueAssociateRequest`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400511f0`

## callees

- `0x140015790`
- `0x140016cc8`
- `0x14005149c`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140051666`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140051666`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140051649`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140051649`
- `ntoskrnl!IoAllocateIrp` at `0x140051528`
- `ntoskrnl!IoAllocateIrp` at `0x140051528`
- `ntoskrnl!IoQueueThreadIrp` at `0x1400515c3`
- `ntoskrnl!IoQueueThreadIrp` at `0x1400515c3`
- `ntoskrnl!KeClearEvent` at `0x14005150b`
- `ntoskrnl!KeClearEvent` at `0x14005150b`
- `ntoskrnl!ObfReferenceObject` at `0x1400514f4`
- `ntoskrnl!ObfReferenceObject` at `0x1400514f4`
- `ntoskrnl!IofCallDriver` at `0x1400515d5`
- `ntoskrnl!IofCallDriver` at `0x1400515d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140051620`
- `ntoskrnl!KeWaitForSingleObject` at `0x140051620`
- `ntoskrnl!KeInitializeEvent` at `0x1400514d1`
- `ntoskrnl!KeInitializeEvent` at `0x1400514d1`

## pseudocode

```c
__int64 __fastcall SrvNetTdiIssueAssociateRequest(void *a1, PDEVICE_OBJECT *a2, ULONG_PTR a3)
{
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  PIRP Irp; // rax
  IRP *v7; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v9; // rax
  struct _DEVICE_OBJECT *v10; // rbx
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  __int128 v14; // [rsp+30h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+40h] [rbp-28h] BYREF
  PVOID Object; // [rsp+A0h] [rbp+38h] BYREF

  Object = a1;
  memset(&Event, 0, sizeof(Event));
  v14 = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  if ( Object )
  {
    ObfReferenceObject(Object);
  }
  else
  {
    *a2 = 0;
    if ( ObReferenceObjectByHandle(0, 0, 0, 0, &Object, 0) < 0 )
      goto LABEL_21;
  }
  KeClearEvent((PRKEVENT)((char *)Object + 152));
  RelatedDeviceObject = *a2;
  if ( !*a2 )
  {
    RelatedDeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)Object);
    *a2 = RelatedDeviceObject;
  }
  Irp = IoAllocateIrp(RelatedDeviceObject->StackSize, 0);
  v7 = Irp;
  if ( Irp )
  {
    Irp->MdlAddress = 0;
    Irp->Flags = 4;
    *(_WORD *)&Irp->RequestorMode = 0;
    Irp->UserIosb = (PIO_STATUS_BLOCK)&v14;
    Irp->UserEvent = &Event;
    Irp->Overlay.AllocationSize.QuadPart = 0;
    Irp->AssociatedIrp.MasterIrp = 0;
    Irp->UserBuffer = 0;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    Irp->Tail.Overlay.Thread = KeGetCurrentThread();
    Irp->Tail.Overlay.OriginalFileObject = (PFILE_OBJECT)Object;
    Irp->Tail.Overlay.AuxiliaryBuffer = 0;
    Irp->IoStatus.Status = 0;
    Irp->IoStatus.Information = 0;
    CurrentStackLocation[-1].FileObject = (PFILE_OBJECT)Object;
    CurrentStackLocation[-1].DeviceObject = *a2;
    v9 = Irp->Tail.Overlay.CurrentStackLocation;
    *(_WORD *)&v9[-1].MajorFunction = 271;
    v9[-1].Parameters.WMI.ProviderId = a3;
    v10 = *a2;
    IoQueueThreadIrp(v7);
    v11 = IofCallDriver(v10, v7);
    v12 = v11;
    if ( v11 == 259 )
    {
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
    }
    else if ( v11 < 0 )
    {
      goto LABEL_17;
    }
    v12 = v14;
    if ( (int)v14 >= 0 )
      return v12;
LABEL_17:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f4edf8bb09033153e0e3095b0e0d8d4b_Traceguids, v7, v12);
    }
    return v12;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f4edf8bb09033153e0e3095b0e0d8d4b_Traceguids);
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids);
  }
  return 3221225989LL;
}

```

## disassembly

```asm
0x14005149c  push    rbp
0x14005149e  push    rbx
0x14005149f  push    rsi
0x1400514a0  push    rdi
0x1400514a1  push    r14
0x1400514a3  push    r15
0x1400514a5  mov     rbp, rsp
0x1400514a8  sub     rsp, 68h
0x1400514ac  xor     eax, eax
0x1400514ae  mov     [rbp+Object], rcx
0x1400514b2  xorps   xmm0, xmm0
0x1400514b5  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x1400514b9  mov     r14, r8
0x1400514bc  lea     rcx, [rbp+Event]; Event
0x1400514c0  mov     rbx, rdx
0x1400514c3  xor     r8d, r8d; State
0x1400514c6  lea     edx, [rax+1]; Type
0x1400514c9  movups  xmmword ptr [rbp+Event.Header], xmm0
0x1400514cd  movups  [rbp+var_38], xmm0
0x1400514d1  call    cs:__imp_KeInitializeEvent
0x1400514d8  nop     dword ptr [rax+rax+00h]
0x1400514dd  mov     rcx, [rbp+Object]; Object
0x1400514e1  lea     rsi, WPP_GLOBAL_Control
0x1400514e8  xor     r15d, r15d
0x1400514eb  test    rcx, rcx
0x1400514ee  jz      loc_14005162E
0x1400514f4  call    cs:__imp_ObfReferenceObject
0x1400514fb  nop     dword ptr [rax+rax+00h]
0x140051500  mov     rcx, [rbp+Object]
0x140051504  add     rcx, 98h; Event
0x14005150b  call    cs:__imp_KeClearEvent
0x140051512  nop     dword ptr [rax+rax+00h]
0x140051517  mov     rax, [rbx]
0x14005151a  test    rax, rax
0x14005151d  jz      loc_140051662
0x140051523  mov     cl, [rax+4Ch]; StackSize
0x140051526  xor     edx, edx; ChargeQuota
0x140051528  call    cs:__imp_IoAllocateIrp
0x14005152f  nop     dword ptr [rax+rax+00h]
0x140051534  mov     rdi, rax
0x140051537  test    rax, rax
0x14005153a  jz      loc_14005167A
0x140051540  mov     [rax+8], r15
0x140051544  mov     dword ptr [rax+10h], 4
0x14005154b  mov     [rax+40h], r15w
0x140051550  lea     rax, [rbp+var_38]
0x140051554  mov     [rdi+48h], rax
0x140051558  lea     rax, [rbp+Event]
0x14005155c  mov     [rdi+50h], rax
0x140051560  mov     [rdi+58h], r15
0x140051564  mov     [rdi+18h], r15
0x140051568  mov     [rdi+70h], r15
0x14005156c  mov     rax, gs:188h
0x140051575  mov     rcx, [rdi+0B8h]
0x14005157c  mov     [rdi+98h], rax
0x140051583  mov     rax, [rbp+Object]
0x140051587  mov     [rdi+0C0h], rax
0x14005158e  mov     [rdi+0A0h], r15
0x140051595  mov     [rdi+30h], r15d
0x140051599  mov     [rdi+38h], r15
0x14005159d  mov     rax, [rbp+Object]
0x1400515a1  mov     [rcx-18h], rax
0x1400515a5  mov     rax, [rbx]
0x1400515a8  mov     [rcx-20h], rax
0x1400515ac  mov     rcx, rdi; Irp
0x1400515af  mov     rax, [rdi+0B8h]
0x1400515b6  mov     word ptr [rax-48h], 10Fh
0x1400515bc  mov     [rax-40h], r14
0x1400515c0  mov     rbx, [rbx]
0x1400515c3  call    cs:__imp_IoQueueThreadIrp
0x1400515ca  nop     dword ptr [rax+rax+00h]
0x1400515cf  mov     rdx, rdi; Irp
0x1400515d2  mov     rcx, rbx; DeviceObject
0x1400515d5  call    cs:__imp_IofCallDriver
0x1400515dc  nop     dword ptr [rax+rax+00h]
0x1400515e1  mov     ebx, eax
0x1400515e3  cmp     eax, 103h
0x1400515e8  jz      short loc_14005160D
0x1400515ea  test    eax, eax
0x1400515ec  js      loc_1400516BA
0x1400515f2  mov     ebx, dword ptr [rbp+var_38]
0x1400515f5  test    ebx, ebx
0x1400515f7  js      loc_1400516BA
0x1400515fd  mov     eax, ebx
0x1400515ff  add     rsp, 68h
0x140051603  pop     r15
0x140051605  pop     r14
0x140051607  pop     rdi
0x140051608  pop     rsi
0x140051609  pop     rbx
0x14005160a  pop     rbp
0x14005160b  retn
0x14005160d  xor     r9d, r9d; Alertable
0x140051610  mov     [rsp+68h+Timeout], r15; Timeout
0x140051615  xor     r8d, r8d; WaitMode
0x140051618  lea     rcx, [rbp+Event]; Object
0x14005161c  lea     edx, [r9+6]; WaitReason
0x140051620  call    cs:__imp_KeWaitForSingleObject
0x140051627  nop     dword ptr [rax+rax+00h]
0x14005162c  jmp     short loc_1400515F2
0x14005162e  lea     rax, [rbp+Object]
0x140051632  mov     [rsp+68h+HandleInformation], r15; HandleInformation
0x140051637  xor     r9d, r9d; AccessMode
0x14005163a  mov     [rsp+68h+Timeout], rax; Object
0x14005163f  xor     r8d, r8d; ObjectType
0x140051642  mov     [rbx], r15
0x140051645  xor     edx, edx; DesiredAccess
0x140051647  xor     ecx, ecx; Handle
0x140051649  call    cs:__imp_ObReferenceObjectByHandle
0x140051650  nop     dword ptr [rax+rax+00h]
0x140051655  test    eax, eax
0x140051657  js      loc_14005770E
0x14005165d  jmp     loc_140051500
0x140051662  mov     rcx, [rbp+Object]; FileObject
0x140051666  call    cs:__imp_IoGetRelatedDeviceObject
0x14005166d  nop     dword ptr [rax+rax+00h]
0x140051672  mov     [rbx], rax
0x140051675  jmp     loc_140051523
0x14005167a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051681  cmp     rcx, rsi
0x140051684  jz      loc_14005770E
0x14005168a  mov     eax, [rcx+2Ch]
0x14005168d  test    al, 10h
0x14005168f  jz      loc_14005770E
0x140051695  cmp     byte ptr [rcx+29h], 1
0x140051699  jb      loc_14005770E
0x14005169f  mov     rcx, [rcx+18h]
0x1400516a3  lea     r8, WPP_f4edf8bb09033153e0e3095b0e0d8d4b_Traceguids
0x1400516aa  mov     edx, 0Ah
0x1400516af  call    WPP_SF_
0x1400516b4  nop
0x1400516b5  jmp     loc_14005770E
0x1400516ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400516c1  lea     rsi, WPP_GLOBAL_Control
0x1400516c8  cmp     rcx, rsi
0x1400516cb  jz      loc_1400515FD
0x1400516d1  mov     eax, [rcx+2Ch]
0x1400516d4  test    al, 10h
0x1400516d6  jz      loc_1400515FD
0x1400516dc  cmp     byte ptr [rcx+29h], 1
0x1400516e0  jb      loc_1400515FD
0x1400516e6  mov     rcx, [rcx+18h]
0x1400516ea  lea     r8, WPP_f4edf8bb09033153e0e3095b0e0d8d4b_Traceguids
0x1400516f1  mov     edx, 0Bh
0x1400516f6  mov     dword ptr [rsp+68h+Timeout], ebx
0x1400516fa  mov     r9, rdi
0x1400516fd  call    WPP_SF_qD
0x140051702  jmp     loc_1400515FD
0x14005770e  mov     rcx, cs:WPP_GLOBAL_Control
0x140057715  cmp     rcx, rsi
0x140057718  jz      short loc_14005773E
0x14005771a  test    dword ptr [rcx+2Ch], 400h
0x140057721  jz      short loc_14005773E
0x140057723  cmp     byte ptr [rcx+29h], 1
0x140057727  jb      short loc_14005773E
0x140057729  mov     rcx, [rcx+18h]
0x14005772d  lea     r8, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids
0x140057734  mov     edx, 22h ; '"'
0x140057739  call    WPP_SF_
0x14005773e  mov     eax, 0C0000205h
0x140057743  jmp     loc_1400515FF
```
