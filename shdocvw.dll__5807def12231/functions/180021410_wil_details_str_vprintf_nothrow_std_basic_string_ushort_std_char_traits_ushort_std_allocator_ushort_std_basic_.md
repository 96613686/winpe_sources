# wil::details::str_vprintf_nothrow<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ushort const *,char * &)

- ea: `0x180021410`
- end: `0x180021589`
- name: `??$str_vprintf_nothrow@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAPEAD@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180021384`

## callees

- `0x1800066d0`
- `0x180008320`
- `0x18000903c`
- `0x180009090`
- `0x18000b924`
- `0x180021410`
- `0x180021a00`
- `0x180024678`

## string_xrefs

- `0x180021477`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002154d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<std::wstring>(__int64 a1, const wchar_t *a2, va_list *a3)
{
  size_t v6; // rbx
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // edi
  wchar_t *v10; // rdi
  unsigned __int64 v11; // rsi
  unsigned int v12; // ebx
  int v13; // eax
  __int128 v14; // xmm0
  __m128i v15; // xmm1
  wchar_t *Buffer[2]; // [rsp+20h] [rbp-50h] BYREF
  __m128i si128; // [rsp+30h] [rbp-40h]
  _OWORD v19[2]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v6 = vscwprintf(a2, *a3);
  *(_OWORD *)Buffer = 0;
  LOWORD(Buffer[0]) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v8 = wil::details::string_maker<std::wstring>::make(Buffer, v7, v6);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      (int)Buffer[0]);
    goto LABEL_18;
  }
  v10 = (wchar_t *)Buffer;
  v11 = v6 + 1;
  if ( si128.m128i_i64[1] > 7uLL )
    v10 = Buffer[0];
  if ( v6 == -1 )
  {
    v12 = -2147024809;
    goto LABEL_17;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    v12 = -2147024809;
LABEL_16:
    *v10 = 0;
    goto LABEL_17;
  }
  v13 = vsnwprintf(v10, v6, a2, *a3);
  if ( v13 < 0 || v13 > v6 )
  {
    v10[v6] = 0;
    v12 = -2147024774;
    if ( (v11 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      goto LABEL_16;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v12,
      (int)Buffer[0]);
    v9 = v12;
    goto LABEL_18;
  }
  if ( v13 == v6 )
    v10[v6] = 0;
  v14 = *(_OWORD *)Buffer;
  v15 = si128;
  LOWORD(Buffer[0]) = 0;
  v19[0] = v14;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v19[1] = v15;
  std::wstring::operator=(a1, v19);
  std::wstring::_Tidy_deallocate(v19);
  v9 = 0;
LABEL_18:
  std::wstring::_Tidy_deallocate(Buffer);
  return v9;
}

```

## disassembly

```asm
0x180021410  push    rbp
0x180021412  push    rbx
0x180021413  push    rsi
0x180021414  push    rdi
0x180021415  push    r12
0x180021417  push    r14
0x180021419  push    r15
0x18002141b  mov     rbp, rsp
0x18002141e  sub     rsp, 70h
0x180021422  mov     rax, cs:__security_cookie
0x180021429  xor     rax, rsp
0x18002142c  mov     [rbp+var_10], rax
0x180021430  mov     r14, rdx
0x180021433  mov     r12, rcx
0x180021436  mov     rdx, [r8]; ArgList
0x180021439  mov     rcx, r14; Format
0x18002143c  mov     r15, r8
0x18002143f  call    _vscwprintf
0x180021444  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002144c  lea     rcx, [rbp+Buffer]
0x180021450  movsxd  rbx, eax
0x180021453  xorps   xmm0, xmm0
0x180021456  xor     eax, eax
0x180021458  mov     r8, rbx
0x18002145b  movups  xmmword ptr [rbp+Buffer], xmm0
0x18002145f  mov     word ptr [rbp+Buffer], ax
0x180021463  movdqu  [rbp+var_40], xmm1
0x180021468  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x18002146d  mov     edi, eax
0x18002146f  test    eax, eax
0x180021471  jns     short loc_180021490
0x180021473  mov     rcx, [rbp+38h]; this
0x180021477  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002147e  mov     r9d, eax; char *
0x180021481  mov     edx, 7CDh; void *
0x180021486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002148b  jmp     loc_180021563
0x180021490  cmp     qword ptr [rbp+var_40+8], 7
0x180021495  lea     rdi, [rbp+Buffer]
0x180021499  lea     rsi, [rbx+1]
0x18002149d  cmova   rdi, [rbp+Buffer]
0x1800214a2  test    rsi, rsi
0x1800214a5  jz      loc_18002153A
0x1800214ab  cmp     rsi, 7FFFFFFFh
0x1800214b2  jbe     short loc_1800214BE
0x1800214b4  mov     ebx, 80070057h
0x1800214b9  jmp     loc_180021544
0x1800214be  mov     r9, [r15]; Args
0x1800214c1  mov     r8, r14; Format
0x1800214c4  mov     rdx, rbx; BufferCount
0x1800214c7  mov     rcx, rdi; Buffer
0x1800214ca  call    _vsnwprintf
0x1800214cf  test    eax, eax
0x1800214d1  js      short loc_18002151E
0x1800214d3  cdqe
0x1800214d5  cmp     rax, rbx
0x1800214d8  ja      short loc_18002151E
0x1800214da  jnz     short loc_1800214E2
0x1800214dc  xor     eax, eax
0x1800214de  mov     [rdi+rbx*2], ax
0x1800214e2  movups  xmm0, xmmword ptr [rbp+Buffer]
0x1800214e6  xor     eax, eax
0x1800214e8  lea     rdx, [rbp+var_30]
0x1800214ec  movups  xmm1, [rbp+var_40]
0x1800214f0  mov     rcx, r12
0x1800214f3  mov     word ptr [rbp+Buffer], ax
0x1800214f7  movups  [rbp+var_30], xmm0
0x1800214fb  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180021503  movdqu  [rbp+var_40], xmm0
0x180021508  movups  [rbp+var_20], xmm1
0x18002150c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180021511  lea     rcx, [rbp+var_30]
0x180021515  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002151a  xor     edi, edi
0x18002151c  jmp     short loc_180021563
0x18002151e  xor     eax, eax
0x180021520  mov     [rdi+rbx*2], ax
0x180021524  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002152e  mov     ebx, 8007007Ah
0x180021533  test    rax, rsi
0x180021536  jbe     short loc_180021549
0x180021538  jmp     short loc_180021544
0x18002153a  mov     ebx, 80070057h
0x18002153f  test    rsi, rsi
0x180021542  jz      short loc_180021549
0x180021544  xor     eax, eax
0x180021546  mov     [rdi], ax
0x180021549  mov     rcx, [rbp+38h]; this
0x18002154d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021554  mov     r9d, ebx; char *
0x180021557  mov     edx, 7D1h; void *
0x18002155c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021561  mov     edi, ebx
0x180021563  lea     rcx, [rbp+Buffer]
0x180021567  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002156c  mov     eax, edi
0x18002156e  mov     rcx, [rbp+var_10]
0x180021572  xor     rcx, rsp; StackCookie
0x180021575  call    __security_check_cookie
0x18002157a  add     rsp, 70h
0x18002157e  pop     r15
0x180021580  pop     r14
0x180021582  pop     r12
0x180021584  pop     rdi
0x180021585  pop     rsi
0x180021586  pop     rbx
0x180021587  pop     rbp
0x180021588  retn
```
