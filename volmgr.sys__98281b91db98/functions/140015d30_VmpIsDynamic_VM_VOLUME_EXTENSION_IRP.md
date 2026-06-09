# VmpIsDynamic(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015d30`
- end: `0x140015d5f`
- name: `?VmpIsDynamic@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x140015d30`

## pseudocode

```c
__int64 __fastcall VmpIsDynamic(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 result; // rax

  if ( !a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length )
    return 3221225485LL;
  LOBYTE(a2->AssociatedIrp.MasterIrp->Type) = *((_BYTE *)a1 + 426) != 0;
  result = 0;
  a2->IoStatus.Information = 1;
  return result;
}

```

## disassembly

```asm
0x140015d30  mov     rax, [rdx+0B8h]
0x140015d37  cmp     dword ptr [rax+8], 1
0x140015d3b  jb      short loc_140015D59
0x140015d3d  cmp     byte ptr [rcx+1AAh], 0
0x140015d44  mov     rax, [rdx+18h]
0x140015d48  setnz   cl
0x140015d4b  mov     [rax], cl
0x140015d4d  xor     eax, eax
0x140015d4f  mov     qword ptr [rdx+38h], 1
0x140015d57  retn
0x140015d59  mov     eax, 0C000000Dh
0x140015d5e  retn
```
