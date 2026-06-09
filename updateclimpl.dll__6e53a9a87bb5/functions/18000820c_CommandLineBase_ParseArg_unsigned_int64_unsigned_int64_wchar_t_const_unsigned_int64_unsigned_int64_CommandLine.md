# CommandLineBase::ParseArg(unsigned __int64 *,unsigned __int64,wchar_t const * *,unsigned __int64,unsigned __int64,CommandLineArg *,unsigned __int64,wchar_t const *,wchar_t const * *)

- ea: `0x18000820c`
- end: `0x18000837c`
- name: `?ParseArg@CommandLineBase@@AEAAJPEA_K_KPEAPEB_W11PEAUCommandLineArg@@1PEB_W2@Z`
- size: `368`
- prototype: `__int64 __fastcall(CommandLineBase *__hidden this, unsigned __int64 *, unsigned __int64, const wchar_t **, unsigned __int64, unsigned __int64, struct CommandLineArg *, unsigned __int64, const wchar_t *, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007dec`

## callees

- `0x18000820c`
- `0x180010310`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall CommandLineBase::ParseArg(
        CommandLineBase *this,
        unsigned __int64 *a2,
        unsigned __int64 a3,
        const wchar_t **a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        struct CommandLineArg *a7,
        unsigned __int64 a8,
        const wchar_t *a9,
        const wchar_t **a10)
{
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // rdi
  bool v18; // cc
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // r10
  unsigned __int64 v22; // rcx
  __int64 result; // rax
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  _QWORD *v27; // rcx
  unsigned __int64 v28; // rdx
  __int64 v29; // [rsp+30h] [rbp-38h] BYREF

  if ( a10 )
    *a10 = 0;
  v13 = *a2;
  v14 = 0;
  v15 = a3 + v13;
  v16 = a5 - v15;
  v29 = 0;
  v17 = (char *)a7 + 56 * a6;
  v18 = v15 <= a5;
  v19 = (unsigned __int64)&a4[v15];
  if ( v18 )
    v14 = v16;
  v20 = *((_QWORD *)v17 + 3);
  v21 = v19 & -(__int64)(v14 != 0);
  if ( (v17[48] & 0x10) != 0 )
  {
    v22 = *((_QWORD *)v17 + 4);
    if ( v22 >= v20 )
    {
      if ( a10 )
        *a10 = a9;
      return 2147942424LL;
    }
    v20 = 1;
    v24 = *((_QWORD *)v17 + 1) + *((_QWORD *)v17 + 2) * v22;
    v25 = v22 + 1;
  }
  else
  {
    v24 = *((_QWORD *)v17 + 1);
    v25 = 1;
  }
  *((_QWORD *)v17 + 4) = v25;
  result = (*((__int64 (__fastcall **)(__int64, __int64, char *, unsigned __int64, __int64 *))v17 + 5))(
             v21,
             v14,
             (char *)this + v24,
             v20,
             &v29);
  if ( (int)result >= 0 )
  {
    v26 = a8;
    if ( a8 )
    {
      v27 = (_QWORD *)((char *)a7 + 32);
      do
      {
        if ( v27 - 4 != (_QWORD *)v17 && *((_QWORD *)v17 + 1) == *(v27 - 3) )
          *v27 = *((_QWORD *)v17 + 4);
        v27 += 7;
        --v26;
      }
      while ( v26 );
    }
    v28 = v29 + *a2;
    *a2 = v28;
    if ( a3 > 1 )
      *a2 = v28 + a3 - 1;
    return 0;
  }
  else if ( a10 )
  {
    *a10 = a9;
  }
  return result;
}

