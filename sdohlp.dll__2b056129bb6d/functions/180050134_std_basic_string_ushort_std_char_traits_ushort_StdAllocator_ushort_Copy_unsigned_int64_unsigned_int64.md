# std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180050134`
- end: `0x18005026d`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAX_K0@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800508c0`

## callees

- `0x180024068`
- `0x180024e34`
- `0x18003e744`
- `0x18003ebc4`
- `0x180050134`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800501cb`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x1800501cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::_Copy(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rdx
  char *v11; // r14
  const void *v12; // rdx
  char *v13; // rcx
  __int64 result; // rax
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-78h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v18[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v21; // [rsp+80h] [rbp+8h]
  const char *v22; // [rsp+88h] [rbp+10h] BYREF
  __int64 v23; // [rsp+90h] [rbp+18h]
  char *v24; // [rsp+98h] [rbp+20h] BYREF

  v23 = a3;
  v22 = (const char *)a2;
  v3 = a3;
  v4 = a2;
  v5 = (const void **)a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 24);
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    if ( v4 + 1 > 0x7FFFFFFF )
    {
      v24 = "bad allocation";
      exception::exception((exception *)pExceptionObject, (const char *const *)&v24, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v11 = (char *)operator new(2 * (v4 + 1));
  }
  catch ( ... )
  {
    if ( (unsigned __int64)(v22 + 1) <= 0x7FFFFFFF )
    {
      v24 = (char *)operator new(2LL * (_QWORD)(v22 + 1));
      v5 = (const void **)a1;
      v3 = v23;
      v4 = (unsigned __int64)v22;
      v11 = v24;
      goto LABEL_8;
    }
    try
    {
      exception::exception((exception *)v18, &v22, 1);
      v18[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)v18;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(v21, v15, 0);
      throw;
    }
  }
LABEL_8:
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v12 = v5;
    else
      v12 = *v5;
    std::char_traits<unsigned short>::copy(v11, v12, v3);
  }
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v5, v10, 0);
  *v5 = v11;
  v5[3] = (const void *)v4;
  v13 = (char *)v5;
  if ( v4 >= 8 )
    v13 = v11;
  v5[2] = (const void *)v3;
  result = 0;
  *(_WORD *)&v13[2 * v3] = 0;
  return result;
}

```

## disassembly

```asm
0x180050134  mov     [rsp+arg_10], r8
0x180050139  mov     [rsp+arg_8], rdx
0x18005013e  mov     [rsp+arg_0], rcx
0x180050143  push    rbx
0x180050144  push    rsi
0x180050145  push    rdi
0x180050146  push    r14
0x180050148  sub     rsp, 58h
0x18005014c  mov     rsi, r8
0x18005014f  mov     rbx, rdx
0x180050152  mov     rdi, rcx
0x180050155  or      rdx, 7
0x180050159  mov     r9, 7FFFFFFFFFFFFFFEh
0x180050163  cmp     rdx, r9
0x180050166  ja      short loc_18005019C
0x180050168  mov     rbx, rdx
0x18005016b  mov     r8, [rcx+18h]
0x18005016f  mov     rcx, r8
0x180050172  shr     rcx, 1
0x180050175  mov     rax, 0AAAAAAAAAAAAAAABh
0x18005017f  mul     rdx
0x180050182  shr     rdx, 1
0x180050185  cmp     rcx, rdx
0x180050188  jbe     short loc_18005019C
0x18005018a  mov     rax, r9
0x18005018d  sub     rax, rcx
0x180050190  cmp     r8, rax
0x180050193  lea     rbx, [rcx+r8]
0x180050197  jbe     short loc_18005019C
0x180050199  mov     rbx, r9
0x18005019c  lea     rcx, [rbx+1]
0x1800501a0  cmp     rcx, 7FFFFFFFh
0x1800501a7  jbe     short loc_1800501EE
0x1800501a9  lea     rax, aBadAllocation; "bad allocation"
0x1800501b0  mov     [rsp+78h+arg_18], rax
0x1800501b8  mov     r8d, 1
0x1800501be  lea     rdx, [rsp+78h+arg_18]
0x1800501c6  lea     rcx, [rsp+78h+pExceptionObject]
0x1800501cb  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x1800501d1  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800501d8  mov     [rsp+78h+pExceptionObject], rax
0x1800501dd  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800501e4  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800501e9  call    _CxxThrowException_0
0x1800501ee  add     rcx, rcx; Size
0x1800501f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800501f6  mov     r14, rax
0x1800501f9  jmp     short loc_18005021B
0x1800501fb  mov     rdi, [rsp+78h+arg_0]
0x180050203  mov     rsi, [rsp+78h+arg_10]
0x18005020b  mov     rbx, [rsp+78h+arg_8]
0x180050213  mov     r14, [rsp+78h+arg_18]
0x18005021b  test    rsi, rsi
0x18005021e  jz      short loc_18005023A
0x180050220  cmp     qword ptr [rdi+18h], 8
0x180050225  jb      short loc_18005022C
0x180050227  mov     rdx, [rdi]
0x18005022a  jmp     short loc_18005022F
0x18005022c  mov     rdx, rdi
0x18005022f  mov     r8, rsi
0x180050232  mov     rcx, r14
0x180050235  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18005023a  xor     r8d, r8d
0x18005023d  mov     dl, 1
0x18005023f  mov     rcx, rdi
0x180050242  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180050247  mov     [rdi], r14
0x18005024a  mov     [rdi+18h], rbx
0x18005024e  mov     rcx, rdi
0x180050251  cmp     rbx, 8
0x180050255  cmovnb  rcx, r14
0x180050259  mov     [rdi+10h], rsi
0x18005025d  xor     eax, eax
0x18005025f  mov     [rcx+rsi*2], ax
0x180050263  add     rsp, 58h
0x180050267  pop     r14
0x180050269  pop     rdi
0x18005026a  pop     rsi
0x18005026b  pop     rbx
0x18005026c  retn
```
