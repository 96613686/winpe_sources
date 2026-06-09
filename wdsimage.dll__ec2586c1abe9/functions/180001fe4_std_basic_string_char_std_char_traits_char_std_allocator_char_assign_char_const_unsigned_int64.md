# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001fe4`
- end: `0x1800020d8`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002250`
- `0x1800022c0`
- `0x180002350`

## callees

- `0x180001cc8`
- `0x180001e50`
- `0x180001ed8`
- `0x180001fe4`
- `0x1800024a8`

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
0x180001fe4  mov     [rsp+arg_0], rbx
0x180001fe9  mov     [rsp+arg_8], rsi
0x180001fee  push    rdi
0x180001fef  sub     rsp, 20h
0x180001ff3  mov     rdi, r8
0x180001ff6  mov     rsi, rdx
0x180001ff9  mov     rbx, rcx
0x180001ffc  test    rdx, rdx
0x180001fff  jz      short loc_18000204D
0x180002001  cmp     qword ptr [rcx+18h], 10h
0x180002006  jb      short loc_18000200D
0x180002008  mov     rax, [rcx]
0x18000200b  jmp     short loc_180002010
0x18000200d  mov     rax, rbx
0x180002010  cmp     rsi, rax
0x180002013  jb      short loc_18000204D
0x180002015  cmp     qword ptr [rcx+18h], 10h
0x18000201a  jb      short loc_18000201F
0x18000201c  mov     rcx, [rcx]
0x18000201f  add     rcx, [rbx+10h]
0x180002023  cmp     rcx, rsi
0x180002026  jbe     short loc_18000204D
0x180002028  cmp     qword ptr [rbx+18h], 10h
0x18000202d  jb      short loc_180002034
0x18000202f  mov     rax, [rbx]
0x180002032  jmp     short loc_180002037
0x180002034  mov     rax, rbx
0x180002037  sub     rsi, rax
0x18000203a  mov     r9, rdi
0x18000203d  mov     r8, rsi
0x180002040  mov     rdx, rbx
0x180002043  mov     rcx, rbx; void *
0x180002046  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000204b  jmp     short loc_1800020BF
0x18000204d  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002051  ja      short loc_1800020CF
0x180002053  cmp     [rbx+18h], rdi
0x180002057  jnb     short loc_180002079
0x180002059  mov     r8, [rbx+10h]
0x18000205d  mov     rdx, rdi
0x180002060  mov     rcx, rbx; Src
0x180002063  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002068  test    rdi, rdi
0x18000206b  jz      short loc_1800020BC
0x18000206d  cmp     qword ptr [rbx+18h], 10h
0x180002072  jb      short loc_180002097
0x180002074  mov     rcx, [rbx]
0x180002077  jmp     short loc_18000209A
0x180002079  test    rdi, rdi
0x18000207c  jnz     short loc_18000206D
0x18000207e  cmp     qword ptr [rbx+18h], 10h
0x180002083  jb      short loc_18000208A
0x180002085  mov     rax, [rbx]
0x180002088  jmp     short loc_18000208D
0x18000208a  mov     rax, rbx
0x18000208d  and     qword ptr [rbx+10h], 0
0x180002092  mov     byte ptr [rax], 0
0x180002095  jmp     short loc_1800020BC
0x180002097  mov     rcx, rbx; void *
0x18000209a  mov     r8, rdi; Size
0x18000209d  mov     rdx, rsi; Src
0x1800020a0  call    memcpy_0
0x1800020a5  cmp     qword ptr [rbx+18h], 10h
0x1800020aa  jb      short loc_1800020B1
0x1800020ac  mov     rax, [rbx]
0x1800020af  jmp     short loc_1800020B4
0x1800020b1  mov     rax, rbx
0x1800020b4  mov     [rbx+10h], rdi
0x1800020b8  mov     byte ptr [rax+rdi], 0
0x1800020bc  mov     rax, rbx
0x1800020bf  mov     rbx, [rsp+28h+arg_0]
0x1800020c4  mov     rsi, [rsp+28h+arg_8]
0x1800020c9  add     rsp, 20h
0x1800020cd  pop     rdi
0x1800020ce  retn
0x1800020cf  mov     rcx, rbx
0x1800020d2  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
