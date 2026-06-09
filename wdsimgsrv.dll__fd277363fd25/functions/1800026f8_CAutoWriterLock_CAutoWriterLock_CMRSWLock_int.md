# CAutoWriterLock::CAutoWriterLock(CMRSWLock *,int)

- ea: `0x1800026f8`
- end: `0x180002724`
- name: `??0CAutoWriterLock@@QEAA@PEAVCMRSWLock@@H@Z`
- size: `44`
- prototype: `CAutoWriterLock *__fastcall(CAutoWriterLock *__hidden this, struct CMRSWLock *, int)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007700`
- `0x180008f9c`
- `0x180009490`
- `0x18000c69c`

## import_xrefs

- `WdsCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x18000270b`
- `WdsCommonLib!?WriterLock@CMRSWLock@@QEAAXXZ` at `0x18000270b`

## pseudocode

```c
CAutoWriterLock *__fastcall CAutoWriterLock::CAutoWriterLock(CAutoWriterLock *this, struct CMRSWLock *a2)
{
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = a2;
  CMRSWLock::WriterLock(a2);
  ++*((_DWORD *)this + 2);
  return this;
}

```

## disassembly

```asm
0x1800026f8  push    rbx
0x1800026fa  sub     rsp, 20h
0x1800026fe  and     dword ptr [rcx+8], 0
0x180002702  mov     rbx, rcx
0x180002705  mov     [rcx], rdx
0x180002708  mov     rcx, rdx
0x18000270b  call    cs:__imp_?WriterLock@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterLock(void)
0x180002712  nop     dword ptr [rax+rax+00h]
0x180002717  inc     dword ptr [rbx+8]
0x18000271a  mov     rax, rbx
0x18000271d  add     rsp, 20h
0x180002721  pop     rbx
0x180002722  retn
```
