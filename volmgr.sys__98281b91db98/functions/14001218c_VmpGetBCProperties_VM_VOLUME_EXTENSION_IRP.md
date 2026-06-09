# VmpGetBCProperties(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14001218c`
- end: `0x1400122bf`
- name: `?VmpGetBCProperties@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005050`
- `0x140005090`
- `0x14001218c`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140012249`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140012249`

## pseudocode

```c
__int64 __fastcall VmpGetBCProperties(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  bool v2; // zf
  __int64 result; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rbx
  struct _MDL *v7; // rdx
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-28h]

  v2 = *((_BYTE *)a1 + 426) == 0;
  v8 = 0;
  v9 = 0;
  if ( !v2 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(*((_QWORD *)a1 + 54));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x20 )
    return 3221225485LL;
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 1 )
    return 3221225485LL;
  v7 = *(struct _MDL **)&MasterIrp->Flags;
  if ( MasterIrp->MdlAddress > v7 || (unsigned __int64)v7 >= *((_QWORD *)a1 + 50) )
    return 3221225485LL;
  CurrentStackLocation->Parameters.Read.Length = 32;
  CurrentStackLocation->Parameters.Create.Options = 0;
  CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 2971648;
  a2->AssociatedIrp.MasterIrp = (struct _IRP *)&v8;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 46), a2);
  result = (unsigned int)a2->IoStatus.Status;
  a2->AssociatedIrp.MasterIrp = MasterIrp;
  if ( (int)result >= 0 )
  {
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_OWORD *)&MasterIrp->Flags = 0;
    *(_OWORD *)&MasterIrp->Type = v8;
    *(_OWORD *)&MasterIrp->Flags = v9;
    a2->IoStatus.Information = 32;
  }
  return result;
}

```

## disassembly

```asm
0x14001218c  mov     [rsp+arg_10], rbx
0x140012191  push    rdi
0x140012192  sub     rsp, 50h
0x140012196  mov     rax, cs:__security_cookie
0x14001219d  xor     rax, rsp
0x1400121a0  mov     [rsp+58h+var_18], rax
0x1400121a5  cmp     byte ptr [rcx+1AAh], 0
0x1400121ac  xorps   xmm0, xmm0
0x1400121af  movups  [rsp+58h+var_38], xmm0
0x1400121b4  mov     rdi, rdx
0x1400121b7  movups  [rsp+58h+var_28], xmm0
0x1400121bc  jz      short loc_1400121DE
0x1400121be  mov     rax, [rcx+8]
0x1400121c2  mov     rcx, [rcx+1B0h]
0x1400121c9  mov     r8, [rax+188h]
0x1400121d0  mov     rax, [r8+68h]
0x1400121d4  call    _guard_dispatch_icall
0x1400121d9  jmp     loc_1400122A6
0x1400121de  mov     rax, [rdx+0B8h]
0x1400121e5  cmp     dword ptr [rax+10h], 20h ; ' '
0x1400121e9  jb      loc_1400122A1
0x1400121ef  cmp     dword ptr [rax+8], 20h ; ' '
0x1400121f3  jb      loc_1400122A1
0x1400121f9  mov     rbx, [rdx+18h]
0x1400121fd  cmp     dword ptr [rbx], 1
0x140012200  jnz     loc_1400122A1
0x140012206  mov     rdx, [rbx+10h]
0x14001220a  cmp     [rbx+8], rdx
0x14001220e  ja      loc_1400122A1
0x140012214  cmp     rdx, [rcx+190h]
0x14001221b  jnb     loc_1400122A1
0x140012221  mov     dword ptr [rax+8], 20h ; ' '
0x140012228  mov     rdx, rdi; Irp
0x14001222b  mov     dword ptr [rax+10h], 0
0x140012232  mov     dword ptr [rax+18h], 2D5800h
0x140012239  lea     rax, [rsp+58h+var_38]
0x14001223e  mov     [rdi+18h], rax
0x140012242  mov     rcx, [rcx+170h]; DeviceObject
0x140012249  call    cs:__imp_IoForwardIrpSynchronously
0x140012250  nop     dword ptr [rax+rax+00h]
0x140012255  mov     eax, [rdi+30h]
0x140012258  mov     [rdi+18h], rbx
0x14001225c  test    eax, eax
0x14001225e  js      short loc_1400122A6
0x140012260  xorps   xmm0, xmm0
0x140012263  movups  xmmword ptr [rbx], xmm0
0x140012266  movups  xmmword ptr [rbx+10h], xmm0
0x14001226a  mov     ecx, dword ptr [rsp+58h+var_38]
0x14001226e  mov     [rbx], ecx
0x140012270  mov     ecx, dword ptr [rsp+58h+var_38+4]
0x140012274  mov     [rbx+4], ecx
0x140012277  mov     rcx, qword ptr [rsp+58h+var_38+8]
0x14001227c  mov     [rbx+8], rcx
0x140012280  mov     ecx, dword ptr [rsp+58h+var_28]
0x140012284  mov     [rbx+10h], ecx
0x140012287  mov     rcx, qword ptr [rsp+58h+var_28+8]
0x14001228c  mov     [rbx+18h], rcx
0x140012290  mov     ecx, dword ptr [rsp+58h+var_28+4]
0x140012294  mov     [rbx+14h], ecx
0x140012297  mov     qword ptr [rdi+38h], 20h ; ' '
0x14001229f  jmp     short loc_1400122A6
0x1400122a1  mov     eax, 0C000000Dh
0x1400122a6  mov     rcx, [rsp+58h+var_18]
0x1400122ab  xor     rcx, rsp; StackCookie
0x1400122ae  call    __security_check_cookie
0x1400122b3  mov     rbx, [rsp+58h+arg_10]
0x1400122b8  add     rsp, 50h
0x1400122bc  pop     rdi
0x1400122bd  retn
```
