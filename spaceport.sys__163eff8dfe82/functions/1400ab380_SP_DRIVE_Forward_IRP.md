# SP_DRIVE::Forward(_IRP *)

- ea: `0x1400ab380`
- end: `0x1400ab4d0`
- name: `?Forward@SP_DRIVE@@QEAAJPEAU_IRP@@@Z`
- size: `336`
- prototype: `int(SP_DRIVE *__hidden this, struct _IRP *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a5d68`
- `0x1400ac1a0`

## callees

- `0x1400ab380`

## import_xrefs

- `ntoskrnl!IoSynchronousCallDriver` at `0x1400ab4a1`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400ab4a1`
- `ntoskrnl!IoFreeIrp` at `0x1400ab4b3`
- `ntoskrnl!IoFreeIrp` at `0x1400ab4b3`
- `ntoskrnl!IoAllocateIrp` at `0x1400ab3d7`
- `ntoskrnl!IoAllocateIrp` at `0x1400ab3d7`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400ab3a2`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400ab3a2`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400ab455`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400ab455`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400ab412`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400ab412`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ab401`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ab401`

## pseudocode

```c
__int64 __fastcall SP_DRIVE::Forward(SP_DRIVE *this, struct _IRP *a2)
{
  struct _DEVICE_OBJECT *v4; // rcx
  int Status; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PIRP Irp; // rsi
  IO_PRIORITY_HINT IoPriorityHint; // eax
  struct _IO_STACK_LOCATION *v9; // rax

  v4 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 82);
  if ( a2->CurrentLocation <= v4->StackSize )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->MajorFunction == 14 || CurrentStackLocation->MajorFunction == 27 )
    {
      Irp = IoAllocateIrp(v4->StackSize, 0);
      if ( Irp )
      {
        Irp->Flags |= a2->Flags & 2;
        IoPriorityHint = IoGetIoPriorityHint(a2);
        IoSetIoPriorityHint(Irp, IoPriorityHint);
        Irp->AssociatedIrp.MasterIrp = a2->AssociatedIrp.MasterIrp;
        Irp->IoStatus.Status = a2->IoStatus.Status;
        Irp->Tail.Overlay.Thread = a2->Tail.Overlay.Thread;
        Irp->Tail.Overlay.OriginalFileObject = a2->Tail.Overlay.OriginalFileObject;
        Status = IoPropagateIrpExtensionEx(a2, Irp, 0, 0xFFFFFFFFLL);
        if ( Status >= 0 )
        {
          v9 = Irp->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v9[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
          *(_OWORD *)&v9[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v9[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota + 6);
          v9[-1].FileObject = CurrentStackLocation->FileObject;
          v9[-1].Control = 0;
          IoSynchronousCallDriver(*((_QWORD *)this + 82), Irp);
          Status = Irp->IoStatus.Status;
        }
        IoFreeIrp(Irp);
      }
      else
      {
        Status = -1073741670;
      }
    }
    else
    {
      Status = -1073741595;
    }
  }
  else
  {
    IoForwardIrpSynchronously(v4, a2);
    Status = a2->IoStatus.Status;
  }
  a2->IoStatus.Status = Status;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400ab380  push    rbx
0x1400ab382  push    rbp
0x1400ab383  push    rsi
0x1400ab384  push    rdi
0x1400ab385  push    r14
0x1400ab387  sub     rsp, 20h
0x1400ab38b  mov     rbp, rcx
0x1400ab38e  mov     rbx, rdx
0x1400ab391  mov     rcx, [rcx+290h]; DeviceObject
0x1400ab398  mov     r8b, [rcx+4Ch]
0x1400ab39c  cmp     [rdx+43h], r8b
0x1400ab3a0  jle     short loc_1400AB3B6
0x1400ab3a2  call    cs:__imp_IoForwardIrpSynchronously
0x1400ab3a9  nop     dword ptr [rax+rax+00h]
0x1400ab3ae  mov     edi, [rbx+30h]
0x1400ab3b1  jmp     loc_1400AB4BF
0x1400ab3b6  mov     r14, [rdx+0B8h]
0x1400ab3bd  mov     al, [r14]
0x1400ab3c0  cmp     al, 0Eh
0x1400ab3c2  jz      short loc_1400AB3D2
0x1400ab3c4  cmp     al, 1Bh
0x1400ab3c6  jz      short loc_1400AB3D2
0x1400ab3c8  mov     edi, 0C00000E5h
0x1400ab3cd  jmp     loc_1400AB4BF
0x1400ab3d2  xor     edx, edx; ChargeQuota
0x1400ab3d4  mov     cl, r8b; StackSize
0x1400ab3d7  call    cs:__imp_IoAllocateIrp
0x1400ab3de  nop     dword ptr [rax+rax+00h]
0x1400ab3e3  mov     rsi, rax
0x1400ab3e6  test    rax, rax
0x1400ab3e9  jnz     short loc_1400AB3F5
0x1400ab3eb  mov     edi, 0C000009Ah
0x1400ab3f0  jmp     loc_1400AB4BF
0x1400ab3f5  mov     eax, [rbx+10h]
0x1400ab3f8  mov     rcx, rbx; Irp
0x1400ab3fb  and     eax, 2
0x1400ab3fe  or      [rsi+10h], eax
0x1400ab401  call    cs:__imp_IoGetIoPriorityHint
0x1400ab408  nop     dword ptr [rax+rax+00h]
0x1400ab40d  mov     edx, eax; PriorityHint
0x1400ab40f  mov     rcx, rsi; Irp
0x1400ab412  call    cs:__imp_IoSetIoPriorityHint
0x1400ab419  nop     dword ptr [rax+rax+00h]
0x1400ab41e  mov     rax, [rbx+18h]
0x1400ab422  or      r9d, 0FFFFFFFFh
0x1400ab426  mov     [rsi+18h], rax
0x1400ab42a  xor     r8d, r8d
0x1400ab42d  mov     eax, [rbx+30h]
0x1400ab430  mov     rdx, rsi
0x1400ab433  mov     [rsi+30h], eax
0x1400ab436  mov     rcx, rbx
0x1400ab439  mov     rax, [rbx+98h]
0x1400ab440  mov     [rsi+98h], rax
0x1400ab447  mov     rax, [rbx+0C0h]
0x1400ab44e  mov     [rsi+0C0h], rax
0x1400ab455  call    cs:__imp_IoPropagateIrpExtensionEx
0x1400ab45c  nop     dword ptr [rax+rax+00h]
0x1400ab461  mov     edi, eax
0x1400ab463  test    eax, eax
0x1400ab465  js      short loc_1400AB4B0
0x1400ab467  movups  xmm0, xmmword ptr [r14]
0x1400ab46b  mov     rax, [rsi+0B8h]
0x1400ab472  mov     rdx, rsi
0x1400ab475  movups  xmmword ptr [rax-48h], xmm0
0x1400ab479  movups  xmm1, xmmword ptr [r14+10h]
0x1400ab47e  movups  xmmword ptr [rax-38h], xmm1
0x1400ab482  movups  xmm0, xmmword ptr [r14+20h]
0x1400ab487  movups  xmmword ptr [rax-28h], xmm0
0x1400ab48b  movsd   xmm1, qword ptr [r14+30h]
0x1400ab491  movsd   qword ptr [rax-18h], xmm1
0x1400ab496  mov     byte ptr [rax-45h], 0
0x1400ab49a  mov     rcx, [rbp+290h]
0x1400ab4a1  call    cs:__imp_IoSynchronousCallDriver
0x1400ab4a8  nop     dword ptr [rax+rax+00h]
0x1400ab4ad  mov     edi, [rsi+30h]
0x1400ab4b0  mov     rcx, rsi; Irp
0x1400ab4b3  call    cs:__imp_IoFreeIrp
0x1400ab4ba  nop     dword ptr [rax+rax+00h]
0x1400ab4bf  mov     [rbx+30h], edi
0x1400ab4c2  mov     eax, edi
0x1400ab4c4  add     rsp, 20h
0x1400ab4c8  pop     r14
0x1400ab4ca  pop     rdi
0x1400ab4cb  pop     rsi
0x1400ab4cc  pop     rbp
0x1400ab4cd  pop     rbx
0x1400ab4ce  retn
```
