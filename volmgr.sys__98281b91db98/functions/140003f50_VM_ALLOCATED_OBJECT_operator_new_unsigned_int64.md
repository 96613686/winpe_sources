# VM_ALLOCATED_OBJECT::operator new(unsigned __int64)

- ea: `0x140003f50`
- end: `0x140003f76`
- name: `??2VM_ALLOCATED_OBJECT@@SAPEAX_K@Z`
- size: `38`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400127f0`
- `0x140012b3c`
- `0x14001462c`
- `0x140014838`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140003f64`
- `ntoskrnl!ExAllocatePool2` at `0x140003f64`

## pseudocode

```c
__int64 __fastcall VM_ALLOCATED_OBJECT::operator new()
{
  return ExAllocatePool2(258, 40, 538987862);
}

```

## disassembly

```asm
0x140003f50  sub     rsp, 28h
0x140003f54  mov     edx, 28h ; '('
0x140003f59  mov     r8d, 20204D56h
0x140003f5f  mov     ecx, 102h
0x140003f64  call    cs:__imp_ExAllocatePool2
0x140003f6b  nop     dword ptr [rax+rax+00h]
0x140003f70  add     rsp, 28h
0x140003f74  retn
```
