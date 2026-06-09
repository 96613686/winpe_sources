# VmpGetPartitionInfo(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14000e010`
- end: `0x14000e13b`
- name: `?VmpGetPartitionInfo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, PIRP Irp)`
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
- `0x14000e010`
- `0x140015da0`
- `0x140016990`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000e08f`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000e08f`
- `ntoskrnl!IofCompleteRequest` at `0x14000e11e`
- `ntoskrnl!IofCompleteRequest` at `0x14000e11e`

## pseudocode

```c
__int64 __fastcall VmpGetPartitionInfo(struct VM_VOLUME_EXTENSION *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  __int64 v3; // rbp
  __int64 result; // rax
  int Status; // esi
  LARGE_INTEGER *MasterIrp; // rdi
  struct VM_VOLUME_EXTENSION *v9; // rcx
  _PARTITION_INFORMATION_EX v10; // [rsp+30h] [rbp-B8h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = *((_QWORD *)a1 + 1);
  result = VmpAllSystemsGo(a1, Irp, 1, 1, 0);
  Status = result;
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 259 )
      return result;
    if ( *((_BYTE *)a1 + 426) )
    {
      Status = (*(__int64 (__fastcall **)(_QWORD, PIRP))(*(_QWORD *)(v3 + 392) + 104LL))(*((_QWORD *)a1 + 54), Irp);
      VmpReleaseRundownShared(a1);
    }
    else
    {
      IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 43), Irp);
      Status = Irp->IoStatus.Status;
      VmpReleaseRundownShared(a1);
      if ( Status >= 0 && (CurrentStackLocation->Flags & 2) != 0 && (*(_DWORD *)(*(_QWORD *)a1 + 52LL) & 1) != 0 )
      {
        MasterIrp = (LARGE_INTEGER *)Irp->AssociatedIrp.MasterIrp;
        *((_DWORD *)&v10.PartitionStyle + 1) = 0;
        memset(&v10.PartitionNumber, 0, 0x78u);
        v10.StartingOffset = *MasterIrp;
        v10.PartitionLength = MasterIrp[1];
        v10.PartitionStyle = PARTITION_STYLE_MBR;
        VmpAcquireDevices((struct VM_ROOT_EXTENSION *)v3);
        if ( !(unsigned __int8)VmpIsVolumeDead(a1) )
          VmpSetPartitionInformation(v9, &v10);
        VmpReleaseDevices((struct VM_ROOT_EXTENSION *)v3);
      }
    }
  }
  Irp->IoStatus.Status = Status;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000e010  push    rbx
0x14000e012  push    rbp
0x14000e013  push    rsi
0x14000e014  push    rdi
0x14000e015  push    r14
0x14000e017  sub     rsp, 0C0h
0x14000e01e  mov     rdi, [rdx+0B8h]
0x14000e025  mov     r9b, 1; unsigned __int8
0x14000e028  mov     rbp, [rcx+8]
0x14000e02c  movzx   r8d, r9b; unsigned __int8
0x14000e030  mov     rbx, rdx
0x14000e033  mov     [rsp+0E8h+var_C8], 0; char
0x14000e038  mov     r14, rcx
0x14000e03b  call    ?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z; VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)
0x14000e040  mov     esi, eax
0x14000e042  test    eax, eax
0x14000e044  js      loc_14000E116
0x14000e04a  cmp     eax, 103h
0x14000e04f  jz      loc_14000E12C
0x14000e055  cmp     byte ptr [r14+1AAh], 0
0x14000e05d  mov     rdx, rbx; Irp
0x14000e060  jz      short loc_14000E088
0x14000e062  mov     rax, [rbp+188h]
0x14000e069  mov     rcx, [r14+1B0h]
0x14000e070  mov     rax, [rax+68h]
0x14000e074  call    _guard_dispatch_icall
0x14000e079  mov     rcx, r14; struct VM_VOLUME_EXTENSION *
0x14000e07c  mov     esi, eax
0x14000e07e  call    ?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)
0x14000e083  jmp     loc_14000E116
0x14000e088  mov     rcx, [r14+158h]; DeviceObject
0x14000e08f  call    cs:__imp_IoForwardIrpSynchronously
0x14000e096  nop     dword ptr [rax+rax+00h]
0x14000e09b  mov     esi, [rbx+30h]
0x14000e09e  mov     rcx, r14; struct VM_VOLUME_EXTENSION *
0x14000e0a1  call    ?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)
0x14000e0a6  test    esi, esi
0x14000e0a8  js      short loc_14000E116
0x14000e0aa  test    byte ptr [rdi+2], 2
0x14000e0ae  jz      short loc_14000E116
0x14000e0b0  mov     rax, [r14]
0x14000e0b3  mov     ecx, [rax+34h]
0x14000e0b6  test    cl, 1
0x14000e0b9  jz      short loc_14000E116
0x14000e0bb  mov     rdi, [rbx+18h]
0x14000e0bf  lea     rcx, [rsp+0E8h+var_B8.PartitionNumber]; void *
0x14000e0c4  xor     eax, eax
0x14000e0c6  xor     edx, edx; Val
0x14000e0c8  mov     r8d, 78h ; 'x'; Size
0x14000e0ce  mov     dword ptr [rsp+0E8h+var_B8+4], eax
0x14000e0d2  call    memset
0x14000e0d7  mov     rax, [rdi]
0x14000e0da  mov     rcx, rbp; struct VM_ROOT_EXTENSION *
0x14000e0dd  mov     qword ptr [rsp+0E8h+var_B8.StartingOffset], rax
0x14000e0e2  mov     rax, [rdi+8]
0x14000e0e6  mov     qword ptr [rsp+0E8h+var_B8.PartitionLength], rax
0x14000e0eb  mov     [rsp+0E8h+var_B8.PartitionStyle], 0
0x14000e0f3  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x14000e0f8  mov     rcx, r14
0x14000e0fb  call    VmpIsVolumeDead
0x14000e100  test    al, al
0x14000e102  jnz     short loc_14000E10E
0x14000e104  lea     rdx, [rsp+0E8h+var_B8]; struct _PARTITION_INFORMATION_EX *
0x14000e109  call    ?VmpSetPartitionInformation@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_PARTITION_INFORMATION_EX@@@Z; VmpSetPartitionInformation(VM_VOLUME_EXTENSION *,_PARTITION_INFORMATION_EX *)
0x14000e10e  mov     rcx, rbp; struct VM_ROOT_EXTENSION *
0x14000e111  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14000e116  xor     edx, edx; PriorityBoost
0x14000e118  mov     [rbx+30h], esi
0x14000e11b  mov     rcx, rbx; Irp
0x14000e11e  call    cs:__imp_IofCompleteRequest
0x14000e125  nop     dword ptr [rax+rax+00h]
0x14000e12a  mov     eax, esi
0x14000e12c  add     rsp, 0C0h
0x14000e133  pop     r14
0x14000e135  pop     rdi
0x14000e136  pop     rsi
0x14000e137  pop     rbp
0x14000e138  pop     rbx
0x14000e139  retn
```
