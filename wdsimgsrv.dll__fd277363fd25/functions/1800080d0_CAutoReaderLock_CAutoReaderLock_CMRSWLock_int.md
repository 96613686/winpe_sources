# CAutoReaderLock::CAutoReaderLock(CMRSWLock *,int)

- ea: `0x1800080d0`
- end: `0x1800080fc`
- name: `??0CAutoReaderLock@@QEAA@PEAVCMRSWLock@@H@Z`
- size: `44`
- prototype: `CAutoReaderLock *__fastcall(CAutoReaderLock *__hidden this, struct CMRSWLock *, int)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000891c`
- `0x1800092ec`
- `0x18000b858`

## import_xrefs

- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800080e3`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800080e3`

## pseudocode

```c
CAutoReaderLock *__fastcall CAutoReaderLock::CAutoReaderLock(CAutoReaderLock *this, struct CMRSWLock *a2)
{
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = a2;
  CMRSWLock::ReaderLock(a2);
  ++*((_DWORD *)this + 2);
  return this;
}

```

## disassembly

```asm
0x1800080d0  push    rbx
0x1800080d2  sub     rsp, 20h
0x1800080d6  and     dword ptr [rcx+8], 0
0x1800080da  mov     rbx, rcx
0x1800080dd  mov     [rcx], rdx
0x1800080e0  mov     rcx, rdx
0x1800080e3  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800080ea  nop     dword ptr [rax+rax+00h]
0x1800080ef  inc     dword ptr [rbx+8]
0x1800080f2  mov     rax, rbx
0x1800080f5  add     rsp, 20h
0x1800080f9  pop     rbx
0x1800080fa  retn
```
