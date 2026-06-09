# VmpPrepareForCriticalIo(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140015d10`
- end: `0x140015d23`
- name: `?VmpPrepareForCriticalIo@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `19`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## pseudocode

```c
__int64 __fastcall VmpPrepareForCriticalIo(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  return a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 8 ? 0xC000000D : 0;
}

```

## disassembly

```asm
0x140015d10  mov     rax, [rdx+0B8h]
0x140015d17  cmp     dword ptr [rax+10h], 8
0x140015d1b  sbb     eax, eax
0x140015d1d  and     eax, 0C000000Dh
0x140015d22  retn
```
