# CWinHost::CWinHost(void)

- ea: `0x14000566c`
- end: `0x140005733`
- name: `??0CWinHost@@QEAA@XZ`
- size: `199`
- prototype: `CWinHost *__fastcall(CWinHost *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002310`
- `0x140006c88`

## callees

- `0x140001488`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005704`
- `KERNEL32!GetCurrentThreadId` at `0x140005704`

## pseudocode

```c
CWinHost *__fastcall CWinHost::CWinHost(CWinHost *this)
{
  CWinHost *result; // rax

  *(_QWORD *)this = &CHost::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *(_QWORD *)((char *)this + 60) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  CCriticalSection::CCriticalSection((CWinHost *)((char *)this + 696));
  *((_WORD *)this + 40) = 0;
  *((_DWORD *)this + 14) = GetCurrentThreadId();
  *(_QWORD *)this = &CWinHost::`vftable';
  result = this;
  g_pHost = this;
  *((_QWORD *)this + 93) = 0;
  return result;
}

```

## disassembly

```asm
0x14000566c  mov     [rsp+arg_0], rbx
0x140005671  push    rdi
0x140005672  sub     rsp, 20h
0x140005676  xor     edi, edi
0x140005678  lea     rax, ??_7CHost@@6B@; const CHost::`vftable'
0x14000567f  mov     [rcx], rax
0x140005682  mov     rbx, rcx
0x140005685  mov     [rcx+8], edi
0x140005688  mov     [rcx+10h], rdi
0x14000568c  mov     [rcx+18h], rdi
0x140005690  mov     [rcx+20h], rdi
0x140005694  mov     [rcx+28h], rdi
0x140005698  mov     [rcx+30h], rdi
0x14000569c  mov     [rcx+3Ch], rdi
0x1400056a0  mov     [rcx+44h], edi
0x1400056a3  mov     [rcx+48h], rdi
0x1400056a7  mov     [rcx+260h], rdi
0x1400056ae  mov     [rcx+268h], rdi
0x1400056b5  mov     [rcx+270h], rdi
0x1400056bc  mov     [rcx+278h], rdi
0x1400056c3  mov     [rcx+280h], rdi
0x1400056ca  mov     [rcx+288h], rdi
0x1400056d1  mov     [rcx+290h], rdi
0x1400056d8  mov     [rcx+298h], rdi
0x1400056df  mov     [rcx+2A0h], rdi
0x1400056e6  mov     [rcx+2A8h], rdi
0x1400056ed  mov     [rcx+2B0h], rdi
0x1400056f4  add     rcx, 2B8h; this
0x1400056fb  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x140005700  mov     [rbx+50h], di
0x140005704  call    cs:__imp_GetCurrentThreadId
0x14000570a  mov     [rbx+38h], eax
0x14000570d  lea     rax, ??_7CWinHost@@6B@; const CWinHost::`vftable'
0x140005714  mov     [rbx], rax
0x140005717  mov     rax, rbx
0x14000571a  mov     cs:?g_pHost@@3PEAVCHost@@EA, rbx; CHost * g_pHost
0x140005721  mov     [rbx+2E8h], rdi
0x140005728  mov     rbx, [rsp+28h+arg_0]
0x14000572d  add     rsp, 20h
0x140005731  pop     rdi
0x140005732  retn
```
