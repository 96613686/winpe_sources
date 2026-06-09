# VMX_ALLOCATED_OBJECT::operator delete(void *)

- ea: `0x140005fb0`
- end: `0x140005fcd`
- name: `??3VMX_ALLOCATED_OBJECT@@SAXPEAX@Z`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `42`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140006c80`
- `0x140006f20`
- `0x140008d00`
- `0x140008d28`
- `0x140008d50`
- `0x140008d78`
- `0x140008da0`
- `0x140008dc8`
- `0x140008df0`
- `0x140008e18`
- `0x140009da0`
- `0x140009de0`
- `0x140009e10`
- `0x140009e38`
- `0x140009e60`
- `0x140009f7c`
- `0x140009fa4`
- `0x14000aa70`
- `0x14000aab0`
- `0x14000aaf0`
- `0x14000ab30`
- `0x14000ab70`
- `0x14000abb0`
- `0x14000abf0`
- `0x14000ac30`
- `0x14000aca0`
- `0x14000ace0`
- `0x14000ad60`
- `0x14000ada0`
- `0x14001a52c`
- `0x14001b30c`
- `0x14001b334`
- `0x14002a3f4`
- `0x140031648`
- `0x140032930`
- `0x140033350`
- `0x1400430ac`
- `0x1400430fc`
- `0x140045ed0`
- `0x14004a59c`
- `0x14004a70c`
- `0x14004b3dc`

## callees

- `0x140005fb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005fbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005fbb`

## pseudocode

```c
void __fastcall VMX_ALLOCATED_OBJECT::operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x140005fb0  sub     rsp, 28h
0x140005fb4  test    rcx, rcx
0x140005fb7  jz      short loc_140005FC7
0x140005fb9  xor     edx, edx; Tag
0x140005fbb  call    cs:__imp_ExFreePoolWithTag
0x140005fc2  nop     dword ptr [rax+rax+00h]
0x140005fc7  add     rsp, 28h
0x140005fcb  retn
```
