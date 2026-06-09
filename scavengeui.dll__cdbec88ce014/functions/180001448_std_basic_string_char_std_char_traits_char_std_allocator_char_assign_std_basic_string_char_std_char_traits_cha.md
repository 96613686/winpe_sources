# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180001448`
- end: `0x180001538`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `240`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001540`

## callees

- `0x180001238`
- `0x1800013c0`
- `0x180001430`
- `0x180001448`
- `0x180001720`
- `0x180002026`

## pseudocode

```c
void **__fastcall std::string::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // rsi
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _BYTE *v11; // rax
  void **v12; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    goto LABEL_27;
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] >= v8 + a3 )
    {
      if ( (unsigned __int64)a1[3] >= 0x10 )
        a1 = (void **)*a1;
      v7[2] = v9;
      *((_BYTE *)a1 + (_QWORD)v9) = 0;
      std::string::erase(v7, 0);
      return v7;
    }
LABEL_27:
    std::string::_Xran();
  }
  if ( v8 == -1 )
    std::string::_Xlen();
  if ( (unsigned __int64)a1[3] >= v8 )
  {
    if ( !v8 )
    {
      if ( (unsigned __int64)a1[3] < 0x10 )
        v11 = a1;
      else
        v11 = *a1;
      a1[2] = 0;
      *v11 = 0;
      return v7;
    }
  }
  else
  {
    std::string::_Copy((const void **)a1, v8, (size_t)a1[2]);
    if ( !v8 )
      return v7;
  }
  if ( (unsigned __int64)v6[3] >= 0x10 )
    v6 = (void **)*v6;
  if ( (unsigned __int64)v7[3] < 0x10 )
    v10 = v7;
  else
    v10 = *v7;
  memcpy_0(v10, (char *)v6 + a3, v8);
  if ( (unsigned __int64)v7[3] < 0x10 )
    v12 = v7;
  else
    v12 = (void **)*v7;
  v7[2] = (void *)v8;
  *((_BYTE *)v12 + v8) = 0;
  return v7;
}

```

## disassembly

```asm
0x180001448  push    rbx
0x18000144a  push    rbp
0x18000144b  push    rsi
0x18000144c  push    rdi
0x18000144d  sub     rsp, 28h
0x180001451  mov     rdi, [rdx+10h]
0x180001455  mov     rbp, r8
0x180001458  mov     rsi, rdx
0x18000145b  mov     rbx, rcx
0x18000145e  cmp     rdi, r8
0x180001461  jb      loc_18000152C
0x180001467  sub     rdi, r8
0x18000146a  cmp     r9, rdi
0x18000146d  cmovb   rdi, r9
0x180001471  cmp     rcx, rdx
0x180001474  jnz     short loc_1800014A2
0x180001476  lea     rax, [rdi+r8]
0x18000147a  cmp     [rcx+10h], rax
0x18000147e  jb      loc_18000152C
0x180001484  cmp     qword ptr [rcx+18h], 10h
0x180001489  jb      short loc_18000148E
0x18000148b  mov     rcx, [rcx]
0x18000148e  mov     [rbx+10h], rax
0x180001492  xor     edx, edx
0x180001494  mov     byte ptr [rax+rcx], 0
0x180001498  mov     rcx, rbx
0x18000149b  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x1800014a0  jmp     short loc_180001520
0x1800014a2  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800014a6  ja      loc_180001532
0x1800014ac  cmp     [rcx+18h], rdi
0x1800014b0  jnb     short loc_1800014D9
0x1800014b2  mov     r8, [rcx+10h]
0x1800014b6  mov     rdx, rdi
0x1800014b9  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800014be  test    rdi, rdi
0x1800014c1  jz      short loc_180001520
0x1800014c3  cmp     qword ptr [rsi+18h], 10h
0x1800014c8  jb      short loc_1800014CD
0x1800014ca  mov     rsi, [rsi]
0x1800014cd  cmp     qword ptr [rbx+18h], 10h
0x1800014d2  jb      short loc_1800014FA
0x1800014d4  mov     rcx, [rbx]
0x1800014d7  jmp     short loc_1800014FD
0x1800014d9  test    rdi, rdi
0x1800014dc  jnz     short loc_1800014C3
0x1800014de  cmp     qword ptr [rcx+18h], 10h
0x1800014e3  jb      short loc_1800014EA
0x1800014e5  mov     rax, [rcx]
0x1800014e8  jmp     short loc_1800014ED
0x1800014ea  mov     rax, rbx
0x1800014ed  mov     qword ptr [rcx+10h], 0
0x1800014f5  mov     byte ptr [rax], 0
0x1800014f8  jmp     short loc_180001520
0x1800014fa  mov     rcx, rbx; void *
0x1800014fd  lea     rdx, [rsi+rbp]; Src
0x180001501  mov     r8, rdi; Size
0x180001504  call    memcpy_0
0x180001509  cmp     qword ptr [rbx+18h], 10h
0x18000150e  jb      short loc_180001515
0x180001510  mov     rax, [rbx]
0x180001513  jmp     short loc_180001518
0x180001515  mov     rax, rbx
0x180001518  mov     [rbx+10h], rdi
0x18000151c  mov     byte ptr [rax+rdi], 0
0x180001520  mov     rax, rbx
0x180001523  add     rsp, 28h
0x180001527  pop     rdi
0x180001528  pop     rsi
0x180001529  pop     rbp
0x18000152a  pop     rbx
0x18000152b  retn
0x18000152c  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
0x180001532  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
