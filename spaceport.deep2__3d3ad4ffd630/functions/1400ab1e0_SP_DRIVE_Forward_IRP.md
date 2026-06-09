# SP_DRIVE::Forward(_IRP *)

- ea: `0x1400ab1e0`
- end: `0x1400ab330`
- name: `?Forward@SP_DRIVE@@QEAAJPEAU_IRP@@@Z`
- size: `336`
- prototype: `int(SP_DRIVE *__hidden this, struct _IRP *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a5c38`
- `0x1400ac000`

## callees

- `0x1400ab1e0`

## import_xrefs

- `ntoskrnl!IoSynchronousCallDriver` at `0x1400ab301`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400ab301`
- `ntoskrnl!IoFreeIrp` at `0x1400ab313`
- `ntoskrnl!IoFreeIrp` at `0x1400ab313`
- `ntoskrnl!IoAllocateIrp` at `0x1400ab237`
- `ntoskrnl!IoAllocateIrp` at `0x1400ab237`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400ab202`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400ab202`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400ab2b5`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400ab2b5`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400ab272`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400ab272`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ab261`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400ab261`

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
0x1400ab1e0  push    rbx
0x1400ab1e2  push    rbp
0x1400ab1e3  push    rsi
0x1400ab1e4  push    rdi
0x1400ab1e5  push    r14
0x1400ab1e7  sub     rsp, 20h
0x1400ab1eb  mov     rbp, rcx
0x1400ab1ee  mov     rbx, rdx
0x1400ab1f1  mov     rcx, [rcx+290h]; DeviceObject
0x1400ab1f8  mov     r8b, [rcx+4Ch]
0x1400ab1fc  cmp     [rdx+43h], r8b
0x1400ab200  jle     short loc_1400AB216
0x1400ab202  call    cs:__imp_IoForwardIrpSynchronously
0x1400ab209  nop     dword ptr [rax+rax+00h]
0x1400ab20e  mov     edi, [rbx+30h]
0x1400ab211  jmp     loc_1400AB31F
0x1400ab216  mov     r14, [rdx+0B8h]
0x1400ab21d  mov     al, [r14]
0x1400ab220  cmp     al, 0Eh
0x1400ab222  jz      short loc_1400AB232
0x1400ab224  cmp     al, 1Bh
0x1400ab226  jz      short loc_1400AB232
0x1400ab228  mov     edi, 0C00000E5h
0x1400ab22d  jmp     loc_1400AB31F
0x1400ab232  xor     edx, edx; ChargeQuota
0x1400ab234  mov     cl, r8b; StackSize
0x1400ab237  call    cs:__imp_IoAllocateIrp
0x1400ab23e  nop     dword ptr [rax+rax+00h]
0x1400ab243  mov     rsi, rax
0x1400ab246  test    rax, rax
0x1400ab249  jnz     short loc_1400AB255
0x1400ab24b  mov     edi, 0C000009Ah
0x1400ab250  jmp     loc_1400AB31F
0x1400ab255  mov     eax, [rbx+10h]
0x1400ab258  mov     rcx, rbx; Irp
0x1400ab25b  and     eax, 2
0x1400ab25e  or      [rsi+10h], eax
0x1400ab261  call    cs:__imp_IoGetIoPriorityHint
0x1400ab268  nop     dword ptr [rax+rax+00h]
0x1400ab26d  mov     edx, eax; PriorityHint
0x1400ab26f  mov     rcx, rsi; Irp
0x1400ab272  call    cs:__imp_IoSetIoPriorityHint
0x1400ab279  nop     dword ptr [rax+rax+00h]
0x1400ab27e  mov     rax, [rbx+18h]
0x1400ab282  or      r9d, 0FFFFFFFFh
0x1400ab286  mov     [rsi+18h], rax
0x1400ab28a  xor     r8d, r8d
0x1400ab28d  mov     eax, [rbx+30h]
0x1400ab290  mov     rdx, rsi
0x1400ab293  mov     [rsi+30h], eax
0x1400ab296  mov     rcx, rbx
0x1400ab299  mov     rax, [rbx+98h]
0x1400ab2a0  mov     [rsi+98h], rax
0x1400ab2a7  mov     rax, [rbx+0C0h]
0x1400ab2ae  mov     [rsi+0C0h], rax
0x1400ab2b5  call    cs:__imp_IoPropagateIrpExtensionEx
0x1400ab2bc  nop     dword ptr [rax+rax+00h]
0x1400ab2c1  mov     edi, eax
0x1400ab2c3  test    eax, eax
0x1400ab2c5  js      short loc_1400AB310
0x1400ab2c7  movups  xmm0, xmmword ptr [r14]
0x1400ab2cb  mov     rax, [rsi+0B8h]
0x1400ab2d2  mov     rdx, rsi
0x1400ab2d5  movups  xmmword ptr [rax-48h], xmm0
0x1400ab2d9  movups  xmm1, xmmword ptr [r14+10h]
0x1400ab2de  movups  xmmword ptr [rax-38h], xmm1
0x1400ab2e2  movups  xmm0, xmmword ptr [r14+20h]
0x1400ab2e7  movups  xmmword ptr [rax-28h], xmm0
0x1400ab2eb  movsd   xmm1, qword ptr [r14+30h]
0x1400ab2f1  movsd   qword ptr [rax-18h], xmm1
0x1400ab2f6  mov     byte ptr [rax-45h], 0
0x1400ab2fa  mov     rcx, [rbp+290h]
0x1400ab301  call    cs:__imp_IoSynchronousCallDriver
0x1400ab308  nop     dword ptr [rax+rax+00h]
0x1400ab30d  mov     edi, [rsi+30h]
0x1400ab310  mov     rcx, rsi; Irp
0x1400ab313  call    cs:__imp_IoFreeIrp
0x1400ab31a  nop     dword ptr [rax+rax+00h]
0x1400ab31f  mov     [rbx+30h], edi
0x1400ab322  mov     eax, edi
0x1400ab324  add     rsp, 20h
0x1400ab328  pop     r14
0x1400ab32a  pop     rdi
0x1400ab32b  pop     rsi
0x1400ab32c  pop     rbp
0x1400ab32d  pop     rbx
0x1400ab32e  retn
```
