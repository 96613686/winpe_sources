# CConsentUI::CConsentUI(void)

- ea: `0x180009944`
- end: `0x180009a20`
- name: `??0CConsentUI@@QEAA@XZ`
- size: `220`
- prototype: `CConsentUI *__fastcall(CConsentUI *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b20`
- `0x180007490`
- `0x180007a70`
- `0x18000a70c`

## callees

- `0x180005c80`

## pseudocode

```c
CConsentUI *__fastcall CConsentUI::CConsentUI(CConsentUI *this)
{
  CConsentUI *result; // rax

  *((_QWORD *)this + 7) = -1;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 4;
  *(_QWORD *)((char *)this + 140) = 0;
  *(_QWORD *)((char *)this + 148) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 22) = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((_QWORD *)this + 23);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((_QWORD *)this + 27);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((_QWORD *)this + 31);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((_QWORD *)this + 35);
  result = this;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 84) = 0;
  return result;
}

```

## disassembly

```asm
0x180009944  mov     [rsp+arg_0], rbx
0x180009949  push    rdi
0x18000994a  sub     rsp, 20h
0x18000994e  xor     edi, edi
0x180009950  mov     qword ptr [rcx+38h], 0FFFFFFFFFFFFFFFFh
0x180009958  mov     [rcx], edi
0x18000995a  xor     eax, eax
0x18000995c  mov     [rcx+8], rdi
0x180009960  mov     rbx, rcx
0x180009963  mov     [rcx+10h], rdi
0x180009967  mov     [rcx+18h], rdi
0x18000996b  mov     [rcx+20h], rdi
0x18000996f  mov     [rcx+28h], rdi
0x180009973  mov     [rcx+30h], rdi
0x180009977  mov     [rcx+40h], rdi
0x18000997b  mov     [rcx+48h], edi
0x18000997e  mov     [rcx+50h], rdi
0x180009982  mov     [rcx+58h], rdi
0x180009986  mov     [rcx+60h], rdi
0x18000998a  mov     [rcx+68h], rdi
0x18000998e  mov     [rcx+70h], rdi
0x180009992  mov     [rcx+78h], edi
0x180009995  mov     [rcx+80h], rdi
0x18000999c  mov     dword ptr [rcx+88h], 4
0x1800099a6  mov     [rcx+8Ch], rax
0x1800099ad  mov     [rcx+94h], rax
0x1800099b4  mov     [rcx+0A0h], rdi
0x1800099bb  mov     [rcx+0A8h], edi
0x1800099c1  mov     [rcx+0B0h], rax
0x1800099c8  add     rcx, 0B8h; void *
0x1800099cf  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800099d4  lea     rcx, [rbx+0D8h]; void *
0x1800099db  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800099e0  lea     rcx, [rbx+0F8h]; void *
0x1800099e7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800099ec  lea     rcx, [rbx+118h]; void *
0x1800099f3  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800099f8  mov     rax, rbx
0x1800099fb  mov     [rbx+138h], rdi
0x180009a02  mov     [rbx+140h], edi
0x180009a08  mov     [rbx+148h], rdi
0x180009a0f  mov     [rbx+150h], edi
0x180009a15  mov     rbx, [rsp+28h+arg_0]
0x180009a1a  add     rsp, 20h
0x180009a1e  pop     rdi
0x180009a1f  retn
```
