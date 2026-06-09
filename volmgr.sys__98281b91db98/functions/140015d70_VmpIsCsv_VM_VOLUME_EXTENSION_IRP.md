# VmpIsCsv(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015d70`
- end: `0x140015d96`
- name: `?VmpIsCsv@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `38`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140015d70`

## pseudocode

```c
__int64 __fastcall VmpIsCsv(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 result; // rax

  if ( !a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length )
    return 3221225485LL;
  result = 0;
  LOBYTE(a2->AssociatedIrp.MasterIrp->Type) = 0;
  a2->IoStatus.Information = 1;
  return result;
}

```

## disassembly

```asm
0x140015d70  mov     rax, [rdx+0B8h]
0x140015d77  cmp     dword ptr [rax+8], 1
0x140015d7b  jb      short loc_140015D90
0x140015d7d  mov     rcx, [rdx+18h]
0x140015d81  xor     eax, eax
0x140015d83  mov     byte ptr [rcx], 0
0x140015d86  mov     qword ptr [rdx+38h], 1
0x140015d8e  retn
0x140015d90  mov     eax, 0C000000Dh
0x140015d95  retn
```
