# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001674`
- end: `0x180001768`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800018e0`
- `0x180001950`
- `0x1800019e0`

## callees

- `0x180001358`
- `0x1800014e0`
- `0x180001568`
- `0x180001674`
- `0x180002176`

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
0x180001674  mov     [rsp+arg_0], rbx
0x180001679  mov     [rsp+arg_8], rsi
0x18000167e  push    rdi
0x18000167f  sub     rsp, 20h
0x180001683  mov     rdi, r8
0x180001686  mov     rsi, rdx
0x180001689  mov     rbx, rcx
0x18000168c  test    rdx, rdx
0x18000168f  jz      short loc_1800016DD
0x180001691  cmp     qword ptr [rcx+18h], 10h
0x180001696  jb      short loc_18000169D
0x180001698  mov     rax, [rcx]
0x18000169b  jmp     short loc_1800016A0
0x18000169d  mov     rax, rbx
0x1800016a0  cmp     rsi, rax
0x1800016a3  jb      short loc_1800016DD
0x1800016a5  cmp     qword ptr [rcx+18h], 10h
0x1800016aa  jb      short loc_1800016AF
0x1800016ac  mov     rcx, [rcx]
0x1800016af  add     rcx, [rbx+10h]
0x1800016b3  cmp     rcx, rsi
0x1800016b6  jbe     short loc_1800016DD
0x1800016b8  cmp     qword ptr [rbx+18h], 10h
0x1800016bd  jb      short loc_1800016C4
0x1800016bf  mov     rax, [rbx]
0x1800016c2  jmp     short loc_1800016C7
0x1800016c4  mov     rax, rbx
0x1800016c7  sub     rsi, rax
0x1800016ca  mov     r9, rdi
0x1800016cd  mov     r8, rsi
0x1800016d0  mov     rdx, rbx
0x1800016d3  mov     rcx, rbx; void *
0x1800016d6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800016db  jmp     short loc_18000174F
0x1800016dd  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800016e1  ja      short loc_18000175F
0x1800016e3  cmp     [rbx+18h], rdi
0x1800016e7  jnb     short loc_180001709
0x1800016e9  mov     r8, [rbx+10h]
0x1800016ed  mov     rdx, rdi
0x1800016f0  mov     rcx, rbx; Src
0x1800016f3  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800016f8  test    rdi, rdi
0x1800016fb  jz      short loc_18000174C
0x1800016fd  cmp     qword ptr [rbx+18h], 10h
0x180001702  jb      short loc_180001727
0x180001704  mov     rcx, [rbx]
0x180001707  jmp     short loc_18000172A
0x180001709  test    rdi, rdi
0x18000170c  jnz     short loc_1800016FD
0x18000170e  cmp     qword ptr [rbx+18h], 10h
0x180001713  jb      short loc_18000171A
0x180001715  mov     rax, [rbx]
0x180001718  jmp     short loc_18000171D
0x18000171a  mov     rax, rbx
0x18000171d  and     qword ptr [rbx+10h], 0
0x180001722  mov     byte ptr [rax], 0
0x180001725  jmp     short loc_18000174C
0x180001727  mov     rcx, rbx; void *
0x18000172a  mov     r8, rdi; Size
0x18000172d  mov     rdx, rsi; Src
0x180001730  call    memcpy_0
0x180001735  cmp     qword ptr [rbx+18h], 10h
0x18000173a  jb      short loc_180001741
0x18000173c  mov     rax, [rbx]
0x18000173f  jmp     short loc_180001744
0x180001741  mov     rax, rbx
0x180001744  mov     [rbx+10h], rdi
0x180001748  mov     byte ptr [rax+rdi], 0
0x18000174c  mov     rax, rbx
0x18000174f  mov     rbx, [rsp+28h+arg_0]
0x180001754  mov     rsi, [rsp+28h+arg_8]
0x180001759  add     rsp, 20h
0x18000175d  pop     rdi
0x18000175e  retn
0x18000175f  mov     rcx, rbx
0x180001762  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
