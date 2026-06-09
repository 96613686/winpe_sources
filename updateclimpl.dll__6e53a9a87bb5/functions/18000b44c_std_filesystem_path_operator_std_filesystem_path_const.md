# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x18000b44c`
- end: `0x18000b6ab`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `607`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000892c`

## callees

- `0x18000af3c`
- `0x18000b090`
- `0x18000b1b4`
- `0x18000b2f4`
- `0x18000b44c`
- `0x18000c1f0`
- `0x18000c2d0`
- `0x180014d20`

## pseudocode

```c
std::filesystem *__fastcall std::filesystem::path::operator/=(std::filesystem *Src, std::filesystem *a2)
{
  std::filesystem *v3; // rcx
  std::filesystem *v4; // rdi
  __int64 v5; // rsi
  const wchar_t *v6; // r8
  __int64 v7; // rdx
  std::filesystem *v8; // r15
  std::filesystem *v9; // r11
  __int64 v10; // rax
  const wchar_t *v11; // r12
  const wchar_t *v12; // r14
  const wchar_t *v13; // rsi
  const wchar_t *v14; // r8
  std::filesystem *v15; // r11
  const wchar_t *v16; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // r11
  const wchar_t *v19; // rbp
  unsigned __int64 v20; // r12
  unsigned __int64 v21; // r13
  size_t v22; // r8
  const wchar_t *root_name_end; // rax
  const wchar_t *v24; // rcx
  unsigned __int64 v25; // rsi
  std::filesystem *v26; // rax
  unsigned __int64 v27; // rcx
  std::filesystem *v28; // rax
  __int64 v29; // rcx
  unsigned __int64 v30; // r14
  bool v31; // cc
  __int64 v32; // rsi
  std::filesystem *v33; // rdi
  const wchar_t *v35; // [rsp+30h] [rbp-48h]

  v3 = a2;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v3 = *(std::filesystem **)a2;
  v5 = *((_QWORD *)a2 + 2);
  v6 = (const wchar_t *)(2 * v5);
  v7 = (2 * v5) >> 1;
  if ( v7 < 2 || (*(_DWORD *)v3 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    root_name_end = std::filesystem::_Find_root_name_end(v3, (const wchar_t *const)((char *)v3 + (_QWORD)v6), v6);
    if ( v24 == root_name_end )
      goto LABEL_8;
LABEL_23:
    if ( Src == v4 )
      return Src;
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(std::filesystem **)v4;
    goto LABEL_21;
  }
  if ( v7 >= 3 && (*((_WORD *)v3 + 2) == 92 || *((_WORD *)v3 + 2) == 47) )
    goto LABEL_23;
LABEL_8:
  v8 = Src;
  if ( *((_QWORD *)Src + 3) > 7u )
    v8 = *(std::filesystem **)Src;
  v9 = v4;
  v10 = *((_QWORD *)Src + 2);
  v11 = (const wchar_t *)((char *)v8 + 2 * v10);
  v35 = v11;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v9 = *(std::filesystem **)v4;
  v12 = (const wchar_t *)((char *)v9 + 2 * v5);
  v13 = std::filesystem::_Find_root_name_end(v8, (const wchar_t *const)v8 + v10, v6);
  v16 = std::filesystem::_Find_root_name_end(v15, v12, v14);
  v19 = v16;
  if ( v18 == v16 )
  {
LABEL_28:
    if ( v19 != v12 && (*v19 == 92 || *v19 == 47) )
    {
      v25 = ((char *)v13 - (char *)v8) >> 1;
      if ( *((_QWORD *)Src + 2) < v25 )
        std::_String_val<std::_Simple_types<wchar_t>>::_Xran(v17, 0);
      *((_QWORD *)Src + 2) = v25;
      v26 = Src;
      if ( *((_QWORD *)Src + 3) > 7u )
        v26 = *(std::filesystem **)Src;
      *((_WORD *)v26 + v25) = 0;
      goto LABEL_45;
    }
    if ( v13 == v11 )
    {
      if ( (__int64)(((char *)v13 - (char *)v8) & 0xFFFFFFFFFFFFFFFEuLL) >= 6 )
        goto LABEL_40;
    }
    else if ( *(v11 - 1) != 92 && *(v11 - 1) != 47 )
    {
LABEL_40:
      v27 = *((_QWORD *)Src + 2);
      if ( v27 >= *((_QWORD *)Src + 3) )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(Src);
      }
      else
      {
        *((_QWORD *)Src + 2) = v27 + 1;
        v28 = Src;
        if ( *((_QWORD *)Src + 3) > 7u )
          v28 = *(std::filesystem **)Src;
        *(_DWORD *)((char *)v28 + 2 * v27) = 92;
      }
    }
LABEL_45:
    v29 = *((_QWORD *)Src + 2);
    v30 = v12 - v19;
    if ( v30 > *((_QWORD *)Src + 3) - v29 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAAEAV34_QEB_W_K_Z_PEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_W0_Z_PEB_W_K_Z(
        Src,
        v30);
    }
    else
    {
      v31 = *((_QWORD *)Src + 3) <= 7u;
      v32 = v29 + v30;
      *((_QWORD *)Src + 2) = v29 + v30;
      v33 = Src;
      if ( !v31 )
        v33 = *(std::filesystem **)Src;
      memmove((char *)v33 + 2 * v29, v19, 2 * v30);
      *((_WORD *)v33 + v32) = 0;
    }
    return Src;
  }
  v20 = v16 - v18;
  v21 = ((char *)v13 - (char *)v8) >> 1;
  v22 = v21;
  if ( v20 < v21 )
    v22 = v16 - v18;
  if ( !wmemcmp((const wchar_t *)v8, v18, v22) && v21 >= v20 && v21 <= v20 )
  {
    v11 = v35;
    goto LABEL_28;
  }
  if ( Src != v4 )
  {
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(std::filesystem **)v4;
LABEL_21:
    std::wstring::assign(Src, v4);
  }
  return Src;
}

