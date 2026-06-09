# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001820`
- end: `0x180001917`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001aa0`
- `0x180001b10`
- `0x180001ba0`

## callees

- `0x180001518`
- `0x1800016a0`
- `0x180001728`
- `0x180001820`
- `0x1800022e6`

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
0x180001820  mov     [rsp+arg_0], rbx
0x180001825  mov     [rsp+arg_8], rsi
0x18000182a  push    rdi
0x18000182b  sub     rsp, 20h
0x18000182f  mov     rdi, r8
0x180001832  mov     rsi, rdx
0x180001835  mov     rbx, rcx
0x180001838  test    rdx, rdx
0x18000183b  jz      short loc_180001889
0x18000183d  cmp     qword ptr [rcx+18h], 10h
0x180001842  jb      short loc_180001849
0x180001844  mov     rax, [rcx]
0x180001847  jmp     short loc_18000184C
0x180001849  mov     rax, rbx
0x18000184c  cmp     rsi, rax
0x18000184f  jb      short loc_180001889
0x180001851  cmp     qword ptr [rcx+18h], 10h
0x180001856  jb      short loc_18000185B
0x180001858  mov     rcx, [rcx]
0x18000185b  add     rcx, [rbx+10h]
0x18000185f  cmp     rcx, rsi
0x180001862  jbe     short loc_180001889
0x180001864  cmp     qword ptr [rbx+18h], 10h
0x180001869  jb      short loc_180001870
0x18000186b  mov     rax, [rbx]
0x18000186e  jmp     short loc_180001873
0x180001870  mov     rax, rbx
0x180001873  sub     rsi, rax
0x180001876  mov     r9, rdi
0x180001879  mov     r8, rsi
0x18000187c  mov     rdx, rbx
0x18000187f  mov     rcx, rbx; void *
0x180001882  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001887  jmp     short loc_1800018FE
0x180001889  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000188d  ja      short loc_18000190E
0x18000188f  cmp     [rbx+18h], rdi
0x180001893  jnb     short loc_1800018B5
0x180001895  mov     r8, [rbx+10h]
0x180001899  mov     rdx, rdi
0x18000189c  mov     rcx, rbx; Src
0x18000189f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800018a4  test    rdi, rdi
0x1800018a7  jz      short loc_1800018FB
0x1800018a9  cmp     qword ptr [rbx+18h], 10h
0x1800018ae  jb      short loc_1800018D6
0x1800018b0  mov     rcx, [rbx]
0x1800018b3  jmp     short loc_1800018D9
0x1800018b5  test    rdi, rdi
0x1800018b8  jnz     short loc_1800018A9
0x1800018ba  cmp     qword ptr [rbx+18h], 10h
0x1800018bf  jb      short loc_1800018C6
0x1800018c1  mov     rax, [rbx]
0x1800018c4  jmp     short loc_1800018C9
0x1800018c6  mov     rax, rbx
0x1800018c9  mov     qword ptr [rbx+10h], 0
0x1800018d1  mov     byte ptr [rax], 0
0x1800018d4  jmp     short loc_1800018FB
0x1800018d6  mov     rcx, rbx; void *
0x1800018d9  mov     r8, rdi; Size
0x1800018dc  mov     rdx, rsi; Src
0x1800018df  call    memcpy_0
0x1800018e4  cmp     qword ptr [rbx+18h], 10h
0x1800018e9  jb      short loc_1800018F0
0x1800018eb  mov     rax, [rbx]
0x1800018ee  jmp     short loc_1800018F3
0x1800018f0  mov     rax, rbx
0x1800018f3  mov     [rbx+10h], rdi
0x1800018f7  mov     byte ptr [rax+rdi], 0
0x1800018fb  mov     rax, rbx
0x1800018fe  mov     rbx, [rsp+28h+arg_0]
0x180001903  mov     rsi, [rsp+28h+arg_8]
0x180001908  add     rsp, 20h
0x18000190c  pop     rdi
0x18000190d  retn
0x18000190e  mov     rcx, rbx
0x180001911  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
