# XmlPrinter::PrintStartElement(wchar_t const *)

- ea: `0x14000e924`
- end: `0x14000eacd`
- name: `?PrintStartElement@XmlPrinter@@QEAAXPEB_W@Z`
- size: `425`
- prototype: `void __fastcall(XmlPrinter *__hidden this, const wchar_t *)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14000db10`
- `0x14000e550`
- `0x1400100dc`
- `0x140026680`

## callees

- `0x14000cabc`
- `0x14000cc04`
- `0x14000d144`
- `0x14000d868`
- `0x14000d88c`
- `0x14000d8c4`
- `0x14000e924`
- `0x14001af4c`
- `0x140021b00`
- `0x140027930`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XmlPrinter::PrintStartElement(XmlPrinter *this, const wchar_t *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int128 *p_Src; // rcx
  __int64 v7; // r8
  __int64 v8; // r8
  void *v9; // rax
  _OWORD *v10; // rdx
  __int128 v11; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v12[16]; // [rsp+30h] [rbp-40h] BYREF
  __int128 Src; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]

  v4 = (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 5;
  if ( *((_BYTE *)this + 32) )
  {
    std::wstring::wstring(&Src, 2 * v4);
    v5 = si128.m128i_i64[0];
    p_Src = &Src;
    if ( si128.m128i_i64[0] >= (unsigned __int64)si128.m128i_i64[1] )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&Src);
    }
    else
    {
      ++si128.m128i_i64[0];
      if ( si128.m128i_i64[1] > 7uLL )
        p_Src = (__int128 *)Src;
      *(_DWORD *)((char *)p_Src + 2 * v5) = 60;
    }
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    std::wstring::_Append<wchar_t>(&Src);
    v11 = *(_OWORD *)std::wstring::operator std::wstring_view(&Src, v12);
    FilePuts(*(HANDLE *)this, &v11);
  }
  else
  {
    if ( !v4 )
      goto LABEL_15;
    std::wstring::wstring(&Src, 2 * v4 - 2);
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = (void *)std::wstring::_Append<wchar_t>(&Src);
    std::wstring::_Append<wchar_t>(v9);
    v11 = *(_OWORD *)std::wstring::operator std::wstring_view(&Src, v12);
    FilePuts(*(HANDLE *)this, &v11);
  }
  std::wstring::_Tidy_deallocate(&Src);
LABEL_15:
  *((_BYTE *)this + 33) = 1;
  std::wstring::wstring(&Src, a2);
  v10 = (_OWORD *)*((_QWORD *)this + 2);
  if ( v10 == *((_OWORD **)this + 3) )
  {
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring>((char *)this + 8, v10, &Src);
  }
  else
  {
    *v10 = Src;
    v10[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src) = 0;
    *((_QWORD *)this + 2) += 32LL;
  }
  std::wstring::_Tidy_deallocate(&Src);
}

