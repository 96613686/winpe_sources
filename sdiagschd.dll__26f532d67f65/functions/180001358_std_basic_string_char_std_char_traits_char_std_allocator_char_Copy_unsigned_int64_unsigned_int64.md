# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001358`
- end: `0x18000144f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001568`
- `0x180001674`

## callees

- `0x180001174`
- `0x180001358`
- `0x1800014b8`
- `0x180001fc6`
- `0x180002176`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  const void **v4; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  void *v8; // rsi
  const void *v9; // rdx
  size_t *result; // rax
  void *v11; // rax
  _QWORD *v12; // rdx
  _QWORD v13[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v17; // [rsp+78h] [rbp+20h]

  v13[4] = -2;
  v3 = a3;
  v4 = Src;
  v5 = a2 | 0xF;
  if ( (a2 | 0xF) == 0xFFFFFFFFFFFFFFFFuLL )
  {
    v5 = a2;
  }
  else
  {
    v6 = (unsigned __int64)Src[3];
    v7 = v6 >> 1;
    if ( v6 >> 1 > v5 / 3 )
    {
      v5 = v7 + v6;
      if ( v6 > -2LL - v7 )
        v5 = -2;
    }
  }
  try
  {
    v8 = 0;
    if ( v5 != -1 )
    {
      v8 = operator new(v5 + 1);
      if ( !v8 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v11 = 0;
      if ( a2 != -1 )
      {
        v11 = operator new(a2 + 1);
        if ( !v11 )
          std::_Xbad_alloc();
      }
      v17 = v11;
    }
    catch ( ... )
    {
      v12 = v13;
      LOBYTE(v12) = 1;
      std::string::_Tidy(Src, v12, 0);
      throw;
    }
    v4 = Src;
    v3 = a3;
    v5 = a2;
    v8 = v17;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v4[3] < 0x10 )
      v9 = v4;
    else
      v9 = *v4;
    memcpy_0(v8, v9, v3);
  }
  if ( (unsigned __int64)v4[3] >= 0x10 )
    operator delete((void *)*v4);
  result = (size_t *)(v4 + 2);
  *v4 = v8;
  v4[3] = (const void *)v5;
  if ( v5 >= 0x10 )
    v4 = (const void **)v8;
  *result = v3;
  *((_BYTE *)v4 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180001358  mov     rax, rsp
0x18000135b  mov     [rax+18h], r8
0x18000135f  mov     [rax+10h], rdx
0x180001363  mov     [rax+8], rcx
0x180001367  push    rbx
0x180001368  push    rsi
0x180001369  push    rdi
0x18000136a  push    r14
0x18000136c  sub     rsp, 38h
0x180001370  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001378  mov     r14, r8
0x18000137b  mov     rbx, rcx
0x18000137e  mov     rdi, rdx
0x180001381  or      rdi, 0Fh
0x180001385  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000138c  cmp     rdi, r9
0x18000138f  jbe     short loc_180001396
0x180001391  mov     rdi, rdx
0x180001394  jmp     short loc_1800013C7
0x180001396  mov     r8, [rcx+18h]
0x18000139a  mov     rcx, r8
0x18000139d  shr     rcx, 1
0x1800013a0  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800013aa  mul     rdi
0x1800013ad  shr     rdx, 1
0x1800013b0  cmp     rcx, rdx
0x1800013b3  jbe     short loc_1800013C7
0x1800013b5  mov     rax, r9
0x1800013b8  sub     rax, rcx
0x1800013bb  cmp     r8, rax
0x1800013be  lea     rdi, [rcx+r8]
0x1800013c2  jbe     short loc_1800013C7
0x1800013c4  mov     rdi, r9
0x1800013c7  lea     rcx, [rdi+1]; Size
0x1800013cb  xor     esi, esi
0x1800013cd  test    rcx, rcx
0x1800013d0  jz      short loc_1800013DF
0x1800013d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800013d7  mov     rsi, rax
0x1800013da  test    rax, rax
0x1800013dd  jz      short loc_180001448
0x1800013df  jmp     short loc_1800013F5
0x1800013e1  mov     rbx, [rsp+58h+arg_0]
0x1800013e6  mov     r14, [rsp+58h+arg_10]
0x1800013eb  mov     rdi, [rsp+58h+arg_8]
0x1800013f0  mov     rsi, [rsp+58h+arg_18]
0x1800013f5  test    r14, r14
0x1800013f8  jz      short loc_180001414
0x1800013fa  cmp     qword ptr [rbx+18h], 10h
0x1800013ff  jb      short loc_180001406
0x180001401  mov     rdx, [rbx]
0x180001404  jmp     short loc_180001409
0x180001406  mov     rdx, rbx; Src
0x180001409  mov     r8, r14; Size
0x18000140c  mov     rcx, rsi; void *
0x18000140f  call    memcpy_0
0x180001414  cmp     qword ptr [rbx+18h], 10h
0x180001419  jb      short loc_180001423
0x18000141b  mov     rcx, [rbx]; void *
0x18000141e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001423  lea     rax, [rbx+10h]
0x180001427  mov     [rbx], rsi
0x18000142a  mov     [rbx+18h], rdi
0x18000142e  cmp     rdi, 10h
0x180001432  cmovnb  rbx, rsi
0x180001436  mov     [rax], r14
0x180001439  mov     byte ptr [rbx+r14], 0
0x18000143e  add     rsp, 38h
0x180001442  pop     r14
0x180001444  pop     rdi
0x180001445  pop     rsi
0x180001446  pop     rbx
0x180001447  retn
0x180001448  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
