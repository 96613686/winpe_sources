# VmpIsRedirectionSupported(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140012508`
- end: `0x14001251b`
- name: `?VmpIsRedirectionSupported@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `19`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002ea0`

## pseudocode

```c
__int64 __fastcall VmpIsRedirectionSupported(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  return a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 0x18 ? 0xC000000D : 0;
}

```

## disassembly

```asm
0x140012508  mov     rax, [rdx+0B8h]
0x14001250f  cmp     dword ptr [rax+10h], 18h
0x140012513  sbb     eax, eax
0x140012515  and     eax, 0C000000Dh
0x14001251a  retn
```
