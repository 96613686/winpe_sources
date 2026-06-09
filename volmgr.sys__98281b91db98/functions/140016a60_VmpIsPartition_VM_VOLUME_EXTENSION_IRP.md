# VmpIsPartition(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140016a60`
- end: `0x140016a92`
- name: `?VmpIsPartition@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x140016a60`

## pseudocode

```c
__int64 __fastcall VmpIsPartition(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD, struct _IRP *))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(
             *((_QWORD *)a1 + 54),
             a2);
  else
    return 0;
}

```

## disassembly

```asm
0x140016a60  sub     rsp, 28h
0x140016a64  cmp     byte ptr [rcx+1AAh], 0
0x140016a6b  jnz     short loc_140016A75
0x140016a6d  xor     eax, eax
0x140016a6f  add     rsp, 28h
0x140016a73  retn
0x140016a75  mov     rax, [rcx+8]
0x140016a79  mov     rcx, [rcx+1B0h]
0x140016a80  mov     r8, [rax+188h]
0x140016a87  mov     rax, [r8+68h]
0x140016a8b  call    _guard_dispatch_icall
0x140016a90  jmp     short loc_140016A6F
```
