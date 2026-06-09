# LISTENER_CHANNEL::LISTENER_CHANNEL(void)

- ea: `0x18000aa04`
- end: `0x18000aae8`
- name: `??0LISTENER_CHANNEL@@QEAA@XZ`
- size: `228`
- prototype: `LISTENER_CHANNEL *__fastcall(LISTENER_CHANNEL *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b708`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000aa5f`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000aa5f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa22`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa39`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa4c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa22`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa39`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000aa4c`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000aa91`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000aa91`

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
0x18000aa04  push    rbx
0x18000aa06  sub     rsp, 20h
0x18000aa0a  lea     rax, ??_7LISTENER_CHANNEL@@6B@; const LISTENER_CHANNEL::`vftable'
0x18000aa11  mov     dword ptr [rcx+0Ch], 1
0x18000aa18  mov     [rcx], rax
0x18000aa1b  mov     rbx, rcx
0x18000aa1e  add     rcx, 10h
0x18000aa22  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000aa29  nop     dword ptr [rax+rax+00h]
0x18000aa2e  lea     rcx, [rbx+50h]
0x18000aa32  mov     dword ptr [rbx+48h], 0
0x18000aa39  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000aa40  nop     dword ptr [rax+rax+00h]
0x18000aa45  lea     rcx, [rbx+88h]
0x18000aa4c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000aa53  nop     dword ptr [rax+rax+00h]
0x18000aa58  lea     rcx, [rbx+0C0h]
0x18000aa5f  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000aa66  nop     dword ptr [rax+rax+00h]
0x18000aa6b  lea     rcx, [rbx+118h]
0x18000aa72  mov     dword ptr [rbx+0F0h], 0
0x18000aa7c  mov     dword ptr [rbx+108h], 0
0x18000aa86  mov     qword ptr [rbx+110h], 0
0x18000aa91  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000aa98  nop     dword ptr [rax+rax+00h]
0x18000aa9d  lea     rax, [rbx+128h]
0x18000aaa4  mov     qword ptr [rbx+120h], 0
0x18000aaaf  mov     qword ptr [rbx+138h], 0
0x18000aaba  mov     dword ptr [rbx+8], 53515057h
0x18000aac1  mov     [rax+8], rax
0x18000aac5  mov     [rax], rax
0x18000aac8  mov     rax, rbx
0x18000aacb  mov     qword ptr [rbx+0F8h], 0
0x18000aad6  mov     qword ptr [rbx+100h], 0
0x18000aae1  add     rsp, 20h
0x18000aae5  pop     rbx
0x18000aae6  retn
```
