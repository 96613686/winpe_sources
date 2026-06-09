# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x180005f3c`
- end: `0x18000619b`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `607`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800061a4`

## callees

- `0x180005e5c`
- `0x180005f3c`
- `0x1800084c4`
- `0x180008b78`
- `0x180008cb8`
- `0x1800095c8`
- `0x180009974`
- `0x180015e40`

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
0x180005f3c  mov     [rsp+arg_10], rbx
0x180005f41  push    rbp
0x180005f42  push    rsi
0x180005f43  push    rdi
0x180005f44  push    r12
0x180005f46  push    r13
0x180005f48  push    r14
0x180005f4a  push    r15
0x180005f4c  sub     rsp, 40h
0x180005f50  cmp     qword ptr [rdx+18h], 7
0x180005f55  mov     rbx, rcx
0x180005f58  mov     rcx, rdx
0x180005f5b  mov     rdi, rdx
0x180005f5e  jbe     short loc_180005F63
0x180005f60  mov     rcx, [rdx]; this
0x180005f63  mov     rsi, [rdx+10h]
0x180005f67  mov     r13d, 5Ch ; '\'
0x180005f6d  lea     r8, [rsi+rsi]; wchar_t *
0x180005f71  mov     rdx, r8
0x180005f74  sar     rdx, 1
0x180005f77  cmp     rdx, 2
0x180005f7b  jl      loc_18000605D
0x180005f81  mov     eax, [rcx]
0x180005f83  and     eax, 0FFFFFFDFh
0x180005f86  sub     eax, 3A0041h
0x180005f8b  cmp     eax, 1Ah
0x180005f8e  jnb     loc_18000605D
0x180005f94  cmp     rdx, 3
0x180005f98  jl      short loc_180005FB0
0x180005f9a  cmp     [rcx+4], r13w
0x180005f9f  jz      loc_18000606F
0x180005fa5  cmp     word ptr [rcx+4], 2Fh ; '/'
0x180005faa  jz      loc_18000606F
0x180005fb0  cmp     qword ptr [rbx+18h], 7
0x180005fb5  mov     r15, rbx
0x180005fb8  jbe     short loc_180005FBD
0x180005fba  mov     r15, [rbx]
0x180005fbd  cmp     qword ptr [rdi+18h], 7
0x180005fc2  mov     r11, rdi
0x180005fc5  mov     rax, [rbx+10h]
0x180005fc9  lea     r12, [r15+rax*2]
0x180005fcd  mov     [rsp+78h+var_48], r12
0x180005fd2  jbe     short loc_180005FD7
0x180005fd4  mov     r11, [rdi]
0x180005fd7  mov     rdx, r12; wchar_t *
0x180005fda  lea     r14, [r11+rsi*2]
0x180005fde  mov     rcx, r15; this
0x180005fe1  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180005fe6  mov     rdx, r14; wchar_t *
0x180005fe9  mov     rcx, r11; this
0x180005fec  mov     rsi, rax
0x180005fef  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180005ff4  xor     edx, edx
0x180005ff6  mov     rbp, rax
0x180005ff9  cmp     r11, rax
0x180005ffc  jz      loc_180006092
0x180006002  mov     r12, rax
0x180006005  mov     r13, rsi
0x180006008  sub     r12, r11
0x18000600b  sub     r13, r15
0x18000600e  sar     r12, 1
0x180006011  mov     rdx, r11; S2
0x180006014  sar     r13, 1
0x180006017  mov     rcx, r15; S1
0x18000601a  cmp     r12, r13
0x18000601d  mov     r8, r13
0x180006020  cmovb   r8, r12; N
0x180006024  call    wmemcmp
0x180006029  xor     edx, edx
0x18000602b  test    eax, eax
0x18000602d  jnz     short loc_180006036
0x18000602f  cmp     r13, r12
0x180006032  jb      short loc_180006036
0x180006034  jbe     short loc_180006087
0x180006036  cmp     rbx, rdi
0x180006039  jz      loc_18000617A
0x18000603f  cmp     qword ptr [rdi+18h], 7
0x180006044  mov     r8, [rdi+10h]
0x180006048  jbe     short loc_18000604D
0x18000604a  mov     rdi, [rdi]
0x18000604d  mov     rdx, rdi; Src
0x180006050  mov     rcx, rbx; void *
0x180006053  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180006058  jmp     loc_18000617A
0x18000605d  lea     rdx, [r8+rcx]; wchar_t *
0x180006061  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180006066  cmp     rcx, rax
0x180006069  jz      loc_180005FB0
0x18000606f  cmp     rbx, rdi
0x180006072  jz      loc_18000617A
0x180006078  cmp     qword ptr [rdi+18h], 7
0x18000607d  jbe     short loc_180006082
0x18000607f  mov     rdi, [rdi]
0x180006082  mov     r8, rsi
0x180006085  jmp     short loc_18000604D
0x180006087  mov     r12, [rsp+78h+var_48]
0x18000608c  mov     r13d, 5Ch ; '\'
0x180006092  cmp     rbp, r14
0x180006095  jz      short loc_1800060CC
0x180006097  cmp     [rbp+0], r13w
0x18000609c  jz      short loc_1800060A5
0x18000609e  cmp     word ptr [rbp+0], 2Fh ; '/'
0x1800060a3  jnz     short loc_1800060CC
0x1800060a5  sub     rsi, r15
0x1800060a8  sar     rsi, 1
0x1800060ab  cmp     [rbx+10h], rsi
0x1800060af  jb      loc_180006195
0x1800060b5  mov     [rbx+10h], rsi
0x1800060b9  mov     rax, rbx
0x1800060bc  cmp     qword ptr [rbx+18h], 7
0x1800060c1  jbe     short loc_1800060C6
0x1800060c3  mov     rax, [rbx]
0x1800060c6  mov     [rax+rsi*2], dx
0x1800060ca  jmp     short loc_180006124
0x1800060cc  cmp     rsi, r12
0x1800060cf  jnz     short loc_1800060E0
0x1800060d1  sub     rsi, r15
0x1800060d4  and     rsi, 0FFFFFFFFFFFFFFFEh
0x1800060d8  cmp     rsi, 6
0x1800060dc  jl      short loc_180006124
0x1800060de  jmp     short loc_1800060F1
0x1800060e0  cmp     [r12-2], r13w
0x1800060e6  jz      short loc_180006124
0x1800060e8  cmp     word ptr [r12-2], 2Fh ; '/'
0x1800060ef  jz      short loc_180006124
0x1800060f1  mov     rcx, [rbx+10h]
0x1800060f5  cmp     rcx, [rbx+18h]
0x1800060f9  jnb     short loc_180006119
0x1800060fb  lea     rax, [rcx+1]
0x1800060ff  mov     [rbx+10h], rax
0x180006103  mov     rax, rbx
0x180006106  cmp     qword ptr [rbx+18h], 7
0x18000610b  jbe     short loc_180006110
0x18000610d  mov     rax, [rbx]
0x180006110  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x180006117  jmp     short loc_180006124
0x180006119  mov     r9d, r13d
0x18000611c  mov     rcx, rbx; Src
0x18000611f  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x180006124  mov     rcx, [rbx+10h]
0x180006128  sub     r14, rbp
0x18000612b  mov     rax, [rbx+18h]
0x18000612f  sar     r14, 1
0x180006132  sub     rax, rcx
0x180006135  cmp     r14, rax
0x180006138  ja      short loc_180006167
0x18000613a  cmp     qword ptr [rbx+18h], 7
0x18000613f  lea     rsi, [rcx+r14]
0x180006143  mov     [rbx+10h], rsi
0x180006147  mov     rdi, rbx
0x18000614a  jbe     short loc_18000614F
0x18000614c  mov     rdi, [rbx]
0x18000614f  lea     r8, [r14+r14]; Size
0x180006153  mov     rdx, rbp; Src
0x180006156  lea     rcx, [rdi+rcx*2]; void *
0x18000615a  call    memmove
0x18000615f  xor     eax, eax
0x180006161  mov     [rdi+rsi*2], ax
0x180006165  jmp     short loc_18000617A
0x180006167  mov     r9, rbp
0x18000616a  mov     [rsp+78h+var_58], r14; __int64
0x18000616f  mov     rdx, r14
0x180006172  mov     rcx, rbx; Src
0x180006175  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x18000617a  mov     rax, rbx
0x18000617d  mov     rbx, [rsp+78h+arg_10]
0x180006185  add     rsp, 40h
0x180006189  pop     r15
0x18000618b  pop     r14
0x18000618d  pop     r13
0x18000618f  pop     r12
0x180006191  pop     rdi
0x180006192  pop     rsi
0x180006193  pop     rbp
0x180006194  retn
0x180006195  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
