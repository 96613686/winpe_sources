# VmpGetLengthInfo(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016130`
- end: `0x140016311`
- name: `?VmpGetLengthInfo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x1400014d0`
- `0x140003130`
- `0x140003170`
- `0x140003990`
- `0x140005090`
- `0x140005540`
- `0x140015da0`
- `0x140016130`
- `0x140016990`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140016224`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140016224`
- `ntoskrnl!IofCallDriver` at `0x140016303`
- `ntoskrnl!IofCallDriver` at `0x140016303`
- `ntoskrnl!IofCompleteRequest` at `0x140016289`
- `ntoskrnl!IofCompleteRequest` at `0x140016289`

## pseudocode

```c
NTSTATUS __fastcall VmpGetLengthInfo(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v5; // r14
  int Status; // ebp
  NTSTATUS result; // eax
  struct _IRP *MasterIrp; // r15
  struct VM_VOLUME_EXTENSION *v9; // rcx
  struct _IO_STACK_LOCATION *v10; // rax
  struct _IO_STACK_LOCATION *v11; // rcx
  void *LowPart; // rax
  struct _PARTITION_INFORMATION_EX v13; // [rsp+30h] [rbp-A8h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&v13, 0, sizeof(v13));
  v5 = *((_QWORD *)a1 + 1);
  a2->IoStatus.Information = 0;
  if ( CurrentStackLocation->Parameters.Read.Length >= 8 )
  {
    result = VmpAllSystemsGo(a1, a2, 1, 1, 0);
    Status = result;
    if ( result >= 0 )
    {
      if ( result == 259 )
        return result;
      if ( *((_BYTE *)a1 + 426) )
      {
        Status = (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(v5 + 392) + 104LL))(
                   *((_QWORD *)a1 + 54),
                   a2);
        VmpReleaseRundownShared(a1);
      }
      else
      {
        if ( (CurrentStackLocation->Flags & 2) == 0 || (*(_DWORD *)(*(_QWORD *)a1 + 52LL) & 1) == 0 )
        {
          v10 = a2->Tail.Overlay.CurrentStackLocation;
          *(_OWORD *)&v10[-1].MajorFunction = *(_OWORD *)&v10->MajorFunction;
          *(_OWORD *)&v10[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v10->Parameters.NotifyDirectoryEx.CompletionFilter;
          *(_OWORD *)(&v10[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v10->Parameters.SetQuota + 6);
          v10[-1].FileObject = v10->FileObject;
          v10[-1].Control = 0;
          v11 = a2->Tail.Overlay.CurrentStackLocation;
          LowPart = (void *)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
          v11[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)VmpRefCountCompletionRoutine;
          v11[-1].Context = LowPart;
          v11[-1].Control = -32;
          return IofCallDriver(*((PDEVICE_OBJECT *)a1 + 43), a2);
        }
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        a2->AssociatedIrp.MasterIrp = (struct _IRP *)&v13;
        CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 458824;
        CurrentStackLocation->Parameters.Read.Length = 144;
        IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 43), a2);
        Status = a2->IoStatus.Status;
        a2->AssociatedIrp.MasterIrp = MasterIrp;
        VmpReleaseRundownShared(a1);
        if ( Status >= 0 )
        {
          VmpAcquireDevices((struct VM_ROOT_EXTENSION *)v5);
          if ( !(unsigned __int8)VmpIsVolumeDead(a1) )
            VmpSetPartitionInformation(v9, &v13);
          VmpReleaseDevices((struct VM_ROOT_EXTENSION *)v5);
          *(_QWORD *)&MasterIrp->Type = v13.PartitionLength.QuadPart;
          a2->IoStatus.Information = 8;
        }
      }
    }
  }
  else
  {
    Status = -1073741789;
  }
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  return Status;
}

```

## disassembly

