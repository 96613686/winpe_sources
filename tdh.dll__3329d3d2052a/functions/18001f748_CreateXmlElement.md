# CreateXmlElement

- ea: `0x18001f748`
- end: `0x18001f90c`
- name: `CreateXmlElement`
- size: `452`
- prototype: `unsigned __int64 __fastcall(_QWORD *Src, __int64, __int128 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001f48c`

## callees

- `0x18001f748`
- `0x18001f914`
- `0x1800207c0`
- `0x18002f4c4`
- `0x18002f910`
- `0x1800345b0`
- `0x18003c754`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall CreateXmlElement(_QWORD *Src, __int64 a2, __int128 *a3, unsigned int a4)
{
  _QWORD *v6; // rbx
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rdx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 result; // rax
  __int128 v15; // [rsp+30h] [rbp-58h] BYREF

  v6 = Src;
  v7 = Src[2];
  if ( v7 >= v6[3] )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(v6);
  }
  else
  {
    v6[2] = v7 + 1;
    if ( v6[3] <= 7u )
      v8 = v6;
    else
      v8 = (_QWORD *)*v6;
    *(_DWORD *)((char *)v8 + 2 * v7) = 60;
  }
  std::wstring::_Append<wchar_t>(v6);
  if ( *((_QWORD *)a3 + 1) )
  {
    std::wstring::_Append<wchar_t>(v6);
    v15 = *a3;
    AppendXmlEscaped(v6);
    std::wstring::_Append<wchar_t>(v6);
  }
  else
  {
    v9 = v6[2];
    if ( v9 >= v6[3] )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(v6);
    }
    else
    {
      v6[2] = v9 + 1;
      if ( v6[3] <= 7u )
        v10 = v6;
      else
        v10 = (_QWORD *)*v6;
      *(_DWORD *)((char *)v10 + 2 * v9) = 62;
    }
  }
  v11 = v6[2];
  if ( v11 >= v6[3] )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(v6);
  }
  else
  {
    v6[2] = v11 + 1;
    if ( v6[3] <= 7u )
      v12 = v6;
    else
      v12 = (_QWORD *)*v6;
    *(_DWORD *)((char *)v12 + 2 * v11) = 37;
  }
  std::_Integral_to_string<wchar_t,unsigned long>(&v15, a4);
  std::wstring::_Append<wchar_t>(v6);
  std::wstring::_Tidy_deallocate(&v15);
  std::wstring::_Append<wchar_t>(v6);
  std::wstring::_Append<wchar_t>(v6);
  v13 = v6[2];
  if ( v13 >= v6[3] )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(v6);
  result = v13 + 1;
  v6[2] = v13 + 1;
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  *(_DWORD *)((char *)v6 + 2 * v13) = 62;
  return result;
}

