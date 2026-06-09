# VmpReferenceDependantVolume(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x1400139b4`
- end: `0x140013b98`
- name: `?VmpReferenceDependantVolume@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140002ea0`

## callees

- `0x140003170`
- `0x140003990`
- `0x140005090`
- `0x1400139b4`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140013ada`
- `ntoskrnl!ObfReferenceObject` at `0x140013b58`
- `ntoskrnl!ObfReferenceObject` at `0x140013ada`
- `ntoskrnl!ObfReferenceObject` at `0x140013b58`
- `ntoskrnl!ExAllocatePool2` at `0x140013a92`
- `ntoskrnl!ExAllocatePool2` at `0x140013a92`

## pseudocode

```c
__int64 __fastcall VmpReferenceDependantVolume(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IRP *MasterIrp; // rdi
  __int64 **v6; // rbx
  __int64 *v7; // r12
  __int64 **v8; // rsi
  int v9; // ebp
  __int64 **i; // r15
  __int64 Pool2; // rax
  unsigned int v12; // ebx
  _DWORD *v13; // rcx
  __int64 *v15; // rbx
  __int64 v16; // rbp
  char v17; // [rsp+68h] [rbp+10h] BYREF
  PMDL MdlAddress; // [rsp+70h] [rbp+18h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v17 = 0;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x18 || CurrentStackLocation->Parameters.Read.Length < 8 )
    return 3221225485LL;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v6 = 0;
  v7 = *(__int64 **)&MasterIrp->Type;
  MdlAddress = MasterIrp->MdlAddress;
  VmpAcquireDevices(a1);
  v8 = (__int64 **)((char *)a1 + 208);
  v9 = 0;
  for ( i = (__int64 **)*((_QWORD *)a1 + 26); i != v8; i = (__int64 **)*i )
  {
    v6 = i - 4;
    if ( *((_BYTE *)i + 394) )
    {
      if ( v6[54] && *((_BYTE *)v6 + 156) )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *, PMDL, char *))(*((_QWORD *)a1 + 49) + 200LL))(
               v6[54],
               MdlAddress,
               &v17) )
        {
          ++v9;
        }
      }
    }
    else if ( v6[43] == v7 )
    {
      if ( *((_BYTE *)v6 + 156) )
        ++v9;
      break;
    }
  }
  Pool2 = ExAllocatePool2(258, 8 * v9 + 8, 538987862);
  *(_QWORD *)&MasterIrp->Type = Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
LABEL_21:
    VmpReleaseDevices((struct _KMUTANT *)a1);
    return v12;
  }
  a2->IoStatus.Information = 8;
  if ( i != v8 )
  {
    v13 = *(_DWORD **)&MasterIrp->Type;
    if ( *((_BYTE *)v6 + 156) )
    {
      *v13 = 1;
      *(_QWORD *)(*(_QWORD *)&MasterIrp->Type + 8LL) = *v6;
      ObfReferenceObject(*v6);
    }
    else
    {
      *v13 = 0;
    }
    v12 = 0;
    goto LABEL_21;
  }
  v15 = *v8;
  v16 = 0;
  while ( v15 != (__int64 *)v8 )
  {
    if ( *((_BYTE *)v15 + 394)
      && v15[50]
      && *((_BYTE *)v15 + 124)
      && (*(unsigned __int8 (__fastcall **)(__int64, PMDL, __int64 *))(*((_QWORD *)a1 + 49) + 208LL))(
           v15[50],
           MdlAddress,
           v7) )
    {
      *(_QWORD *)(*(_QWORD *)&MasterIrp->Type + 8 * v16 + 8) = *(v15 - 4);
      v16 = (unsigned int)(v16 + 1);
      ObfReferenceObject((PVOID)*(v15 - 4));
    }
    v15 = (__int64 *)*v15;
  }
  **(_DWORD **)&MasterIrp->Type = v16;
  VmpReleaseDevices((struct _KMUTANT *)a1);
  return 0;
}

