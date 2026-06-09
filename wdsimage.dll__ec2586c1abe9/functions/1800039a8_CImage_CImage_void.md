# CImage::CImage(void)

- ea: `0x1800039a8`
- end: `0x180003a57`
- name: `??0CImage@@QEAA@XZ`
- size: `175`
- prototype: `CImage *__fastcall(CImage *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ff0`
- `0x180005920`
- `0x180006090`
- `0x1800081b8`
- `0x1800094b8`
- `0x180009cb4`
- `0x18000a948`
- `0x18000abe0`
- `0x18000c77c`

## callees

- `0x18000fee5`

## pseudocode

```c
CImage *__fastcall CImage::CImage(CImage *this)
{
  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CImage::`vftable';
  *((_DWORD *)this + 4) = 4;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_DWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 52) = 0;
  *((_DWORD *)this + 17) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  memset_0((char *)this + 136, 0, 0xD8u);
  *((_DWORD *)this + 70) = -1;
  return this;
}

```

## disassembly

```asm
0x1800039a8  mov     [rsp+arg_0], rbx
0x1800039ad  push    rdi
0x1800039ae  sub     rsp, 20h
0x1800039b2  mov     dword ptr [rcx+8], 1
0x1800039b9  lea     rax, ??_7CImage@@6B@; const CImage::`vftable'
0x1800039c0  mov     [rcx], rax
0x1800039c3  xorps   xmm0, xmm0
0x1800039c6  xor     eax, eax
0x1800039c8  mov     dword ptr [rcx+10h], 4
0x1800039cf  mov     [rcx+18h], rax
0x1800039d3  mov     rdi, rcx
0x1800039d6  mov     [rcx+58h], rax
0x1800039da  xor     edx, edx; Val
0x1800039dc  mov     [rcx+60h], rax
0x1800039e0  mov     r8d, 0D8h; Size
0x1800039e6  mov     [rcx+68h], rax
0x1800039ea  mov     [rcx+70h], rax
0x1800039ee  mov     [rcx+78h], rax
0x1800039f2  mov     [rcx+80h], rax
0x1800039f9  mov     [rcx+160h], rax
0x180003a00  mov     [rcx+168h], rax
0x180003a07  mov     [rcx+170h], rax
0x180003a0e  mov     [rcx+178h], rax
0x180003a15  mov     [rcx+180h], rax
0x180003a1c  mov     [rcx+188h], rax
0x180003a23  movups  xmmword ptr [rcx+20h], xmm0
0x180003a27  mov     [rcx+30h], eax
0x180003a2a  movups  xmmword ptr [rcx+34h], xmm0
0x180003a2e  mov     [rcx+44h], eax
0x180003a31  movups  xmmword ptr [rcx+48h], xmm0
0x180003a35  add     rcx, 88h; void *
0x180003a3c  call    memset_0
0x180003a41  or      dword ptr [rdi+118h], 0FFFFFFFFh
0x180003a48  mov     rax, rdi
0x180003a4b  mov     rbx, [rsp+28h+arg_0]
0x180003a50  add     rsp, 20h
0x180003a54  pop     rdi
0x180003a55  retn
```