```

## disassembly

```asm
0x18000b44c  mov     [rsp+arg_10], rbx
0x18000b451  push    rbp
0x18000b452  push    rsi
0x18000b453  push    rdi
0x18000b454  push    r12
0x18000b456  push    r13
0x18000b458  push    r14
0x18000b45a  push    r15
0x18000b45c  sub     rsp, 40h
0x18000b460  cmp     qword ptr [rdx+18h], 7
0x18000b465  mov     rbx, rcx
0x18000b468  mov     rcx, rdx
0x18000b46b  mov     rdi, rdx
0x18000b46e  jbe     short loc_18000B473
0x18000b470  mov     rcx, [rdx]; this
0x18000b473  mov     rsi, [rdx+10h]
0x18000b477  mov     r13d, 5Ch ; '\'
0x18000b47d  lea     r8, [rsi+rsi]; wchar_t *
0x18000b481  mov     rdx, r8
0x18000b484  sar     rdx, 1
0x18000b487  cmp     rdx, 2
0x18000b48b  jl      loc_18000B56D
0x18000b491  mov     eax, [rcx]
0x18000b493  and     eax, 0FFFFFFDFh
0x18000b496  sub     eax, 3A0041h
0x18000b49b  cmp     eax, 1Ah
0x18000b49e  jnb     loc_18000B56D
0x18000b4a4  cmp     rdx, 3
0x18000b4a8  jl      short loc_18000B4C0
0x18000b4aa  cmp     [rcx+4], r13w
0x18000b4af  jz      loc_18000B57F
0x18000b4b5  cmp     word ptr [rcx+4], 2Fh ; '/'
0x18000b4ba  jz      loc_18000B57F
0x18000b4c0  cmp     qword ptr [rbx+18h], 7
0x18000b4c5  mov     r15, rbx
0x18000b4c8  jbe     short loc_18000B4CD
0x18000b4ca  mov     r15, [rbx]
0x18000b4cd  cmp     qword ptr [rdi+18h], 7
0x18000b4d2  mov     r11, rdi
0x18000b4d5  mov     rax, [rbx+10h]
0x18000b4d9  lea     r12, [r15+rax*2]
0x18000b4dd  mov     [rsp+78h+var_48], r12
0x18000b4e2  jbe     short loc_18000B4E7
0x18000b4e4  mov     r11, [rdi]
0x18000b4e7  mov     rdx, r12; wchar_t *
0x18000b4ea  lea     r14, [r11+rsi*2]
0x18000b4ee  mov     rcx, r15; this
0x18000b4f1  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18000b4f6  mov     rdx, r14; wchar_t *
0x18000b4f9  mov     rcx, r11; this
0x18000b4fc  mov     rsi, rax
0x18000b4ff  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18000b504  xor     edx, edx
0x18000b506  mov     rbp, rax
0x18000b509  cmp     r11, rax
0x18000b50c  jz      loc_18000B5A2
0x18000b512  mov     r12, rax
0x18000b515  mov     r13, rsi
0x18000b518  sub     r12, r11
0x18000b51b  sub     r13, r15
0x18000b51e  sar     r12, 1
0x18000b521  mov     rdx, r11; S2
0x18000b524  sar     r13, 1
0x18000b527  mov     rcx, r15; S1
0x18000b52a  cmp     r12, r13
0x18000b52d  mov     r8, r13
0x18000b530  cmovb   r8, r12; N
0x18000b534  call    wmemcmp
0x18000b539  xor     edx, edx
0x18000b53b  test    eax, eax
0x18000b53d  jnz     short loc_18000B546
0x18000b53f  cmp     r13, r12
0x18000b542  jb      short loc_18000B546
0x18000b544  jbe     short loc_18000B597
0x18000b546  cmp     rbx, rdi
0x18000b549  jz      loc_18000B68A
0x18000b54f  cmp     qword ptr [rdi+18h], 7
0x18000b554  mov     r8, [rdi+10h]
0x18000b558  jbe     short loc_18000B55D
0x18000b55a  mov     rdi, [rdi]
0x18000b55d  mov     rdx, rdi; Src
0x18000b560  mov     rcx, rbx; void *
0x18000b563  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18000b568  jmp     loc_18000B68A
0x18000b56d  lea     rdx, [r8+rcx]; wchar_t *
0x18000b571  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18000b576  cmp     rcx, rax
0x18000b579  jz      loc_18000B4C0
0x18000b57f  cmp     rbx, rdi
0x18000b582  jz      loc_18000B68A
0x18000b588  cmp     qword ptr [rdi+18h], 7
0x18000b58d  jbe     short loc_18000B592
0x18000b58f  mov     rdi, [rdi]
0x18000b592  mov     r8, rsi
0x18000b595  jmp     short loc_18000B55D
0x18000b597  mov     r12, [rsp+78h+var_48]
0x18000b59c  mov     r13d, 5Ch ; '\'
0x18000b5a2  cmp     rbp, r14
0x18000b5a5  jz      short loc_18000B5DC
0x18000b5a7  cmp     [rbp+0], r13w
0x18000b5ac  jz      short loc_18000B5B5
0x18000b5ae  cmp     word ptr [rbp+0], 2Fh ; '/'
0x18000b5b3  jnz     short loc_18000B5DC
0x18000b5b5  sub     rsi, r15
0x18000b5b8  sar     rsi, 1
0x18000b5bb  cmp     [rbx+10h], rsi
0x18000b5bf  jb      loc_18000B6A5
0x18000b5c5  mov     [rbx+10h], rsi
0x18000b5c9  mov     rax, rbx
0x18000b5cc  cmp     qword ptr [rbx+18h], 7
0x18000b5d1  jbe     short loc_18000B5D6
0x18000b5d3  mov     rax, [rbx]
0x18000b5d6  mov     [rax+rsi*2], dx
0x18000b5da  jmp     short loc_18000B634
0x18000b5dc  cmp     rsi, r12
0x18000b5df  jnz     short loc_18000B5F0
0x18000b5e1  sub     rsi, r15
0x18000b5e4  and     rsi, 0FFFFFFFFFFFFFFFEh
0x18000b5e8  cmp     rsi, 6
0x18000b5ec  jl      short loc_18000B634
0x18000b5ee  jmp     short loc_18000B601
0x18000b5f0  cmp     [r12-2], r13w
0x18000b5f6  jz      short loc_18000B634
0x18000b5f8  cmp     word ptr [r12-2], 2Fh ; '/'
0x18000b5ff  jz      short loc_18000B634
0x18000b601  mov     rcx, [rbx+10h]
0x18000b605  cmp     rcx, [rbx+18h]
0x18000b609  jnb     short loc_18000B629
0x18000b60b  lea     rax, [rcx+1]
0x18000b60f  mov     [rbx+10h], rax
0x18000b613  mov     rax, rbx
0x18000b616  cmp     qword ptr [rbx+18h], 7
0x18000b61b  jbe     short loc_18000B620
0x18000b61d  mov     rax, [rbx]
0x18000b620  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x18000b627  jmp     short loc_18000B634
0x18000b629  mov     r9d, r13d
0x18000b62c  mov     rcx, rbx; Src
0x18000b62f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x18000b634  mov     rcx, [rbx+10h]
0x18000b638  sub     r14, rbp
0x18000b63b  mov     rax, [rbx+18h]
0x18000b63f  sar     r14, 1
0x18000b642  sub     rax, rcx
0x18000b645  cmp     r14, rax
0x18000b648  ja      short loc_18000B677
0x18000b64a  cmp     qword ptr [rbx+18h], 7
0x18000b64f  lea     rsi, [rcx+r14]
0x18000b653  mov     [rbx+10h], rsi
0x18000b657  mov     rdi, rbx
0x18000b65a  jbe     short loc_18000B65F
0x18000b65c  mov     rdi, [rbx]
0x18000b65f  lea     r8, [r14+r14]; Size
0x18000b663  mov     rdx, rbp; Src
0x18000b666  lea     rcx, [rdi+rcx*2]; void *
0x18000b66a  call    memmove
0x18000b66f  xor     eax, eax
0x18000b671  mov     [rdi+rsi*2], ax
0x18000b675  jmp     short loc_18000B68A
0x18000b677  mov     r9, rbp
0x18000b67a  mov     [rsp+78h+var_58], r14; __int64
0x18000b67f  mov     rdx, r14
0x18000b682  mov     rcx, rbx; Src
0x18000b685  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV34@QEB_W_K@Z@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_W0@Z@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::append(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *,unsigned __int64)
0x18000b68a  mov     rax, rbx
0x18000b68d  mov     rbx, [rsp+78h+arg_10]
0x18000b695  add     rsp, 40h
0x18000b699  pop     r15
0x18000b69b  pop     r14
0x18000b69d  pop     r13
0x18000b69f  pop     r12
0x18000b6a1  pop     rdi
0x18000b6a2  pop     rsi
0x18000b6a3  pop     rbp
0x18000b6a4  retn
0x18000b6a5  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
