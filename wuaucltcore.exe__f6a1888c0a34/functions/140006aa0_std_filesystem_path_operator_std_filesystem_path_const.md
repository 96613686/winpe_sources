# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x140006aa0`
- end: `0x140006cff`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `607`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140006d08`
- `0x14000713c`

## callees

- `0x1400069c0`
- `0x140006aa0`
- `0x1400090f0`
- `0x140009650`
- `0x140009790`
- `0x140009bb0`
- `0x14000aac4`
- `0x140020b20`

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
        std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(Src);
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
      std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
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
0x140006aa0  mov     [rsp+arg_10], rbx
0x140006aa5  push    rbp
0x140006aa6  push    rsi
0x140006aa7  push    rdi
0x140006aa8  push    r12
0x140006aaa  push    r13
0x140006aac  push    r14
0x140006aae  push    r15
0x140006ab0  sub     rsp, 40h
0x140006ab4  cmp     qword ptr [rdx+18h], 7
0x140006ab9  mov     rbx, rcx
0x140006abc  mov     rcx, rdx
0x140006abf  mov     rdi, rdx
0x140006ac2  jbe     short loc_140006AC7
0x140006ac4  mov     rcx, [rdx]; this
0x140006ac7  mov     rsi, [rdx+10h]
0x140006acb  mov     r13d, 5Ch ; '\'
0x140006ad1  lea     r8, [rsi+rsi]; wchar_t *
0x140006ad5  mov     rdx, r8
0x140006ad8  sar     rdx, 1
0x140006adb  cmp     rdx, 2
0x140006adf  jl      loc_140006BC1
0x140006ae5  mov     eax, [rcx]
0x140006ae7  and     eax, 0FFFFFFDFh
0x140006aea  sub     eax, 3A0041h
0x140006aef  cmp     eax, 1Ah
0x140006af2  jnb     loc_140006BC1
0x140006af8  cmp     rdx, 3
0x140006afc  jl      short loc_140006B14
0x140006afe  cmp     [rcx+4], r13w
0x140006b03  jz      loc_140006BD3
0x140006b09  cmp     word ptr [rcx+4], 2Fh ; '/'
0x140006b0e  jz      loc_140006BD3
0x140006b14  cmp     qword ptr [rbx+18h], 7
0x140006b19  mov     r15, rbx
0x140006b1c  jbe     short loc_140006B21
0x140006b1e  mov     r15, [rbx]
0x140006b21  cmp     qword ptr [rdi+18h], 7
0x140006b26  mov     r11, rdi
0x140006b29  mov     rax, [rbx+10h]
0x140006b2d  lea     r12, [r15+rax*2]
0x140006b31  mov     [rsp+78h+var_48], r12
0x140006b36  jbe     short loc_140006B3B
0x140006b38  mov     r11, [rdi]
0x140006b3b  mov     rdx, r12; wchar_t *
0x140006b3e  lea     r14, [r11+rsi*2]
0x140006b42  mov     rcx, r15; this
0x140006b45  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x140006b4a  mov     rdx, r14; wchar_t *
0x140006b4d  mov     rcx, r11; this
0x140006b50  mov     rsi, rax
0x140006b53  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x140006b58  xor     edx, edx
0x140006b5a  mov     rbp, rax
0x140006b5d  cmp     r11, rax
0x140006b60  jz      loc_140006BF6
0x140006b66  mov     r12, rax
0x140006b69  mov     r13, rsi
0x140006b6c  sub     r12, r11
0x140006b6f  sub     r13, r15
0x140006b72  sar     r12, 1
0x140006b75  mov     rdx, r11; S2
0x140006b78  sar     r13, 1
0x140006b7b  mov     rcx, r15; S1
0x140006b7e  cmp     r12, r13
0x140006b81  mov     r8, r13
0x140006b84  cmovb   r8, r12; N
0x140006b88  call    wmemcmp
0x140006b8d  xor     edx, edx
0x140006b8f  test    eax, eax
0x140006b91  jnz     short loc_140006B9A
0x140006b93  cmp     r13, r12
0x140006b96  jb      short loc_140006B9A
0x140006b98  jbe     short loc_140006BEB
0x140006b9a  cmp     rbx, rdi
0x140006b9d  jz      loc_140006CDE
0x140006ba3  cmp     qword ptr [rdi+18h], 7
0x140006ba8  mov     r8, [rdi+10h]
0x140006bac  jbe     short loc_140006BB1
0x140006bae  mov     rdi, [rdi]
0x140006bb1  mov     rdx, rdi; Src
0x140006bb4  mov     rcx, rbx; void *
0x140006bb7  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x140006bbc  jmp     loc_140006CDE
0x140006bc1  lea     rdx, [r8+rcx]; wchar_t *
0x140006bc5  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x140006bca  cmp     rcx, rax
0x140006bcd  jz      loc_140006B14
0x140006bd3  cmp     rbx, rdi
0x140006bd6  jz      loc_140006CDE
0x140006bdc  cmp     qword ptr [rdi+18h], 7
0x140006be1  jbe     short loc_140006BE6
0x140006be3  mov     rdi, [rdi]
0x140006be6  mov     r8, rsi
0x140006be9  jmp     short loc_140006BB1
0x140006beb  mov     r12, [rsp+78h+var_48]
0x140006bf0  mov     r13d, 5Ch ; '\'
0x140006bf6  cmp     rbp, r14
0x140006bf9  jz      short loc_140006C30
0x140006bfb  cmp     [rbp+0], r13w
0x140006c00  jz      short loc_140006C09
0x140006c02  cmp     word ptr [rbp+0], 2Fh ; '/'
0x140006c07  jnz     short loc_140006C30
0x140006c09  sub     rsi, r15
0x140006c0c  sar     rsi, 1
0x140006c0f  cmp     [rbx+10h], rsi
0x140006c13  jb      loc_140006CF9
0x140006c19  mov     [rbx+10h], rsi
0x140006c1d  mov     rax, rbx
0x140006c20  cmp     qword ptr [rbx+18h], 7
0x140006c25  jbe     short loc_140006C2A
0x140006c27  mov     rax, [rbx]
0x140006c2a  mov     [rax+rsi*2], dx
0x140006c2e  jmp     short loc_140006C88
0x140006c30  cmp     rsi, r12
0x140006c33  jnz     short loc_140006C44
0x140006c35  sub     rsi, r15
0x140006c38  and     rsi, 0FFFFFFFFFFFFFFFEh
0x140006c3c  cmp     rsi, 6
0x140006c40  jl      short loc_140006C88
0x140006c42  jmp     short loc_140006C55
0x140006c44  cmp     [r12-2], r13w
0x140006c4a  jz      short loc_140006C88
0x140006c4c  cmp     word ptr [r12-2], 2Fh ; '/'
0x140006c53  jz      short loc_140006C88
0x140006c55  mov     rcx, [rbx+10h]
0x140006c59  cmp     rcx, [rbx+18h]
0x140006c5d  jnb     short loc_140006C7D
0x140006c5f  lea     rax, [rcx+1]
0x140006c63  mov     [rbx+10h], rax
0x140006c67  mov     rax, rbx
0x140006c6a  cmp     qword ptr [rbx+18h], 7
0x140006c6f  jbe     short loc_140006C74
0x140006c71  mov     rax, [rbx]
0x140006c74  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x140006c7b  jmp     short loc_140006C88
0x140006c7d  mov     r9d, r13d
0x140006c80  mov     rcx, rbx; Src
0x140006c83  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x140006c88  mov     rcx, [rbx+10h]
0x140006c8c  sub     r14, rbp
0x140006c8f  mov     rax, [rbx+18h]
0x140006c93  sar     r14, 1
0x140006c96  sub     rax, rcx
0x140006c99  cmp     r14, rax
0x140006c9c  ja      short loc_140006CCB
0x140006c9e  cmp     qword ptr [rbx+18h], 7
0x140006ca3  lea     rsi, [rcx+r14]
0x140006ca7  mov     [rbx+10h], rsi
0x140006cab  mov     rdi, rbx
0x140006cae  jbe     short loc_140006CB3
0x140006cb0  mov     rdi, [rbx]
0x140006cb3  lea     r8, [r14+r14]; Size
0x140006cb7  mov     rdx, rbp; Src
0x140006cba  lea     rcx, [rdi+rcx*2]; void *
0x140006cbe  call    memmove
0x140006cc3  xor     eax, eax
0x140006cc5  mov     [rdi+rsi*2], ax
0x140006cc9  jmp     short loc_140006CDE
0x140006ccb  mov     r9, rbp
0x140006cce  mov     [rsp+78h+var_58], r14; __int64
0x140006cd3  mov     rdx, r14
0x140006cd6  mov     rcx, rbx; Src
0x140006cd9  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x140006cde  mov     rax, rbx
0x140006ce1  mov     rbx, [rsp+78h+arg_10]
0x140006ce9  add     rsp, 40h
0x140006ced  pop     r15
0x140006cef  pop     r14
0x140006cf1  pop     r13
0x140006cf3  pop     r12
0x140006cf5  pop     rdi
0x140006cf6  pop     rsi
0x140006cf7  pop     rbp
0x140006cf8  retn
0x140006cf9  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
