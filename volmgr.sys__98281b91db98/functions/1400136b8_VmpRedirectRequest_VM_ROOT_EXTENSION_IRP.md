# VmpRedirectRequest(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x1400136b8`
- end: `0x1400139ae`
- name: `?VmpRedirectRequest@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `758`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ea0`

## callees

- `0x140003170`
- `0x140003910`
- `0x140003990`
- `0x140005090`
- `0x1400136b8`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400138b2`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400138b2`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x140013922`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x140013922`
- `ntoskrnl!IoFreeIrp` at `0x140013971`
- `ntoskrnl!IoFreeIrp` at `0x140013971`
- `ntoskrnl!ObfDereferenceObject` at `0x140013987`
- `ntoskrnl!ObfDereferenceObject` at `0x140013987`
- `ntoskrnl!IoAllocateMdl` at `0x140013889`
- `ntoskrnl!IoAllocateMdl` at `0x140013889`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001393a`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14001393a`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x14001385b`
- `ntoskrnl!IoMakeAssociatedIrp` at `0x14001385b`
- `ntoskrnl!IoFreeMdl` at `0x14001395b`
- `ntoskrnl!IoFreeMdl` at `0x14001395b`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001383a`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001383a`

## pseudocode

```c
__int64 __fastcall VmpRedirectRequest(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rbx
  struct _IRP *MasterIrp; // rsi
  char *v6; // rdi
  ULONG Blink; // eax
  char v8; // r15
  struct _IRP *v9; // r13
  char v10; // al
  char *v11; // r12
  char *v12; // r14
  __int64 v13; // rcx
  signed int Status; // ebx
  PDEVICE_OBJECT AttachedDeviceReference; // r14
  IRP *Irp; // rax
  IRP *v17; // rdi
  struct _MDL *Mdl; // rax
  struct _MDL *v19; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  ULONG Length; // [rsp+30h] [rbp-68h]
  struct _LIST_ENTRY *Flink; // [rsp+38h] [rbp-60h]
  PMDL MdlAddress; // [rsp+40h] [rbp-58h]
  __int64 v24; // [rsp+48h] [rbp-50h]
  __int64 v25; // [rsp+50h] [rbp-48h]
  char v27; // [rsp+B0h] [rbp+18h]
  char v28; // [rsp+B8h] [rbp+20h] BYREF

  v28 = 0;
  v2 = a2;
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x30 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v6 = 0;
  v24 = *(_QWORD *)&MasterIrp->Type;
  MdlAddress = MasterIrp->MdlAddress;
  v25 = *(_QWORD *)(*(_QWORD *)&MasterIrp->Flags + 184LL);
  if ( (unsigned __int8)(*(_BYTE *)v25 - 3) <= 1u )
  {
    v8 = 1;
    v9 = MasterIrp->AssociatedIrp.MasterIrp;
    Flink = MasterIrp->ThreadListEntry.Flink;
    Blink = (ULONG)MasterIrp->ThreadListEntry.Blink;
  }
  else
  {
    Blink = 0;
    v8 = 0;
    v9 = 0;
    Flink = 0;
  }
  Length = Blink;
  VmpAcquireDevices(a1);
  v10 = 0;
  v11 = (char *)a1 + 208;
  v12 = (char *)*((_QWORD *)a1 + 26);
  v27 = 0;
  while ( 1 )
  {
    if ( v12 == v11 )
    {
      if ( !v10 )
      {
        Status = -1073741811;
        goto LABEL_26;
      }
      goto LABEL_20;
    }
    v6 = v12 - 32;
    if ( v12[394] )
    {
      v13 = *((_QWORD *)v6 + 54);
      if ( !v13 )
        goto LABEL_16;
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, PMDL, char *))(*((_QWORD *)a1 + 49) + 200LL))(
              v13,
              MdlAddress,
              &v28) )
      {
        v10 = v27;
        goto LABEL_16;
      }
    }
    else if ( *((_QWORD *)v6 + 43) != v24 )
    {
      goto LABEL_16;
    }
    if ( !v6[156] )
      break;
    if ( !(unsigned __int8)VmpIsSafeForDirectAccess(v12 - 32) )
    {
      Status = -1073741790;
LABEL_26:
      VmpReleaseDevices(a1);
      return (unsigned int)Status;
    }
    v10 = 1;
    v27 = 1;
    if ( !v6[426] )
      goto LABEL_20;
