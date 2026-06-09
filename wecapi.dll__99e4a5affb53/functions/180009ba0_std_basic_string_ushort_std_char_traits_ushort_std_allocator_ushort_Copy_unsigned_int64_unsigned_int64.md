# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180009ba0`
- end: `0x180009cb2`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `274`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009ff0`
- `0x18000a100`
- `0x18000a4ec`
- `0x18000aaa0`
- `0x18000b380`

## callees

- `0x1800012d8`
- `0x180001ac6`
- `0x18000262c`
- `0x1800026c0`
- `0x180009ba0`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180009ba0  mov     [rsp+arg_10], r8
0x180009ba5  mov     [rsp+arg_8], rdx
0x180009baa  mov     [rsp+arg_0], rcx
0x180009baf  push    rbx
0x180009bb0  push    rsi
0x180009bb1  push    rdi
0x180009bb2  push    r14
0x180009bb4  push    r15
0x180009bb6  sub     rsp, 20h
0x180009bba  mov     r15, r8
0x180009bbd  mov     rdi, rdx
0x180009bc0  mov     rbx, rcx
0x180009bc3  or      rdx, 7
0x180009bc7  mov     r9, 7FFFFFFFFFFFFFFEh
0x180009bd1  cmp     rdx, r9
0x180009bd4  ja      short loc_180009C0A
0x180009bd6  mov     rdi, rdx
0x180009bd9  mov     r8, [rcx+18h]
0x180009bdd  mov     rcx, r8
0x180009be0  shr     rcx, 1
0x180009be3  mov     rax, 0AAAAAAAAAAAAAAABh
0x180009bed  mul     rdx
0x180009bf0  shr     rdx, 1
0x180009bf3  cmp     rcx, rdx
0x180009bf6  jbe     short loc_180009C0A
0x180009bf8  mov     rax, r9
0x180009bfb  sub     rax, rcx
0x180009bfe  cmp     r8, rax
0x180009c01  lea     rdi, [rcx+r8]
0x180009c05  jbe     short loc_180009C0A
0x180009c07  mov     rdi, r9
0x180009c0a  lea     rcx, [rdi+1]
0x180009c0e  xor     esi, esi
0x180009c10  test    rcx, rcx
0x180009c13  jz      short loc_180009C3A
0x180009c15  mov     rax, 7FFFFFFFFFFFFFFFh
0x180009c1f  cmp     rcx, rax
0x180009c22  ja      loc_180009CAB
0x180009c28  add     rcx, rcx; dwBytes
0x180009c2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009c30  mov     r14, rax
0x180009c33  test    rax, rax
0x180009c36  jz      short loc_180009CAB
0x180009c38  jmp     short loc_180009C3D
0x180009c3a  mov     r14, rsi
0x180009c3d  jmp     short loc_180009C55
0x180009c3f  xor     esi, esi
0x180009c41  mov     rbx, [rsp+48h+arg_0]
0x180009c46  mov     r15, [rsp+48h+arg_10]
0x180009c4b  mov     rdi, [rsp+48h+arg_8]
0x180009c50  mov     r14, [rsp+48h+arg_18]
0x180009c55  test    r15, r15
0x180009c58  jz      short loc_180009C75
0x180009c5a  cmp     qword ptr [rbx+18h], 8
0x180009c5f  jb      short loc_180009C66
0x180009c61  mov     rdx, [rbx]
0x180009c64  jmp     short loc_180009C69
0x180009c66  mov     rdx, rbx; Src
0x180009c69  lea     r8, [r15+r15]; Size
0x180009c6d  mov     rcx, r14; void *
0x180009c70  call    memcpy_0
0x180009c75  cmp     qword ptr [rbx+18h], 8
0x180009c7a  jb      short loc_180009C84
0x180009c7c  mov     rcx, [rbx]; void *
0x180009c7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009c84  lea     rax, [rbx+10h]
0x180009c88  mov     [rbx], r14
0x180009c8b  mov     [rbx+18h], rdi
0x180009c8f  cmp     rdi, 8
0x180009c93  cmovnb  rbx, r14
0x180009c97  mov     [rax], r15
0x180009c9a  mov     [rbx+r15*2], si
0x180009c9f  add     rsp, 20h
0x180009ca3  pop     r15
0x180009ca5  pop     r14
0x180009ca7  pop     rdi
0x180009ca8  pop     rsi
0x180009ca9  pop     rbx
0x180009caa  retn
0x180009cab  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
