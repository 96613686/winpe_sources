# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x18000a100`
- end: `0x18000a206`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003178`
- `0x180005f18`
- `0x18000aea4`

## callees

- `0x180001ac6`
- `0x180002084`
- `0x180009ba0`
- `0x180009ff0`
- `0x18000a100`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, char *Src)
{
  void **v3; // rbx
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rdx
  char *v6; // rax
  char *v7; // rax
  void *v8; // rcx
  _WORD *v9; // rcx
  _WORD *v10; // rcx

  v3 = a1;
  if ( *(_WORD *)Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&Src[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = (unsigned __int64)a1[3];
  if ( v5 < 8 )
    v6 = (char *)a1;
  else
    v6 = (char *)*a1;
  if ( Src >= v6 )
  {
    if ( v5 >= 8 )
      a1 = (void **)*a1;
    if ( (char *)a1 + 2 * (_QWORD)v3[2] > Src )
    {
      if ( v5 < 8 )
        v7 = (char *)v3;
      else
        v7 = (char *)*v3;
      return std::wstring::assign(v3, v3, (Src - v7) >> 1, v4);
    }
  }
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( v5 < v4 )
  {
    std::wstring::_Copy((const void **)v3, v4, (__int64)v3[2]);
    if ( !v4 )
      return v3;
    goto LABEL_19;
  }
  if ( v4 )
  {
LABEL_19:
    if ( (unsigned __int64)v3[3] < 8 )
      v8 = v3;
    else
      v8 = *v3;
    memcpy_0(v8, Src, 2 * v4);
    if ( (unsigned __int64)v3[3] < 8 )
      v10 = v3;
    else
      v10 = *v3;
    v3[2] = (void *)v4;
    v10[v4] = 0;
    return v3;
  }
  if ( v5 < 8 )
    v9 = v3;
  else
    v9 = *v3;
  v3[2] = 0;
  *v9 = 0;
  return v3;
}

```

## disassembly

```asm
0x18000a100  push    rbx
0x18000a102  push    rbp
0x18000a103  push    rsi
0x18000a104  push    rdi
0x18000a105  sub     rsp, 28h
0x18000a109  xor     ebp, ebp
0x18000a10b  mov     rsi, rdx
0x18000a10e  mov     rbx, rcx
0x18000a111  cmp     [rdx], bp
0x18000a114  jnz     short loc_18000A11A
0x18000a116  mov     edi, ebp
0x18000a118  jmp     short loc_18000A127
0x18000a11a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a11e  inc     rdi
0x18000a121  cmp     [rdx+rdi*2], bp
0x18000a125  jnz     short loc_18000A11E
0x18000a127  mov     rdx, [rcx+18h]
0x18000a12b  cmp     rdx, 8
0x18000a12f  jb      short loc_18000A136
0x18000a131  mov     rax, [rcx]
0x18000a134  jmp     short loc_18000A139
0x18000a136  mov     rax, rbx
0x18000a139  cmp     rsi, rax
0x18000a13c  jb      short loc_18000A17E
0x18000a13e  cmp     rdx, 8
0x18000a142  jb      short loc_18000A147
0x18000a144  mov     rcx, [rcx]
0x18000a147  mov     rax, [rbx+10h]
0x18000a14b  lea     rcx, [rcx+rax*2]
0x18000a14f  cmp     rcx, rsi
0x18000a152  jbe     short loc_18000A17E
0x18000a154  cmp     rdx, 8
0x18000a158  jb      short loc_18000A15F
0x18000a15a  mov     rax, [rbx]
0x18000a15d  jmp     short loc_18000A162
0x18000a15f  mov     rax, rbx
0x18000a162  sub     rsi, rax
0x18000a165  mov     r9, rdi
0x18000a168  sar     rsi, 1
0x18000a16b  mov     rdx, rbx
0x18000a16e  mov     r8, rsi
0x18000a171  mov     rcx, rbx; void *
0x18000a174  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a179  mov     rbx, rax
0x18000a17c  jmp     short loc_18000A1F4
0x18000a17e  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a188  cmp     rdi, rax
0x18000a18b  ja      short loc_18000A200
0x18000a18d  cmp     rdx, rdi
0x18000a190  jnb     short loc_18000A1B2
0x18000a192  mov     r8, [rbx+10h]
0x18000a196  mov     rdx, rdi
0x18000a199  mov     rcx, rbx; Src
0x18000a19c  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a1a1  test    rdi, rdi
0x18000a1a4  jz      short loc_18000A1F4
0x18000a1a6  cmp     qword ptr [rbx+18h], 8
0x18000a1ab  jb      short loc_18000A1CE
0x18000a1ad  mov     rcx, [rbx]
0x18000a1b0  jmp     short loc_18000A1D1
0x18000a1b2  test    rdi, rdi
0x18000a1b5  jnz     short loc_18000A1A6
0x18000a1b7  cmp     rdx, 8
0x18000a1bb  jb      short loc_18000A1C2
0x18000a1bd  mov     rcx, [rbx]
0x18000a1c0  jmp     short loc_18000A1C5
0x18000a1c2  mov     rcx, rbx
0x18000a1c5  mov     [rbx+10h], rbp
0x18000a1c9  mov     [rcx], bp
0x18000a1cc  jmp     short loc_18000A1F4
0x18000a1ce  mov     rcx, rbx; void *
0x18000a1d1  lea     r8, [rdi+rdi]; Size
0x18000a1d5  mov     rdx, rsi; Src
0x18000a1d8  call    memcpy_0
0x18000a1dd  cmp     qword ptr [rbx+18h], 8
0x18000a1e2  jb      short loc_18000A1E9
0x18000a1e4  mov     rcx, [rbx]
0x18000a1e7  jmp     short loc_18000A1EC
0x18000a1e9  mov     rcx, rbx
0x18000a1ec  mov     [rbx+10h], rdi
0x18000a1f0  mov     [rcx+rdi*2], bp
0x18000a1f4  mov     rax, rbx
0x18000a1f7  add     rsp, 28h
0x18000a1fb  pop     rdi
0x18000a1fc  pop     rsi
0x18000a1fd  pop     rbp
0x18000a1fe  pop     rbx
0x18000a1ff  retn
0x18000a200  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