LABEL_16:
    v12 = *(char **)v12;
  }
  Status = v8 != 0 ? 0xC0000002 : 0;
  if ( v8 )
    goto LABEL_26;
  v2 = a2;
LABEL_20:
  if ( !v8 )
  {
    Status = 0;
    goto LABEL_26;
  }
  if ( v12 == v11 )
  {
    Status = -1073741637;
    goto LABEL_26;
  }
  AttachedDeviceReference = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)v6);
  VmpReleaseDevices(a1);
  Irp = IoMakeAssociatedIrp(*(PIRP *)&MasterIrp->Flags, AttachedDeviceReference->StackSize + 1);
  v17 = Irp;
  if ( Irp )
  {
    Mdl = IoAllocateMdl(v9, Length, 0, 0, Irp);
    v19 = Mdl;
    if ( Mdl )
    {
      IoBuildPartialMdl(*(PMDL *)(*(_QWORD *)&MasterIrp->Flags + 8LL), Mdl, v9, Length);
      CurrentStackLocation = v17->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)v25;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)(v25 + 16);
      *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(v25 + 32);
      CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(v25 + 48);
      CurrentStackLocation[-1].Parameters.Read.Length = Length;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (LONGLONG)Flink;
      --v17->CurrentLocation;
      --v17->Tail.Overlay.CurrentStackLocation;
      Status = IoPropagateIrpExtensionEx(
                 v2,
                 v17,
                 (char *)v9
               - *(unsigned int *)(*(_QWORD *)(*(_QWORD *)&MasterIrp->Flags + 8LL) + 44LL)
               - *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&MasterIrp->Flags + 8LL) + 32LL),
                 0xFFFFFFFFLL);
      if ( Status >= 0 )
      {
        IoForwardIrpSynchronously(AttachedDeviceReference, v17);
        Status = v17->IoStatus.Status;
        if ( Status >= 0 )
          _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)&MasterIrp->Flags + 56LL), v17->IoStatus.Information);
      }
      IoFreeMdl(v19);
    }
    else
    {
      Status = -1073741670;
    }
    IoFreeIrp(v17);
  }
  else
  {
    Status = -1073741670;
  }
  ObfDereferenceObject(AttachedDeviceReference);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400136b8  mov     rax, rsp
