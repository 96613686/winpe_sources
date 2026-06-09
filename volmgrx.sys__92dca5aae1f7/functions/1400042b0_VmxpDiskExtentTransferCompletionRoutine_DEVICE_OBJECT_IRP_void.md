# VmxpDiskExtentTransferCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400042b0`
- end: `0x14000450f`
- name: `?VmxpDiskExtentTransferCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `607`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400042b0`
- `0x14001b78c`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004360`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004360`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400043a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400043a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044fe`
- `ntoskrnl!IofCallDriver` at `0x140004483`
- `ntoskrnl!IofCallDriver` at `0x140004483`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044d3`
- `ntoskrnl!IoFreeIrp` at `0x140004330`
- `ntoskrnl!IoFreeIrp` at `0x140004330`
- `ntoskrnl!IoAllocateIrp` at `0x1400043b5`
- `ntoskrnl!IoAllocateIrp` at `0x1400043b5`
- `ntoskrnl!IoReuseIrp` at `0x1400043d2`
- `ntoskrnl!IoReuseIrp` at `0x1400043d2`

## pseudocode

```c
__int64 __fastcall VmxpDiskExtentTransferCompletionRoutine(struct _DEVICE_OBJECT *a1, struct _IRP *a2, _QWORD *a3)
{
  __int64 v3; // rbp
  NTSTATUS Status; // eax
  __int64 v7; // rsi
  struct _DEVICE_OBJECT *v8; // r14
  struct _IRP *MasterIrp; // rcx
  KIRQL v11; // al
  _QWORD *v12; // r12
  _QWORD *v13; // rcx
  PIRP Irp; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v16; // rcx
  struct _IO_STACK_LOCATION *v17; // rax
  _QWORD **v18; // r13

  v3 = a3[6];
  Status = a2->IoStatus.Status;
  v7 = *(_QWORD *)(v3 + 48);
  v8 = *(struct _DEVICE_OBJECT **)(v7 + 24);
  if ( Status < 0
    && Status != -1073741670
    && Status != -2147483626
    && _InterlockedExchange((volatile __int32 *)(v7 + 44), 1) != 1 )
  {
    VmxpSendRecordedFailureNotification((struct VMX_DISK_DEVICE *)v7);
  }
  *((_OWORD *)a3 + 6) = *(_OWORD *)&a2->IoStatus.Status;
  if ( a2 != (struct _IRP *)a3[4] )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    if ( MasterIrp )
      ExFreePoolWithTag(MasterIrp, 0);
    if ( a2 == *(struct _IRP **)(v3 + 72) )
    {
      v18 = (_QWORD **)(v3 + 88);
      while ( 1 )
      {
        v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 24));
        v12 = *v18;
        if ( *v18 == v18 )
          break;
        if ( (_QWORD **)v12[1] != v18 || (v13 = (_QWORD *)*v12, *(_QWORD **)(*v12 + 8LL) != v12) )
          __fastfail(3u);
        *v18 = v13;
        v13[1] = v18;
        KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 24), v11);
        Irp = IoAllocateIrp(v8->StackSize + 1, 0);
        if ( !Irp )
        {
          Irp = *(PIRP *)(v3 + 72);
          IoReuseIrp(Irp, 0);
        }
        --Irp->Tail.Overlay.CurrentStackLocation;
        --Irp->CurrentLocation;
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        Irp->MdlAddress = (PMDL)*(v12 - 11);
        Irp->Flags |= *(_DWORD *)(v12 - 6) & 0x8002;
        Irp->Tail.Overlay.Thread = (PETHREAD)*(v12 - 7);
        Irp->Tail.Overlay.OriginalFileObject = (PFILE_OBJECT)*(v12 - 5);
        CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart = 0;
        CurrentStackLocation->Parameters.CreatePipe.Parameters = 0;
        CurrentStackLocation->Parameters.WMI.ProviderId = 1833528662;
        CurrentStackLocation->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)a3;
        v16 = Irp->Tail.Overlay.CurrentStackLocation;
        v16[-1].MajorFunction = (*((_BYTE *)v12 - 30) == 0) + 3;
        v16[-1].Flags = *((_BYTE *)v12 - 31) | 0x10;
        v16[-1].Parameters.Read.ByteOffset.QuadPart = *(_QWORD *)(v3 + 56) + *(v12 - 12);
        v16[-1].Parameters.Read.Length = *((_DWORD *)v12 - 26);
        v17 = Irp->Tail.Overlay.CurrentStackLocation;
        v17[-1].CompletionRoutine = VmxpDiskExtentTransferCompletionRoutine;
        v17[-1].Context = v12 - 14;
        v17[-1].Control = -32;
        IofCallDriver(v8, Irp);
        if ( Irp == a2 )
          goto LABEL_3;
      }
      *(_BYTE *)(v3 + 80) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 24), v11);
    }
    else
    {
      IoFreeIrp(a2);
    }
  }
LABEL_3:
  ((void (__fastcall *)(_QWORD *))a3[5])(a3);
  _InterlockedDecrement((volatile signed __int32 *)(v7 + 56));
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400042b0  push    rbx
0x1400042b2  push    rbp
0x1400042b3  push    rsi
0x1400042b4  push    rdi
0x1400042b5  push    r14
0x1400042b7  sub     rsp, 20h
0x1400042bb  mov     rbp, [r8+30h]
0x1400042bf  mov     rbx, r8
0x1400042c2  mov     eax, [rdx+30h]
0x1400042c5  mov     rdi, rdx
0x1400042c8  mov     rsi, [rbp+30h]
0x1400042cc  mov     r14, [rsi+18h]
0x1400042d0  test    eax, eax
0x1400042d2  js      loc_14000449D
0x1400042d8  movups  xmm0, xmmword ptr [rdi+30h]
0x1400042dc  movups  xmmword ptr [rbx+60h], xmm0
0x1400042e0  cmp     rdi, [rbx+20h]
0x1400042e4  jnz     short loc_140004307
0x1400042e6  mov     rax, [rbx+28h]
0x1400042ea  mov     rcx, rbx
0x1400042ed  call    _guard_dispatch_icall
0x1400042f2  lock dec dword ptr [rsi+38h]
0x1400042f6  mov     eax, 0C0000016h
0x1400042fb  add     rsp, 20h
0x1400042ff  pop     r14
0x140004301  pop     rdi
0x140004302  pop     rsi
0x140004303  pop     rbp
0x140004304  pop     rbx
0x140004305  retn
0x140004307  mov     rcx, [rdi+18h]; P
0x14000430b  test    rcx, rcx
0x14000430e  jnz     loc_1400044D1
0x140004314  mov     [rsp+48h+arg_0], r12
0x140004319  mov     [rsp+48h+arg_8], r13
0x14000431e  mov     [rsp+48h+arg_10], r15
0x140004323  cmp     rdi, [rbp+48h]
0x140004327  jz      loc_1400044E4
0x14000432d  mov     rcx, rdi; Irp
0x140004330  call    cs:__imp_IoFreeIrp
0x140004337  nop     dword ptr [rax+rax+00h]
0x14000433c  mov     rax, [rbx+28h]
0x140004340  mov     rcx, rbx
0x140004343  call    _guard_dispatch_icall
0x140004348  mov     r13, [rsp+48h+arg_8]
0x14000434d  mov     r12, [rsp+48h+arg_0]
0x140004352  mov     r15, [rsp+48h+arg_10]
0x140004357  jmp     short loc_1400042F2
0x140004359  lea     r15, [rbp+18h]
0x14000435d  mov     rcx, r15; SpinLock
0x140004360  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004367  nop     dword ptr [rax+rax+00h]
0x14000436c  mov     r12, [r13+0]
0x140004370  cmp     r12, r13
0x140004373  jz      loc_1400044F4
0x140004379  cmp     [r12+8], r13
0x14000437e  jnz     loc_1400044ED
0x140004384  mov     rcx, [r12]
0x140004388  cmp     [rcx+8], r12
0x14000438c  jnz     loc_1400044ED
0x140004392  mov     [r13+0], rcx
0x140004396  movzx   edx, al; NewIrql
0x140004399  mov     [rcx+8], r13
0x14000439d  mov     rcx, r15; SpinLock
0x1400043a0  call    cs:__imp_KeReleaseSpinLock
0x1400043a7  nop     dword ptr [rax+rax+00h]
0x1400043ac  movzx   ecx, byte ptr [r14+4Ch]
0x1400043b1  xor     edx, edx; ChargeQuota
0x1400043b3  inc     cl; StackSize
0x1400043b5  call    cs:__imp_IoAllocateIrp
0x1400043bc  nop     dword ptr [rax+rax+00h]
0x1400043c1  mov     r15, rax
0x1400043c4  test    rax, rax
0x1400043c7  jnz     short loc_1400043DE
0x1400043c9  mov     r15, [rbp+48h]
0x1400043cd  xor     edx, edx; Iostatus
0x1400043cf  mov     rcx, r15; Irp
0x1400043d2  call    cs:__imp_IoReuseIrp
0x1400043d9  nop     dword ptr [rax+rax+00h]
0x1400043de  add     qword ptr [r15+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400043e6  lea     rdx, [r12-70h]
0x1400043eb  dec     byte ptr [r15+43h]
0x1400043ef  mov     rax, [rdx+18h]
0x1400043f3  mov     rcx, [r15+0B8h]
0x1400043fa  mov     [r15+8], rax
0x1400043fe  mov     eax, [rdx+40h]
0x140004401  and     eax, 8002h
0x140004406  or      [r15+10h], eax
0x14000440a  mov     rax, [rdx+38h]
0x14000440e  mov     [r15+98h], rax
0x140004415  mov     rax, [rdx+48h]
0x140004419  mov     [r15+0C0h], rax
0x140004420  xor     eax, eax
0x140004422  mov     [rcx+18h], rax
0x140004426  mov     [rcx+20h], rax
0x14000442a  mov     qword ptr [rcx+8], 6D496D56h
0x140004432  mov     [rcx+10h], rbx
0x140004436  cmp     [rdx+52h], al
0x140004439  mov     rcx, [r15+0B8h]
0x140004440  setz    al
0x140004443  add     al, 3
0x140004445  mov     [rcx-48h], al
0x140004448  movzx   eax, byte ptr [rdx+51h]
0x14000444c  or      al, 10h
0x14000444e  mov     [rcx-46h], al
0x140004451  mov     rax, [rdx+10h]
0x140004455  add     rax, [rbp+38h]
0x140004459  mov     [rcx-30h], rax
0x14000445d  mov     eax, [rdx+8]
0x140004460  mov     [rcx-40h], eax
0x140004463  lea     rcx, ?VmxpDiskExtentTransferCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; VmxpDiskExtentTransferCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14000446a  mov     rax, [r15+0B8h]
0x140004471  mov     [rax-10h], rcx
0x140004475  mov     rcx, r14; DeviceObject
0x140004478  mov     [rax-8], rdx
0x14000447c  mov     rdx, r15; Irp
0x14000447f  mov     byte ptr [rax-45h], 0E0h
0x140004483  call    cs:__imp_IofCallDriver
0x14000448a  nop     dword ptr [rax+rax+00h]
0x14000448f  cmp     r15, rdi
0x140004492  jnz     loc_140004359
0x140004498  jmp     loc_14000433C
0x14000449d  cmp     eax, 0C000009Ah
0x1400044a2  jz      loc_1400042D8
0x1400044a8  cmp     eax, 80000016h
0x1400044ad  jz      loc_1400042D8
0x1400044b3  mov     eax, 1
0x1400044b8  xchg    eax, [rsi+2Ch]
0x1400044bb  cmp     eax, 1
0x1400044be  jz      loc_1400042D8
0x1400044c4  mov     rcx, rsi; struct VMX_DISK_DEVICE *
0x1400044c7  call    ?VmxpSendRecordedFailureNotification@@YAXPEAVVMX_DISK_DEVICE@@@Z; VmxpSendRecordedFailureNotification(VMX_DISK_DEVICE *)
0x1400044cc  jmp     loc_1400042D8
0x1400044d1  xor     edx, edx; Tag
0x1400044d3  call    cs:__imp_ExFreePoolWithTag
0x1400044da  nop     dword ptr [rax+rax+00h]
0x1400044df  jmp     loc_140004314
0x1400044e4  lea     r13, [rbp+58h]
0x1400044e8  jmp     loc_140004359
0x1400044ed  mov     ecx, 3
0x1400044f2  int     29h; Win8: RtlFailFast(ecx)
0x1400044f4  movzx   edx, al; NewIrql
0x1400044f7  mov     byte ptr [rbp+50h], 0
0x1400044fb  mov     rcx, r15; SpinLock
0x1400044fe  call    cs:__imp_KeReleaseSpinLock
0x140004505  nop     dword ptr [rax+rax+00h]
0x14000450a  jmp     loc_14000433C
```
