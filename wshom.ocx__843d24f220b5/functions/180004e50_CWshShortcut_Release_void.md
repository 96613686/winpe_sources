# CWshShortcut::Release(void)

- ea: `0x180004e50`
- end: `0x180004e60`
- name: `?Release@CWshShortcut@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CWshShortcut *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007540`
- `0x180007550`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWshShortcut::Release(CWshShortcut *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x180004e50  mov     rcx, [rcx+10h]
0x180004e54  mov     rax, [rcx]
0x180004e57  mov     rax, [rax+10h]
0x180004e5b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
