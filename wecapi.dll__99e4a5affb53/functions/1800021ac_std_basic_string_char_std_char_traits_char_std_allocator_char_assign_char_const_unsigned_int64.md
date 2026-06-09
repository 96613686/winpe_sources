# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800021ac`
- end: `0x1800022a3`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002420`
- `0x180002490`
- `0x180002520`

## callees

- `0x180001ac6`
- `0x180001f2c`
- `0x180002084`
- `0x1800020b4`
- `0x1800021ac`

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
    std::wstring::_Xlen(v5);
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
0x1800021ac  mov     [rsp+arg_0], rbx
0x1800021b1  mov     [rsp+arg_8], rsi
0x1800021b6  push    rdi
0x1800021b7  sub     rsp, 20h
0x1800021bb  mov     rdi, r8
0x1800021be  mov     rsi, rdx
0x1800021c1  mov     rbx, rcx
0x1800021c4  test    rdx, rdx
0x1800021c7  jz      short loc_180002215
0x1800021c9  cmp     qword ptr [rcx+18h], 10h
0x1800021ce  jb      short loc_1800021D5
0x1800021d0  mov     rax, [rcx]
0x1800021d3  jmp     short loc_1800021D8
0x1800021d5  mov     rax, rbx
0x1800021d8  cmp     rsi, rax
0x1800021db  jb      short loc_180002215
0x1800021dd  cmp     qword ptr [rcx+18h], 10h
0x1800021e2  jb      short loc_1800021E7
0x1800021e4  mov     rcx, [rcx]
0x1800021e7  add     rcx, [rbx+10h]
0x1800021eb  cmp     rcx, rsi
0x1800021ee  jbe     short loc_180002215
0x1800021f0  cmp     qword ptr [rbx+18h], 10h
0x1800021f5  jb      short loc_1800021FC
0x1800021f7  mov     rax, [rbx]
0x1800021fa  jmp     short loc_1800021FF
0x1800021fc  mov     rax, rbx
0x1800021ff  sub     rsi, rax
0x180002202  mov     r9, rdi
0x180002205  mov     r8, rsi
0x180002208  mov     rdx, rbx
0x18000220b  mov     rcx, rbx; void *
0x18000220e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180002213  jmp     short loc_18000228A
0x180002215  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002219  ja      short loc_18000229A
0x18000221b  cmp     [rbx+18h], rdi
0x18000221f  jnb     short loc_180002241
0x180002221  mov     r8, [rbx+10h]
0x180002225  mov     rdx, rdi
0x180002228  mov     rcx, rbx; Src
0x18000222b  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002230  test    rdi, rdi
0x180002233  jz      short loc_180002287
0x180002235  cmp     qword ptr [rbx+18h], 10h
0x18000223a  jb      short loc_180002262
0x18000223c  mov     rcx, [rbx]
0x18000223f  jmp     short loc_180002265
0x180002241  test    rdi, rdi
0x180002244  jnz     short loc_180002235
0x180002246  cmp     qword ptr [rbx+18h], 10h
0x18000224b  jb      short loc_180002252
0x18000224d  mov     rax, [rbx]
0x180002250  jmp     short loc_180002255
0x180002252  mov     rax, rbx
0x180002255  mov     qword ptr [rbx+10h], 0
0x18000225d  mov     byte ptr [rax], 0
0x180002260  jmp     short loc_180002287
0x180002262  mov     rcx, rbx; void *
0x180002265  mov     r8, rdi; Size
0x180002268  mov     rdx, rsi; Src
0x18000226b  call    memcpy_0
0x180002270  cmp     qword ptr [rbx+18h], 10h
0x180002275  jb      short loc_18000227C
0x180002277  mov     rax, [rbx]
0x18000227a  jmp     short loc_18000227F
0x18000227c  mov     rax, rbx
0x18000227f  mov     [rbx+10h], rdi
0x180002283  mov     byte ptr [rax+rdi], 0
0x180002287  mov     rax, rbx
0x18000228a  mov     rbx, [rsp+28h+arg_0]
0x18000228f  mov     rsi, [rsp+28h+arg_8]
0x180002294  add     rsp, 20h
0x180002298  pop     rdi
0x180002299  retn
0x18000229a  mov     rcx, rbx
0x18000229d  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
