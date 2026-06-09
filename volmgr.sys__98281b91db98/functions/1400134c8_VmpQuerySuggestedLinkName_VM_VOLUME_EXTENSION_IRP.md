# VmpQuerySuggestedLinkName(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x1400134c8`
- end: `0x14001358b`
- name: `?VmpQuerySuggestedLinkName@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x1400134c8`

## pseudocode

```c
__int64 __fastcall VmpQuerySuggestedLinkName(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 v3; // rcx
  unsigned int v4; // edx
  struct _IRP *MasterIrp; // rax

  if ( *((_BYTE *)a1 + 426) )
  {
    v3 = *((_QWORD *)a1 + 54);
    if ( v3 )
      return (*(unsigned int (__fastcall **)(__int64, struct _IRP *, _QWORD, struct _IRP *))(*((_QWORD *)VmRootExtension
                                                                                             + 49)
                                                                                           + 104LL))(
               v3,
               a2,
               *((_QWORD *)VmRootExtension + 49),
               a2);
    return (unsigned int)-1073741810;
  }
  if ( !*((_QWORD *)a1 + 43) )
    return (unsigned int)-1073741810;
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 6 )
    return (unsigned int)-1073741811;
  v4 = -1073741275;
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x400100) != 0 )
    return v4;
  if ( *((_BYTE *)a1 + 424) )
  {
    if ( !*((_BYTE *)a1 + 425) )
      return v4;
LABEL_14:
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    v4 = 0;
    *(_DWORD *)&MasterIrp->Type = 0;
    *(&MasterIrp->Size + 1) = 0;
    a2->IoStatus.Information = 6;
    return v4;
  }
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x200000) != 0 && !*((_BYTE *)VmRootExtension + 285) )
    goto LABEL_14;
  return v4;
}

```

## disassembly

```asm
0x1400134c8  sub     rsp, 28h
0x1400134cc  xor     r10d, r10d
0x1400134cf  mov     r9, rdx
0x1400134d2  mov     r8, rcx
0x1400134d5  cmp     [rcx+1AAh], r10b
0x1400134dc  jz      short loc_14001350C
0x1400134de  mov     rcx, [rcx+1B0h]
0x1400134e5  test    rcx, rcx
0x1400134e8  jz      short loc_140013505
0x1400134ea  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400134f1  mov     r8, [rax+188h]
0x1400134f8  mov     rax, [r8+68h]
0x1400134fc  call    _guard_dispatch_icall
0x140013501  mov     edx, eax
0x140013503  jmp     short loc_140013583
0x140013505  mov     edx, 0C000000Eh
0x14001350a  jmp     short loc_140013583
0x14001350c  cmp     [rcx+158h], r10
0x140013513  jz      short loc_140013505
0x140013515  mov     rax, [rdx+0B8h]
0x14001351c  cmp     dword ptr [rax+8], 6
0x140013520  jnb     short loc_140013529
0x140013522  mov     edx, 0C000000Dh
0x140013527  jmp     short loc_140013583
0x140013529  mov     rax, [rcx]
0x14001352c  mov     edx, 0C0000225h
0x140013531  mov     ecx, [rax+30h]
0x140013534  test    ecx, 400100h
0x14001353a  jnz     short loc_140013583
0x14001353c  cmp     [r8+1A8h], r10b
0x140013543  jz      short loc_140013550
0x140013545  cmp     [r8+1A9h], r10b
0x14001354c  jz      short loc_140013583
0x14001354e  jmp     short loc_14001356C
0x140013550  mov     rax, [r8]
0x140013553  mov     ecx, [rax+30h]
0x140013556  bt      ecx, 15h
0x14001355a  jnb     short loc_140013583
0x14001355c  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140013563  cmp     [rax+11Dh], r10b
0x14001356a  jnz     short loc_140013583
0x14001356c  mov     rax, [r9+18h]
0x140013570  xor     ecx, ecx
0x140013572  mov     edx, r10d
0x140013575  mov     [rax], ecx
0x140013577  mov     [rax+4], cx
0x14001357b  mov     qword ptr [r9+38h], 6
0x140013583  mov     eax, edx
0x140013585  add     rsp, 28h
0x140013589  retn
```
