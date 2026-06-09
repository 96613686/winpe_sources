# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180011b54`
- end: `0x180011c9a`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180011d2c`

## callees

- `0x180008700`
- `0x180008fce`
- `0x180011b54`
- `0x1800124fc`
- `0x180012848`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180011bfd`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180011bfd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const char *__fastcall std::wstring::_Copy(const char **a1, unsigned __int64 a2, const char *a3)
{
  const char *v3; // r15
  unsigned __int64 v4; // rdi
  const char **v5; // rsi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  const char *v10; // r14
  const char **v11; // rdx
  const char *result; // rax
  const char *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[32]; // [rsp+0h] [rbp-78h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v18[8]; // [rsp+38h] [rbp-40h] BYREF
  const char *v20; // [rsp+88h] [rbp+10h] BYREF
  const char *v21; // [rsp+90h] [rbp+18h]
  const char *v22; // [rsp+98h] [rbp+20h] BYREF

  v21 = a3;
  v20 = (const char *)a2;
  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)a1[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
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
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = (const char *)operator new(2 * v9)) == 0 )
    {
      v22 = 0;
      exception::exception((exception *)pExceptionObject, &v22);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v16;
    try
    {
      v13 = 0;
      v14 = (unsigned __int64)(v20 + 1);
      if ( v20 != (const char *)-1LL && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = (const char *)operator new(2 * v14)) == 0) )
      {
        exception::exception((exception *)v18, &v20);
        v18[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)v18;
      }
      v22 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = v21;
    v4 = (unsigned __int64)v20;
    v10 = v22;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = (const char **)*v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = (const char *)v4;
  result = (const char *)v5;
  if ( v4 >= 8 )
    result = v10;
  v5[2] = v3;
  *(_WORD *)&result[2 * (_QWORD)v3] = 0;
  return result;
}

```

## disassembly

```asm
0x180011b54  mov     [rsp+arg_10], r8
0x180011b59  mov     [rsp+arg_8], rdx
0x180011b5e  mov     [rsp+arg_0], rcx
0x180011b63  push    rbx
0x180011b64  push    rsi
0x180011b65  push    rdi
0x180011b66  push    r14
0x180011b68  push    r15
0x180011b6a  sub     rsp, 50h
0x180011b6e  mov     r15, r8
0x180011b71  mov     rdi, rdx
0x180011b74  mov     rsi, rcx
0x180011b77  or      rdx, 7
0x180011b7b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180011b85  cmp     rdx, r9
0x180011b88  ja      short loc_180011BBE
0x180011b8a  mov     rdi, rdx
0x180011b8d  mov     r8, [rcx+18h]
0x180011b91  mov     rcx, r8
0x180011b94  shr     rcx, 1
0x180011b97  mov     rax, 0AAAAAAAAAAAAAAABh
0x180011ba1  mul     rdx
0x180011ba4  shr     rdx, 1
0x180011ba7  cmp     rcx, rdx
0x180011baa  jbe     short loc_180011BBE
0x180011bac  mov     rax, r9
0x180011baf  sub     rax, rcx
0x180011bb2  cmp     r8, rax
0x180011bb5  lea     rdi, [rcx+r8]
0x180011bb9  jbe     short loc_180011BBE
0x180011bbb  mov     rdi, r9
0x180011bbe  lea     rcx, [rdi+1]
0x180011bc2  xor     ebx, ebx
0x180011bc4  test    rcx, rcx
0x180011bc7  jz      short loc_180011C20
0x180011bc9  mov     rax, 7FFFFFFFFFFFFFFFh
0x180011bd3  cmp     rcx, rax
0x180011bd6  ja      short loc_180011BE8
0x180011bd8  add     rcx, rcx; Size
0x180011bdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011be0  mov     r14, rax
0x180011be3  test    rax, rax
0x180011be6  jnz     short loc_180011C23
0x180011be8  mov     [rsp+78h+arg_18], rbx
0x180011bf0  lea     rdx, [rsp+78h+arg_18]
0x180011bf8  lea     rcx, [rsp+78h+pExceptionObject]
0x180011bfd  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180011c03  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180011c0a  mov     [rsp+78h+pExceptionObject], rax
0x180011c0f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180011c16  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180011c1b  call    _CxxThrowException_0
0x180011c20  mov     r14, rbx
0x180011c23  jmp     short loc_180011C47
0x180011c25  xor     ebx, ebx
0x180011c27  mov     rsi, [rsp+78h+arg_0]
0x180011c2f  mov     r15, [rsp+78h+arg_10]
0x180011c37  mov     rdi, [rsp+78h+arg_8]
0x180011c3f  mov     r14, [rsp+78h+arg_18]
0x180011c47  test    r15, r15
0x180011c4a  jz      short loc_180011C66
0x180011c4c  cmp     qword ptr [rsi+18h], 8
0x180011c51  jb      short loc_180011C58
0x180011c53  mov     rdx, [rsi]
0x180011c56  jmp     short loc_180011C5B
0x180011c58  mov     rdx, rsi
0x180011c5b  mov     r8, r15
0x180011c5e  mov     rcx, r14
0x180011c61  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180011c66  xor     r8d, r8d
0x180011c69  mov     dl, 1
0x180011c6b  mov     rcx, rsi
0x180011c6e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011c73  mov     [rsi], r14
0x180011c76  mov     [rsi+18h], rdi
0x180011c7a  mov     rax, rsi
0x180011c7d  cmp     rdi, 8
0x180011c81  cmovnb  rax, r14
0x180011c85  mov     [rsi+10h], r15
0x180011c89  mov     [rax+r15*2], bx
0x180011c8e  add     rsp, 50h
0x180011c92  pop     r15
0x180011c94  pop     r14
0x180011c96  pop     rdi
0x180011c97  pop     rsi
0x180011c98  pop     rbx
0x180011c99  retn
```
