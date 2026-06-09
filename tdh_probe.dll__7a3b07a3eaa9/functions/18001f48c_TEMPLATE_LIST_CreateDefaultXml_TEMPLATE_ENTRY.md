# TEMPLATE_LIST::CreateDefaultXml(TEMPLATE_ENTRY *)

- ea: `0x18001f48c`
- end: `0x18001f741`
- name: `?CreateDefaultXml@TEMPLATE_LIST@@AEAAXPEAVTEMPLATE_ENTRY@@@Z`
- size: `693`
- prototype: `void __fastcall(TEMPLATE_LIST *__hidden this, struct TEMPLATE_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800193cc`

## callees

- `0x18001ed1c`
- `0x18001f48c`
- `0x18001f748`
- `0x18001f914`
- `0x1800207c0`
- `0x18002f910`
- `0x180033da0`
- `0x180033df0`
- `0x1800345b0`
- `0x18003c754`

## string_xrefs

- `0x18001f670`: `ComplexData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TEMPLATE_LIST::CreateDefaultXml(TEMPLATE_LIST *this, struct TEMPLATE_ENTRY *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rcx
  unsigned __int64 v5; // rdx
  __int128 *p_Src; // rcx
  unsigned __int64 v7; // rdx
  __int128 *v8; // rcx
  __int64 v9; // r8
  char v10; // si
  unsigned int v11; // edi
  _QWORD *v12; // rax
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  char v16[16]; // [rsp+80h] [rbp-29h] BYREF
  __int128 Src; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v18; // [rsp+A0h] [rbp-9h]
  unsigned __int64 v19; // [rsp+A8h] [rbp-1h]

  Src = 0;
  v18 = 0;
  v19 = 7;
  LOWORD(Src) = 0;
  std::wstring::_Append<wchar_t>(&Src);
  if ( *((_QWORD *)a2 + 6) )
  {
    std::wstring::_Append<wchar_t>(&Src);
    v3 = (_QWORD *)((char *)a2 + 32);
    if ( *((_QWORD *)a2 + 7) > 7u )
      v3 = (_QWORD *)*v3;
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)v3 + v4) );
    AppendXmlEscaped(&Src);
    v5 = v18;
    p_Src = &Src;
    if ( v18 >= v19 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&Src);
    }
    else
    {
      ++v18;
      if ( v19 > 7 )
        p_Src = (__int128 *)Src;
      *(_DWORD *)((char *)p_Src + 2 * v5) = 34;
    }
  }
  if ( *((_QWORD *)a2 + 14) != *((_QWORD *)a2 + 13) )
  {
    v7 = v18;
    v8 = &Src;
    if ( v18 >= v19 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&Src);
    }
    else
    {
      ++v18;
      if ( v19 > 7 )
        v8 = (__int128 *)Src;
      *(_DWORD *)((char *)v8 + 2 * v7) = 62;
    }
    v9 = *((_QWORD *)a2 + 13);
    if ( (*((_QWORD *)a2 + 14) - v9) >> 3 )
    {
      v10 = 0;
      v11 = 0;
      do
      {
        v12 = (_QWORD *)std::wstring::operator std::wstring_view(*(_QWORD *)(v9 + 8LL * v11), v16);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(L"__binLength", 11, *v12, v12[1]) )
        {
          v10 = 1;
          ++v11;
        }
        else
        {
          if ( !v10 )
          {
            v13 = *(__int64 **)(*((_QWORD *)a2 + 13) + 8LL * v11);
            if ( *((_BYTE *)v13 + 208) )
            {
              if ( (unsigned __int64)v13[3] > 7 )
                v13 = (__int64 *)*v13;
              v14 = -1;
              do
                ++v14;
              while ( *((_WORD *)v13 + v14) );
            }
            else
            {
              if ( (unsigned __int64)v13[3] > 7 )
                v13 = (__int64 *)*v13;
              v15 = -1;
              do
                ++v15;
              while ( *((_WORD *)v13 + v15) );
            }
          }
          ++v11;
          CreateXmlElement(&Src);
        }
        v9 = *((_QWORD *)a2 + 13);
      }
      while ( v11 < (unsigned __int64)((*((_QWORD *)a2 + 14) - v9) >> 3) );
    }
  }
  std::wstring::_Append<wchar_t>(&Src);
  std::wstring::operator=((char *)a2 + 64, &Src);
  *((_DWORD *)a2 + 24) = 1;
  std::wstring::_Tidy_deallocate(&Src);
}

```

## disassembly