```

## disassembly

```asm
0x18001f748  push    rbx
0x18001f74a  push    rbp
0x18001f74b  push    rsi
0x18001f74c  push    rdi
0x18001f74d  push    r15
0x18001f74f  sub     rsp, 60h
0x18001f753  mov     rax, cs:__security_cookie
0x18001f75a  xor     rax, rsp
0x18001f75d  mov     [rsp+88h+var_38], rax
0x18001f762  mov     ebp, r9d
0x18001f765  mov     rsi, r8
0x18001f768  mov     rdi, rdx
0x18001f76b  mov     rbx, rcx
0x18001f76e  mov     rcx, [rcx+10h]
0x18001f772  cmp     rcx, [rbx+18h]
0x18001f776  jnb     short loc_18001F798
0x18001f778  lea     rax, [rcx+1]
0x18001f77c  mov     [rbx+10h], rax
0x18001f780  cmp     qword ptr [rbx+18h], 7
0x18001f785  jbe     short loc_18001F78C
0x18001f787  mov     rdx, [rbx]
0x18001f78a  jmp     short loc_18001F78F
0x18001f78c  mov     rdx, rbx
0x18001f78f  mov     dword ptr [rdx+rcx*2], 3Ch ; '<'
0x18001f796  jmp     short loc_18001F7A6
0x18001f798  mov     r9d, 3Ch ; '<'
0x18001f79e  mov     rcx, rbx; Src
0x18001f7a1  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001f7a6  mov     r8, [rdi+8]
0x18001f7aa  mov     rdx, [rdi]
0x18001f7ad  mov     rcx, rbx; Src
0x18001f7b0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f7b5  mov     r15d, 3Eh ; '>'
0x18001f7bb  cmp     qword ptr [rsi+8], 0
0x18001f7c0  jz      short loc_18001F800
0x18001f7c2  lea     r8d, [r15-37h]
0x18001f7c6  lea     rdx, aName; " Name=\""
0x18001f7cd  mov     rcx, rbx; Src
0x18001f7d0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f7d5  movaps  xmm0, xmmword ptr [rsi]
0x18001f7d8  movdqa  [rsp+88h+var_58], xmm0
0x18001f7de  lea     rdx, [rsp+88h+var_58]
0x18001f7e3  mov     rcx, rbx; Src
0x18001f7e6  call    AppendXmlEscaped
0x18001f7eb  lea     r8d, [r15-3Ch]
0x18001f7ef  lea     rdx, asc_18005842C; "\">"
0x18001f7f6  mov     rcx, rbx; Src
0x18001f7f9  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f7fe  jmp     short loc_18001F832
0x18001f800  mov     rcx, [rbx+10h]
0x18001f804  cmp     rcx, [rbx+18h]
0x18001f808  jnb     short loc_18001F827
0x18001f80a  lea     rax, [rcx+1]
0x18001f80e  mov     [rbx+10h], rax
0x18001f812  cmp     qword ptr [rbx+18h], 7
0x18001f817  jbe     short loc_18001F81E
0x18001f819  mov     rdx, [rbx]
0x18001f81c  jmp     short loc_18001F821
0x18001f81e  mov     rdx, rbx
0x18001f821  mov     [rdx+rcx*2], r15d
0x18001f825  jmp     short loc_18001F832
0x18001f827  mov     r9d, r15d
0x18001f82a  mov     rcx, rbx; Src
0x18001f82d  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001f832  mov     rcx, [rbx+10h]
0x18001f836  cmp     rcx, [rbx+18h]
0x18001f83a  jnb     short loc_18001F85C
0x18001f83c  lea     rax, [rcx+1]
0x18001f840  mov     [rbx+10h], rax
0x18001f844  cmp     qword ptr [rbx+18h], 7
0x18001f849  jbe     short loc_18001F850
0x18001f84b  mov     rdx, [rbx]
0x18001f84e  jmp     short loc_18001F853
0x18001f850  mov     rdx, rbx
0x18001f853  mov     dword ptr [rdx+rcx*2], 25h ; '%'
0x18001f85a  jmp     short loc_18001F86A
0x18001f85c  mov     r9d, 25h ; '%'
0x18001f862  mov     rcx, rbx; Src
0x18001f865  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001f86a  mov     edx, ebp
0x18001f86c  lea     rcx, [rsp+88h+var_58]
0x18001f871  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x18001f876  nop
0x18001f877  lea     rdx, [rsp+88h+var_58]
0x18001f87c  cmp     [rsp+88h+var_40], 7
0x18001f882  cmova   rdx, qword ptr [rsp+88h+var_58]
0x18001f888  mov     r8, [rsp+88h+var_48]
0x18001f88d  mov     rcx, rbx; Src
0x18001f890  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f895  nop
0x18001f896  lea     rcx, [rsp+88h+var_58]
0x18001f89b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f8a0  mov     r8d, 2
0x18001f8a6  lea     rdx, asc_180058434; "</"
0x18001f8ad  mov     rcx, rbx; Src
0x18001f8b0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f8b5  mov     r8, [rdi+8]
0x18001f8b9  mov     rdx, [rdi]
0x18001f8bc  mov     rcx, rbx; Src
0x18001f8bf  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f8c4  mov     rcx, [rbx+10h]
0x18001f8c8  cmp     rcx, [rbx+18h]
0x18001f8cc  jnb     short loc_18001F8E9
0x18001f8ce  lea     rax, [rcx+1]
0x18001f8d2  mov     [rbx+10h], rax
0x18001f8d6  cmp     qword ptr [rbx+18h], 7
0x18001f8db  jbe     short loc_18001F8E0
0x18001f8dd  mov     rbx, [rbx]
0x18001f8e0  mov     dword ptr [rbx+rcx*2], 3Eh ; '>'
0x18001f8e7  jmp     short loc_18001F8F4
0x18001f8e9  mov     r9d, r15d
0x18001f8ec  mov     rcx, rbx; Src
0x18001f8ef  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001f8f4  mov     rcx, [rsp+88h+var_38]
0x18001f8f9  xor     rcx, rsp; StackCookie
0x18001f8fc  call    __security_check_cookie
0x18001f901  add     rsp, 60h
0x18001f905  pop     r15
0x18001f907  pop     rdi
0x18001f908  pop     rsi
0x18001f909  pop     rbp
0x18001f90a  pop     rbx
0x18001f90b  retn
```
