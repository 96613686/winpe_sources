# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180003140`
- end: `0x180003237`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800033c0`
- `0x180003430`
- `0x1800034c0`

## callees

- `0x180002e38`
- `0x180002fc0`
- `0x180003048`
- `0x180003140`
- `0x180003f66`

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
0x180003140  mov     [rsp+arg_0], rbx
0x180003145  mov     [rsp+arg_8], rsi
0x18000314a  push    rdi
0x18000314b  sub     rsp, 20h
0x18000314f  mov     rdi, r8
0x180003152  mov     rsi, rdx
0x180003155  mov     rbx, rcx
0x180003158  test    rdx, rdx
0x18000315b  jz      short loc_1800031A9
0x18000315d  cmp     qword ptr [rcx+18h], 10h
0x180003162  jb      short loc_180003169
0x180003164  mov     rax, [rcx]
0x180003167  jmp     short loc_18000316C
0x180003169  mov     rax, rbx
0x18000316c  cmp     rsi, rax
0x18000316f  jb      short loc_1800031A9
0x180003171  cmp     qword ptr [rcx+18h], 10h
0x180003176  jb      short loc_18000317B
0x180003178  mov     rcx, [rcx]
0x18000317b  add     rcx, [rbx+10h]
0x18000317f  cmp     rcx, rsi
0x180003182  jbe     short loc_1800031A9
0x180003184  cmp     qword ptr [rbx+18h], 10h
0x180003189  jb      short loc_180003190
0x18000318b  mov     rax, [rbx]
0x18000318e  jmp     short loc_180003193
0x180003190  mov     rax, rbx
0x180003193  sub     rsi, rax
0x180003196  mov     r9, rdi
0x180003199  mov     r8, rsi
0x18000319c  mov     rdx, rbx
0x18000319f  mov     rcx, rbx; void *
0x1800031a2  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800031a7  jmp     short loc_18000321E
0x1800031a9  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800031ad  ja      short loc_18000322E
0x1800031af  cmp     [rbx+18h], rdi
0x1800031b3  jnb     short loc_1800031D5
0x1800031b5  mov     r8, [rbx+10h]
0x1800031b9  mov     rdx, rdi
0x1800031bc  mov     rcx, rbx; Src
0x1800031bf  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800031c4  test    rdi, rdi
0x1800031c7  jz      short loc_18000321B
0x1800031c9  cmp     qword ptr [rbx+18h], 10h
0x1800031ce  jb      short loc_1800031F6
0x1800031d0  mov     rcx, [rbx]
0x1800031d3  jmp     short loc_1800031F9
0x1800031d5  test    rdi, rdi
0x1800031d8  jnz     short loc_1800031C9
0x1800031da  cmp     qword ptr [rbx+18h], 10h
0x1800031df  jb      short loc_1800031E6
0x1800031e1  mov     rax, [rbx]
0x1800031e4  jmp     short loc_1800031E9
0x1800031e6  mov     rax, rbx
0x1800031e9  mov     qword ptr [rbx+10h], 0
0x1800031f1  mov     byte ptr [rax], 0
0x1800031f4  jmp     short loc_18000321B
0x1800031f6  mov     rcx, rbx; void *
0x1800031f9  mov     r8, rdi; Size
0x1800031fc  mov     rdx, rsi; Src
0x1800031ff  call    memcpy_0
0x180003204  cmp     qword ptr [rbx+18h], 10h
0x180003209  jb      short loc_180003210
0x18000320b  mov     rax, [rbx]
0x18000320e  jmp     short loc_180003213
0x180003210  mov     rax, rbx
0x180003213  mov     [rbx+10h], rdi
0x180003217  mov     byte ptr [rax+rdi], 0
0x18000321b  mov     rax, rbx
0x18000321e  mov     rbx, [rsp+28h+arg_0]
0x180003223  mov     rsi, [rsp+28h+arg_8]
0x180003228  add     rsp, 20h
0x18000322c  pop     rdi
0x18000322d  retn
0x18000322e  mov     rcx, rbx
0x180003231  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
