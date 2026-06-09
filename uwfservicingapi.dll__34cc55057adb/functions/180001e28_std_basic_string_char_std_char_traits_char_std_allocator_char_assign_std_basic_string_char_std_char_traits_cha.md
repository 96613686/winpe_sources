# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180001e28`
- end: `0x180001f18`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `240`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001f20`

## callees

- `0x180001c18`
- `0x180001da0`
- `0x180001e10`
- `0x180001e28`
- `0x180002100`
- `0x1800024f6`

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
0x180001e28  push    rbx
0x180001e2a  push    rbp
0x180001e2b  push    rsi
0x180001e2c  push    rdi
0x180001e2d  sub     rsp, 28h
0x180001e31  mov     rdi, [rdx+10h]
0x180001e35  mov     rbp, r8
0x180001e38  mov     rsi, rdx
0x180001e3b  mov     rbx, rcx
0x180001e3e  cmp     rdi, r8
0x180001e41  jb      loc_180001F0C
0x180001e47  sub     rdi, r8
0x180001e4a  cmp     r9, rdi
0x180001e4d  cmovb   rdi, r9
0x180001e51  cmp     rcx, rdx
0x180001e54  jnz     short loc_180001E82
0x180001e56  lea     rax, [rdi+r8]
0x180001e5a  cmp     [rcx+10h], rax
0x180001e5e  jb      loc_180001F0C
0x180001e64  cmp     qword ptr [rcx+18h], 10h
0x180001e69  jb      short loc_180001E6E
0x180001e6b  mov     rcx, [rcx]
0x180001e6e  mov     [rbx+10h], rax
0x180001e72  xor     edx, edx
0x180001e74  mov     byte ptr [rax+rcx], 0
0x180001e78  mov     rcx, rbx
0x180001e7b  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x180001e80  jmp     short loc_180001F00
0x180001e82  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180001e86  ja      loc_180001F12
0x180001e8c  cmp     [rcx+18h], rdi
0x180001e90  jnb     short loc_180001EB9
0x180001e92  mov     r8, [rcx+10h]
0x180001e96  mov     rdx, rdi
0x180001e99  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180001e9e  test    rdi, rdi
0x180001ea1  jz      short loc_180001F00
0x180001ea3  cmp     qword ptr [rsi+18h], 10h
0x180001ea8  jb      short loc_180001EAD
0x180001eaa  mov     rsi, [rsi]
0x180001ead  cmp     qword ptr [rbx+18h], 10h
0x180001eb2  jb      short loc_180001EDA
0x180001eb4  mov     rcx, [rbx]
0x180001eb7  jmp     short loc_180001EDD
0x180001eb9  test    rdi, rdi
0x180001ebc  jnz     short loc_180001EA3
0x180001ebe  cmp     qword ptr [rcx+18h], 10h
0x180001ec3  jb      short loc_180001ECA
0x180001ec5  mov     rax, [rcx]
0x180001ec8  jmp     short loc_180001ECD
0x180001eca  mov     rax, rbx
0x180001ecd  mov     qword ptr [rcx+10h], 0
0x180001ed5  mov     byte ptr [rax], 0
0x180001ed8  jmp     short loc_180001F00
0x180001eda  mov     rcx, rbx; void *
0x180001edd  lea     rdx, [rsi+rbp]; Src
0x180001ee1  mov     r8, rdi; Size
0x180001ee4  call    memcpy_0
0x180001ee9  cmp     qword ptr [rbx+18h], 10h
0x180001eee  jb      short loc_180001EF5
0x180001ef0  mov     rax, [rbx]
0x180001ef3  jmp     short loc_180001EF8
0x180001ef5  mov     rax, rbx
0x180001ef8  mov     [rbx+10h], rdi
0x180001efc  mov     byte ptr [rax+rdi], 0
0x180001f00  mov     rax, rbx
0x180001f03  add     rsp, 28h
0x180001f07  pop     rdi
0x180001f08  pop     rsi
0x180001f09  pop     rbp
0x180001f0a  pop     rbx
0x180001f0b  retn
0x180001f0c  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
0x180001f12  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
