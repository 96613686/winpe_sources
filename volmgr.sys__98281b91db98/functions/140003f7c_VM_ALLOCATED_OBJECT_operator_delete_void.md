# VM_ALLOCATED_OBJECT::operator delete(void *)

- ea: `0x140003f7c`
- end: `0x140003f99`
- name: `??3VM_ALLOCATED_OBJECT@@SAXPEAX@Z`
- size: `29`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000e300`

## callees

- `0x140003f7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003f87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003f87`

## pseudocode

```c
void __fastcall VM_ALLOCATED_OBJECT::operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x140003f7c  sub     rsp, 28h
0x140003f80  test    rcx, rcx
0x140003f83  jz      short loc_140003F93
0x140003f85  xor     edx, edx; Tag
0x140003f87  call    cs:__imp_ExFreePoolWithTag
0x140003f8e  nop     dword ptr [rax+rax+00h]
0x140003f93  add     rsp, 28h
0x140003f97  retn
```
