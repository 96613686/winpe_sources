# CWMResizeDMO::Release(void)

- ea: `0x180008550`
- end: `0x180008563`
- name: `?Release@CWMResizeDMO@@UEAAKXZ`
- size: `19`
- prototype: `unsigned int __fastcall(CWMResizeDMO *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008570`
- `0x180008590`
- `0x1800085b0`
- `0x1800085d0`

## callees

- `0x180016010`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::Release(CWMResizeDMO *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 53) + 16LL))(*((_QWORD *)this + 53));
}

```

## disassembly

```asm
0x180008550  mov     rcx, [rcx+1A8h]
0x180008557  mov     rax, [rcx]
0x18000855a  mov     rax, [rax+10h]
0x18000855e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
