# IopSynchronousCall(_DEVICE_OBJECT *,_IO_STACK_LOCATION *,void *,long,uchar,unsigned __int64,unsigned __int64 *)

- ea: `0x140009134`
- end: `0x14000929d`
- name: `?IopSynchronousCall@@YAJPEAU_DEVICE_OBJECT@@PEAU_IO_STACK_LOCATION@@PEAXJE_KPEA_K@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IO_STACK_LOCATION *, void *, int, char, unsigned __int64, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001e80`
- `0x1400092c8`
- `0x140009eb4`
- `0x14000a0fc`

## callees

- `0x140009134`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x140009180`
- `ntoskrnl!IoAllocateIrp` at `0x140009180`
- `ntoskrnl!KeInitializeEvent` at `0x1400091bc`
- `ntoskrnl!KeInitializeEvent` at `0x1400091bc`
- `ntoskrnl!IofCallDriver` at `0x14000921e`
- `ntoskrnl!IofCallDriver` at `0x14000921e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009249`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009249`
- `ntoskrnl!IoFreeIrp` at `0x14000926f`
- `ntoskrnl!IoFreeIrp` at `0x14000926f`
- `ntoskrnl!ObfReferenceObject` at `0x14000916f`
- `ntoskrnl!ObfReferenceObject` at `0x14000916f`
- `ntoskrnl!ObfDereferenceObject` at `0x140009285`
- `ntoskrnl!ObfDereferenceObject` at `0x140009285`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000915e`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14000915e`

## pseudocode

```c
__int64 __fastcall IopSynchronousCall(
        struct _DEVICE_OBJECT *a1,
        struct _IO_STACK_LOCATION *a2,
        void *a3,
        __int64 a4,
        char a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  PDEVICE_OBJECT AttachedDeviceReference; // rdi
  PIRP Irp; // rax
  IRP *v11; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  struct _IO_STACK_LOCATION *v16; // rax
  unsigned int Status; // esi
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  AttachedDeviceReference = a1;
  memset(&Event, 0, sizeof(Event));
  if ( a5 )
    AttachedDeviceReference = IoGetAttachedDeviceReference(a1);
  else
    ObfReferenceObject(a1);
  Irp = IoAllocateIrp(AttachedDeviceReference->StackSize, 0);
  v11 = Irp;
  if ( Irp )
  {
    if ( a3 )
      Irp->UserBuffer = a3;
    Irp->IoStatus.Status = -1073741637;
    Irp->IoStatus.Information = 0;
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    CurrentStackLocation = v11->Tail.Overlay.CurrentStackLocation;
    v13 = *(_OWORD *)&a2->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&a2->MajorFunction;
    v14 = *(_OWORD *)(&a2->Parameters.SetQuota + 6);
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = v13;
    v15 = *(_OWORD *)&a2->FileObject;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = v14;
    *(_QWORD *)&v14 = a2->Context;
    *(_OWORD *)&CurrentStackLocation[-1].FileObject = v15;
    CurrentStackLocation[-1].Context = (PVOID)v14;
    v16 = v11->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FdEvtWdmIrpGenericCompletion;
    v16[-1].Context = &Event;
    v16[-1].Control = -32;
    Status = IofCallDriver(AttachedDeviceReference, v11);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = v11->IoStatus.Status;
    }
    if ( a7 )
      *a7 = v11->IoStatus.Information;
    IoFreeIrp(v11);
  }
  else
  {
    Status = -1073741670;
  }
  ObfDereferenceObject(AttachedDeviceReference);
  return Status;
}

```

## disassembly

