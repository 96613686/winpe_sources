# CVssDiffAreaCandidate::`scalar deleting destructor'(uint)

- ea: `0x18001f3a4`
- end: `0x18001f3d3`
- name: `??_GCVssDiffAreaCandidate@@QEAAPEAXI@Z`
- size: `47`
- prototype: `LPVOID *__fastcall(LPVOID *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001f1b4`
- `0x1800200c0`

## callees

- `0x180001674`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f3b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f3b0`

## pseudocode

```c
LPVOID *__fastcall CVssDiffAreaCandidate::`scalar deleting destructor'(LPVOID *this)
{
  CoTaskMemFree(*this);
  *this = 0;
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001f3a4  push    rbx
0x18001f3a6  sub     rsp, 20h
0x18001f3aa  mov     rbx, rcx
0x18001f3ad  mov     rcx, [rcx]; pv
0x18001f3b0  call    cs:__imp_CoTaskMemFree
0x18001f3b6  mov     edx, 30h ; '0'
0x18001f3bb  mov     qword ptr [rbx], 0
0x18001f3c2  mov     rcx, rbx; Block
0x18001f3c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f3ca  mov     rax, rbx
0x18001f3cd  add     rsp, 20h
0x18001f3d1  pop     rbx
0x18001f3d2  retn
```
