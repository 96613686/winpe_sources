# wil::AdaptFixedSizeToAllocatedResult<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,256>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)

- ea: `0x18000955c`
- end: `0x180009770`
- name: `??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0BAA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000a054`

## callees

- `0x180001dc0`
- `0x180002ab4`
- `0x180004fd4`
- `0x18000885c`
- `0x18000955c`
- `0x180009e38`
- `0x18000a4d4`
- `0x18000a540`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000970b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000970b`

## string_xrefs

- `0x18000961d`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x18000972c`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(__int64 a1, __int64 a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  int v6; // eax
  unsigned __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  __int128 *v10; // rdx
  int v11; // eax
  bool v12; // cc
  __int128 *v13; // rcx
  _OWORD v15[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+48h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-A8h]
  _BYTE v19[512]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v17 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v17) = 0;
  memset_0(v19, 0, sizeof(v19));
  v16 = 0;
  v4 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v19, 256, &v16);
  if ( v4 < 0 )
  {
LABEL_18:
    std::wstring::_Tidy_deallocate(&v17);
    return (unsigned int)v4;
  }
  v5 = v16;
  if ( v16 <= 0x100 )
  {
    v6 = wil::details::string_maker<std::wstring>::make(&v17, v19, v16 - 1);
    v4 = v6;
    if ( v6 >= 0 )
    {
LABEL_15:
      v15[0] = v17;
      v15[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v17) = 0;
      std::wstring::operator=(a1, v15);
      std::wstring::_Tidy_deallocate(v15);
      std::wstring::_Tidy_deallocate(&v17);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)(unsigned int)v6,
      v15[0]);
    goto LABEL_18;
  }
  while ( 1 )
  {
    v7 = v5;
    v8 = wil::details::string_maker<std::wstring>::make(&v17, 0, v5 - 1);
    v9 = v8;
    if ( v8 < 0 )
      break;
    v10 = &v17;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = (__int128 *)v17;
    v11 = wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(a2, v10, v7, &v16);
    if ( v11 < 0 )
    {
      v4 = v11;
      goto LABEL_18;
    }
    v5 = v16;
    v12 = v16 <= v7;
    if ( v16 < v7 )
    {
      if ( si128.m128i_i64[0] < v16 - 1 )
      {
        std::_Xout_of_range("invalid string position");
        __debugbreak();
      }
      si128.m128i_i64[0] = v16 - 1;
      v13 = &v17;
      if ( si128.m128i_i64[1] > 7uLL )
        v13 = (__int128 *)v17;
      *((_WORD *)v13 + v16 - 1) = 0;
      v5 = v16;
      v12 = v16 <= v7;
    }
    if ( v12 )
      goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17A,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
    (const char *)(unsigned int)v8,
    v15[0]);
  std::wstring::_Tidy_deallocate(&v17);
  return v9;
}

