# VmpGetPartitionInfoEx(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016540`
- end: `0x14001662e`
- name: `?VmpGetPartitionInfoEx@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x1400014d0`
- `0x140003130`
- `0x140003170`
- `0x140003990`
- `0x140005090`
- `0x140015da0`
- `0x140016540`
- `0x140016990`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400165b8`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400165b8`
- `ntoskrnl!IofCompleteRequest` at `0x140016614`
- `ntoskrnl!IofCompleteRequest` at `0x140016614`

## pseudocode

```c
__int64 __fastcall VmpGetPartitionInfoEx(struct VM_VOLUME_EXTENSION *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  __int64 v3; // r14
  __int64 result; // rax
  int Status; // ebx
  struct _IRP *MasterIrp; // rbp
  struct VM_VOLUME_EXTENSION *v9; // rcx

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
        MasterIrp = Irp->AssociatedIrp.MasterIrp;
        VmpAcquireDevices((struct VM_ROOT_EXTENSION *)v3);
        if ( !(unsigned __int8)VmpIsVolumeDead(a1) )
          VmpSetPartitionInformation(v9, (struct _PARTITION_INFORMATION_EX *)MasterIrp);
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
0x140016540  push    rbx
0x140016542  push    rbp
0x140016543  push    rsi
0x140016544  push    rdi
0x140016545  push    r14
0x140016547  sub     rsp, 30h
0x14001654b  mov     rbp, [rdx+0B8h]
0x140016552  mov     r9b, 1; unsigned __int8
0x140016555  mov     r14, [rcx+8]
0x140016559  movzx   r8d, r9b; unsigned __int8
0x14001655d  mov     rdi, rdx
0x140016560  mov     [rsp+58h+var_38], 0; char
0x140016565  mov     rsi, rcx
0x140016568  call    ?VmpAllSystemsGo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@EEE@Z; VmpAllSystemsGo(VM_VOLUME_EXTENSION *,_IRP *,uchar,uchar,uchar)
0x14001656d  mov     ebx, eax
0x14001656f  test    eax, eax
0x140016571  js      loc_14001660C
0x140016577  cmp     eax, 103h
0x14001657c  jz      loc_140016622
0x140016582  cmp     byte ptr [rsi+1AAh], 0
0x140016589  mov     rdx, rdi; Irp
0x14001658c  jz      short loc_1400165B1
0x14001658e  mov     rax, [r14+188h]
0x140016595  mov     rcx, [rsi+1B0h]
0x14001659c  mov     rax, [rax+68h]
0x1400165a0  call    _guard_dispatch_icall
0x1400165a5  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x1400165a8  mov     ebx, eax
0x1400165aa  call    ?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)
0x1400165af  jmp     short loc_14001660C
0x1400165b1  mov     rcx, [rsi+158h]; DeviceObject
0x1400165b8  call    cs:__imp_IoForwardIrpSynchronously
0x1400165bf  nop     dword ptr [rax+rax+00h]
0x1400165c4  mov     ebx, [rdi+30h]
0x1400165c7  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x1400165ca  call    ?VmpReleaseRundownShared@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpReleaseRundownShared(VM_VOLUME_EXTENSION *)
0x1400165cf  test    ebx, ebx
0x1400165d1  js      short loc_14001660C
0x1400165d3  test    byte ptr [rbp+2], 2
0x1400165d7  jz      short loc_14001660C
0x1400165d9  mov     rax, [rsi]
0x1400165dc  mov     ecx, [rax+34h]
0x1400165df  test    cl, 1
0x1400165e2  jz      short loc_14001660C
0x1400165e4  mov     rbp, [rdi+18h]
0x1400165e8  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x1400165eb  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x1400165f0  mov     rcx, rsi
0x1400165f3  call    VmpIsVolumeDead
0x1400165f8  test    al, al
0x1400165fa  jnz     short loc_140016604
0x1400165fc  mov     rdx, rbp; struct _PARTITION_INFORMATION_EX *
0x1400165ff  call    ?VmpSetPartitionInformation@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_PARTITION_INFORMATION_EX@@@Z; VmpSetPartitionInformation(VM_VOLUME_EXTENSION *,_PARTITION_INFORMATION_EX *)
0x140016604  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140016607  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x14001660c  xor     edx, edx; PriorityBoost
0x14001660e  mov     [rdi+30h], ebx
0x140016611  mov     rcx, rdi; Irp
0x140016614  call    cs:__imp_IofCompleteRequest
0x14001661b  nop     dword ptr [rax+rax+00h]
0x140016620  mov     eax, ebx
0x140016622  add     rsp, 30h
0x140016626  pop     r14
0x140016628  pop     rdi
0x140016629  pop     rsi
0x14001662a  pop     rbp
0x14001662b  pop     rbx
0x14001662c  retn
```