```asm
0x18001f48c  push    rbp
0x18001f48e  push    rbx
0x18001f48f  push    rsi
0x18001f490  push    rdi
0x18001f491  push    r12
0x18001f493  push    r13
0x18001f495  push    r14
0x18001f497  push    r15
0x18001f499  lea     rbp, [rsp-1Fh]
0x18001f49e  sub     rsp, 0C8h
0x18001f4a5  mov     rax, cs:__security_cookie
0x18001f4ac  xor     rax, rsp
0x18001f4af  mov     [rbp+57h+var_50], rax
0x18001f4b3  mov     rbx, rdx
0x18001f4b6  xorps   xmm0, xmm0
0x18001f4b9  movups  [rbp+57h+Src], xmm0
0x18001f4bd  xor     r15d, r15d
0x18001f4c0  mov     [rbp+57h+var_60], r15
0x18001f4c4  lea     r12d, [r15+7]
0x18001f4c8  mov     [rbp+57h+var_58], r12
0x18001f4cc  mov     word ptr [rbp+57h+Src], r15w
0x18001f4d1  lea     r8d, [r15+0Ah]
0x18001f4d5  lea     rdx, aEventdata; "<EventData"
0x18001f4dc  lea     rcx, [rbp+57h+Src]; Src
0x18001f4e0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f4e5  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001f4e9  cmp     [rbx+30h], r15
0x18001f4ed  jz      short loc_18001F567
0x18001f4ef  mov     r8d, r12d
0x18001f4f2  lea     rdx, aName; " Name=\""
0x18001f4f9  lea     rcx, [rbp+57h+Src]; Src
0x18001f4fd  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f502  lea     rax, [rbx+20h]
0x18001f506  cmp     [rax+18h], r12
0x18001f50a  jbe     short loc_18001F50F
0x18001f50c  mov     rax, [rax]
0x18001f50f  mov     rcx, r13
0x18001f512  inc     rcx
0x18001f515  cmp     [rax+rcx*2], r15w
0x18001f51a  jnz     short loc_18001F512
0x18001f51c  mov     [rsp+100h+var_E0], rax
0x18001f521  mov     [rsp+100h+var_D8], rcx
0x18001f526  lea     rdx, [rsp+100h+var_E0]
0x18001f52b  lea     rcx, [rbp+57h+Src]; Src
0x18001f52f  call    AppendXmlEscaped
0x18001f534  mov     rdx, [rbp+57h+var_60]
0x18001f538  lea     rcx, [rbp+57h+Src]; Src
0x18001f53c  cmp     rdx, [rbp+57h+var_58]
0x18001f540  jnb     short loc_18001F55C
0x18001f542  lea     rax, [rdx+1]
0x18001f546  mov     [rbp+57h+var_60], rax
0x18001f54a  cmp     [rbp+57h+var_58], r12
0x18001f54e  cmova   rcx, qword ptr [rbp+57h+Src]
0x18001f553  mov     dword ptr [rcx+rdx*2], 22h ; '"'
0x18001f55a  jmp     short loc_18001F567
0x18001f55c  mov     r9d, 22h ; '"'
0x18001f562  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001f567  mov     rax, [rbx+70h]
0x18001f56b  cmp     rax, [rbx+68h]
0x18001f56f  jnz     short loc_18001F583
0x18001f571  lea     rdx, asc_180058458; "/>"
0x18001f578  mov     r8d, 2
0x18001f57e  jmp     loc_18001F6FB
0x18001f583  mov     rdx, [rbp+57h+var_60]
0x18001f587  lea     rcx, [rbp+57h+Src]; Src
0x18001f58b  cmp     rdx, [rbp+57h+var_58]
0x18001f58f  jnb     short loc_18001F5AB
0x18001f591  lea     rax, [rdx+1]
0x18001f595  mov     [rbp+57h+var_60], rax
0x18001f599  cmp     [rbp+57h+var_58], r12
0x18001f59d  cmova   rcx, qword ptr [rbp+57h+Src]
0x18001f5a2  mov     dword ptr [rcx+rdx*2], 3Eh ; '>'
0x18001f5a9  jmp     short loc_18001F5B6
0x18001f5ab  mov     r9d, 3Eh ; '>'
0x18001f5b1  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18001f5b6  mov     r8, [rbx+68h]
0x18001f5ba  mov     rax, [rbx+70h]
0x18001f5be  sub     rax, r8
0x18001f5c1  sar     rax, 3
0x18001f5c5  test    rax, rax
0x18001f5c8  jz      loc_18001F6EE
0x18001f5ce  mov     sil, r15b
0x18001f5d1  mov     edi, r15d
0x18001f5d4  mov     r14d, edi
0x18001f5d7  lea     rdx, [rbp+57h+var_80]
0x18001f5db  mov     rcx, [r8+r14*8]
0x18001f5df  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18001f5e4  mov     r8, [rax]
0x18001f5e7  mov     r9, [rax+8]
0x18001f5eb  mov     edx, 0Bh
0x18001f5f0  lea     rcx, aBinlength; "__binLength"
0x18001f5f7  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001f5fc  test    al, al
0x18001f5fe  jz      short loc_18001F60A
0x18001f600  mov     sil, 1
0x18001f603  inc     edi
0x18001f605  jmp     loc_18001F6D4
0x18001f60a  test    sil, sil
0x18001f60d  jz      short loc_18001F641
0x18001f60f  lea     rax, pszFormat
0x18001f616  mov     [rsp+100h+var_E0], rax
0x18001f61b  mov     [rsp+100h+var_D8], r15
0x18001f620  lea     rax, aBinary_0; "Binary"
0x18001f627  mov     [rbp+57h+var_D0], rax
0x18001f62b  mov     [rbp+57h+var_C8], 6
0x18001f633  lea     r8, [rsp+100h+var_E0]
0x18001f638  lea     rdx, [rbp+57h+var_D0]
0x18001f63c  jmp     loc_18001F6C6
0x18001f641  mov     rax, [rbx+68h]
0x18001f645  mov     rcx, [rax+r14*8]
0x18001f649  cmp     [rcx+0D0h], r15b
0x18001f650  jz      short loc_18001F68D
0x18001f652  cmp     [rcx+18h], r12
0x18001f656  jbe     short loc_18001F65B
0x18001f658  mov     rcx, [rcx]
0x18001f65b  mov     rax, r13
0x18001f65e  inc     rax
0x18001f661  cmp     [rcx+rax*2], r15w
0x18001f666  jnz     short loc_18001F65E
0x18001f668  mov     [rbp+57h+var_C0], rcx
0x18001f66c  mov     [rbp+57h+var_B8], rax
0x18001f670  lea     rax, aComplexdata; "ComplexData"
0x18001f677  mov     [rbp+57h+var_B0], rax
0x18001f67b  mov     [rbp+57h+var_A8], 0Bh
0x18001f683  lea     r8, [rbp+57h+var_C0]
0x18001f687  lea     rdx, [rbp+57h+var_B0]
0x18001f68b  jmp     short loc_18001F6C6
0x18001f68d  cmp     [rcx+18h], r12
0x18001f691  jbe     short loc_18001F696
0x18001f693  mov     rcx, [rcx]
0x18001f696  mov     rax, r13
0x18001f699  inc     rax
0x18001f69c  cmp     [rcx+rax*2], r15w
0x18001f6a1  jnz     short loc_18001F699
0x18001f6a3  mov     [rbp+57h+var_A0], rcx
0x18001f6a7  mov     [rbp+57h+var_98], rax
0x18001f6ab  lea     rax, aData_1; "Data"
0x18001f6b2  mov     [rbp+57h+var_90], rax
0x18001f6b6  mov     [rbp+57h+var_88], 4
0x18001f6be  lea     r8, [rbp+57h+var_A0]
0x18001f6c2  lea     rdx, [rbp+57h+var_90]
0x18001f6c6  inc     edi
0x18001f6c8  mov     r9d, edi
0x18001f6cb  lea     rcx, [rbp+57h+Src]; Src
0x18001f6cf  call    CreateXmlElement
0x18001f6d4  mov     r8, [rbx+68h]
0x18001f6d8  mov     rcx, [rbx+70h]
0x18001f6dc  sub     rcx, r8
0x18001f6df  sar     rcx, 3
0x18001f6e3  mov     eax, edi
0x18001f6e5  cmp     rax, rcx
0x18001f6e8  jb      loc_18001F5D4
0x18001f6ee  lea     rdx, aEventdata_0; "</EventData>"
0x18001f6f5  mov     r8d, 0Ch
0x18001f6fb  lea     rcx, [rbp+57h+Src]; Src
0x18001f6ff  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18001f704  lea     rcx, [rbx+40h]
0x18001f708  lea     rdx, [rbp+57h+Src]
0x18001f70c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001f711  mov     dword ptr [rbx+60h], 1
0x18001f718  lea     rcx, [rbp+57h+Src]
0x18001f71c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f721  mov     rcx, [rbp+57h+var_50]
0x18001f725  xor     rcx, rsp; StackCookie
0x18001f728  call    __security_check_cookie
0x18001f72d  add     rsp, 0C8h
0x18001f734  pop     r15
0x18001f736  pop     r14
0x18001f738  pop     r13
0x18001f73a  pop     r12
0x18001f73c  pop     rdi
0x18001f73d  pop     rsi
0x18001f73e  pop     rbx
0x18001f73f  pop     rbp
0x18001f740  retn
```
