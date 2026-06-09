# StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)

- ea: `0x180008c58`
- end: `0x180008e9b`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z`
- size: `579`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800088c0`
- `0x18000a7fc`
- `0x18001bb48`
- `0x18001bd8c`
- `0x18001bfd0`
- `0x18001c4b4`

## callees

- `0x180008c58`
- `0x18000a334`
- `0x18001cc38`
- `0x18002b1b0`
- `0x18002e495`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180008c95`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180008c95`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008d86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008d86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180008d2c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180008d2c`

## string_xrefs

- `0x180008cfa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008d42`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(StateRepository::Cache::Key_NoThrow *this, __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // r9
  HRESULT v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // rbp
  wchar_t *v8; // rcx
  __int64 i; // rbx
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  void *v13; // rax
  void *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  size_t *v17; // r8
  unsigned __int64 v18; // rdx
  size_t *v19; // rax
  unsigned __int64 v20; // rax
  wchar_t *v21; // rdx
  _WORD *v22; // rcx
  unsigned __int64 j; // r8
  int cchToCopy; // [rsp+20h] [rbp-68h]
  wchar_t pszSrc[20]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !(unsigned int)_o__ui64tow_s(a2, pszSrc, 17) )
  {
    v7 = 0;
    v8 = pszSrc;
    for ( i = 0; ; i = v11 )
    {
      v10 = *v8;
      if ( !(_WORD)v10 )
        break;
      if ( ++v7 >= 0x7FFFFFFF )
      {
        v5 = -2147024809;
        v6 = 309;
        goto LABEL_10;
      }
      v11 = i + 1;
      ++v8;
      if ( (_WORD)v10 != 94 )
        v11 = i;
    }
    v12 = v7 + i + *((_QWORD *)this + 65) + 1LL;
    if ( v12 <= *((_QWORD *)this + 66) )
    {
      v17 = (size_t *)*((_QWORD *)this + 67);
      v12 = *((_QWORD *)this + 66);
    }
    else
    {
      v13 = (void *)SRCache_AllocStringBuffer((unsigned int)v12, v10, v3, v4);
      v14 = v13;
      if ( !v13 )
      {
        v5 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          cchToCopy);
        v6 = 310;
        goto LABEL_10;
      }
      memcpy_0(v13, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v16 = *(_QWORD *)this;
      *(_QWORD *)this = v14;
      if ( v16 )
        SRCache_Free(v16, v15);
      v17 = *(size_t **)this;
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v12;
    }
    if ( i )
    {
      v21 = pszSrc;
      v22 = (_WORD *)v17 + *((_QWORD *)this + 65);
      for ( j = 0; j < v7; ++v22 )
      {
        if ( *v21 == 94 )
          *v22++ = 94;
        ++j;
        *v22 = *v21++;
      }
      *v22 = 0;
    }
    else
    {
      if ( v12 - 1 > 0x7FFFFFFE )
      {
        v5 = -2147024809;
LABEL_30:
        v6 = 313;
        goto LABEL_10;
      }
      v18 = v12;
      v19 = v17;
      do
      {
        if ( !*(_WORD *)v19 )
          break;
        v19 = (size_t *)((char *)v19 + 2);
        --v18;
      }
      while ( v18 );
      v5 = v18 == 0 ? 0x80070057 : 0;
      if ( v18 )
        v20 = v12 - v18;
      else
        v20 = 0;
      if ( !v18 )
        goto LABEL_30;
      v5 = StringCopyWorkerW((STRSAFE_LPWSTR)v17 + v20, v12 - v20, v17, pszSrc, 0x7FFFFFFEu);
      if ( v5 < 0 )
        goto LABEL_30;
    }
    *((_QWORD *)this + 65) += v7;
    return 0;
  }
  v5 = -2147418113;
  v6 = 358;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)(unsigned int)v5,
    cchToCopy);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008c58  mov     [rsp+arg_10], rbx
0x180008c5d  mov     [rsp+arg_18], rbp
0x180008c62  push    rsi
0x180008c63  push    rdi
0x180008c64  push    r12
0x180008c66  push    r14
0x180008c68  push    r15
0x180008c6a  sub     rsp, 60h
0x180008c6e  mov     rax, cs:__security_cookie
0x180008c75  xor     rax, rsp
0x180008c78  mov     [rsp+88h+var_30], rax
0x180008c7d  mov     rax, rdx
0x180008c80  mov     r9d, 10h
0x180008c86  mov     rdi, rcx
0x180008c89  lea     rdx, [rsp+88h+pszSrc]
0x180008c8e  mov     rcx, rax
0x180008c91  lea     r8d, [r9+1]
0x180008c95  call    cs:__imp__o__ui64tow_s
0x180008c9b  xor     r15d, r15d
0x180008c9e  test    eax, eax
0x180008ca0  jz      short loc_180008CAE
0x180008ca2  mov     ebx, 8000FFFFh
0x180008ca7  mov     edx, 166h
0x180008cac  jmp     short loc_180008CF2
0x180008cae  mov     rbp, r15
0x180008cb1  lea     rcx, [rsp+88h+pszSrc]
0x180008cb6  mov     rbx, r15
0x180008cb9  mov     r12d, 5Eh ; '^'
0x180008cbf  movzx   edx, word ptr [rcx]
0x180008cc2  test    dx, dx
0x180008cc5  jz      short loc_180008D0E
0x180008cc7  inc     rbp
0x180008cca  cmp     rbp, 7FFFFFFFh
0x180008cd1  jnb     short loc_180008CE8
0x180008cd3  lea     rax, [rbx+1]
0x180008cd7  add     rcx, 2
0x180008cdb  cmp     dx, r12w
0x180008cdf  cmovnz  rax, rbx
0x180008ce3  mov     rbx, rax
0x180008ce6  jmp     short loc_180008CBF
0x180008ce8  mov     ebx, 80070057h
0x180008ced  mov     edx, 135h; void *
0x180008cf2  mov     rcx, [rsp+88h]; this
0x180008cfa  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d01  mov     r9d, ebx; char *
0x180008d04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d09  jmp     loc_180008E73
0x180008d0e  mov     rsi, [rdi+208h]
0x180008d15  mov     rax, [rdi+210h]
0x180008d1c  inc     rsi
0x180008d1f  add     rsi, rbx
0x180008d22  add     rsi, rbp
0x180008d25  cmp     rsi, rax
0x180008d28  jbe     short loc_180008D9F
0x180008d2a  mov     ecx, esi
0x180008d2c  call    cs:__imp_SRCache_AllocStringBuffer
0x180008d32  mov     r14, rax
0x180008d35  test    rax, rax
0x180008d38  jnz     short loc_180008D62
0x180008d3a  mov     rcx, [rsp+88h]; this
0x180008d42  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d49  mov     ebx, 8007000Eh
0x180008d4e  mov     edx, 193h; void *
0x180008d53  mov     r9d, ebx; char *
0x180008d56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d5b  mov     edx, 136h
0x180008d60  jmp     short loc_180008CF2
0x180008d62  mov     r8, [rdi+210h]
0x180008d69  mov     rcx, r14; void *
0x180008d6c  mov     rdx, [rdi+218h]; Src
0x180008d73  add     r8, r8; Size
0x180008d76  call    memcpy_0
0x180008d7b  mov     rcx, [rdi]
0x180008d7e  mov     [rdi], r14
0x180008d81  test    rcx, rcx
0x180008d84  jz      short loc_180008D8C
0x180008d86  call    cs:__imp_SRCache_Free
0x180008d8c  mov     r8, [rdi]
0x180008d8f  mov     [rdi+218h], r8
0x180008d96  mov     [rdi+210h], rsi
0x180008d9d  jmp     short loc_180008DA9
0x180008d9f  mov     r8, [rdi+218h]; pcchNewDestLength
0x180008da6  mov     rsi, rax
0x180008da9  test    rbx, rbx
0x180008dac  jnz     short loc_180008E29
0x180008dae  lea     rax, [rsi-1]
0x180008db2  mov     r9d, 7FFFFFFEh
0x180008db8  cmp     rax, r9
0x180008dbb  ja      short loc_180008E1A
0x180008dbd  mov     rdx, rsi
0x180008dc0  mov     rax, r8
0x180008dc3  cmp     [rax], r15w
0x180008dc7  jz      short loc_180008DD3
0x180008dc9  add     rax, 2
0x180008dcd  sub     rdx, 1
0x180008dd1  jnz     short loc_180008DC3
0x180008dd3  mov     rax, rdx
0x180008dd6  mov     ebx, 80070057h
0x180008ddb  neg     rax
0x180008dde  sbb     ecx, ecx
0x180008de0  not     ecx
0x180008de2  and     ebx, ecx
0x180008de4  test    rdx, rdx
0x180008de7  jz      short loc_180008DF1
0x180008de9  mov     rax, rsi
0x180008dec  sub     rax, rdx
0x180008def  jmp     short loc_180008DF4
0x180008df1  mov     rax, r15
0x180008df4  test    rdx, rdx
0x180008df7  jz      short loc_180008E1F
0x180008df9  sub     rsi, rax
0x180008dfc  mov     qword ptr [rsp+88h+cchToCopy], r9; cchToCopy
0x180008e01  mov     rdx, rsi; cchDest
0x180008e04  lea     rcx, [r8+rax*2]; pszDest
0x180008e08  lea     r9, [rsp+88h+pszSrc]; pszSrc
0x180008e0d  call    StringCopyWorkerW
0x180008e12  mov     ebx, eax
0x180008e14  test    eax, eax
0x180008e16  jns     short loc_180008E69
0x180008e18  jmp     short loc_180008E1F
0x180008e1a  mov     ebx, 80070057h
0x180008e1f  mov     edx, 139h
0x180008e24  jmp     loc_180008CF2
0x180008e29  mov     rax, [rdi+208h]
0x180008e30  lea     rdx, [rsp+88h+pszSrc]
0x180008e35  lea     rcx, [r8+rax*2]
0x180008e39  mov     r8, r15
0x180008e3c  test    rbp, rbp
0x180008e3f  jz      short loc_180008E65
0x180008e41  cmp     [rdx], r12w
0x180008e45  jnz     short loc_180008E4F
0x180008e47  mov     [rcx], r12w
0x180008e4b  add     rcx, 2
0x180008e4f  movzx   eax, word ptr [rdx]
0x180008e52  inc     r8
0x180008e55  mov     [rcx], ax
0x180008e58  add     rdx, 2
0x180008e5c  add     rcx, 2
0x180008e60  cmp     r8, rbp
0x180008e63  jb      short loc_180008E41
0x180008e65  mov     [rcx], r15w
0x180008e69  add     [rdi+208h], rbp
0x180008e70  mov     ebx, r15d
0x180008e73  mov     eax, ebx
0x180008e75  mov     rcx, [rsp+88h+var_30]
0x180008e7a  xor     rcx, rsp; StackCookie
0x180008e7d  call    __security_check_cookie
0x180008e82  lea     r11, [rsp+88h+var_28]
0x180008e87  mov     rbx, [r11+40h]
0x180008e8b  mov     rbp, [r11+48h]
0x180008e8f  mov     rsp, r11
0x180008e92  pop     r15
0x180008e94  pop     r14
0x180008e96  pop     r12
0x180008e98  pop     rdi
0x180008e99  pop     rsi
0x180008e9a  retn
```