```

## disassembly

```asm
0x1400139b4  mov     [rsp+arg_0], rbx
0x1400139b9  push    rbp
0x1400139ba  push    rsi
0x1400139bb  push    rdi
0x1400139bc  push    r12
0x1400139be  push    r13
0x1400139c0  push    r14
0x1400139c2  push    r15
0x1400139c4  sub     rsp, 20h
0x1400139c8  mov     rax, [rdx+0B8h]
0x1400139cf  mov     r13, rdx
0x1400139d2  mov     [rsp+58h+arg_8], 0
0x1400139d7  mov     r14, rcx
0x1400139da  cmp     dword ptr [rax+10h], 18h
0x1400139de  jb      loc_140013B7D
0x1400139e4  cmp     dword ptr [rax+8], 8
0x1400139e8  jb      loc_140013B7D
0x1400139ee  mov     rdi, [rdx+18h]
0x1400139f2  xor     ebx, ebx
0x1400139f4  mov     rax, [rdi+8]
0x1400139f8  mov     r12, [rdi]
0x1400139fb  mov     [rsp+58h+arg_10], rax
0x140013a00  call    ?VmpAcquireDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpAcquireDevices(VM_ROOT_EXTENSION *)
0x140013a05  lea     rsi, [r14+0D0h]
0x140013a0c  xor     ebp, ebp
0x140013a0e  mov     r15, [rsi]
0x140013a11  cmp     r15, rsi
0x140013a14  jz      short loc_140013A7D
0x140013a16  lea     rbx, [r15-20h]
0x140013a1a  cmp     byte ptr [rbx+1AAh], 0
0x140013a21  jz      short loc_140013A63
0x140013a23  cmp     qword ptr [rbx+1B0h], 0
0x140013a2b  jz      short loc_140013A6C
0x140013a2d  mov     al, [rbx+9Ch]
0x140013a33  test    al, al
0x140013a35  jz      short loc_140013A6C
0x140013a37  mov     rax, [r14+188h]
0x140013a3e  lea     r8, [rsp+58h+arg_8]
0x140013a43  mov     rdx, [rsp+58h+arg_10]
0x140013a48  mov     rcx, [rbx+1B0h]
0x140013a4f  mov     rax, [rax+0C8h]
0x140013a56  call    _guard_dispatch_icall
0x140013a5b  test    al, al
0x140013a5d  jz      short loc_140013A6C
0x140013a5f  inc     ebp
0x140013a61  jmp     short loc_140013A6C
0x140013a63  cmp     [rbx+158h], r12
0x140013a6a  jz      short loc_140013A71
0x140013a6c  mov     r15, [r15]
0x140013a6f  jmp     short loc_140013A11
0x140013a71  mov     al, [rbx+9Ch]
0x140013a77  test    al, al
0x140013a79  jz      short loc_140013A7D
0x140013a7b  inc     ebp
0x140013a7d  lea     eax, ds:8[rbp*8]
0x140013a84  mov     ecx, 102h
0x140013a89  movsxd  rdx, eax
0x140013a8c  mov     r8d, 20204D56h
0x140013a92  call    cs:__imp_ExAllocatePool2
0x140013a99  nop     dword ptr [rax+rax+00h]
0x140013a9e  mov     [rdi], rax
0x140013aa1  test    rax, rax
0x140013aa4  jnz     short loc_140013AAD
0x140013aa6  mov     ebx, 0C000009Ah
0x140013aab  jmp     short loc_140013AF0
0x140013aad  mov     qword ptr [r13+38h], 8
0x140013ab5  cmp     r15, rsi
0x140013ab8  jz      short loc_140013AFF
0x140013aba  mov     al, [rbx+9Ch]
0x140013ac0  mov     rcx, [rdi]
0x140013ac3  test    al, al
0x140013ac5  jz      short loc_140013AE8
0x140013ac7  mov     dword ptr [rcx], 1
0x140013acd  mov     rdx, [rdi]
0x140013ad0  mov     rax, [rbx]
0x140013ad3  mov     [rdx+8], rax
0x140013ad7  mov     rcx, [rbx]; Object
0x140013ada  call    cs:__imp_ObfReferenceObject
0x140013ae1  nop     dword ptr [rax+rax+00h]
0x140013ae6  jmp     short loc_140013AEE
0x140013ae8  mov     dword ptr [rcx], 0
0x140013aee  xor     ebx, ebx
0x140013af0  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140013af3  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140013af8  mov     eax, ebx
0x140013afa  jmp     loc_140013B82
0x140013aff  mov     rbx, [rsi]
0x140013b02  xor     ebp, ebp
0x140013b04  jmp     short loc_140013B67
0x140013b06  cmp     byte ptr [rbx+18Ah], 0
0x140013b0d  jz      short loc_140013B64
0x140013b0f  cmp     qword ptr [rbx+190h], 0
0x140013b17  jz      short loc_140013B64
0x140013b19  mov     al, [rbx+7Ch]
0x140013b1c  test    al, al
0x140013b1e  jz      short loc_140013B64
0x140013b20  mov     rax, [r14+188h]
0x140013b27  mov     r8, r12
0x140013b2a  mov     rdx, [rsp+58h+arg_10]
0x140013b2f  mov     rcx, [rbx+190h]
0x140013b36  mov     rax, [rax+0D0h]
0x140013b3d  call    _guard_dispatch_icall
0x140013b42  test    al, al
0x140013b44  jz      short loc_140013B64
0x140013b46  mov     rcx, [rdi]
0x140013b49  mov     rax, [rbx-20h]
0x140013b4d  mov     [rcx+rbp*8+8], rax
0x140013b52  inc     ebp
0x140013b54  mov     rcx, [rbx-20h]; Object
0x140013b58  call    cs:__imp_ObfReferenceObject
0x140013b5f  nop     dword ptr [rax+rax+00h]
0x140013b64  mov     rbx, [rbx]
0x140013b67  cmp     rbx, rsi
0x140013b6a  jnz     short loc_140013B06
0x140013b6c  mov     rax, [rdi]
0x140013b6f  mov     rcx, r14; struct VM_ROOT_EXTENSION *
0x140013b72  mov     [rax], ebp
0x140013b74  call    ?VmpReleaseDevices@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpReleaseDevices(VM_ROOT_EXTENSION *)
0x140013b79  xor     eax, eax
0x140013b7b  jmp     short loc_140013B82
0x140013b7d  mov     eax, 0C000000Dh
0x140013b82  mov     rbx, [rsp+58h+arg_0]
0x140013b87  add     rsp, 20h
0x140013b8b  pop     r15
0x140013b8d  pop     r14
0x140013b8f  pop     r13
0x140013b91  pop     r12
0x140013b93  pop     rdi
0x140013b94  pop     rsi
0x140013b95  pop     rbp
0x140013b96  retn
```
