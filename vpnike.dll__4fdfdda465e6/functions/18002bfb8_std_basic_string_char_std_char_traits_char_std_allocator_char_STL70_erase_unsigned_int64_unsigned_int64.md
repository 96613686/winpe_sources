# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x18002bfb8`
- end: `0x18002c040`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b600`

## callees

- `0x1800015d0`
- `0x18002bfb8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002c015`
- `msvcrt!memmove_s` at `0x18002c015`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax

  v3 = a3;
  if ( a1[3] < a2 )
    std::_String_base::_Xran();
  v6 = a1[3] - a2;
  if ( v6 < a3 )
    v3 = a1[3] - a2;
  if ( v3 )
  {
    v7 = a1[4];
    v8 = a1 + 1;
    if ( v7 < 0x10 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + a2, v7 - a2, (char *)v10 + a2 + v3, v6 - v3);
    v11 = a1[3] - v3;
    if ( a1[4] >= 0x10u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_BYTE *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18002bfb8  push    rbx
0x18002bfba  push    rbp
0x18002bfbb  push    rsi
0x18002bfbc  push    rdi
0x18002bfbd  sub     rsp, 28h
0x18002bfc1  mov     rsi, r8
0x18002bfc4  mov     rbp, rdx
0x18002bfc7  mov     rbx, rcx
0x18002bfca  cmp     [rcx+18h], rdx
0x18002bfce  jnb     short loc_18002BFD5
0x18002bfd0  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18002bfd5  mov     r9, [rbx+18h]
0x18002bfd9  sub     r9, rbp
0x18002bfdc  cmp     r9, rsi
0x18002bfdf  cmovb   rsi, r9
0x18002bfe3  test    rsi, rsi
0x18002bfe6  jz      short loc_18002C034
0x18002bfe8  mov     rdx, [rbx+20h]
0x18002bfec  lea     rdi, [rbx+8]
0x18002bff0  cmp     rdx, 10h
0x18002bff4  jb      short loc_18002BFFE
0x18002bff6  mov     rax, [rdi]
0x18002bff9  mov     rcx, rax
0x18002bffc  jmp     short loc_18002C004
0x18002bffe  mov     rax, rdi
0x18002c001  mov     rcx, rdi
0x18002c004  lea     r8, [rcx+rbp]
0x18002c008  sub     r9, rsi; SourceSize
0x18002c00b  add     r8, rsi; Source
0x18002c00e  lea     rcx, [rax+rbp]; Destination
0x18002c012  sub     rdx, rbp; DestinationSize
0x18002c015  call    cs:__imp_memmove_s
0x18002c01b  mov     rax, [rbx+18h]
0x18002c01f  sub     rax, rsi
0x18002c022  cmp     qword ptr [rbx+20h], 10h
0x18002c027  jb      short loc_18002C02C
0x18002c029  mov     rdi, [rdi]
0x18002c02c  mov     [rbx+18h], rax
0x18002c030  mov     byte ptr [rax+rdi], 0
0x18002c034  mov     rax, rbx
0x18002c037  add     rsp, 28h
0x18002c03b  pop     rdi
0x18002c03c  pop     rsi
0x18002c03d  pop     rbp
0x18002c03e  pop     rbx
0x18002c03f  retn
```
