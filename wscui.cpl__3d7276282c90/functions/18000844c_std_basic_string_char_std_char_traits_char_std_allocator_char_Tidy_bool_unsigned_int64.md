# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x18000844c`
- end: `0x1800084a4`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800082ac`
- `0x18000838c`
- `0x18000afa7`

## callees

- `0x180001cc8`
- `0x180003372`
- `0x18000844c`

## pseudocode

```c
void __fastcall std::string::_Tidy(void **a1, char a2, size_t a3)
{
  void *v5; // rsi

  if ( a2 && (unsigned __int64)a1[3] >= 0x10 )
  {
    v5 = *a1;
    if ( a3 )
      memcpy_0(a1, *a1, a3);
    operator delete(v5);
  }
  a1[3] = (void *)15;
  a1[2] = (void *)a3;
  *((_BYTE *)a1 + a3) = 0;
}

```

## disassembly

```asm
0x18000844c  mov     [rsp+arg_0], rbx
0x180008451  mov     [rsp+arg_8], rsi
0x180008456  push    rdi
0x180008457  sub     rsp, 20h
0x18000845b  mov     rdi, r8
0x18000845e  mov     rbx, rcx
0x180008461  test    dl, dl
0x180008463  jz      short loc_180008484
0x180008465  cmp     qword ptr [rcx+18h], 10h
0x18000846a  jb      short loc_180008484
0x18000846c  mov     rsi, [rcx]
0x18000846f  test    r8, r8
0x180008472  jz      short loc_18000847C
0x180008474  mov     rdx, rsi; Src
0x180008477  call    memcpy_0
0x18000847c  mov     rcx, rsi; Block
0x18000847f  call    ??3@YAXPEAX@Z
0x180008484  mov     rsi, [rsp+28h+arg_8]
0x180008489  mov     qword ptr [rbx+18h], 0Fh
0x180008491  mov     [rbx+10h], rdi
0x180008495  mov     byte ptr [rdi+rbx], 0
0x180008499  mov     rbx, [rsp+28h+arg_0]
0x18000849e  add     rsp, 20h
0x1800084a2  pop     rdi
0x1800084a3  retn
```
