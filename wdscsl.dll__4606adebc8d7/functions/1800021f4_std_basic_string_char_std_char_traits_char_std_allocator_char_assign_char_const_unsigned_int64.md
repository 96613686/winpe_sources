# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800021f4`
- end: `0x1800022e8`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002460`
- `0x1800024d0`
- `0x180002560`

## callees

- `0x180001ed8`
- `0x180002060`
- `0x1800020e8`
- `0x1800021f4`
- `0x1800026b8`

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
0x1800021f4  mov     [rsp+arg_0], rbx
0x1800021f9  mov     [rsp+arg_8], rsi
0x1800021fe  push    rdi
0x1800021ff  sub     rsp, 20h
0x180002203  mov     rdi, r8
0x180002206  mov     rsi, rdx
0x180002209  mov     rbx, rcx
0x18000220c  test    rdx, rdx
0x18000220f  jz      short loc_18000225D
0x180002211  cmp     qword ptr [rcx+18h], 10h
0x180002216  jb      short loc_18000221D
0x180002218  mov     rax, [rcx]
0x18000221b  jmp     short loc_180002220
0x18000221d  mov     rax, rbx
0x180002220  cmp     rsi, rax
0x180002223  jb      short loc_18000225D
0x180002225  cmp     qword ptr [rcx+18h], 10h
0x18000222a  jb      short loc_18000222F
0x18000222c  mov     rcx, [rcx]
0x18000222f  add     rcx, [rbx+10h]
0x180002233  cmp     rcx, rsi
0x180002236  jbe     short loc_18000225D
0x180002238  cmp     qword ptr [rbx+18h], 10h
0x18000223d  jb      short loc_180002244
0x18000223f  mov     rax, [rbx]
0x180002242  jmp     short loc_180002247
0x180002244  mov     rax, rbx
0x180002247  sub     rsi, rax
0x18000224a  mov     r9, rdi
0x18000224d  mov     r8, rsi
0x180002250  mov     rdx, rbx
0x180002253  mov     rcx, rbx; void *
0x180002256  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000225b  jmp     short loc_1800022CF
0x18000225d  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002261  ja      short loc_1800022DF
0x180002263  cmp     [rbx+18h], rdi
0x180002267  jnb     short loc_180002289
0x180002269  mov     r8, [rbx+10h]
0x18000226d  mov     rdx, rdi
0x180002270  mov     rcx, rbx; Src
0x180002273  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002278  test    rdi, rdi
0x18000227b  jz      short loc_1800022CC
0x18000227d  cmp     qword ptr [rbx+18h], 10h
0x180002282  jb      short loc_1800022A7
0x180002284  mov     rcx, [rbx]
0x180002287  jmp     short loc_1800022AA
0x180002289  test    rdi, rdi
0x18000228c  jnz     short loc_18000227D
0x18000228e  cmp     qword ptr [rbx+18h], 10h
0x180002293  jb      short loc_18000229A
0x180002295  mov     rax, [rbx]
0x180002298  jmp     short loc_18000229D
0x18000229a  mov     rax, rbx
0x18000229d  and     qword ptr [rbx+10h], 0
0x1800022a2  mov     byte ptr [rax], 0
0x1800022a5  jmp     short loc_1800022CC
0x1800022a7  mov     rcx, rbx; void *
0x1800022aa  mov     r8, rdi; Size
0x1800022ad  mov     rdx, rsi; Src
0x1800022b0  call    memcpy_0
0x1800022b5  cmp     qword ptr [rbx+18h], 10h
0x1800022ba  jb      short loc_1800022C1
0x1800022bc  mov     rax, [rbx]
0x1800022bf  jmp     short loc_1800022C4
0x1800022c1  mov     rax, rbx
0x1800022c4  mov     [rbx+10h], rdi
0x1800022c8  mov     byte ptr [rax+rdi], 0
0x1800022cc  mov     rax, rbx
0x1800022cf  mov     rbx, [rsp+28h+arg_0]
0x1800022d4  mov     rsi, [rsp+28h+arg_8]
0x1800022d9  add     rsp, 20h
0x1800022dd  pop     rdi
0x1800022de  retn
0x1800022df  mov     rcx, rbx
0x1800022e2  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