```asm
0x140009134  push    rbx
0x140009136  push    rbp
0x140009137  push    rsi
0x140009138  push    rdi
0x140009139  sub     rsp, 58h
0x14000913d  xor     eax, eax
0x14000913f  xorps   xmm0, xmm0
0x140009142  mov     rsi, r8
0x140009145  mov     rbp, rdx
0x140009148  mov     rdi, rcx
0x14000914b  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x140009150  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x140009155  cmp     [rsp+78h+arg_20], al
0x14000915c  jz      short loc_14000916F
0x14000915e  call    cs:__imp_IoGetAttachedDeviceReference
0x140009165  nop     dword ptr [rax+rax+00h]
0x14000916a  mov     rdi, rax
0x14000916d  jmp     short loc_14000917B
0x14000916f  call    cs:__imp_ObfReferenceObject
0x140009176  nop     dword ptr [rax+rax+00h]
0x14000917b  mov     cl, [rdi+4Ch]; StackSize
0x14000917e  xor     edx, edx; ChargeQuota
0x140009180  call    cs:__imp_IoAllocateIrp
0x140009187  nop     dword ptr [rax+rax+00h]
0x14000918c  mov     rbx, rax
0x14000918f  test    rax, rax
0x140009192  jz      loc_14000927D
0x140009198  test    rsi, rsi
0x14000919b  jz      short loc_1400091A1
0x14000919d  mov     [rax+70h], rsi
0x1400091a1  xor     r8d, r8d; State
0x1400091a4  mov     dword ptr [rax+30h], 0C00000BBh
0x1400091ab  lea     rcx, [rsp+78h+Event]; Event
0x1400091b0  mov     qword ptr [rax+38h], 0
0x1400091b8  lea     edx, [r8+1]; Type
0x1400091bc  call    cs:__imp_KeInitializeEvent
0x1400091c3  nop     dword ptr [rax+rax+00h]
0x1400091c8  mov     rax, [rbx+0B8h]
0x1400091cf  lea     rcx, FdEvtWdmIrpGenericCompletion
0x1400091d6  movups  xmm0, xmmword ptr [rbp+0]
0x1400091da  mov     rdx, rbx; Irp
0x1400091dd  movups  xmm1, xmmword ptr [rbp+10h]
0x1400091e1  movups  xmmword ptr [rax-48h], xmm0
0x1400091e5  movups  xmm0, xmmword ptr [rbp+20h]
0x1400091e9  movups  xmmword ptr [rax-38h], xmm1
0x1400091ed  movups  xmm1, xmmword ptr [rbp+30h]
0x1400091f1  movups  xmmword ptr [rax-28h], xmm0
0x1400091f5  movsd   xmm0, qword ptr [rbp+40h]
0x1400091fa  movups  xmmword ptr [rax-18h], xmm1
0x1400091fe  movsd   qword ptr [rax-8], xmm0
0x140009203  mov     rax, [rbx+0B8h]
0x14000920a  mov     [rax-10h], rcx
0x14000920e  lea     rcx, [rsp+78h+Event]
0x140009213  mov     [rax-8], rcx
0x140009217  mov     rcx, rdi; DeviceObject
0x14000921a  mov     byte ptr [rax-45h], 0E0h
0x14000921e  call    cs:__imp_IofCallDriver
0x140009225  nop     dword ptr [rax+rax+00h]
0x14000922a  mov     esi, eax
0x14000922c  cmp     eax, 103h
0x140009231  jnz     short loc_140009258
0x140009233  xor     r9d, r9d; Alertable
0x140009236  mov     [rsp+78h+Timeout], 0; Timeout
0x14000923f  xor     r8d, r8d; WaitMode
0x140009242  lea     rcx, [rsp+78h+Event]; Object
0x140009247  xor     edx, edx; WaitReason
0x140009249  call    cs:__imp_KeWaitForSingleObject
0x140009250  nop     dword ptr [rax+rax+00h]
0x140009255  mov     esi, [rbx+30h]
0x140009258  mov     rcx, [rsp+78h+arg_30]
0x140009260  test    rcx, rcx
0x140009263  jz      short loc_14000926C
0x140009265  mov     rax, [rbx+38h]
0x140009269  mov     [rcx], rax
0x14000926c  mov     rcx, rbx; Irp
0x14000926f  call    cs:__imp_IoFreeIrp
0x140009276  nop     dword ptr [rax+rax+00h]
0x14000927b  jmp     short loc_140009282
0x14000927d  mov     esi, 0C000009Ah
0x140009282  mov     rcx, rdi; Object
0x140009285  call    cs:__imp_ObfDereferenceObject
0x14000928c  nop     dword ptr [rax+rax+00h]
0x140009291  mov     eax, esi
0x140009293  add     rsp, 58h
0x140009297  pop     rdi
0x140009298  pop     rsi
0x140009299  pop     rbp
0x14000929a  pop     rbx
0x14000929b  retn
```
