# VmpFreeBCStream(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140012128`
- end: `0x140012186`
- name: `?VmpFreeBCStream@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x140012128`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140012170`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140012170`

## pseudocode

```c
__int64 __fastcall VmpFreeBCStream(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  if ( *((_BYTE *)a1 + 426) )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)a1 + 1) + 392LL) + 104LL))(*((_QWORD *)a1 + 54));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation->MinorFunction = 4;
  CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 3004424;
  IoForwardIrpSynchronously(*((PDEVICE_OBJECT *)a1 + 46), a2);
  return (unsigned int)a2->IoStatus.Status;
}

```

## disassembly

```asm
0x140012128  push    rbx
0x14001212a  sub     rsp, 20h
0x14001212e  cmp     byte ptr [rcx+1AAh], 0
0x140012135  mov     rbx, rdx
0x140012138  jz      short loc_140012157
0x14001213a  mov     rax, [rcx+8]
0x14001213e  mov     rcx, [rcx+1B0h]
0x140012145  mov     r8, [rax+188h]
0x14001214c  mov     rax, [r8+68h]
0x140012150  call    _guard_dispatch_icall
0x140012155  jmp     short loc_14001217F
0x140012157  mov     rax, [rdx+0B8h]
0x14001215e  mov     byte ptr [rax+1], 4
0x140012162  mov     dword ptr [rax+18h], 2DD808h
0x140012169  mov     rcx, [rcx+170h]; DeviceObject
0x140012170  call    cs:__imp_IoForwardIrpSynchronously
0x140012177  nop     dword ptr [rax+rax+00h]
0x14001217c  mov     eax, [rbx+30h]
0x14001217f  add     rsp, 20h
0x140012183  pop     rbx
0x140012184  retn
```
