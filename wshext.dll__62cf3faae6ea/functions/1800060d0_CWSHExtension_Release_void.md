# CWSHExtension::Release(void)

- ea: `0x1800060d0`
- end: `0x1800060e0`
- name: `?Release@CWSHExtension@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CWSHExtension *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800060f0`
- `0x180006100`
- `0x180006110`
- `0x180006120`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::Release(CWSHExtension *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x1800060d0  mov     rcx, [rcx+30h]
0x1800060d4  mov     rax, [rcx]
0x1800060d7  mov     rax, [rax+10h]
0x1800060db  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