0x1400136bb  mov     [rax+8], rbx
0x1400136bf  mov     [rax+10h], rdx
0x1400136c3  push    rbp
0x1400136c4  push    rsi
0x1400136c5  push    rdi
0x1400136c6  push    r12
0x1400136c8  push    r13
0x1400136ca  push    r14
0x1400136cc  push    r15
0x1400136ce  sub     rsp, 60h
0x1400136d2  mov     byte ptr [rax+20h], 0
0x1400136d6  mov     rbx, rdx
0x1400136d9  mov     rax, [rdx+0B8h]
0x1400136e0  mov     rbp, rcx
0x1400136e3  cmp     dword ptr [rax+10h], 30h ; '0'
0x1400136e7  jnb     short loc_1400136F3
0x1400136e9  mov     eax, 0C000000Dh
0x1400136ee  jmp     loc_140013995
0x1400136f3  mov     rsi, [rdx+18h]
0x1400136f7  xor     edi, edi
0x1400136f9  mov     rax, [rsi]
0x1400136fc  mov     [rsp+98h+var_50], rax
0x140013701  mov     rax, [rsi+8]
0x140013705  mov     [rsp+98h+var_58], rax
0x14001370a  mov     rax, [rsi+10h]
0x14001370e  mov     rax, [rax+0B8h]
0x140013715  mov     [rsp+98h+var_48], rax
0x14001371a  mov     al, [rax]
0x14001371c  sub     al, 3
0x14001371e  cmp     al, 1
0x140013720  jbe     short loc_140013731
0x140013722  xor     eax, eax
0x140013724  xor     r15b, r15b
0x140013727  xor     r13d, r13d
0x14001372a  mov     [rsp+98h+var_60], rax
0x14001372f  jmp     short loc_140013744
0x140013731  mov     rax, [rsi+20h]
0x140013735  mov     r15b, 1
0x140013738  mov     r13, [rsi+18h]
0x14001373c  mov     [rsp+98h+var_60], rax
0x140013741  mov     eax, [rsi+28h]
0x140013744  mov     [rsp+98h+Length], eax
0x140013748  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x14001374d  xor     al, al
0x14001374f  lea     r12, [rbp+0D0h]
0x140013756  mov     r14, [r12]
0x14001375a  mov     [rsp+98h+arg_10], al
0x140013761  cmp     r14, r12
0x140013764  jz      loc_140013815
0x14001376a  lea     rdi, [r14-20h]
0x14001376e  cmp     byte ptr [rdi+1AAh], 0
0x140013775  jz      short loc_1400137B0
0x140013777  mov     rcx, [rdi+1B0h]
0x14001377e  test    rcx, rcx
0x140013781  jz      short loc_1400137E6
0x140013783  mov     rax, [rbp+188h]
0x14001378a  lea     r8, [rsp+98h+arg_18]
0x140013792  mov     rdx, [rsp+98h+var_58]
0x140013797  mov     rax, [rax+0C8h]
0x14001379e  call    _guard_dispatch_icall
0x1400137a3  test    al, al
0x1400137a5  jnz     short loc_1400137BE
0x1400137a7  mov     al, [rsp+98h+arg_10]
0x1400137ae  jmp     short loc_1400137E6
0x1400137b0  mov     rcx, [rsp+98h+var_50]
0x1400137b5  cmp     [rdi+158h], rcx
0x1400137bc  jnz     short loc_1400137E6
0x1400137be  mov     al, [rdi+9Ch]
0x1400137c4  test    al, al
0x1400137c6  jz      short loc_1400137F5
0x1400137c8  mov     rcx, rdi
0x1400137cb  call    VmpIsSafeForDirectAccess
0x1400137d0  test    al, al
0x1400137d2  jz      short loc_1400137EE
0x1400137d4  cmp     byte ptr [rdi+1AAh], 0
0x1400137db  mov     al, 1
0x1400137dd  mov     [rsp+98h+arg_10], al
0x1400137e4  jz      short loc_14001380C
0x1400137e6  mov     r14, [r14]
0x1400137e9  jmp     loc_140013761
0x1400137ee  mov     ebx, 0C0000022h
0x1400137f3  jmp     short loc_14001382A
0x1400137f5  mov     al, r15b
0x1400137f8  neg     al
0x1400137fa  sbb     ebx, ebx
0x1400137fc  and     ebx, 0C0000002h
0x140013802  jl      short loc_14001382A
0x140013804  mov     rbx, [rsp+98h+arg_8]
0x14001380c  test    r15b, r15b
0x14001380f  jnz     short loc_140013820
0x140013811  xor     ebx, ebx
0x140013813  jmp     short loc_14001382A
0x140013815  test    al, al
0x140013817  jnz     short loc_14001380C
0x140013819  mov     ebx, 0C000000Dh
0x14001381e  jmp     short loc_14001382A
0x140013820  cmp     r14, r12
0x140013823  jnz     short loc_140013837
0x140013825  mov     ebx, 0C00000BBh
0x14001382a  mov     rcx, rbp; struct VM_ROOT_EXTENSION *
0x14001382d  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140013832  jmp     loc_140013993
0x140013837  mov     rcx, [rdi]; DeviceObject
0x14001383a  call    cs:__imp_IoGetAttachedDeviceReference
0x140013841  nop     dword ptr [rax+rax+00h]
0x140013846  mov     rcx, rbp; struct VM_ROOT_EXTENSION *
0x140013849  mov     r14, rax
0x14001384c  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140013851  mov     dl, [r14+4Ch]
0x140013855  mov     rcx, [rsi+10h]; Irp
0x140013859  inc     dl; StackSize
0x14001385b  call    cs:__imp_IoMakeAssociatedIrp
0x140013862  nop     dword ptr [rax+rax+00h]
0x140013867  mov     rdi, rax
0x14001386a  test    rax, rax
0x14001386d  jz      loc_14001397F
0x140013873  mov     r15d, [rsp+98h+Length]
0x140013878  xor     r9d, r9d; ChargeQuota
0x14001387b  mov     edx, r15d; Length
0x14001387e  mov     [rsp+98h+Irp], rax; Irp
0x140013883  xor     r8d, r8d; SecondaryBuffer
0x140013886  mov     rcx, r13; VirtualAddress
0x140013889  call    cs:__imp_IoAllocateMdl
0x140013890  nop     dword ptr [rax+rax+00h]
0x140013895  mov     rbp, rax
0x140013898  test    rax, rax
0x14001389b  jz      loc_140013969
0x1400138a1  mov     rcx, [rsi+10h]
0x1400138a5  mov     r9d, r15d; Length
0x1400138a8  mov     r8, r13; VirtualAddress
0x1400138ab  mov     rdx, rax; TargetMdl
0x1400138ae  mov     rcx, [rcx+8]; SourceMdl
0x1400138b2  call    cs:__imp_IoBuildPartialMdl
0x1400138b9  nop     dword ptr [rax+rax+00h]
0x1400138be  mov     rcx, [rdi+0B8h]
0x1400138c5  or      r9d, 0FFFFFFFFh
0x1400138c9  mov     rax, [rsp+98h+var_48]
0x1400138ce  mov     rdx, rdi
0x1400138d1  movups  xmm0, xmmword ptr [rax]
0x1400138d4  movups  xmmword ptr [rcx-48h], xmm0
0x1400138d8  movups  xmm1, xmmword ptr [rax+10h]
0x1400138dc  movups  xmmword ptr [rcx-38h], xmm1
0x1400138e0  movups  xmm0, xmmword ptr [rax+20h]
0x1400138e4  movups  xmmword ptr [rcx-28h], xmm0
0x1400138e8  movsd   xmm1, qword ptr [rax+30h]
0x1400138ed  mov     rax, [rsp+98h+var_60]
0x1400138f2  movsd   qword ptr [rcx-18h], xmm1
0x1400138f7  mov     [rcx-40h], r15d
0x1400138fb  mov     [rcx-30h], rax
0x1400138ff  dec     byte ptr [rdi+43h]
0x140013902  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14001390a  mov     rax, [rsi+10h]
0x14001390e  mov     rcx, [rax+8]
0x140013912  mov     eax, [rcx+2Ch]
0x140013915  sub     r13, rax
0x140013918  sub     r13, [rcx+20h]
0x14001391c  mov     rcx, rbx
0x14001391f  mov     r8, r13
0x140013922  call    cs:__imp_IoPropagateIrpExtensionEx
0x140013929  nop     dword ptr [rax+rax+00h]
0x14001392e  mov     ebx, eax
0x140013930  test    eax, eax
0x140013932  js      short loc_140013958
0x140013934  mov     rdx, rdi; Irp
0x140013937  mov     rcx, r14; DeviceObject
0x14001393a  call    cs:__imp_IoForwardIrpSynchronously
0x140013941  nop     dword ptr [rax+rax+00h]
0x140013946  mov     ebx, [rdi+30h]
0x140013949  test    ebx, ebx
0x14001394b  js      short loc_140013958
0x14001394d  mov     rcx, [rsi+10h]
0x140013951  mov     eax, [rdi+38h]
0x140013954  lock add [rcx+38h], eax
0x140013958  mov     rcx, rbp; Mdl
0x14001395b  call    cs:__imp_IoFreeMdl
0x140013962  nop     dword ptr [rax+rax+00h]
0x140013967  jmp     short loc_14001396E
0x140013969  mov     ebx, 0C000009Ah
0x14001396e  mov     rcx, rdi; Irp
0x140013971  call    cs:__imp_IoFreeIrp
0x140013978  nop     dword ptr [rax+rax+00h]
0x14001397d  jmp     short loc_140013984
0x14001397f  mov     ebx, 0C000009Ah
0x140013984  mov     rcx, r14; Object
0x140013987  call    cs:__imp_ObfDereferenceObject
0x14001398e  nop     dword ptr [rax+rax+00h]
0x140013993  mov     eax, ebx
0x140013995  mov     rbx, [rsp+98h+arg_0]
0x14001399d  add     rsp, 60h
0x1400139a1  pop     r15
0x1400139a3  pop     r14
0x1400139a5  pop     r13
0x1400139a7  pop     r12
0x1400139a9  pop     rdi
0x1400139aa  pop     rsi
0x1400139ab  pop     rbp
0x1400139ac  retn
```
