# LISTENER_CHANNEL::LISTENER_CHANNEL(void)

- ea: `0x180009e24`
- end: `0x180009ee9`
- name: `??0LISTENER_CHANNEL@@QEAA@XZ`
- size: `197`
- prototype: `LISTENER_CHANNEL *__fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a9b4`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180009e6d`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180009e6d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009e42`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009e53`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009e60`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009e42`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009e53`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180009e60`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180009e99`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180009e99`

## pseudocode

```c
LISTENER_CHANNEL *__fastcall LISTENER_CHANNEL::LISTENER_CHANNEL(LISTENER_CHANNEL *this)
{
  LISTENER_CHANNEL *result; // rax

  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &LISTENER_CHANNEL::`vftable';
  STRU::STRU((LISTENER_CHANNEL *)((char *)this + 16));
  *((_DWORD *)this + 18) = 0;
  STRU::STRU((LISTENER_CHANNEL *)((char *)this + 80));
  STRU::STRU((LISTENER_CHANNEL *)((char *)this + 136));
  BUFFER::BUFFER((LISTENER_CHANNEL *)((char *)this + 192));
  *((_DWORD *)this + 60) = 0;
  *((_DWORD *)this + 66) = 0;
  *((_QWORD *)this + 34) = 0;
  CReaderWriterLock3::CReaderWriterLock3((LISTENER_CHANNEL *)((char *)this + 280));
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 2) = 1397837911;
  *((_QWORD *)this + 38) = (char *)this + 296;
  *((_QWORD *)this + 37) = (char *)this + 296;
  result = this;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x180009e24  push    rbx
0x180009e26  sub     rsp, 20h
0x180009e2a  lea     rax, ??_7LISTENER_CHANNEL@@6B@; const LISTENER_CHANNEL::`vftable'
0x180009e31  mov     dword ptr [rcx+0Ch], 1
0x180009e38  mov     [rcx], rax
0x180009e3b  mov     rbx, rcx
0x180009e3e  add     rcx, 10h
0x180009e42  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009e48  lea     rcx, [rbx+50h]
0x180009e4c  mov     dword ptr [rbx+48h], 0
0x180009e53  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009e59  lea     rcx, [rbx+88h]
0x180009e60  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180009e66  lea     rcx, [rbx+0C0h]
0x180009e6d  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180009e73  lea     rcx, [rbx+118h]
0x180009e7a  mov     dword ptr [rbx+0F0h], 0
0x180009e84  mov     dword ptr [rbx+108h], 0
0x180009e8e  mov     qword ptr [rbx+110h], 0
0x180009e99  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180009e9f  lea     rax, [rbx+128h]
0x180009ea6  mov     qword ptr [rbx+120h], 0
0x180009eb1  mov     qword ptr [rbx+138h], 0
0x180009ebc  mov     dword ptr [rbx+8], 53515057h
0x180009ec3  mov     [rax+8], rax
0x180009ec7  mov     [rax], rax
0x180009eca  mov     rax, rbx
0x180009ecd  mov     qword ptr [rbx+0F8h], 0
0x180009ed8  mov     qword ptr [rbx+100h], 0
0x180009ee3  add     rsp, 20h
0x180009ee7  pop     rbx
0x180009ee8  retn
```
