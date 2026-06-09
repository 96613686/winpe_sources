# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180012ae8`
- end: `0x180012c35`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180012cd0`

## callees

- `0x180008f6c`
- `0x18000983e`
- `0x180012ae8`
- `0x1800134bc`
- `0x180013814`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180012b91`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180012b91`

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
0x180012ae8  mov     [rsp+arg_10], r8
0x180012aed  mov     [rsp+arg_8], rdx
0x180012af2  mov     [rsp+arg_0], rcx
0x180012af7  push    rbx
0x180012af8  push    rsi
0x180012af9  push    rdi
0x180012afa  push    r14
0x180012afc  push    r15
0x180012afe  sub     rsp, 50h
0x180012b02  mov     r15, r8
0x180012b05  mov     rdi, rdx
0x180012b08  mov     rsi, rcx
0x180012b0b  or      rdx, 7
0x180012b0f  mov     r9, 7FFFFFFFFFFFFFFEh
0x180012b19  cmp     rdx, r9
0x180012b1c  ja      short loc_180012B52
0x180012b1e  mov     rdi, rdx
0x180012b21  mov     r8, [rcx+18h]
0x180012b25  mov     rcx, r8
0x180012b28  shr     rcx, 1
0x180012b2b  mov     rax, 0AAAAAAAAAAAAAAABh
0x180012b35  mul     rdx
0x180012b38  shr     rdx, 1
0x180012b3b  cmp     rcx, rdx
0x180012b3e  jbe     short loc_180012B52
0x180012b40  mov     rax, r9
0x180012b43  sub     rax, rcx
0x180012b46  cmp     r8, rax
0x180012b49  lea     rdi, [rcx+r8]
0x180012b4d  jbe     short loc_180012B52
0x180012b4f  mov     rdi, r9
0x180012b52  lea     rcx, [rdi+1]
0x180012b56  xor     ebx, ebx
0x180012b58  test    rcx, rcx
0x180012b5b  jz      short loc_180012BBA
0x180012b5d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180012b67  cmp     rcx, rax
0x180012b6a  ja      short loc_180012B7C
0x180012b6c  add     rcx, rcx; Size
0x180012b6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012b74  mov     r14, rax
0x180012b77  test    rax, rax
0x180012b7a  jnz     short loc_180012BBD
0x180012b7c  mov     [rsp+78h+arg_18], rbx
0x180012b84  lea     rdx, [rsp+78h+arg_18]
0x180012b8c  lea     rcx, [rsp+78h+pExceptionObject]
0x180012b91  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180012b98  nop     dword ptr [rax+rax+00h]
0x180012b9d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180012ba4  mov     [rsp+78h+pExceptionObject], rax
0x180012ba9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180012bb0  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180012bb5  call    _CxxThrowException_0
0x180012bba  mov     r14, rbx
0x180012bbd  jmp     short loc_180012BE1
0x180012bbf  xor     ebx, ebx
0x180012bc1  mov     rsi, [rsp+78h+arg_0]
0x180012bc9  mov     r15, [rsp+78h+arg_10]
0x180012bd1  mov     rdi, [rsp+78h+arg_8]
0x180012bd9  mov     r14, [rsp+78h+arg_18]
0x180012be1  test    r15, r15
0x180012be4  jz      short loc_180012C00
0x180012be6  cmp     qword ptr [rsi+18h], 8
0x180012beb  jb      short loc_180012BF2
0x180012bed  mov     rdx, [rsi]
0x180012bf0  jmp     short loc_180012BF5
0x180012bf2  mov     rdx, rsi
0x180012bf5  mov     r8, r15
0x180012bf8  mov     rcx, r14
0x180012bfb  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180012c00  xor     r8d, r8d
0x180012c03  mov     dl, 1
0x180012c05  mov     rcx, rsi
0x180012c08  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012c0d  mov     [rsi], r14
0x180012c10  mov     [rsi+18h], rdi
0x180012c14  mov     rax, rsi
0x180012c17  cmp     rdi, 8
0x180012c1b  cmovnb  rax, r14
0x180012c1f  mov     [rsi+10h], r15
0x180012c23  mov     [rax+r15*2], bx
0x180012c28  add     rsp, 50h
0x180012c2c  pop     r15
0x180012c2e  pop     r14
0x180012c30  pop     rdi
0x180012c31  pop     rsi
0x180012c32  pop     rbx
0x180012c33  retn
```
