# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001540`
- end: `0x180001637`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `void **__fastcall(_QWORD *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800017c0`
- `0x180001830`
- `0x1800018c0`

## callees

- `0x180001238`
- `0x1800013c0`
- `0x180001448`
- `0x180001540`
- `0x180002026`

## pseudocode

```c
void **__fastcall std::string::assign(_QWORD *a1, char *Src, size_t Size)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _BYTE *v7; // rax
  void *v9; // rcx
  _BYTE *v10; // rax
  _BYTE *v11; // rax

  v5 = a1;
  if ( !Src )
    goto LABEL_13;
  v6 = a1[3] < 0x10u ? (char *)a1 : (char *)*a1;
  if ( Src < v6 )
    goto LABEL_13;
  if ( a1[3] >= 0x10u )
    a1 = (_QWORD *)*a1;
  if ( (char *)a1 + v5[2] <= Src )
  {
LABEL_13:
    if ( Size == -1 )
      std::string::_Xlen();
    if ( v5[3] >= Size )
    {
      if ( !Size )
      {
        if ( v5[3] < 0x10u )
          v10 = v5;
        else
          v10 = (_BYTE *)*v5;
        v5[2] = 0;
        *v10 = 0;
        return (void **)v5;
      }
    }
    else
    {
      std::string::_Copy((const void **)v5, Size, v5[2]);
      if ( !Size )
        return (void **)v5;
    }
    if ( v5[3] < 0x10u )
      v9 = v5;
    else
      v9 = (void *)*v5;
    memcpy_0(v9, Src, Size);
    if ( v5[3] < 0x10u )
      v11 = v5;
    else
      v11 = (_BYTE *)*v5;
    v5[2] = Size;
    v11[Size] = 0;
    return (void **)v5;
  }
  if ( v5[3] < 0x10u )
    v7 = v5;
  else
    v7 = (_BYTE *)*v5;
  return std::string::assign((void **)v5, (void **)v5, Src - v7, Size);
}

```

## disassembly

```asm
0x180001540  mov     [rsp+arg_0], rbx
0x180001545  mov     [rsp+arg_8], rsi
0x18000154a  push    rdi
0x18000154b  sub     rsp, 20h
0x18000154f  mov     rdi, r8
0x180001552  mov     rsi, rdx
0x180001555  mov     rbx, rcx
0x180001558  test    rdx, rdx
0x18000155b  jz      short loc_1800015A9
0x18000155d  cmp     qword ptr [rcx+18h], 10h
0x180001562  jb      short loc_180001569
0x180001564  mov     rax, [rcx]
0x180001567  jmp     short loc_18000156C
0x180001569  mov     rax, rbx
0x18000156c  cmp     rsi, rax
0x18000156f  jb      short loc_1800015A9
0x180001571  cmp     qword ptr [rcx+18h], 10h
0x180001576  jb      short loc_18000157B
0x180001578  mov     rcx, [rcx]
0x18000157b  add     rcx, [rbx+10h]
0x18000157f  cmp     rcx, rsi
0x180001582  jbe     short loc_1800015A9
0x180001584  cmp     qword ptr [rbx+18h], 10h
0x180001589  jb      short loc_180001590
0x18000158b  mov     rax, [rbx]
0x18000158e  jmp     short loc_180001593
0x180001590  mov     rax, rbx
0x180001593  sub     rsi, rax
0x180001596  mov     r9, rdi
0x180001599  mov     r8, rsi
0x18000159c  mov     rdx, rbx
0x18000159f  mov     rcx, rbx; void *
0x1800015a2  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800015a7  jmp     short loc_18000161E
0x1800015a9  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800015ad  ja      short loc_18000162E
0x1800015af  cmp     [rbx+18h], rdi
0x1800015b3  jnb     short loc_1800015D5
0x1800015b5  mov     r8, [rbx+10h]
0x1800015b9  mov     rdx, rdi
0x1800015bc  mov     rcx, rbx; Src
0x1800015bf  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800015c4  test    rdi, rdi
0x1800015c7  jz      short loc_18000161B
0x1800015c9  cmp     qword ptr [rbx+18h], 10h
0x1800015ce  jb      short loc_1800015F6
0x1800015d0  mov     rcx, [rbx]
0x1800015d3  jmp     short loc_1800015F9
0x1800015d5  test    rdi, rdi
0x1800015d8  jnz     short loc_1800015C9
0x1800015da  cmp     qword ptr [rbx+18h], 10h
0x1800015df  jb      short loc_1800015E6
0x1800015e1  mov     rax, [rbx]
0x1800015e4  jmp     short loc_1800015E9
0x1800015e6  mov     rax, rbx
0x1800015e9  mov     qword ptr [rbx+10h], 0
0x1800015f1  mov     byte ptr [rax], 0
0x1800015f4  jmp     short loc_18000161B
0x1800015f6  mov     rcx, rbx; void *
0x1800015f9  mov     r8, rdi; Size
0x1800015fc  mov     rdx, rsi; Src
0x1800015ff  call    memcpy_0
0x180001604  cmp     qword ptr [rbx+18h], 10h
0x180001609  jb      short loc_180001610
0x18000160b  mov     rax, [rbx]
0x18000160e  jmp     short loc_180001613
0x180001610  mov     rax, rbx
0x180001613  mov     [rbx+10h], rdi
0x180001617  mov     byte ptr [rax+rdi], 0
0x18000161b  mov     rax, rbx
0x18000161e  mov     rbx, [rsp+28h+arg_0]
0x180001623  mov     rsi, [rsp+28h+arg_8]
0x180001628  add     rsp, 20h
0x18000162c  pop     rdi
0x18000162d  retn
0x18000162e  mov     rcx, rbx
0x180001631  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
