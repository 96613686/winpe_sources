# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000ff54`
- end: `0x1800100ac`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `344`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002300`
- `0x1800054cc`
- `0x18000be1c`
- `0x1800100b4`
- `0x1800103a8`
- `0x180010548`
- `0x1800106fc`
- `0x180010958`

## callees

- `0x180001264`
- `0x180001e44`
- `0x180004bdc`
- `0x18000ff54`
- `0x18001b3d6`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010051`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010051`

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
  __int64 v12; // r12
  _QWORD *result; // rax
  void *v14; // rax
  unsigned __int64 v15; // rcx
  const char *v16; // rdx
  _BYTE *v17; // rdx
  _BYTE v18[32]; // [rsp+0h] [rbp-88h] BYREF
  void *v19; // [rsp+20h] [rbp-68h]
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v21[72]; // [rsp+40h] [rbp-48h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
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
    v10 = 0;
    if ( v4 != -1 && (v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, (const char *)v6);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v19 = v10;
  }
  catch ( ... )
  {
    v16 = v18;
    try
    {
      v14 = 0;
      v15 = a2 + 1;
      if ( a2 != -1 && (v15 > 0x7FFFFFFFFFFFFFFFLL || (v14 = operator new(2 * v15)) == 0) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v21, v16);
        throw (std::bad_alloc *)v21;
      }
      v19 = v14;
    }
    catch ( ... )
    {
      v17 = v18;
      LOBYTE(v17) = 1;
      std::wstring::_Tidy(Src, v17, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v19;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    v12 = 2 * v3;
    memcpy_0(v10, v11, 2 * v3);
  }
  else
  {
    v12 = 0;
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  v5[3] = (const void *)7;
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *(_WORD *)((char *)v5 + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000ff54  mov     rax, rsp
0x18000ff57  mov     [rax+20h], rbx
0x18000ff5b  mov     [rax+18h], r8
0x18000ff5f  mov     [rax+10h], rdx
0x18000ff63  mov     [rax+8], rcx
0x18000ff67  push    rsi
0x18000ff68  push    rdi
0x18000ff69  push    r12
0x18000ff6b  push    r14
0x18000ff6d  push    r15
0x18000ff6f  sub     rsp, 60h
0x18000ff73  mov     r15, r8
0x18000ff76  mov     rdi, rdx
0x18000ff79  mov     rbx, rcx
0x18000ff7c  or      rdx, 7
0x18000ff80  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000ff8a  cmp     rdx, r9
0x18000ff8d  ja      short loc_18000FFC3
0x18000ff8f  mov     rdi, rdx
0x18000ff92  mov     r8, [rcx+18h]
0x18000ff96  mov     rcx, r8
0x18000ff99  shr     rcx, 1
0x18000ff9c  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000ffa6  mul     rdx
0x18000ffa9  shr     rdx, 1; char *
0x18000ffac  cmp     rcx, rdx
0x18000ffaf  jbe     short loc_18000FFC3
0x18000ffb1  mov     rax, r9
0x18000ffb4  sub     rax, rcx
0x18000ffb7  cmp     r8, rax
0x18000ffba  lea     rdi, [rcx+r8]
0x18000ffbe  jbe     short loc_18000FFC3
0x18000ffc0  mov     rdi, r9
0x18000ffc3  lea     rcx, [rdi+1]
0x18000ffc7  xor     esi, esi
0x18000ffc9  mov     r14d, esi
0x18000ffcc  test    rcx, rcx
0x18000ffcf  jz      short loc_18000FFF8
0x18000ffd1  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000ffdb  cmp     rcx, rax
0x18000ffde  ja      loc_18001008F
0x18000ffe4  add     rcx, rcx; Size
0x18000ffe7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ffec  mov     r14, rax
0x18000ffef  test    rax, rax
0x18000fff2  jz      loc_18001008F
0x18000fff8  mov     [rsp+88h+var_68], r14
0x18000fffd  jmp     short loc_18001001E
0x18000ffff  xor     esi, esi
0x180010001  mov     rbx, [rsp+88h+arg_0]
0x180010009  mov     r15, [rsp+88h+arg_10]
0x180010011  mov     rdi, [rsp+88h+arg_8]
0x180010019  mov     r14, [rsp+88h+var_68]
0x18001001e  test    r15, r15
0x180010021  jz      short loc_180010043
0x180010023  cmp     qword ptr [rbx+18h], 8
0x180010028  jb      short loc_18001002F
0x18001002a  mov     rdx, [rbx]
0x18001002d  jmp     short loc_180010032
0x18001002f  mov     rdx, rbx; Src
0x180010032  lea     r12, [r15+r15]
0x180010036  mov     r8, r12; Size
0x180010039  mov     rcx, r14; void *
0x18001003c  call    memcpy_0
0x180010041  jmp     short loc_180010047
0x180010043  lea     r12, [r15+r15]
0x180010047  cmp     qword ptr [rbx+18h], 8
0x18001004c  jb      short loc_180010057
0x18001004e  mov     rcx, [rbx]
0x180010051  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010057  mov     qword ptr [rbx+18h], 7
0x18001005f  lea     rax, [rbx+10h]
0x180010063  mov     [rbx], r14
0x180010066  mov     [rbx+18h], rdi
0x18001006a  cmp     rdi, 8
0x18001006e  cmovnb  rbx, r14
0x180010072  mov     [rax], r15
0x180010075  mov     [r12+rbx], si
0x18001007a  mov     rbx, [rsp+88h+arg_18]
0x180010082  add     rsp, 60h
0x180010086  pop     r15
0x180010088  pop     r14
0x18001008a  pop     r12
0x18001008c  pop     rdi
0x18001008d  pop     rsi
0x18001008e  retn
0x18001008f  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180010094  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180010099  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800100a0  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800100a5  call    _CxxThrowException_0
```
