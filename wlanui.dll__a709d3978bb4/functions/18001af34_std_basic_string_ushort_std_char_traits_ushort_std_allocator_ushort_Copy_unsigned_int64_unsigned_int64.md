# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18001af34`
- end: `0x18001b047`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180019c58`
- `0x18001a8c0`
- `0x18001b214`
- `0x18001b4b8`
- `0x18001b820`

## callees

- `0x1800011d0`
- `0x180001378`
- `0x180001e26`
- `0x18001af34`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b013`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b013`

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
0x18001af34  mov     [rsp+arg_10], r8
0x18001af39  mov     [rsp+arg_8], rdx
0x18001af3e  mov     [rsp+arg_0], rcx
0x18001af43  push    rbx
0x18001af44  push    rsi
0x18001af45  push    rdi
0x18001af46  push    r14
0x18001af48  push    r15
0x18001af4a  sub     rsp, 20h
0x18001af4e  mov     r15, r8
0x18001af51  mov     rdi, rdx
0x18001af54  mov     rbx, rcx
0x18001af57  or      rdx, 7
0x18001af5b  mov     r9, 7FFFFFFFFFFFFFFEh
0x18001af65  cmp     rdx, r9
0x18001af68  ja      short loc_18001AF9E
0x18001af6a  mov     rdi, rdx
0x18001af6d  mov     r8, [rcx+18h]
0x18001af71  mov     rcx, r8
0x18001af74  shr     rcx, 1
0x18001af77  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001af81  mul     rdx
0x18001af84  shr     rdx, 1
0x18001af87  cmp     rcx, rdx
0x18001af8a  jbe     short loc_18001AF9E
0x18001af8c  mov     rax, r9
0x18001af8f  sub     rax, rcx
0x18001af92  cmp     r8, rax
0x18001af95  lea     rdi, [rcx+r8]
0x18001af99  jbe     short loc_18001AF9E
0x18001af9b  mov     rdi, r9
0x18001af9e  lea     rcx, [rdi+1]
0x18001afa2  xor     esi, esi
0x18001afa4  test    rcx, rcx
0x18001afa7  jz      short loc_18001AFCE
0x18001afa9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001afb3  cmp     rcx, rax
0x18001afb6  ja      loc_18001B040
0x18001afbc  add     rcx, rcx; Size
0x18001afbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001afc4  mov     r14, rax
0x18001afc7  test    rax, rax
0x18001afca  jz      short loc_18001B040
0x18001afcc  jmp     short loc_18001AFD1
0x18001afce  mov     r14, rsi
0x18001afd1  jmp     short loc_18001AFE9
0x18001afd3  xor     esi, esi
0x18001afd5  mov     rbx, [rsp+48h+arg_0]
0x18001afda  mov     r15, [rsp+48h+arg_10]
0x18001afdf  mov     rdi, [rsp+48h+arg_8]
0x18001afe4  mov     r14, [rsp+48h+arg_18]
0x18001afe9  test    r15, r15
0x18001afec  jz      short loc_18001B009
0x18001afee  cmp     qword ptr [rbx+18h], 8
0x18001aff3  jb      short loc_18001AFFA
0x18001aff5  mov     rdx, [rbx]
0x18001aff8  jmp     short loc_18001AFFD
0x18001affa  mov     rdx, rbx; Src
0x18001affd  lea     r8, [r15+r15]; Size
0x18001b001  mov     rcx, r14; void *
0x18001b004  call    memcpy_0
0x18001b009  cmp     qword ptr [rbx+18h], 8
0x18001b00e  jb      short loc_18001B019
0x18001b010  mov     rcx, [rbx]
0x18001b013  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b019  lea     rax, [rbx+10h]
0x18001b01d  mov     [rbx], r14
0x18001b020  mov     [rbx+18h], rdi
0x18001b024  cmp     rdi, 8
0x18001b028  cmovnb  rbx, r14
0x18001b02c  mov     [rax], r15
0x18001b02f  mov     [rbx+r15*2], si
0x18001b034  add     rsp, 20h
0x18001b038  pop     r15
0x18001b03a  pop     r14
0x18001b03c  pop     rdi
0x18001b03d  pop     rsi
0x18001b03e  pop     rbx
0x18001b03f  retn
0x18001b040  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
