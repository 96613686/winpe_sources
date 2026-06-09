# CWMResizeDMO::AddRef(void)

- ea: `0x180002f40`
- end: `0x180002f53`
- name: `?AddRef@CWMResizeDMO@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMResizeDMO *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f60`
- `0x180002f80`
- `0x180002fa0`
- `0x180002fc0`

## callees

- `0x180016010`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::AddRef(CWMResizeDMO *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 53) + 8LL))(*((_QWORD *)this + 53));
}

```

## disassembly

```asm
0x180002f40  mov     rcx, [rcx+1A8h]
0x180002f47  mov     rax, [rcx]
0x180002f4a  mov     rax, [rax+8]
0x180002f4e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
