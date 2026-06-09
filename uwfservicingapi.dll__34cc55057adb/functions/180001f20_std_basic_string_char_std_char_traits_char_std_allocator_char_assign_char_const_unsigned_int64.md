# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001f20`
- end: `0x180002017`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `void **__fastcall(_QWORD *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800021a0`
- `0x180002210`
- `0x1800022a0`

## callees

- `0x180001c18`
- `0x180001da0`
- `0x180001e28`
- `0x180001f20`
- `0x1800024f6`

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
0x180001f20  mov     [rsp+arg_0], rbx
0x180001f25  mov     [rsp+arg_8], rsi
0x180001f2a  push    rdi
0x180001f2b  sub     rsp, 20h
0x180001f2f  mov     rdi, r8
0x180001f32  mov     rsi, rdx
0x180001f35  mov     rbx, rcx
0x180001f38  test    rdx, rdx
0x180001f3b  jz      short loc_180001F89
0x180001f3d  cmp     qword ptr [rcx+18h], 10h
0x180001f42  jb      short loc_180001F49
0x180001f44  mov     rax, [rcx]
0x180001f47  jmp     short loc_180001F4C
0x180001f49  mov     rax, rbx
0x180001f4c  cmp     rsi, rax
0x180001f4f  jb      short loc_180001F89
0x180001f51  cmp     qword ptr [rcx+18h], 10h
0x180001f56  jb      short loc_180001F5B
0x180001f58  mov     rcx, [rcx]
0x180001f5b  add     rcx, [rbx+10h]
0x180001f5f  cmp     rcx, rsi
0x180001f62  jbe     short loc_180001F89
0x180001f64  cmp     qword ptr [rbx+18h], 10h
0x180001f69  jb      short loc_180001F70
0x180001f6b  mov     rax, [rbx]
0x180001f6e  jmp     short loc_180001F73
0x180001f70  mov     rax, rbx
0x180001f73  sub     rsi, rax
0x180001f76  mov     r9, rdi
0x180001f79  mov     r8, rsi
0x180001f7c  mov     rdx, rbx
0x180001f7f  mov     rcx, rbx; void *
0x180001f82  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001f87  jmp     short loc_180001FFE
0x180001f89  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180001f8d  ja      short loc_18000200E
0x180001f8f  cmp     [rbx+18h], rdi
0x180001f93  jnb     short loc_180001FB5
0x180001f95  mov     r8, [rbx+10h]
0x180001f99  mov     rdx, rdi
0x180001f9c  mov     rcx, rbx; Src
0x180001f9f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180001fa4  test    rdi, rdi
0x180001fa7  jz      short loc_180001FFB
0x180001fa9  cmp     qword ptr [rbx+18h], 10h
0x180001fae  jb      short loc_180001FD6
0x180001fb0  mov     rcx, [rbx]
0x180001fb3  jmp     short loc_180001FD9
0x180001fb5  test    rdi, rdi
0x180001fb8  jnz     short loc_180001FA9
0x180001fba  cmp     qword ptr [rbx+18h], 10h
0x180001fbf  jb      short loc_180001FC6
0x180001fc1  mov     rax, [rbx]
0x180001fc4  jmp     short loc_180001FC9
0x180001fc6  mov     rax, rbx
0x180001fc9  mov     qword ptr [rbx+10h], 0
0x180001fd1  mov     byte ptr [rax], 0
0x180001fd4  jmp     short loc_180001FFB
0x180001fd6  mov     rcx, rbx; void *
0x180001fd9  mov     r8, rdi; Size
0x180001fdc  mov     rdx, rsi; Src
0x180001fdf  call    memcpy_0
0x180001fe4  cmp     qword ptr [rbx+18h], 10h
0x180001fe9  jb      short loc_180001FF0
0x180001feb  mov     rax, [rbx]
0x180001fee  jmp     short loc_180001FF3
0x180001ff0  mov     rax, rbx
0x180001ff3  mov     [rbx+10h], rdi
0x180001ff7  mov     byte ptr [rax+rdi], 0
0x180001ffb  mov     rax, rbx
0x180001ffe  mov     rbx, [rsp+28h+arg_0]
0x180002003  mov     rsi, [rsp+28h+arg_8]
0x180002008  add     rsp, 20h
0x18000200c  pop     rdi
0x18000200d  retn
0x18000200e  mov     rcx, rbx
0x180002011  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
