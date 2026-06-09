# VmpAllocateBCStream(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14000fbf8`
- end: `0x14000fd3f`
- name: `?VmpAllocateBCStream@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005050`
- `0x140005090`
- `0x14000fbf8`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000fce9`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000fce9`

## pseudocode

```c
__int64 __fastcall VmpAllocateBCStream(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 result; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IRP *MasterIrp; // rbx
  struct _IRP *v6; // rax
  __int128 v7; // [rsp+20h] [rbp-20h] BYREF
  struct _LIST_ENTRY *Flink; // [rsp+30h] [rbp-10h]

  Flink = 0;
  v7 = 0;
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(*((_QWORD *)a1 + 54));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x28 )
    return 3221225485LL;
  if ( CurrentStackLocation->Parameters.Read.Length < 0x10 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type != 1 )
    return 3221225485LL;
  v6 = MasterIrp->AssociatedIrp.MasterIrp;
  if ( *(_QWORD *)&MasterIrp->Flags > (unsigned __int64)v6 || (unsigned __int64)v6 >= *((_QWORD *)a1 + 50) )
    return 3221225485LL;
  LODWORD(v7) = 1;
  *(_QWORD *)((char *)&v7 + 4) = *(_QWORD *)(&MasterIrp->Size + 1);
  WORD6(v7) = WORD2(MasterIrp->MdlAddress);
  Flink = MasterIrp->ThreadListEntry.Flink;
  CurrentStackLocation->MinorFunction = 4;
  CurrentStackLocation->Parameters.Read.Length = 16;
  CurrentStackLocation->Parameters.Create.Options = 24;
  CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 3004420;
  a2->AssociatedIrp.MasterIrp = (struct _IRP *)&v7;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 46), a2);
  result = (unsigned int)a2->IoStatus.Status;
  a2->AssociatedIrp.MasterIrp = MasterIrp;
  if ( (int)result >= 0 )
  {
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_QWORD *)&MasterIrp->Type = v7;
    LODWORD(MasterIrp->MdlAddress) = DWORD2(v7);
    a2->IoStatus.Information = 16;
  }
  return result;
}

```

## disassembly

```asm
0x14000fbf8  mov     [rsp-8+arg_10], rbx
0x14000fbfd  mov     [rsp-8+arg_18], rdi
0x14000fc02  push    rbp
0x14000fc03  mov     rbp, rsp
0x14000fc06  sub     rsp, 40h
0x14000fc0a  mov     rax, cs:__security_cookie
0x14000fc11  xor     rax, rsp
0x14000fc14  mov     [rbp+var_8], rax
0x14000fc18  xor     eax, eax
0x14000fc1a  xorps   xmm0, xmm0
0x14000fc1d  mov     rdi, rdx
0x14000fc20  mov     [rbp+var_10], rax
0x14000fc24  movups  [rbp+var_20], xmm0
0x14000fc28  cmp     [rcx+1AAh], al
0x14000fc2e  jz      short loc_14000FC50
0x14000fc30  mov     rax, [rcx+8]
0x14000fc34  mov     rcx, [rcx+1B0h]
0x14000fc3b  mov     r8, [rax+188h]
0x14000fc42  mov     rax, [r8+68h]
0x14000fc46  call    _guard_dispatch_icall
0x14000fc4b  jmp     loc_14000FD22
0x14000fc50  mov     rdx, [rdx+0B8h]
0x14000fc57  cmp     dword ptr [rdx+10h], 28h ; '('
0x14000fc5b  jb      loc_14000FD1D
0x14000fc61  cmp     dword ptr [rdx+8], 10h
0x14000fc65  jb      loc_14000FD1D
0x14000fc6b  mov     rbx, [rdi+18h]
0x14000fc6f  cmp     dword ptr [rbx], 1
0x14000fc72  jnz     loc_14000FD1D
0x14000fc78  mov     rax, [rbx+18h]
0x14000fc7c  cmp     [rbx+10h], rax
0x14000fc80  ja      loc_14000FD1D
0x14000fc86  cmp     rax, [rcx+190h]
0x14000fc8d  jnb     loc_14000FD1D
0x14000fc93  mov     dword ptr [rbp+var_20], 1
0x14000fc9a  mov     eax, [rbx+4]
0x14000fc9d  mov     dword ptr [rbp+var_20+4], eax
0x14000fca0  mov     eax, [rbx+8]
0x14000fca3  mov     dword ptr [rbp+var_20+8], eax
0x14000fca6  mov     al, [rbx+0Ch]
0x14000fca9  mov     byte ptr [rbp+var_20+0Ch], al
0x14000fcac  mov     al, [rbx+0Dh]
0x14000fcaf  mov     byte ptr [rbp+var_20+0Dh], al
0x14000fcb2  mov     eax, [rbx+20h]
0x14000fcb5  mov     dword ptr [rbp+var_10], eax
0x14000fcb8  mov     eax, [rbx+24h]
0x14000fcbb  mov     dword ptr [rbp+var_10+4], eax
0x14000fcbe  lea     rax, [rbp+var_20]
0x14000fcc2  mov     byte ptr [rdx+1], 4
0x14000fcc6  mov     dword ptr [rdx+8], 10h
0x14000fccd  mov     dword ptr [rdx+10h], 18h
0x14000fcd4  mov     dword ptr [rdx+18h], 2DD804h
0x14000fcdb  mov     rdx, rdi; Irp
0x14000fcde  mov     [rdi+18h], rax
0x14000fce2  mov     rcx, [rcx+170h]; DeviceObject
0x14000fce9  call    cs:__imp_IoForwardIrpSynchronously
0x14000fcf0  nop     dword ptr [rax+rax+00h]
0x14000fcf5  mov     eax, [rdi+30h]
0x14000fcf8  mov     [rdi+18h], rbx
0x14000fcfc  test    eax, eax
0x14000fcfe  js      short loc_14000FD22
0x14000fd00  xorps   xmm0, xmm0
0x14000fd03  movups  xmmword ptr [rbx], xmm0
0x14000fd06  mov     rcx, qword ptr [rbp+var_20]
0x14000fd0a  mov     [rbx], rcx
0x14000fd0d  mov     ecx, dword ptr [rbp+var_20+8]
0x14000fd10  mov     [rbx+8], ecx
0x14000fd13  mov     qword ptr [rdi+38h], 10h
0x14000fd1b  jmp     short loc_14000FD22
0x14000fd1d  mov     eax, 0C000000Dh
0x14000fd22  mov     rcx, [rbp+var_8]
0x14000fd26  xor     rcx, rsp; StackCookie
0x14000fd29  call    __security_check_cookie
0x14000fd2e  mov     rbx, [rsp+40h+arg_10]
0x14000fd33  mov     rdi, [rsp+40h+arg_18]
0x14000fd38  add     rsp, 40h
0x14000fd3c  pop     rbp
0x14000fd3d  retn
```