```asm
0x140016130  mov     [rsp+arg_8], rbx
0x140016135  mov     [rsp+arg_10], rbp
0x14001613a  push    rsi
0x14001613b  push    rdi
0x14001613c  push    r14
0x14001613e  sub     rsp, 0C0h
0x140016145  mov     rsi, [rdx+0B8h]
0x14001614c  mov     rbx, rdx
0x14001614f  mov     rdi, rcx
0x140016152  xor     edx, edx; Val
0x140016154  lea     rcx, [rsp+0D8h+var_A8]; void *
0x140016159  mov     r8d, 90h; Size
0x14001615f  call    memset
0x140016164  mov     r14, [rdi+8]
0x140016168  mov     qword ptr [rbx+38h], 0
0x140016170  cmp     dword ptr [rsi+8], 8
0x140016174  jnb     short loc_140016180
0x140016176  mov     ebp, 0C0000023h
0x14001617b  jmp     loc_140016281
0x140016180  mov     r9b, 1; unsigned __int8
0x140016183  mov     [rsp+0D8h+var_B8], 0; char
0x140016188  movzx   r8d, r9b; unsigned __int8
0x14001618c  mov     rdx, rbx; struct _IRP *
0x14001618f  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140016192  call    ?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z; VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)
0x140016197  mov     ebp, eax
0x140016199  test    eax, eax
0x14001619b  js      loc_140016281
0x1400161a1  cmp     eax, 103h
0x1400161a6  jz      loc_140016297
0x1400161ac  cmp     byte ptr [rdi+1AAh], 0
0x1400161b3  jz      short loc_1400161DE
0x1400161b5  mov     rax, [r14+188h]
0x1400161bc  mov     rdx, rbx
0x1400161bf  mov     rcx, [rdi+1B0h]
0x1400161c6  mov     rax, [rax+68h]
0x1400161ca  call    _guard_dispatch_icall
0x1400161cf  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x1400161d2  mov     ebp, eax
0x1400161d4  call    ?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)
0x1400161d9  jmp     loc_140016281
0x1400161de  test    byte ptr [rsi+2], 2
0x1400161e2  jz      loc_1400162B0
0x1400161e8  mov     rax, [rdi]
0x1400161eb  mov     ecx, [rax+34h]
0x1400161ee  test    cl, 1
0x1400161f1  jz      loc_1400162B0
0x1400161f7  lea     rax, [rsp+0D8h+var_A8]
0x1400161fc  mov     [rsp+0D8h+arg_0], r15
0x140016204  mov     r15, [rbx+18h]
0x140016208  mov     rdx, rbx; Irp
0x14001620b  mov     [rbx+18h], rax
0x14001620f  mov     dword ptr [rsi+18h], 70048h
0x140016216  mov     dword ptr [rsi+8], 90h
0x14001621d  mov     rcx, [rdi+158h]; DeviceObject
0x140016224  call    cs:__imp_IoForwardIrpSynchronously
0x14001622b  nop     dword ptr [rax+rax+00h]
0x140016230  mov     ebp, [rbx+30h]
0x140016233  mov     rcx, rdi; struct VM_VOLUME_EXTENSION *
0x140016236  mov     [rbx+18h], r15
0x14001623a  call    ?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)
0x14001623f  test    ebp, ebp
0x140016241  js      short loc_140016279
0x140016243  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140016246  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x14001624b  mov     rcx, rdi
0x14001624e  call    VmpIsVolumeDead
0x140016253  test    al, al
0x140016255  jnz     short loc_140016261
0x140016257  lea     rdx, [rsp+0D8h+var_A8]; struct _PARTITION_INFORMATION_EX *
0x14001625c  call    ?VmpSetPartitionInformation@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_PARTITION_INFORMATION_EX@@@Z; VmpSetPartitionInformation(VM_VOLUME_EXTENSION *,_PARTITION_INFORMATION_EX *)
0x140016261  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140016264  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140016269  mov     rax, qword ptr [rsp+0D8h+var_A8.PartitionLength]
0x14001626e  mov     [r15], rax
0x140016271  mov     qword ptr [rbx+38h], 8
0x140016279  mov     r15, [rsp+0D8h+arg_0]
0x140016281  xor     edx, edx; PriorityBoost
0x140016283  mov     [rbx+30h], ebp
0x140016286  mov     rcx, rbx; Irp
0x140016289  call    cs:__imp_IofCompleteRequest
0x140016290  nop     dword ptr [rax+rax+00h]
0x140016295  mov     eax, ebp
0x140016297  lea     r11, [rsp+0D8h+var_18]
0x14001629f  mov     rbx, [r11+28h]
0x1400162a3  mov     rbp, [r11+30h]
0x1400162a7  mov     rsp, r11
0x1400162aa  pop     r14
0x1400162ac  pop     rdi
0x1400162ad  pop     rsi
0x1400162ae  retn
0x1400162b0  mov     rax, [rbx+0B8h]
0x1400162b7  lea     rdx, VmpRefCountCompletionRoutine
0x1400162be  movups  xmm0, xmmword ptr [rax]
0x1400162c1  movups  xmmword ptr [rax-48h], xmm0
0x1400162c5  movups  xmm1, xmmword ptr [rax+10h]
0x1400162c9  movups  xmmword ptr [rax-38h], xmm1
0x1400162cd  movups  xmm0, xmmword ptr [rax+20h]
0x1400162d1  movups  xmmword ptr [rax-28h], xmm0
0x1400162d5  movsd   xmm1, qword ptr [rax+30h]
0x1400162da  movsd   qword ptr [rax-18h], xmm1
0x1400162df  mov     byte ptr [rax-45h], 0
0x1400162e3  mov     rcx, [rbx+0B8h]
0x1400162ea  mov     eax, [rsi+18h]
0x1400162ed  mov     [rcx-10h], rdx
0x1400162f1  mov     rdx, rbx; Irp
0x1400162f4  mov     [rcx-8], rax
0x1400162f8  mov     byte ptr [rcx-45h], 0E0h
0x1400162fc  mov     rcx, [rdi+158h]; DeviceObject
0x140016303  call    cs:__imp_IofCallDriver
0x14001630a  nop     dword ptr [rax+rax+00h]
0x14001630f  jmp     short loc_140016297
```
