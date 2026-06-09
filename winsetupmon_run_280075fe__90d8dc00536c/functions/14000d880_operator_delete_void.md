# operator delete(void *)

- ea: `0x14000d880`
- end: `0x14000d8a0`
- name: `??3@YAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001f4e0`
- `0x14001f5e0`

## callees

- `0x14000d880`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d88e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d88e`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0x6E6D7377u);
}

```

## disassembly

```asm
0x14000d880  sub     rsp, 28h
0x14000d884  test    rcx, rcx
0x14000d887  jz      short loc_14000D89A
0x14000d889  mov     edx, 6E6D7377h; Tag
0x14000d88e  call    cs:__imp_ExFreePoolWithTag
0x14000d895  nop     dword ptr [rax+rax+00h]
0x14000d89a  add     rsp, 28h
0x14000d89e  retn
```
