# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator+=(ushort const *)

- ea: `0x180019c58`
- end: `0x180019d99`
- name: `??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z`
- size: `321`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180019ea4`
- `0x180019fa0`
- `0x18001a09c`
- `0x18001a660`
- `0x18001ab44`
- `0x18001ad64`
- `0x18001ae4c`

## callees

- `0x180001e26`
- `0x18001661c`
- `0x180019c58`
- `0x18001af34`
- `0x18001b214`

## pseudocode

```c
_QWORD *__fastcall std::wstring::operator+=(_QWORD *Src, char *a2)
{
  _QWORD *v3; // rbx
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rdx
  char *v6; // rax
  _BYTE *v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  char *v10; // rcx
  _WORD *v11; // rcx
  _BYTE *v12; // rcx

  v3 = Src;
  if ( *(_WORD *)a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a2[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = Src[3];
  if ( v5 < 8 )
    v6 = (char *)Src;
  else
    v6 = (char *)*Src;
  if ( a2 >= v6 )
  {
    if ( v5 >= 8 )
      Src = (_QWORD *)*Src;
    if ( (char *)Src + 2 * v3[2] > a2 )
    {
      if ( v5 < 8 )
        v7 = v3;
      else
        v7 = (_BYTE *)*v3;
      return (_QWORD *)std::wstring::append(v3, v3, (a2 - v7) >> 1, v4);
    }
  }
  v8 = v3[2];
  if ( ~v8 <= v4 )
    std::wstring::_Xlen();
  if ( v4 )
  {
    v9 = v8 + v4;
    if ( v8 + v4 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v5 < v9 )
    {
      std::wstring::_Copy((const void **)v3, v8 + v4, v8);
      if ( !v9 )
        return v3;
      goto LABEL_21;
    }
    if ( v9 )
    {
LABEL_21:
      if ( v3[3] < 8u )
        v10 = (char *)v3;
      else
        v10 = (char *)*v3;
      memcpy_0(&v10[2 * v3[2]], a2, 2 * v4);
      if ( v3[3] < 8u )
        v12 = v3;
      else
        v12 = (_BYTE *)*v3;
      v3[2] = v9;
      *(_WORD *)&v12[2 * v9] = 0;
      return v3;
    }
    if ( v5 < 8 )
      v11 = v3;
    else
      v11 = (_WORD *)*v3;
    v3[2] = 0;
    *v11 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180019c58  push    rbx
0x180019c5a  push    rbp
0x180019c5b  push    rsi
0x180019c5c  push    rdi
0x180019c5d  push    r14
0x180019c5f  sub     rsp, 20h
0x180019c63  xor     r14d, r14d
0x180019c66  mov     rbp, rdx
0x180019c69  mov     rbx, rcx
0x180019c6c  cmp     [rdx], r14w
0x180019c70  jnz     short loc_180019C77
0x180019c72  mov     esi, r14d
0x180019c75  jmp     short loc_180019C85
0x180019c77  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180019c7b  inc     rsi
0x180019c7e  cmp     [rdx+rsi*2], r14w
0x180019c83  jnz     short loc_180019C7B
0x180019c85  mov     rdx, [rcx+18h]
0x180019c89  cmp     rdx, 8
0x180019c8d  jb      short loc_180019C94
0x180019c8f  mov     rax, [rcx]
0x180019c92  jmp     short loc_180019C97
0x180019c94  mov     rax, rbx
0x180019c97  cmp     rbp, rax
0x180019c9a  jb      short loc_180019CDF
0x180019c9c  cmp     rdx, 8
0x180019ca0  jb      short loc_180019CA5
0x180019ca2  mov     rcx, [rcx]
0x180019ca5  mov     rax, [rbx+10h]
0x180019ca9  lea     rcx, [rcx+rax*2]
0x180019cad  cmp     rcx, rbp
0x180019cb0  jbe     short loc_180019CDF
0x180019cb2  cmp     rdx, 8
0x180019cb6  jb      short loc_180019CBD
0x180019cb8  mov     rax, [rbx]
0x180019cbb  jmp     short loc_180019CC0
0x180019cbd  mov     rax, rbx
0x180019cc0  sub     rbp, rax
0x180019cc3  mov     r9, rsi
0x180019cc6  sar     rbp, 1
0x180019cc9  mov     rdx, rbx
0x180019ccc  mov     r8, rbp
0x180019ccf  mov     rcx, rbx
0x180019cd2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180019cd7  mov     rbx, rax
0x180019cda  jmp     loc_180019D7F
0x180019cdf  mov     r8, [rbx+10h]
0x180019ce3  mov     rax, r8
0x180019ce6  not     rax
0x180019ce9  cmp     rax, rsi
0x180019cec  jbe     loc_180019D8D
0x180019cf2  test    rsi, rsi
0x180019cf5  jz      loc_180019D7F
0x180019cfb  lea     rdi, [r8+rsi]
0x180019cff  mov     rax, 7FFFFFFFFFFFFFFEh
0x180019d09  cmp     rdi, rax
0x180019d0c  ja      loc_180019D93
0x180019d12  cmp     rdx, rdi
0x180019d15  jnb     short loc_180019D33
0x180019d17  mov     rdx, rdi
0x180019d1a  mov     rcx, rbx; Src
0x180019d1d  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180019d22  test    rdi, rdi
0x180019d25  jz      short loc_180019D7F
0x180019d27  cmp     qword ptr [rbx+18h], 8
0x180019d2c  jb      short loc_180019D50
0x180019d2e  mov     rcx, [rbx]
0x180019d31  jmp     short loc_180019D53
0x180019d33  test    rdi, rdi
0x180019d36  jnz     short loc_180019D27
0x180019d38  cmp     rdx, 8
0x180019d3c  jb      short loc_180019D43
0x180019d3e  mov     rcx, [rbx]
0x180019d41  jmp     short loc_180019D46
0x180019d43  mov     rcx, rbx
0x180019d46  mov     [rbx+10h], r14
0x180019d4a  mov     [rcx], r14w
0x180019d4e  jmp     short loc_180019D7F
0x180019d50  mov     rcx, rbx
0x180019d53  mov     rax, [rbx+10h]
0x180019d57  lea     r8, [rsi+rsi]; Size
0x180019d5b  mov     rdx, rbp; Src
0x180019d5e  lea     rcx, [rcx+rax*2]; void *
0x180019d62  call    memcpy_0
0x180019d67  cmp     qword ptr [rbx+18h], 8
0x180019d6c  jb      short loc_180019D73
0x180019d6e  mov     rcx, [rbx]
0x180019d71  jmp     short loc_180019D76
0x180019d73  mov     rcx, rbx
0x180019d76  mov     [rbx+10h], rdi
0x180019d7a  mov     [rcx+rdi*2], r14w
0x180019d7f  mov     rax, rbx
0x180019d82  add     rsp, 20h
0x180019d86  pop     r14
0x180019d88  pop     rdi
0x180019d89  pop     rsi
0x180019d8a  pop     rbp
0x180019d8b  pop     rbx
0x180019d8c  retn
0x180019d8d  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x180019d93  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
