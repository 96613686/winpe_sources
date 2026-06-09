# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x180009650`
- end: `0x1800098af`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `607`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800098b8`

## callees

- `0x180009174`
- `0x180009254`
- `0x1800093a8`
- `0x1800093b8`
- `0x1800094f8`
- `0x180009650`
- `0x18000a85c`
- `0x180015df0`

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
0x180009650  mov     [rsp+arg_10], rbx
0x180009655  push    rbp
0x180009656  push    rsi
0x180009657  push    rdi
0x180009658  push    r12
0x18000965a  push    r13
0x18000965c  push    r14
0x18000965e  push    r15
0x180009660  sub     rsp, 40h
0x180009664  cmp     qword ptr [rdx+18h], 7
0x180009669  mov     rbx, rcx
0x18000966c  mov     rcx, rdx
0x18000966f  mov     rdi, rdx
0x180009672  jbe     short loc_180009677
0x180009674  mov     rcx, [rdx]; this
0x180009677  mov     rsi, [rdx+10h]
0x18000967b  mov     r13d, 5Ch ; '\'
0x180009681  lea     r8, [rsi+rsi]; wchar_t *
0x180009685  mov     rdx, r8
0x180009688  sar     rdx, 1
0x18000968b  cmp     rdx, 2
0x18000968f  jl      loc_180009771
0x180009695  mov     eax, [rcx]
0x180009697  and     eax, 0FFFFFFDFh
0x18000969a  sub     eax, 3A0041h
0x18000969f  cmp     eax, 1Ah
0x1800096a2  jnb     loc_180009771
0x1800096a8  cmp     rdx, 3
0x1800096ac  jl      short loc_1800096C4
0x1800096ae  cmp     [rcx+4], r13w
0x1800096b3  jz      loc_180009783
0x1800096b9  cmp     word ptr [rcx+4], 2Fh ; '/'
0x1800096be  jz      loc_180009783
0x1800096c4  cmp     qword ptr [rbx+18h], 7
0x1800096c9  mov     r15, rbx
0x1800096cc  jbe     short loc_1800096D1
0x1800096ce  mov     r15, [rbx]
0x1800096d1  cmp     qword ptr [rdi+18h], 7
0x1800096d6  mov     r11, rdi
0x1800096d9  mov     rax, [rbx+10h]
0x1800096dd  lea     r12, [r15+rax*2]
0x1800096e1  mov     [rsp+78h+var_48], r12
0x1800096e6  jbe     short loc_1800096EB
0x1800096e8  mov     r11, [rdi]
0x1800096eb  mov     rdx, r12; wchar_t *
0x1800096ee  lea     r14, [r11+rsi*2]
0x1800096f2  mov     rcx, r15; this
0x1800096f5  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x1800096fa  mov     rdx, r14; wchar_t *
0x1800096fd  mov     rcx, r11; this
0x180009700  mov     rsi, rax
0x180009703  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180009708  xor     edx, edx
0x18000970a  mov     rbp, rax
0x18000970d  cmp     r11, rax
0x180009710  jz      loc_1800097A6
0x180009716  mov     r12, rax
0x180009719  mov     r13, rsi
0x18000971c  sub     r12, r11
0x18000971f  sub     r13, r15
0x180009722  sar     r12, 1
0x180009725  mov     rdx, r11; S2
0x180009728  sar     r13, 1
0x18000972b  mov     rcx, r15; S1
0x18000972e  cmp     r12, r13
0x180009731  mov     r8, r13
0x180009734  cmovb   r8, r12; N
0x180009738  call    wmemcmp
0x18000973d  xor     edx, edx
0x18000973f  test    eax, eax
0x180009741  jnz     short loc_18000974A
0x180009743  cmp     r13, r12
0x180009746  jb      short loc_18000974A
0x180009748  jbe     short loc_18000979B
0x18000974a  cmp     rbx, rdi
0x18000974d  jz      loc_18000988E
0x180009753  cmp     qword ptr [rdi+18h], 7
0x180009758  mov     r8, [rdi+10h]
0x18000975c  jbe     short loc_180009761
0x18000975e  mov     rdi, [rdi]
0x180009761  mov     rdx, rdi; Src
0x180009764  mov     rcx, rbx; void *
0x180009767  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18000976c  jmp     loc_18000988E
0x180009771  lea     rdx, [r8+rcx]; wchar_t *
0x180009775  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18000977a  cmp     rcx, rax
0x18000977d  jz      loc_1800096C4
0x180009783  cmp     rbx, rdi
0x180009786  jz      loc_18000988E
0x18000978c  cmp     qword ptr [rdi+18h], 7
0x180009791  jbe     short loc_180009796
0x180009793  mov     rdi, [rdi]
0x180009796  mov     r8, rsi
0x180009799  jmp     short loc_180009761
0x18000979b  mov     r12, [rsp+78h+var_48]
0x1800097a0  mov     r13d, 5Ch ; '\'
0x1800097a6  cmp     rbp, r14
0x1800097a9  jz      short loc_1800097E0
0x1800097ab  cmp     [rbp+0], r13w
0x1800097b0  jz      short loc_1800097B9
0x1800097b2  cmp     word ptr [rbp+0], 2Fh ; '/'
0x1800097b7  jnz     short loc_1800097E0
0x1800097b9  sub     rsi, r15
0x1800097bc  sar     rsi, 1
0x1800097bf  cmp     [rbx+10h], rsi
0x1800097c3  jb      loc_1800098A9
0x1800097c9  mov     [rbx+10h], rsi
0x1800097cd  mov     rax, rbx
0x1800097d0  cmp     qword ptr [rbx+18h], 7
0x1800097d5  jbe     short loc_1800097DA
0x1800097d7  mov     rax, [rbx]
0x1800097da  mov     [rax+rsi*2], dx
0x1800097de  jmp     short loc_180009838
0x1800097e0  cmp     rsi, r12
0x1800097e3  jnz     short loc_1800097F4
0x1800097e5  sub     rsi, r15
0x1800097e8  and     rsi, 0FFFFFFFFFFFFFFFEh
0x1800097ec  cmp     rsi, 6
0x1800097f0  jl      short loc_180009838
0x1800097f2  jmp     short loc_180009805
0x1800097f4  cmp     [r12-2], r13w
0x1800097fa  jz      short loc_180009838
0x1800097fc  cmp     word ptr [r12-2], 2Fh ; '/'
0x180009803  jz      short loc_180009838
0x180009805  mov     rcx, [rbx+10h]
0x180009809  cmp     rcx, [rbx+18h]
0x18000980d  jnb     short loc_18000982D
0x18000980f  lea     rax, [rcx+1]
0x180009813  mov     [rbx+10h], rax
0x180009817  mov     rax, rbx
0x18000981a  cmp     qword ptr [rbx+18h], 7
0x18000981f  jbe     short loc_180009824
0x180009821  mov     rax, [rbx]
0x180009824  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x18000982b  jmp     short loc_180009838
0x18000982d  mov     r9d, r13d
0x180009830  mov     rcx, rbx; Src
0x180009833  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x180009838  mov     rcx, [rbx+10h]
0x18000983c  sub     r14, rbp
0x18000983f  mov     rax, [rbx+18h]
0x180009843  sar     r14, 1
0x180009846  sub     rax, rcx
0x180009849  cmp     r14, rax
0x18000984c  ja      short loc_18000987B
0x18000984e  cmp     qword ptr [rbx+18h], 7
0x180009853  lea     rsi, [rcx+r14]
0x180009857  mov     [rbx+10h], rsi
0x18000985b  mov     rdi, rbx
0x18000985e  jbe     short loc_180009863
0x180009860  mov     rdi, [rbx]
0x180009863  lea     r8, [r14+r14]; Size
0x180009867  mov     rdx, rbp; Src
0x18000986a  lea     rcx, [rdi+rcx*2]; void *
0x18000986e  call    memmove
0x180009873  xor     eax, eax
0x180009875  mov     [rdi+rsi*2], ax
0x180009879  jmp     short loc_18000988E
0x18000987b  mov     r9, rbp
0x18000987e  mov     [rsp+78h+var_58], r14; __int64
0x180009883  mov     rdx, r14
0x180009886  mov     rcx, rbx; Src
0x180009889  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x18000988e  mov     rax, rbx
0x180009891  mov     rbx, [rsp+78h+arg_10]
0x180009899  add     rsp, 40h
0x18000989d  pop     r15
0x18000989f  pop     r14
0x1800098a1  pop     r13
0x1800098a3  pop     r12
0x1800098a5  pop     rdi
0x1800098a6  pop     rsi
0x1800098a7  pop     rbp
0x1800098a8  retn
0x1800098a9  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