```

## disassembly

```asm
0x18000820c  push    rbx
0x18000820e  push    rbp
0x18000820f  push    rsi
0x180008210  push    rdi
0x180008211  push    r14
0x180008213  sub     rsp, 40h
0x180008217  mov     rax, cs:__security_cookie
0x18000821e  xor     rax, rsp
0x180008221  mov     [rsp+68h+var_30], rax
0x180008226  mov     rbx, [rsp+68h+arg_48]
0x18000822e  mov     rbp, r8
0x180008231  mov     rax, [rsp+68h+arg_28]
0x180008239  mov     rsi, rdx
0x18000823c  mov     r14, [rsp+68h+arg_30]
0x180008244  mov     r8, rcx
0x180008247  test    rbx, rbx
0x18000824a  jz      short loc_180008253
0x18000824c  mov     qword ptr [rbx], 0
0x180008253  mov     rcx, [rdx]
0x180008256  xor     edx, edx
0x180008258  imul    rdi, rax, 38h ; '8'
0x18000825c  mov     rax, [rsp+68h+arg_20]
0x180008264  add     rcx, rbp
0x180008267  sub     rax, rcx
0x18000826a  mov     [rsp+68h+var_38], 0
0x180008273  add     rdi, r14
0x180008276  cmp     rcx, [rsp+68h+arg_20]
0x18000827e  lea     rcx, [r9+rcx*8]
0x180008282  cmovbe  rdx, rax
0x180008286  mov     r9, [rdi+18h]
0x18000828a  mov     rax, rdx
0x18000828d  neg     rax
0x180008290  sbb     r10, r10
0x180008293  and     r10, rcx
0x180008296  test    byte ptr [rdi+30h], 10h
0x18000829a  jz      short loc_1800082D6
0x18000829c  mov     rcx, [rdi+20h]
0x1800082a0  cmp     rcx, r9
0x1800082a3  jb      short loc_1800082BF
0x1800082a5  test    rbx, rbx
0x1800082a8  jz      short loc_1800082B5
0x1800082aa  mov     rax, [rsp+68h+arg_40]
0x1800082b2  mov     [rbx], rax
0x1800082b5  mov     eax, 80070018h
0x1800082ba  jmp     loc_180008364
0x1800082bf  mov     rax, rcx
0x1800082c2  mov     r9d, 1
0x1800082c8  imul    rax, [rdi+10h]
0x1800082cd  add     rax, [rdi+8]
0x1800082d1  inc     rcx
0x1800082d4  jmp     short loc_1800082DF
0x1800082d6  mov     rax, [rdi+8]
0x1800082da  mov     ecx, 1
0x1800082df  add     r8, rax
0x1800082e2  mov     [rdi+20h], rcx
0x1800082e6  lea     rax, [rsp+68h+var_38]
0x1800082eb  mov     rcx, r10
0x1800082ee  mov     [rsp+68h+var_48], rax
0x1800082f3  mov     rax, [rdi+28h]
0x1800082f7  call    _guard_dispatch_icall
0x1800082fc  test    eax, eax
0x1800082fe  jns     short loc_180008312
0x180008300  test    rbx, rbx
0x180008303  jz      short loc_180008364
0x180008305  mov     rcx, [rsp+68h+arg_40]
0x18000830d  mov     [rbx], rcx
0x180008310  jmp     short loc_180008364
0x180008312  mov     rdx, [rsp+68h+arg_38]
0x18000831a  test    rdx, rdx
0x18000831d  jz      short loc_180008347
0x18000831f  lea     rcx, [r14+20h]
0x180008323  lea     rax, [rcx-20h]
0x180008327  cmp     rax, rdi
0x18000832a  jz      short loc_18000833D
0x18000832c  mov     rax, [rcx-18h]
0x180008330  cmp     [rdi+8], rax
0x180008334  jnz     short loc_18000833D
0x180008336  mov     rax, [rdi+20h]
0x18000833a  mov     [rcx], rax
0x18000833d  add     rcx, 38h ; '8'
0x180008341  sub     rdx, 1
0x180008345  jnz     short loc_180008323
0x180008347  mov     rdx, [rsi]
0x18000834a  add     rdx, [rsp+68h+var_38]
0x18000834f  mov     [rsi], rdx
0x180008352  cmp     rbp, 1
0x180008356  jbe     short loc_180008362
0x180008358  lea     rax, [rbp-1]
0x18000835c  add     rax, rdx
0x18000835f  mov     [rsi], rax
0x180008362  xor     eax, eax
0x180008364  mov     rcx, [rsp+68h+var_30]
0x180008369  xor     rcx, rsp; StackCookie
0x18000836c  call    __security_check_cookie
0x180008371  add     rsp, 40h
0x180008375  pop     r14
0x180008377  pop     rdi
0x180008378  pop     rsi
0x180008379  pop     rbp
0x18000837a  pop     rbx
0x18000837b  retn
```
