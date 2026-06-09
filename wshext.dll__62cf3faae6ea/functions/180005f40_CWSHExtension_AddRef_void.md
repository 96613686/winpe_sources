# CWSHExtension::AddRef(void)

- ea: `0x180005f40`
- end: `0x180005f50`
- name: `?AddRef@CWSHExtension@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CWSHExtension *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005f60`
- `0x180005f70`
- `0x180005f80`
- `0x180005f90`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::AddRef(CWSHExtension *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x180005f40  mov     rcx, [rcx+30h]
0x180005f44  mov     rax, [rcx]
0x180005f47  mov     rax, [rax+8]
0x180005f4b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
