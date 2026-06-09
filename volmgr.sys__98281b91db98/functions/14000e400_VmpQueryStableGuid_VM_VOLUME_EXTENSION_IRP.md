# VmpQueryStableGuid(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14000e400`
- end: `0x14000e47e`
- name: `?VmpQueryStableGuid@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x14000e400`

## pseudocode

```c
__int64 __fastcall VmpQueryStableGuid(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *, _QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1)
                                                                                               + 392LL)
                                                                                   + 104LL))(
             *((_QWORD *)a1 + 54),
             a2,
             *(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL),
             a2);
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 0x10 )
    return 3221225485LL;
  if ( (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 43) + 64LL) + 40LL) & 0x200) != 0 )
    return 3221225473LL;
  *(_OWORD *)&a2->AssociatedIrp.MasterIrp->Type = *(_OWORD *)((char *)a1 + 408);
  a2->IoStatus.Information = 16;
  return 0;
}

```

## disassembly

```asm
0x14000e400  sub     rsp, 28h
0x14000e404  cmp     byte ptr [rcx+1AAh], 0
0x14000e40b  mov     r9, rdx
0x14000e40e  jz      short loc_14000E431
0x14000e410  mov     rax, [rcx+8]
0x14000e414  mov     rcx, [rcx+1B0h]
0x14000e41b  mov     r8, [rax+188h]
0x14000e422  mov     rax, [r8+68h]
0x14000e426  call    _guard_dispatch_icall
0x14000e42b  add     rsp, 28h
0x14000e42f  retn
0x14000e431  mov     rax, [rdx+0B8h]
0x14000e438  cmp     dword ptr [rax+8], 10h
0x14000e43c  jnb     short loc_14000E445
0x14000e43e  mov     eax, 0C000000Dh
0x14000e443  jmp     short loc_14000E478
0x14000e445  mov     rax, [rcx+158h]
0x14000e44c  mov     rdx, [rax+40h]
0x14000e450  mov     eax, [rdx+28h]
0x14000e453  bt      eax, 9
0x14000e457  jnb     short loc_14000E460
0x14000e459  mov     eax, 0C0000001h
0x14000e45e  jmp     short loc_14000E478
0x14000e460  mov     rax, [r9+18h]
0x14000e464  movups  xmm0, xmmword ptr [rcx+198h]
0x14000e46b  movups  xmmword ptr [rax], xmm0
0x14000e46e  mov     qword ptr [r9+38h], 10h
0x14000e476  xor     eax, eax
0x14000e478  add     rsp, 28h
0x14000e47c  retn
```
