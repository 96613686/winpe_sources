# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800164c4`
- end: `0x1800165b4`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001664c`
- `0x180016744`

## callees

- `0x1800011d0`
- `0x180001378`
- `0x180001e26`
- `0x1800164c4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016582`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016582`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800164c4  mov     [rsp+arg_10], r8
0x1800164c9  mov     [rsp+arg_8], rdx
0x1800164ce  mov     [rsp+arg_0], rcx
0x1800164d3  push    rbx
0x1800164d4  push    rsi
0x1800164d5  push    rdi
0x1800164d6  push    r14
0x1800164d8  sub     rsp, 28h
0x1800164dc  mov     r14, r8
0x1800164df  mov     rdi, rdx
0x1800164e2  mov     rbx, rcx
0x1800164e5  or      rdx, 0Fh
0x1800164e9  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800164f0  cmp     rdx, r9
0x1800164f3  ja      short loc_180016529
0x1800164f5  mov     rdi, rdx
0x1800164f8  mov     r8, [rcx+18h]
0x1800164fc  mov     rcx, r8
0x1800164ff  shr     rcx, 1
0x180016502  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001650c  mul     rdx
0x18001650f  shr     rdx, 1
0x180016512  cmp     rcx, rdx
0x180016515  jbe     short loc_180016529
0x180016517  mov     rax, r9
0x18001651a  sub     rax, rcx
0x18001651d  cmp     r8, rax
0x180016520  lea     rdi, [rcx+r8]
0x180016524  jbe     short loc_180016529
0x180016526  mov     rdi, r9
0x180016529  lea     rcx, [rdi+1]; Size
0x18001652d  test    rcx, rcx
0x180016530  jz      short loc_180016541
0x180016532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016537  mov     rsi, rax
0x18001653a  test    rax, rax
0x18001653d  jz      short loc_1800165AD
0x18001653f  jmp     short loc_180016543
0x180016541  xor     esi, esi
0x180016543  jmp     short loc_180016559
0x180016545  mov     rbx, [rsp+48h+arg_0]
0x18001654a  mov     r14, [rsp+48h+arg_10]
0x18001654f  mov     rdi, [rsp+48h+arg_8]
0x180016554  mov     rsi, [rsp+48h+arg_18]
0x180016559  test    r14, r14
0x18001655c  jz      short loc_180016578
0x18001655e  cmp     qword ptr [rbx+18h], 10h
0x180016563  jb      short loc_18001656A
0x180016565  mov     rdx, [rbx]
0x180016568  jmp     short loc_18001656D
0x18001656a  mov     rdx, rbx; Src
0x18001656d  mov     r8, r14; Size
0x180016570  mov     rcx, rsi; void *
0x180016573  call    memcpy_0
0x180016578  cmp     qword ptr [rbx+18h], 10h
0x18001657d  jb      short loc_180016588
0x18001657f  mov     rcx, [rbx]
0x180016582  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016588  lea     rax, [rbx+10h]
0x18001658c  mov     [rbx], rsi
0x18001658f  mov     [rbx+18h], rdi
0x180016593  cmp     rdi, 10h
0x180016597  cmovnb  rbx, rsi
0x18001659b  mov     [rax], r14
0x18001659e  mov     byte ptr [rbx+r14], 0
0x1800165a3  add     rsp, 28h
0x1800165a7  pop     r14
0x1800165a9  pop     rdi
0x1800165aa  pop     rsi
0x1800165ab  pop     rbx
0x1800165ac  retn
0x1800165ad  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
