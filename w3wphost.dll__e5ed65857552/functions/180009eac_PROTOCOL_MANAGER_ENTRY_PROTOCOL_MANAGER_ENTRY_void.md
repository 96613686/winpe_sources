# PROTOCOL_MANAGER_ENTRY::PROTOCOL_MANAGER_ENTRY(void)

- ea: `0x180009eac`
- end: `0x180009f4b`
- name: `??0PROTOCOL_MANAGER_ENTRY@@QEAA@XZ`
- size: `159`
- prototype: `PROTOCOL_MANAGER_ENTRY *__fastcall(PROTOCOL_MANAGER_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a0f4`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180009f35`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180009f35`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009ec3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009ee3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009ec3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009ee3`

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
0x180009eac  push    rbx
0x180009eae  sub     rsp, 20h
0x180009eb2  mov     rbx, rcx
0x180009eb5  lea     rdx, [rcx+48h]
0x180009eb9  add     rcx, 10h
0x180009ebd  mov     r8d, 20h ; ' '
0x180009ec3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009eca  nop     dword ptr [rax+rax+00h]
0x180009ecf  lea     rdx, [rbx+0C0h]
0x180009ed6  mov     r8d, 20h ; ' '
0x180009edc  lea     rcx, [rbx+88h]
0x180009ee3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009eea  nop     dword ptr [rax+rax+00h]
0x180009eef  xor     eax, eax
0x180009ef1  lea     rcx, [rbx+140h]
0x180009ef8  mov     [rbx+100h], rax
0x180009eff  mov     [rbx+108h], rax
0x180009f06  mov     [rbx+110h], rax
0x180009f0d  mov     [rbx+118h], rax
0x180009f14  mov     [rbx+120h], rax
0x180009f1b  mov     [rbx+128h], rax
0x180009f22  mov     [rbx+130h], rax
0x180009f29  mov     [rbx+138h], eax
0x180009f2f  mov     [rbx+13Ch], eax
0x180009f35  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180009f3c  nop     dword ptr [rax+rax+00h]
0x180009f41  mov     rax, rbx
0x180009f44  add     rsp, 20h
0x180009f48  pop     rbx
0x180009f49  retn
```
