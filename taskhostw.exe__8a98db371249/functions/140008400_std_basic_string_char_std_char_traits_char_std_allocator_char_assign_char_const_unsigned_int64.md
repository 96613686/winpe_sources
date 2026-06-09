# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x140008400`
- end: `0x1400084f7`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140008680`
- `0x1400086f0`
- `0x140008780`

## callees

- `0x1400080f8`
- `0x140008280`
- `0x140008308`
- `0x140008400`
- `0x140008966`

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
0x140008400  mov     [rsp+arg_0], rbx
0x140008405  mov     [rsp+arg_8], rsi
0x14000840a  push    rdi
0x14000840b  sub     rsp, 20h
0x14000840f  mov     rdi, r8
0x140008412  mov     rsi, rdx
0x140008415  mov     rbx, rcx
0x140008418  test    rdx, rdx
0x14000841b  jz      short loc_140008469
0x14000841d  cmp     qword ptr [rcx+18h], 10h
0x140008422  jb      short loc_140008429
0x140008424  mov     rax, [rcx]
0x140008427  jmp     short loc_14000842C
0x140008429  mov     rax, rbx
0x14000842c  cmp     rsi, rax
0x14000842f  jb      short loc_140008469
0x140008431  cmp     qword ptr [rcx+18h], 10h
0x140008436  jb      short loc_14000843B
0x140008438  mov     rcx, [rcx]
0x14000843b  add     rcx, [rbx+10h]
0x14000843f  cmp     rcx, rsi
0x140008442  jbe     short loc_140008469
0x140008444  cmp     qword ptr [rbx+18h], 10h
0x140008449  jb      short loc_140008450
0x14000844b  mov     rax, [rbx]
0x14000844e  jmp     short loc_140008453
0x140008450  mov     rax, rbx
0x140008453  sub     rsi, rax
0x140008456  mov     r9, rdi
0x140008459  mov     r8, rsi
0x14000845c  mov     rdx, rbx
0x14000845f  mov     rcx, rbx; void *
0x140008462  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x140008467  jmp     short loc_1400084DE
0x140008469  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x14000846d  ja      short loc_1400084EE
0x14000846f  cmp     [rbx+18h], rdi
0x140008473  jnb     short loc_140008495
0x140008475  mov     r8, [rbx+10h]
0x140008479  mov     rdx, rdi
0x14000847c  mov     rcx, rbx; Src
0x14000847f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140008484  test    rdi, rdi
0x140008487  jz      short loc_1400084DB
0x140008489  cmp     qword ptr [rbx+18h], 10h
0x14000848e  jb      short loc_1400084B6
0x140008490  mov     rcx, [rbx]
0x140008493  jmp     short loc_1400084B9
0x140008495  test    rdi, rdi
0x140008498  jnz     short loc_140008489
0x14000849a  cmp     qword ptr [rbx+18h], 10h
0x14000849f  jb      short loc_1400084A6
0x1400084a1  mov     rax, [rbx]
0x1400084a4  jmp     short loc_1400084A9
0x1400084a6  mov     rax, rbx
0x1400084a9  mov     qword ptr [rbx+10h], 0
0x1400084b1  mov     byte ptr [rax], 0
0x1400084b4  jmp     short loc_1400084DB
0x1400084b6  mov     rcx, rbx; void *
0x1400084b9  mov     r8, rdi; Size
0x1400084bc  mov     rdx, rsi; Src
0x1400084bf  call    memcpy_0
0x1400084c4  cmp     qword ptr [rbx+18h], 10h
0x1400084c9  jb      short loc_1400084D0
0x1400084cb  mov     rax, [rbx]
0x1400084ce  jmp     short loc_1400084D3
0x1400084d0  mov     rax, rbx
0x1400084d3  mov     [rbx+10h], rdi
0x1400084d7  mov     byte ptr [rax+rdi], 0
0x1400084db  mov     rax, rbx
0x1400084de  mov     rbx, [rsp+28h+arg_0]
0x1400084e3  mov     rsi, [rsp+28h+arg_8]
0x1400084e8  add     rsp, 20h
0x1400084ec  pop     rdi
0x1400084ed  retn
0x1400084ee  mov     rcx, rbx
0x1400084f1  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
