# CRegSetting::CRegSetting(void)

- ea: `0x180009a30`
- end: `0x180009a71`
- name: `??0CRegSetting@@QEAA@XZ`
- size: `65`
- prototype: `CRegSetting *__fastcall(CRegSetting *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a8f4`
- `0x18000b334`

## callees

- `0x180005c80`
- `0x180009928`

## pseudocode

```c
CRegSetting *__fastcall CRegSetting::CRegSetting(CRegSetting *this)
{
  CRegSetting *result; // rax

  *(_WORD *)this = 0;
  *((_DWORD *)this + 1) = 0;
  utl::vector<unsigned char,utl::allocator<unsigned char>>::vector<unsigned char,utl::allocator<unsigned char>>((char *)this + 8);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((char *)this + 32);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((char *)this + 64);
  result = this;
  *((_QWORD *)this + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180009a30  push    rbx
0x180009a32  sub     rsp, 20h
0x180009a36  mov     word ptr [rcx], 0
0x180009a3b  mov     rbx, rcx
0x180009a3e  mov     dword ptr [rcx+4], 0
0x180009a45  add     rcx, 8
0x180009a49  call    ??0?$vector@EV?$allocator@E@utl@@@utl@@QEAA@XZ; utl::vector<uchar,utl::allocator<uchar>>::vector<uchar,utl::allocator<uchar>>(void)
0x180009a4e  lea     rcx, [rbx+20h]; void *
0x180009a52  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180009a57  lea     rcx, [rbx+40h]; void *
0x180009a5b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180009a60  mov     rax, rbx
0x180009a63  mov     qword ptr [rbx+60h], 0
0x180009a6b  add     rsp, 20h
0x180009a6f  pop     rbx
0x180009a70  retn
```
