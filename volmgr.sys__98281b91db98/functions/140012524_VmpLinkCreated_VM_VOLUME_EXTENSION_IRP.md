# VmpLinkCreated(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140012524`
- end: `0x140012566`
- name: `?VmpLinkCreated@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x140012524`

## pseudocode

```c
__int64 __fastcall VmpLinkCreated(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
             *((_QWORD *)a1 + 54),
             a2);
  else
    return a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options < 4 ? 0xC000000D : 0;
}

```

## disassembly

```asm
0x140012524  sub     rsp, 28h
0x140012528  cmp     byte ptr [rcx+1AAh], 0
0x14001252f  jz      short loc_14001254E
0x140012531  mov     rax, [rcx+8]
0x140012535  mov     rcx, [rcx+1B0h]
0x14001253c  mov     r8, [rax+188h]
0x140012543  mov     rax, [r8+68h]
0x140012547  call    _guard_dispatch_icall
0x14001254c  jmp     short loc_140012560
0x14001254e  mov     rax, [rdx+0B8h]
0x140012555  cmp     dword ptr [rax+10h], 4
0x140012559  sbb     eax, eax
0x14001255b  and     eax, 0C000000Dh
0x140012560  add     rsp, 28h
0x140012564  retn
```
