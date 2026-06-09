# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180009ff0`
- end: `0x18000a0f7`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `263`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a100`
- `0x18000aaa0`

## callees

- `0x180001ac6`
- `0x180002084`
- `0x18000209c`
- `0x180009ba0`
- `0x180009ff0`
- `0x18000a20c`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // r14
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _WORD *v11; // rax
  void **v12; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] < v8 + a3 )
      std::wstring::_Xran();
    if ( (unsigned __int64)a1[3] >= 8 )
      a1 = (void **)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + (_QWORD)v9) = 0;
    std::wstring::erase(v7, 0);
  }
  else
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( (unsigned __int64)a1[3] >= v8 )
    {
      if ( !v8 )
      {
        if ( (unsigned __int64)a1[3] < 8 )
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
      std::wstring::_Copy((const void **)a1, v8, (__int64)a1[2]);
      if ( !v8 )
        return v7;
    }
    if ( (unsigned __int64)v6[3] >= 8 )
      v6 = (void **)*v6;
    if ( (unsigned __int64)v7[3] < 8 )
      v10 = v7;
    else
      v10 = *v7;
    memcpy_0(v10, (char *)v6 + 2 * a3, 2 * v8);
    if ( (unsigned __int64)v7[3] < 8 )
      v12 = v7;
    else
      v12 = (void **)*v7;
    v7[2] = (void *)v8;
    *((_WORD *)v12 + v8) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180009ff0  push    rbx
0x180009ff2  push    rbp
0x180009ff3  push    rsi
0x180009ff4  push    rdi
0x180009ff5  push    r14
0x180009ff7  sub     rsp, 20h
0x180009ffb  mov     rdi, [rdx+10h]
0x180009fff  mov     rbp, r8
0x18000a002  mov     r14, rdx
0x18000a005  mov     rbx, rcx
0x18000a008  cmp     rdi, r8
0x18000a00b  jb      loc_18000A0E5
0x18000a011  sub     rdi, r8
0x18000a014  cmp     r9, rdi
0x18000a017  cmovb   rdi, r9
0x18000a01b  cmp     rcx, rdx
0x18000a01e  jnz     short loc_18000A051
0x18000a020  lea     rax, [rdi+r8]
0x18000a024  cmp     [rcx+10h], rax
0x18000a028  jb      loc_18000A0EB
0x18000a02e  cmp     qword ptr [rcx+18h], 8
0x18000a033  jb      short loc_18000A038
0x18000a035  mov     rcx, [rcx]
0x18000a038  xor     esi, esi
0x18000a03a  mov     [rbx+10h], rax
0x18000a03e  mov     [rcx+rax*2], si
0x18000a042  xor     edx, edx
0x18000a044  mov     rcx, rbx
0x18000a047  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18000a04c  jmp     loc_18000A0D7
0x18000a051  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a05b  cmp     rdi, rax
0x18000a05e  ja      loc_18000A0F1
0x18000a064  xor     esi, esi
0x18000a066  cmp     [rcx+18h], rdi
0x18000a06a  jnb     short loc_18000A093
0x18000a06c  mov     r8, [rcx+10h]
0x18000a070  mov     rdx, rdi
0x18000a073  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a078  test    rdi, rdi
0x18000a07b  jz      short loc_18000A0D7
0x18000a07d  cmp     qword ptr [r14+18h], 8
0x18000a082  jb      short loc_18000A087
0x18000a084  mov     r14, [r14]
0x18000a087  cmp     qword ptr [rbx+18h], 8
0x18000a08c  jb      short loc_18000A0B0
0x18000a08e  mov     rcx, [rbx]
0x18000a091  jmp     short loc_18000A0B3
0x18000a093  test    rdi, rdi
0x18000a096  jnz     short loc_18000A07D
0x18000a098  cmp     qword ptr [rcx+18h], 8
0x18000a09d  jb      short loc_18000A0A4
0x18000a09f  mov     rax, [rcx]
0x18000a0a2  jmp     short loc_18000A0A7
0x18000a0a4  mov     rax, rbx
0x18000a0a7  mov     [rcx+10h], rsi
0x18000a0ab  mov     [rax], si
0x18000a0ae  jmp     short loc_18000A0D7
0x18000a0b0  mov     rcx, rbx; void *
0x18000a0b3  lea     r8, [rdi+rdi]; Size
0x18000a0b7  lea     rdx, [r14+rbp*2]; Src
0x18000a0bb  call    memcpy_0
0x18000a0c0  cmp     qword ptr [rbx+18h], 8
0x18000a0c5  jb      short loc_18000A0CC
0x18000a0c7  mov     rax, [rbx]
0x18000a0ca  jmp     short loc_18000A0CF
0x18000a0cc  mov     rax, rbx
0x18000a0cf  mov     [rbx+10h], rdi
0x18000a0d3  mov     [rax+rdi*2], si
0x18000a0d7  mov     rax, rbx
0x18000a0da  add     rsp, 20h
0x18000a0de  pop     r14
0x18000a0e0  pop     rdi
0x18000a0e1  pop     rsi
0x18000a0e2  pop     rbp
0x18000a0e3  pop     rbx
0x18000a0e4  retn
0x18000a0e5  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000a0eb  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000a0f1  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
