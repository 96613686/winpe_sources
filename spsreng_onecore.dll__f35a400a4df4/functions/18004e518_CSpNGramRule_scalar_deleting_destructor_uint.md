# CSpNGramRule::`scalar deleting destructor'(uint)

- ea: `0x18004e518`
- end: `0x18004e549`
- name: `??_GCSpNGramRule@@QEAAPEAXI@Z`
- size: `49`
- prototype: `void *__fastcall(CSpNGramRule *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004e26c`
- `0x1800516b0`
- `0x180052dfc`

## callees

- `0x1800034d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e525`

## pseudocode

```c
LPVOID *__fastcall CSpNGramRule::`scalar deleting destructor'(LPVOID *this)
{
  CoTaskMemFree(this[15]);
  this[15] = 0;
  operator delete(this, 0x2F8u);
  return this;
}

```

## disassembly

```asm
0x18004e518  push    rbx
0x18004e51a  sub     rsp, 20h
0x18004e51e  mov     rbx, rcx
0x18004e521  mov     rcx, [rcx+78h]; pv
0x18004e525  call    cs:__imp_CoTaskMemFree
0x18004e52b  mov     edx, 2F8h; unsigned __int64
0x18004e530  mov     qword ptr [rbx+78h], 0
0x18004e538  mov     rcx, rbx; void *
0x18004e53b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004e540  mov     rax, rbx
0x18004e543  add     rsp, 20h
0x18004e547  pop     rbx
0x18004e548  retn
```
