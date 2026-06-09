# PROTOCOL_MANAGER_ENTRY::PROTOCOL_MANAGER_ENTRY(void)

- ea: `0x180009428`
- end: `0x1800094b4`
- name: `??0PROTOCOL_MANAGER_ENTRY@@QEAA@XZ`
- size: `140`
- prototype: `PROTOCOL_MANAGER_ENTRY *__fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009630`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800094a5`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800094a5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000943f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009459`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000943f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009459`

## pseudocode

```c
PROTOCOL_MANAGER_ENTRY *__fastcall PROTOCOL_MANAGER_ENTRY::PROTOCOL_MANAGER_ENTRY(PROTOCOL_MANAGER_ENTRY *this)
{
  STRU::STRU((PROTOCOL_MANAGER_ENTRY *)((char *)this + 16), (unsigned __int16 *)this + 36, 0x20u);
  STRU::STRU((PROTOCOL_MANAGER_ENTRY *)((char *)this + 136), (unsigned __int16 *)this + 96, 0x20u);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_DWORD *)this + 79) = 0;
  CReaderWriterLock3::CReaderWriterLock3((PROTOCOL_MANAGER_ENTRY *)((char *)this + 320));
  return this;
}

```

## disassembly

```asm
0x180009428  push    rbx
0x18000942a  sub     rsp, 20h
0x18000942e  mov     rbx, rcx
0x180009431  lea     rdx, [rcx+48h]
0x180009435  add     rcx, 10h
0x180009439  mov     r8d, 20h ; ' '
0x18000943f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009445  lea     rdx, [rbx+0C0h]
0x18000944c  mov     r8d, 20h ; ' '
0x180009452  lea     rcx, [rbx+88h]
0x180009459  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000945f  xor     eax, eax
0x180009461  lea     rcx, [rbx+140h]
0x180009468  mov     [rbx+100h], rax
0x18000946f  mov     [rbx+108h], rax
0x180009476  mov     [rbx+110h], rax
0x18000947d  mov     [rbx+118h], rax
0x180009484  mov     [rbx+120h], rax
0x18000948b  mov     [rbx+128h], rax
0x180009492  mov     [rbx+130h], rax
0x180009499  mov     [rbx+138h], eax
0x18000949f  mov     [rbx+13Ch], eax
0x1800094a5  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x1800094ab  mov     rax, rbx
0x1800094ae  add     rsp, 20h
0x1800094b2  pop     rbx
0x1800094b3  retn
```
