# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800024c4`
- end: `0x1800025b8`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002730`
- `0x1800027a0`
- `0x180002830`

## callees

- `0x1800021a8`
- `0x180002330`
- `0x1800023b8`
- `0x1800024c4`
- `0x180002988`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::string::_Xlen(v5);
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800024c4  mov     [rsp+arg_0], rbx
0x1800024c9  mov     [rsp+arg_8], rsi
0x1800024ce  push    rdi
0x1800024cf  sub     rsp, 20h
0x1800024d3  mov     rdi, r8
0x1800024d6  mov     rsi, rdx
0x1800024d9  mov     rbx, rcx
0x1800024dc  test    rdx, rdx
0x1800024df  jz      short loc_18000252D
0x1800024e1  cmp     qword ptr [rcx+18h], 10h
0x1800024e6  jb      short loc_1800024ED
0x1800024e8  mov     rax, [rcx]
0x1800024eb  jmp     short loc_1800024F0
0x1800024ed  mov     rax, rbx
0x1800024f0  cmp     rsi, rax
0x1800024f3  jb      short loc_18000252D
0x1800024f5  cmp     qword ptr [rcx+18h], 10h
0x1800024fa  jb      short loc_1800024FF
0x1800024fc  mov     rcx, [rcx]
0x1800024ff  add     rcx, [rbx+10h]
0x180002503  cmp     rcx, rsi
0x180002506  jbe     short loc_18000252D
0x180002508  cmp     qword ptr [rbx+18h], 10h
0x18000250d  jb      short loc_180002514
0x18000250f  mov     rax, [rbx]
0x180002512  jmp     short loc_180002517
0x180002514  mov     rax, rbx
0x180002517  sub     rsi, rax
0x18000251a  mov     r9, rdi
0x18000251d  mov     r8, rsi
0x180002520  mov     rdx, rbx
0x180002523  mov     rcx, rbx; void *
0x180002526  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000252b  jmp     short loc_18000259F
0x18000252d  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002531  ja      short loc_1800025AF
0x180002533  cmp     [rbx+18h], rdi
0x180002537  jnb     short loc_180002559
0x180002539  mov     r8, [rbx+10h]
0x18000253d  mov     rdx, rdi
0x180002540  mov     rcx, rbx; Src
0x180002543  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002548  test    rdi, rdi
0x18000254b  jz      short loc_18000259C
0x18000254d  cmp     qword ptr [rbx+18h], 10h
0x180002552  jb      short loc_180002577
0x180002554  mov     rcx, [rbx]
0x180002557  jmp     short loc_18000257A
0x180002559  test    rdi, rdi
0x18000255c  jnz     short loc_18000254D
0x18000255e  cmp     qword ptr [rbx+18h], 10h
0x180002563  jb      short loc_18000256A
0x180002565  mov     rax, [rbx]
0x180002568  jmp     short loc_18000256D
0x18000256a  mov     rax, rbx
0x18000256d  and     qword ptr [rbx+10h], 0
0x180002572  mov     byte ptr [rax], 0
0x180002575  jmp     short loc_18000259C
0x180002577  mov     rcx, rbx; void *
0x18000257a  mov     r8, rdi; Size
0x18000257d  mov     rdx, rsi; Src
0x180002580  call    memcpy_0
0x180002585  cmp     qword ptr [rbx+18h], 10h
0x18000258a  jb      short loc_180002591
0x18000258c  mov     rax, [rbx]
0x18000258f  jmp     short loc_180002594
0x180002591  mov     rax, rbx
0x180002594  mov     [rbx+10h], rdi
0x180002598  mov     byte ptr [rax+rdi], 0
0x18000259c  mov     rax, rbx
0x18000259f  mov     rbx, [rsp+28h+arg_0]
0x1800025a4  mov     rsi, [rsp+28h+arg_8]
0x1800025a9  add     rsp, 20h
0x1800025ad  pop     rdi
0x1800025ae  retn
0x1800025af  mov     rcx, rbx
0x1800025b2  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
