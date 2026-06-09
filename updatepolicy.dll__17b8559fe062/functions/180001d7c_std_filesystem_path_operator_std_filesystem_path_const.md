# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x180001d7c`
- end: `0x180001fdb`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `607`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001fe4`

## callees

- `0x180001c9c`
- `0x180001d7c`
- `0x18000467c`
- `0x180004af8`
- `0x180004c38`
- `0x180005384`
- `0x180005744`
- `0x180015870`

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
0x180001d7c  mov     [rsp+arg_10], rbx
0x180001d81  push    rbp
0x180001d82  push    rsi
0x180001d83  push    rdi
0x180001d84  push    r12
0x180001d86  push    r13
0x180001d88  push    r14
0x180001d8a  push    r15
0x180001d8c  sub     rsp, 40h
0x180001d90  cmp     qword ptr [rdx+18h], 7
0x180001d95  mov     rbx, rcx
0x180001d98  mov     rcx, rdx
0x180001d9b  mov     rdi, rdx
0x180001d9e  jbe     short loc_180001DA3
0x180001da0  mov     rcx, [rdx]; this
0x180001da3  mov     rsi, [rdx+10h]
0x180001da7  mov     r13d, 5Ch ; '\'
0x180001dad  lea     r8, [rsi+rsi]; wchar_t *
0x180001db1  mov     rdx, r8
0x180001db4  sar     rdx, 1
0x180001db7  cmp     rdx, 2
0x180001dbb  jl      loc_180001E9D
0x180001dc1  mov     eax, [rcx]
0x180001dc3  and     eax, 0FFFFFFDFh
0x180001dc6  sub     eax, 3A0041h
0x180001dcb  cmp     eax, 1Ah
0x180001dce  jnb     loc_180001E9D
0x180001dd4  cmp     rdx, 3
0x180001dd8  jl      short loc_180001DF0
0x180001dda  cmp     [rcx+4], r13w
0x180001ddf  jz      loc_180001EAF
0x180001de5  cmp     word ptr [rcx+4], 2Fh ; '/'
0x180001dea  jz      loc_180001EAF
0x180001df0  cmp     qword ptr [rbx+18h], 7
0x180001df5  mov     r15, rbx
0x180001df8  jbe     short loc_180001DFD
0x180001dfa  mov     r15, [rbx]
0x180001dfd  cmp     qword ptr [rdi+18h], 7
0x180001e02  mov     r11, rdi
0x180001e05  mov     rax, [rbx+10h]
0x180001e09  lea     r12, [r15+rax*2]
0x180001e0d  mov     [rsp+78h+var_48], r12
0x180001e12  jbe     short loc_180001E17
0x180001e14  mov     r11, [rdi]
0x180001e17  mov     rdx, r12; wchar_t *
0x180001e1a  lea     r14, [r11+rsi*2]
0x180001e1e  mov     rcx, r15; this
0x180001e21  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180001e26  mov     rdx, r14; wchar_t *
0x180001e29  mov     rcx, r11; this
0x180001e2c  mov     rsi, rax
0x180001e2f  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180001e34  xor     edx, edx
0x180001e36  mov     rbp, rax
0x180001e39  cmp     r11, rax
0x180001e3c  jz      loc_180001ED2
0x180001e42  mov     r12, rax
0x180001e45  mov     r13, rsi
0x180001e48  sub     r12, r11
0x180001e4b  sub     r13, r15
0x180001e4e  sar     r12, 1
0x180001e51  mov     rdx, r11; S2
0x180001e54  sar     r13, 1
0x180001e57  mov     rcx, r15; S1
0x180001e5a  cmp     r12, r13
0x180001e5d  mov     r8, r13
0x180001e60  cmovb   r8, r12; N
0x180001e64  call    wmemcmp
0x180001e69  xor     edx, edx
0x180001e6b  test    eax, eax
0x180001e6d  jnz     short loc_180001E76
0x180001e6f  cmp     r13, r12
0x180001e72  jb      short loc_180001E76
0x180001e74  jbe     short loc_180001EC7
0x180001e76  cmp     rbx, rdi
0x180001e79  jz      loc_180001FBA
0x180001e7f  cmp     qword ptr [rdi+18h], 7
0x180001e84  mov     r8, [rdi+10h]
0x180001e88  jbe     short loc_180001E8D
0x180001e8a  mov     rdi, [rdi]
0x180001e8d  mov     rdx, rdi; Src
0x180001e90  mov     rcx, rbx; void *
0x180001e93  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180001e98  jmp     loc_180001FBA
0x180001e9d  lea     rdx, [r8+rcx]; wchar_t *
0x180001ea1  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180001ea6  cmp     rcx, rax
0x180001ea9  jz      loc_180001DF0
0x180001eaf  cmp     rbx, rdi
0x180001eb2  jz      loc_180001FBA
0x180001eb8  cmp     qword ptr [rdi+18h], 7
0x180001ebd  jbe     short loc_180001EC2
0x180001ebf  mov     rdi, [rdi]
0x180001ec2  mov     r8, rsi
0x180001ec5  jmp     short loc_180001E8D
0x180001ec7  mov     r12, [rsp+78h+var_48]
0x180001ecc  mov     r13d, 5Ch ; '\'
0x180001ed2  cmp     rbp, r14
0x180001ed5  jz      short loc_180001F0C
0x180001ed7  cmp     [rbp+0], r13w
0x180001edc  jz      short loc_180001EE5
0x180001ede  cmp     word ptr [rbp+0], 2Fh ; '/'
0x180001ee3  jnz     short loc_180001F0C
0x180001ee5  sub     rsi, r15
0x180001ee8  sar     rsi, 1
0x180001eeb  cmp     [rbx+10h], rsi
0x180001eef  jb      loc_180001FD5
0x180001ef5  mov     [rbx+10h], rsi
0x180001ef9  mov     rax, rbx
0x180001efc  cmp     qword ptr [rbx+18h], 7
0x180001f01  jbe     short loc_180001F06
0x180001f03  mov     rax, [rbx]
0x180001f06  mov     [rax+rsi*2], dx
0x180001f0a  jmp     short loc_180001F64
0x180001f0c  cmp     rsi, r12
0x180001f0f  jnz     short loc_180001F20
0x180001f11  sub     rsi, r15
0x180001f14  and     rsi, 0FFFFFFFFFFFFFFFEh
0x180001f18  cmp     rsi, 6
0x180001f1c  jl      short loc_180001F64
0x180001f1e  jmp     short loc_180001F31
0x180001f20  cmp     [r12-2], r13w
0x180001f26  jz      short loc_180001F64
0x180001f28  cmp     word ptr [r12-2], 2Fh ; '/'
0x180001f2f  jz      short loc_180001F64
0x180001f31  mov     rcx, [rbx+10h]
0x180001f35  cmp     rcx, [rbx+18h]
0x180001f39  jnb     short loc_180001F59
0x180001f3b  lea     rax, [rcx+1]
0x180001f3f  mov     [rbx+10h], rax
0x180001f43  mov     rax, rbx
0x180001f46  cmp     qword ptr [rbx+18h], 7
0x180001f4b  jbe     short loc_180001F50
0x180001f4d  mov     rax, [rbx]
0x180001f50  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x180001f57  jmp     short loc_180001F64
0x180001f59  mov     r9d, r13d
0x180001f5c  mov     rcx, rbx; Src
0x180001f5f  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x180001f64  mov     rcx, [rbx+10h]
0x180001f68  sub     r14, rbp
0x180001f6b  mov     rax, [rbx+18h]
0x180001f6f  sar     r14, 1
0x180001f72  sub     rax, rcx
0x180001f75  cmp     r14, rax
0x180001f78  ja      short loc_180001FA7
0x180001f7a  cmp     qword ptr [rbx+18h], 7
0x180001f7f  lea     rsi, [rcx+r14]
0x180001f83  mov     [rbx+10h], rsi
0x180001f87  mov     rdi, rbx
0x180001f8a  jbe     short loc_180001F8F
0x180001f8c  mov     rdi, [rbx]
0x180001f8f  lea     r8, [r14+r14]; Size
0x180001f93  mov     rdx, rbp; Src
0x180001f96  lea     rcx, [rdi+rcx*2]; void *
0x180001f9a  call    memmove
0x180001f9f  xor     eax, eax
0x180001fa1  mov     [rdi+rsi*2], ax
0x180001fa5  jmp     short loc_180001FBA
0x180001fa7  mov     r9, rbp
0x180001faa  mov     [rsp+78h+var_58], r14; __int64
0x180001faf  mov     rdx, r14
0x180001fb2  mov     rcx, rbx; Src
0x180001fb5  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x180001fba  mov     rax, rbx
0x180001fbd  mov     rbx, [rsp+78h+arg_10]
0x180001fc5  add     rsp, 40h
0x180001fc9  pop     r15
0x180001fcb  pop     r14
0x180001fcd  pop     r13
0x180001fcf  pop     r12
0x180001fd1  pop     rdi
0x180001fd2  pop     rsi
0x180001fd3  pop     rbp
0x180001fd4  retn
0x180001fd5  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