```

## disassembly

```asm
0x14000e924  mov     [rsp-18h+arg_10], rbx
0x14000e929  mov     [rsp-18h+arg_18], rsi
0x14000e92e  push    rbp
0x14000e92f  push    rdi
0x14000e930  push    r14
0x14000e932  mov     rbp, rsp
0x14000e935  sub     rsp, 70h
0x14000e939  mov     rax, cs:__security_cookie
0x14000e940  xor     rax, rsp
0x14000e943  mov     [rbp+var_10], rax
0x14000e947  mov     rdi, rdx
0x14000e94a  mov     rsi, rcx
0x14000e94d  mov     rdx, [rcx+10h]
0x14000e951  sub     rdx, [rcx+8]
0x14000e955  sar     rdx, 5
0x14000e959  xor     r14d, r14d
0x14000e95c  cmp     [rcx+20h], r14b
0x14000e960  jz      short loc_14000E9E1
0x14000e962  add     rdx, rdx
0x14000e965  lea     rcx, [rbp+Src]
0x14000e969  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x14000e96e  nop
0x14000e96f  mov     rdx, qword ptr [rbp+var_20]
0x14000e973  lea     rcx, [rbp+Src]; Src
0x14000e977  cmp     rdx, qword ptr [rbp+var_20+8]
0x14000e97b  jnb     short loc_14000E998
0x14000e97d  lea     rax, [rdx+1]
0x14000e981  mov     qword ptr [rbp+var_20], rax
0x14000e985  cmp     qword ptr [rbp+var_20+8], 7
0x14000e98a  cmova   rcx, qword ptr [rbp+Src]
0x14000e98f  mov     dword ptr [rcx+rdx*2], 3Ch ; '<'
0x14000e996  jmp     short loc_14000E9A3
0x14000e998  mov     r9d, 3Ch ; '<'
0x14000e99e  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x14000e9a3  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000e9a7  inc     r8
0x14000e9aa  cmp     [rdi+r8*2], r14w
0x14000e9af  jnz     short loc_14000E9A7
0x14000e9b1  mov     rdx, rdi
0x14000e9b4  lea     rcx, [rbp+Src]; Src
0x14000e9b8  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000e9bd  lea     rdx, [rbp+var_40]
0x14000e9c1  lea     rcx, [rbp+Src]
0x14000e9c5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000e9ca  movups  xmm0, xmmword ptr [rax]
0x14000e9cd  movdqu  [rbp+var_50], xmm0
0x14000e9d2  lea     rdx, [rbp+var_50]
0x14000e9d6  mov     rcx, [rsi]; hFile
0x14000e9d9  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000e9de  nop
0x14000e9df  jmp     short loc_14000EA49
0x14000e9e1  test    rdx, rdx
0x14000e9e4  jz      short loc_14000EA52
0x14000e9e6  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000e9ee  lea     rcx, [rbp+Src]
0x14000e9f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x14000e9f7  nop
0x14000e9f8  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000e9fc  inc     r8
0x14000e9ff  cmp     [rdi+r8*2], r14w
0x14000ea04  jnz     short loc_14000E9FC
0x14000ea06  mov     rdx, rdi
0x14000ea09  lea     rcx, [rbp+Src]; Src
0x14000ea0d  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000ea12  mov     r8d, 3
0x14000ea18  lea     rdx, asc_140039608; ":\r\n"
0x14000ea1f  mov     rcx, rax; Src
0x14000ea22  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000ea27  lea     rdx, [rbp+var_40]
0x14000ea2b  lea     rcx, [rbp+Src]
0x14000ea2f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000ea34  movups  xmm0, xmmword ptr [rax]
0x14000ea37  movdqu  [rbp+var_50], xmm0
0x14000ea3c  lea     rdx, [rbp+var_50]
0x14000ea40  mov     rcx, [rsi]; hFile
0x14000ea43  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000ea48  nop
0x14000ea49  lea     rcx, [rbp+Src]
0x14000ea4d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000ea52  mov     byte ptr [rsi+21h], 1
0x14000ea56  mov     rdx, rdi
0x14000ea59  lea     rcx, [rbp+Src]
0x14000ea5d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14000ea62  nop
0x14000ea63  mov     rdx, [rsi+10h]
0x14000ea67  cmp     rdx, [rsi+18h]
0x14000ea6b  jz      short loc_14000EA95
0x14000ea6d  movups  xmm0, [rbp+Src]
0x14000ea71  movups  xmmword ptr [rdx], xmm0
0x14000ea74  movups  xmm1, [rbp+var_20]
0x14000ea78  movups  xmmword ptr [rdx+10h], xmm1
0x14000ea7c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14000ea84  movdqu  [rbp+var_20], xmm0
0x14000ea89  mov     word ptr [rbp+Src], r14w
0x14000ea8e  add     qword ptr [rsi+10h], 20h ; ' '
0x14000ea93  jmp     short loc_14000EAA3
0x14000ea95  lea     r8, [rbp+Src]
0x14000ea99  lea     rcx, [rsi+8]
0x14000ea9d  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14000eaa2  nop
0x14000eaa3  lea     rcx, [rbp+Src]
0x14000eaa7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000eaac  mov     rcx, [rbp+var_10]
0x14000eab0  xor     rcx, rsp; StackCookie
0x14000eab3  call    __security_check_cookie
0x14000eab8  lea     r11, [rsp+70h+var_s0]
0x14000eabd  mov     rbx, [r11+30h]
0x14000eac1  mov     rsi, [r11+38h]
0x14000eac5  mov     rsp, r11
0x14000eac8  pop     r14
0x14000eaca  pop     rdi
0x14000eacb  pop     rbp
0x14000eacc  retn
```