```

## disassembly

```asm
0x18000955c  mov     [rsp-8+arg_10], rbx
0x180009561  mov     [rsp-8+arg_18], rsi
0x180009566  push    rbp
0x180009567  push    rdi
0x180009568  push    r14
0x18000956a  lea     rbp, [rsp-180h]
0x180009572  sub     rsp, 280h
0x180009579  mov     rax, cs:__security_cookie
0x180009580  xor     rax, rsp
0x180009583  mov     [rbp+190h+var_20], rax
0x18000958a  mov     rsi, rdx
0x18000958d  mov     r14, rcx
0x180009590  xorps   xmm0, xmm0
0x180009593  movups  [rsp+290h+var_248], xmm0
0x180009598  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800095a0  movdqu  [rsp+290h+var_238], xmm1
0x1800095a6  xor     eax, eax
0x1800095a8  mov     word ptr [rsp+290h+var_248], ax
0x1800095ad  xor     edx, edx; Val
0x1800095af  mov     r8d, 200h; Size
0x1800095b5  lea     rcx, [rsp+290h+var_220]; void *
0x1800095ba  call    memset_0
0x1800095bf  mov     [rsp+290h+var_250], 0
0x1800095c8  lea     r9, [rsp+290h+var_250]
0x1800095cd  mov     edi, 100h
0x1800095d2  mov     r8d, edi
0x1800095d5  lea     rdx, [rsp+290h+var_220]
0x1800095da  mov     rcx, rsi
0x1800095dd  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x1800095e2  mov     ebx, eax
0x1800095e4  test    eax, eax
0x1800095e6  js      loc_180009714
0x1800095ec  mov     rax, [rsp+290h+var_250]
0x1800095f1  cmp     rax, rdi
0x1800095f4  ja      short loc_180009631
0x1800095f6  lea     r8, [rax-1]
0x1800095fa  lea     rdx, [rsp+290h+var_220]
0x1800095ff  lea     rcx, [rsp+290h+var_248]
0x180009604  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x180009609  mov     ebx, eax
0x18000960b  test    eax, eax
0x18000960d  jns     loc_1800096B6
0x180009613  mov     rcx, [rbp+198h]; this
0x18000961a  mov     r9d, eax; char *
0x18000961d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009624  lea     edx, [rdi+6Fh]; void *
0x180009627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000962c  jmp     loc_180009714
0x180009631  mov     rbx, rax
0x180009634  lea     r8, [rax-1]
0x180009638  xor     edx, edx
0x18000963a  lea     rcx, [rsp+290h+var_248]
0x18000963f  call    ?make@?$string_maker@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<std::wstring>::make(ushort const *,unsigned __int64)
0x180009644  mov     edi, eax
0x180009646  test    eax, eax
0x180009648  js      loc_180009722
0x18000964e  lea     rdx, [rsp+290h+var_248]
0x180009653  cmp     qword ptr [rsp+290h+var_238+8], 7
0x180009659  cmova   rdx, qword ptr [rsp+290h+var_248]
0x18000965f  lea     r9, [rsp+290h+var_250]
0x180009664  mov     r8, rbx
0x180009667  mov     rcx, rsi
0x18000966a  call    ??R?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEBAJPEAG_KPEA_K@Z; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort *,unsigned __int64,unsigned __int64 *)
0x18000966f  test    eax, eax
0x180009671  js      loc_180009712
0x180009677  mov     rax, [rsp+290h+var_250]
0x18000967c  cmp     rax, rbx
0x18000967f  jnb     short loc_1800096B0
0x180009681  lea     rdx, [rax-1]
0x180009685  cmp     qword ptr [rsp+290h+var_238], rdx
0x18000968a  jb      short loc_180009704
0x18000968c  mov     qword ptr [rsp+290h+var_238], rdx
0x180009691  lea     rcx, [rsp+290h+var_248]
0x180009696  cmp     qword ptr [rsp+290h+var_238+8], 7
0x18000969c  cmova   rcx, qword ptr [rsp+290h+var_248]
0x1800096a2  xor     eax, eax
0x1800096a4  mov     [rcx+rdx*2], ax
0x1800096a8  mov     rax, [rsp+290h+var_250]
0x1800096ad  cmp     rax, rbx
0x1800096b0  ja      loc_180009631
0x1800096b6  movups  xmm0, [rsp+290h+var_248]
0x1800096bb  movups  [rsp+290h+var_270], xmm0
0x1800096c0  movups  xmm1, [rsp+290h+var_238]
0x1800096c5  movups  [rsp+290h+var_260], xmm1
0x1800096ca  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800096d2  movdqu  [rsp+290h+var_238], xmm0
0x1800096d8  xor     eax, eax
0x1800096da  mov     word ptr [rsp+290h+var_248], ax
0x1800096df  lea     rdx, [rsp+290h+var_270]
0x1800096e4  mov     rcx, r14
0x1800096e7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800096ec  lea     rcx, [rsp+290h+var_270]
0x1800096f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096f6  lea     rcx, [rsp+290h+var_248]
0x1800096fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009700  xor     eax, eax
0x180009702  jmp     short loc_180009749
0x180009704  lea     rcx, aInvalidStringP; "invalid string position"
0x18000970b  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180009711  int     3; Trap to Debugger
0x180009712  mov     ebx, eax
0x180009714  lea     rcx, [rsp+290h+var_248]
0x180009719  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000971e  mov     eax, ebx
0x180009720  jmp     short loc_180009749
0x180009722  mov     rcx, [rbp+198h]; this
0x180009729  mov     r9d, edi; char *
0x18000972c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009733  mov     edx, 17Ah; void *
0x180009738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000973d  lea     rcx, [rsp+290h+var_248]
0x180009742  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009747  mov     eax, edi
0x180009749  mov     rcx, [rbp+190h+var_20]
0x180009750  xor     rcx, rsp; StackCookie
0x180009753  call    __security_check_cookie
0x180009758  lea     r11, [rsp+290h+var_10]
0x180009760  mov     rbx, [r11+30h]
0x180009764  mov     rsi, [r11+38h]
0x180009768  mov     rsp, r11
0x18000976b  pop     r14
0x18000976d  pop     rdi
0x18000976e  pop     rbp
0x18000976f  retn
```
