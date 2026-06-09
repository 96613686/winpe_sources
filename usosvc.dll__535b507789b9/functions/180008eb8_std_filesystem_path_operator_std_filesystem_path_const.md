# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x180008eb8`
- end: `0x180009189`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `721`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008c74`

## callees

- `0x1800076e4`
- `0x180007a34`
- `0x180007dfc`
- `0x180008eb8`
- `0x180009d40`
- `0x18000a360`
- `0x18000a8a0`
- `0x18000e460`

## pseudocode

```c
std::filesystem *__fastcall std::filesystem::path::operator/=(std::filesystem *Src, std::filesystem *this)
{
  std::filesystem *v2; // rsi
  std::filesystem *v4; // rcx
  unsigned __int64 v5; // r11
  __int64 v6; // r8
  size_t v7; // r14
  __int64 v8; // rdx
  std::filesystem *v9; // r12
  const unsigned __int16 *root_name_end; // rax
  const unsigned __int16 *v11; // rcx
  std::filesystem *v12; // rbx
  unsigned __int64 v13; // rdx
  std::filesystem *v14; // r11
  const unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rbp
  const unsigned __int16 *v17; // r8
  std::filesystem *v18; // r11
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // r11
  __int64 v22; // r14
  const unsigned __int16 *v23; // r13
  unsigned __int64 v24; // rax
  size_t v25; // r8
  std::filesystem *v26; // rbp
  __int64 v27; // rbx
  unsigned __int64 v28; // rbp
  std::filesystem *v29; // rax
  unsigned __int64 v30; // rcx
  std::filesystem *v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rbx
  bool v34; // cc
  __int64 v35; // rbp
  std::filesystem *v36; // rsi
  unsigned __int64 v38; // [rsp+78h] [rbp+10h]
  unsigned __int64 v39; // [rsp+80h] [rbp+18h]
  const unsigned __int16 *v40; // [rsp+88h] [rbp+20h]

  v2 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v4 = this;
  else
    v4 = *(std::filesystem **)this;
  v5 = *((_QWORD *)this + 2);
  v6 = 92;
  v7 = 2 * v5;
  v8 = (__int64)(2 * v5) >> 1;
  if ( v8 < 2 || (*(_DWORD *)v4 & 0xFFFFFFDF) - 3801153 >= 0x1A )
  {
    root_name_end = std::filesystem::_Find_root_name_end(
                      v4,
                      (const unsigned __int16 *const)((char *)v4 + v7),
                      (const unsigned __int16 *const)0x5C);
    if ( v11 == root_name_end )
      goto LABEL_9;
  }
  else if ( v8 < 3 || *((_WORD *)v4 + 2) != 92 && *((_WORD *)v4 + 2) != 47 )
  {
LABEL_9:
    if ( *((_QWORD *)Src + 3) <= 7u )
      v9 = Src;
    else
      v9 = *(std::filesystem **)Src;
    v40 = (const unsigned __int16 *)((char *)v9 + 2 * *((_QWORD *)Src + 2));
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v14 = v2;
    else
      v14 = *(std::filesystem **)v2;
    v15 = (const unsigned __int16 *)((char *)v14 + v7);
    v16 = std::filesystem::_Find_root_name_end(
            v9,
            (const unsigned __int16 *const)v9 + *((_QWORD *)Src + 2),
            (const unsigned __int16 *const)v6);
    v19 = std::filesystem::_Find_root_name_end(v18, v15, v17);
    v22 = (char *)v16 - (char *)v9;
    v23 = v19;
    if ( v21 != v19 )
    {
      v24 = v19 - v21;
      v25 = v22 >> 1;
      v39 = v22 >> 1;
      v38 = v24;
      if ( v24 < v22 >> 1 )
        v25 = v24;
      if ( wmemcmp((const wchar_t *)v9, v21, v25) || v39 < v38 || v39 > v38 )
      {
        if ( Src == v2 )
          return Src;
        v13 = *((_QWORD *)v2 + 2);
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(std::filesystem **)v2;
        if ( v13 <= *((_QWORD *)Src + 3) )
        {
          if ( *((_QWORD *)Src + 3) <= 7u )
            v26 = Src;
          else
            v26 = *(std::filesystem **)Src;
          v27 = 2 * v13;
          *((_QWORD *)Src + 2) = v13;
          memmove_0(v26, v2, 2 * v13);
          *(_WORD *)((char *)v26 + v27) = 0;
          return Src;
        }
LABEL_21:
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          Src,
          v13,
          v6,
          v2);
        return Src;
      }
    }
    if ( v23 != v15 && (*v23 == 92 || *v23 == 47) )
    {
      v28 = ((char *)v16 - (char *)v9) >> 1;
      if ( *((_QWORD *)Src + 2) < v28 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v20, 92);
      *((_QWORD *)Src + 2) = v28;
      if ( *((_QWORD *)Src + 3) <= 7u )
        v29 = Src;
      else
        v29 = *(std::filesystem **)Src;
      *((_WORD *)v29 + v28) = 0;
      goto LABEL_59;
    }
    if ( v16 == v40 )
    {
      if ( (__int64)(v22 & 0xFFFFFFFFFFFFFFFEuLL) >= 6 )
        goto LABEL_53;
    }
    else if ( *(v40 - 1) != 92 && *(v40 - 1) != 47 )
    {
LABEL_53:
      v30 = *((_QWORD *)Src + 2);
      if ( v30 >= *((_QWORD *)Src + 3) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        *((_QWORD *)Src + 2) = v30 + 1;
        if ( *((_QWORD *)Src + 3) <= 7u )
          v31 = Src;
        else
          v31 = *(std::filesystem **)Src;
        *(_DWORD *)((char *)v31 + 2 * v30) = 92;
      }
    }
LABEL_59:
    v32 = *((_QWORD *)Src + 2);
    v33 = v15 - v23;
    if ( v33 > *((_QWORD *)Src + 3) - v32 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        Src,
        v33);
    }
    else
    {
      v34 = *((_QWORD *)Src + 3) <= 7u;
      v35 = v33 + v32;
      *((_QWORD *)Src + 2) = v33 + v32;
      if ( v34 )
        v36 = Src;
      else
        v36 = *(std::filesystem **)Src;
      memmove_0((char *)v36 + 2 * v32, v23, 2 * v33);
      *((_WORD *)v36 + v35) = 0;
    }
    return Src;
  }
  if ( Src == v2 )
    return Src;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(std::filesystem **)v2;
  if ( v5 > *((_QWORD *)Src + 3) )
  {
    v13 = v5;
    goto LABEL_21;
  }
  if ( *((_QWORD *)Src + 3) <= 7u )
    v12 = Src;
  else
    v12 = *(std::filesystem **)Src;
  *((_QWORD *)Src + 2) = v5;
  memmove_0(v12, v2, v7);
  *(_WORD *)((char *)v12 + v7) = 0;
  return Src;
}

```

## disassembly

```asm
0x180008eb8  mov     [rsp+arg_0], rbx
0x180008ebd  push    rbp
0x180008ebe  push    rsi
0x180008ebf  push    rdi
0x180008ec0  push    r12
0x180008ec2  push    r13
0x180008ec4  push    r14
0x180008ec6  push    r15
0x180008ec8  sub     rsp, 30h
0x180008ecc  cmp     qword ptr [rdx+18h], 7
0x180008ed1  mov     rsi, rdx
0x180008ed4  mov     rdi, rcx
0x180008ed7  jbe     short loc_180008EDE
0x180008ed9  mov     rcx, [rdx]
0x180008edc  jmp     short loc_180008EE1
0x180008ede  mov     rcx, rsi; this
0x180008ee1  mov     r11, [rdx+10h]
0x180008ee5  mov     r8d, 5Ch ; '\'; unsigned __int16 *
0x180008eeb  lea     r14, [r11+r11]
0x180008eef  mov     rdx, r14
0x180008ef2  sar     rdx, 1
0x180008ef5  cmp     rdx, 2
0x180008ef9  jl      short loc_180008F2A
0x180008efb  mov     eax, [rcx]
0x180008efd  and     eax, 0FFFFFFDFh
0x180008f00  sub     eax, 3A0041h
0x180008f05  cmp     eax, 1Ah
0x180008f08  jnb     short loc_180008F2A
0x180008f0a  cmp     rdx, 3
0x180008f0e  jl      short loc_180008F1E
0x180008f10  cmp     [rcx+4], r8w
0x180008f15  jz      short loc_180008F38
0x180008f17  cmp     word ptr [rcx+4], 2Fh ; '/'
0x180008f1c  jz      short loc_180008F38
0x180008f1e  cmp     qword ptr [rdi+18h], 7
0x180008f23  jbe     short loc_180008F92
0x180008f25  mov     r12, [rdi]
0x180008f28  jmp     short loc_180008F95
0x180008f2a  lea     rdx, [r14+rcx]; unsigned __int16 *
0x180008f2e  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180008f33  cmp     rcx, rax
0x180008f36  jz      short loc_180008F1E
0x180008f38  cmp     rdi, rsi
0x180008f3b  jz      loc_18000916B
0x180008f41  cmp     qword ptr [rsi+18h], 7
0x180008f46  jbe     short loc_180008F4B
0x180008f48  mov     rsi, [rsi]
0x180008f4b  cmp     r11, [rdi+18h]
0x180008f4f  ja      short loc_180008F7F
0x180008f51  cmp     qword ptr [rdi+18h], 7
0x180008f56  jbe     short loc_180008F5D
0x180008f58  mov     rbx, [rdi]
0x180008f5b  jmp     short loc_180008F60
0x180008f5d  mov     rbx, rdi
0x180008f60  mov     r8, r14; Size
0x180008f63  mov     [rdi+10h], r11
0x180008f67  mov     rdx, rsi; Src
0x180008f6a  mov     rcx, rbx; void *
0x180008f6d  call    memmove_0
0x180008f72  xor     r15d, r15d
0x180008f75  mov     [r14+rbx], r15w
0x180008f7a  jmp     loc_18000916B
0x180008f7f  mov     rdx, r11
0x180008f82  mov     r9, rsi
0x180008f85  mov     rcx, rdi
0x180008f88  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180008f8d  jmp     loc_18000916B
0x180008f92  mov     r12, rdi
0x180008f95  cmp     qword ptr [rsi+18h], 7
0x180008f9a  mov     rax, [rdi+10h]
0x180008f9e  lea     rdx, [r12+rax*2]; unsigned __int16 *
0x180008fa2  mov     [rsp+68h+arg_18], rdx
0x180008faa  jbe     short loc_180008FB1
0x180008fac  mov     r11, [rsi]
0x180008faf  jmp     short loc_180008FB4
0x180008fb1  mov     r11, rsi
0x180008fb4  mov     rcx, r12; this
0x180008fb7  lea     rbx, [r14+r11]
0x180008fbb  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180008fc0  mov     rdx, rbx; unsigned __int16 *
0x180008fc3  mov     rcx, r11; this
0x180008fc6  mov     rbp, rax
0x180008fc9  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x180008fce  mov     r14, rbp
0x180008fd1  xor     r15d, r15d
0x180008fd4  sub     r14, r12
0x180008fd7  mov     r13, rax
0x180008fda  cmp     r11, rax
0x180008fdd  jz      loc_180009076
0x180008fe3  sub     rax, r11
0x180008fe6  mov     rcx, r14
0x180008fe9  sar     rcx, 1
0x180008fec  mov     rdx, r11; S2
0x180008fef  sar     rax, 1
0x180008ff2  mov     r8, rcx
0x180008ff5  cmp     rax, rcx
0x180008ff8  mov     [rsp+68h+arg_10], rcx
0x180009000  mov     rcx, r12; S1
0x180009003  mov     [rsp+68h+arg_8], rax
0x180009008  cmovb   r8, rax; N
0x18000900c  call    wmemcmp
0x180009011  test    eax, eax
0x180009013  jnz     short loc_180009026
0x180009015  mov     rax, [rsp+68h+arg_8]
0x18000901a  cmp     [rsp+68h+arg_10], rax
0x180009022  jb      short loc_180009026
0x180009024  jbe     short loc_180009076
0x180009026  cmp     rdi, rsi
0x180009029  jz      loc_18000916B
0x18000902f  cmp     qword ptr [rsi+18h], 7
0x180009034  mov     rdx, [rsi+10h]
0x180009038  jbe     short loc_18000903D
0x18000903a  mov     rsi, [rsi]
0x18000903d  cmp     rdx, [rdi+18h]
0x180009041  ja      loc_180008F82
0x180009047  cmp     qword ptr [rdi+18h], 7
0x18000904c  jbe     short loc_180009053
0x18000904e  mov     rbp, [rdi]
0x180009051  jmp     short loc_180009056
0x180009053  mov     rbp, rdi
0x180009056  lea     rbx, [rdx+rdx]
0x18000905a  mov     [rdi+10h], rdx
0x18000905e  mov     r8, rbx; Size
0x180009061  mov     rdx, rsi; Src
0x180009064  mov     rcx, rbp; void *
0x180009067  call    memmove_0
0x18000906c  mov     [rbx+rbp], r15w
0x180009071  jmp     loc_18000916B
0x180009076  mov     edx, 5Ch ; '\'
0x18000907b  cmp     r13, rbx
0x18000907e  jz      short loc_1800090B9
0x180009080  cmp     [r13+0], dx
0x180009085  jz      short loc_18000908F
0x180009087  cmp     word ptr [r13+0], 2Fh ; '/'
0x18000908d  jnz     short loc_1800090B9
0x18000908f  sub     rbp, r12
0x180009092  sar     rbp, 1
0x180009095  cmp     [rdi+10h], rbp
0x180009099  jb      loc_180009183
0x18000909f  mov     [rdi+10h], rbp
0x1800090a3  cmp     qword ptr [rdi+18h], 7
0x1800090a8  jbe     short loc_1800090AF
0x1800090aa  mov     rax, [rdi]
0x1800090ad  jmp     short loc_1800090B2
0x1800090af  mov     rax, rdi
0x1800090b2  mov     [rax+rbp*2], r15w
0x1800090b7  jmp     short loc_180009114
0x1800090b9  mov     rax, [rsp+68h+arg_18]
0x1800090c1  cmp     rbp, rax
0x1800090c4  jnz     short loc_1800090D2
0x1800090c6  and     r14, 0FFFFFFFFFFFFFFFEh
0x1800090ca  cmp     r14, 6
0x1800090ce  jl      short loc_180009114
0x1800090d0  jmp     short loc_1800090DF
0x1800090d2  cmp     [rax-2], dx
0x1800090d6  jz      short loc_180009114
0x1800090d8  cmp     word ptr [rax-2], 2Fh ; '/'
0x1800090dd  jz      short loc_180009114
0x1800090df  mov     rcx, [rdi+10h]
0x1800090e3  cmp     rcx, [rdi+18h]
0x1800090e7  jnb     short loc_180009109
0x1800090e9  lea     rax, [rcx+1]
0x1800090ed  mov     [rdi+10h], rax
0x1800090f1  cmp     qword ptr [rdi+18h], 7
0x1800090f6  jbe     short loc_1800090FD
0x1800090f8  mov     rax, [rdi]
0x1800090fb  jmp     short loc_180009100
0x1800090fd  mov     rax, rdi
0x180009100  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x180009107  jmp     short loc_180009114
0x180009109  mov     r9d, edx
0x18000910c  mov     rcx, rdi; Src
0x18000910f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180009114  mov     rcx, [rdi+10h]
0x180009118  sub     rbx, r13
0x18000911b  mov     rax, [rdi+18h]
0x18000911f  sar     rbx, 1
0x180009122  sub     rax, rcx
0x180009125  cmp     rbx, rax
0x180009128  ja      short loc_180009158
0x18000912a  cmp     qword ptr [rdi+18h], 7
0x18000912f  lea     rbp, [rbx+rcx]
0x180009133  mov     [rdi+10h], rbp
0x180009137  jbe     short loc_18000913E
0x180009139  mov     rsi, [rdi]
0x18000913c  jmp     short loc_180009141
0x18000913e  mov     rsi, rdi
0x180009141  lea     r8, [rbx+rbx]; Size
0x180009145  mov     rdx, r13; Src
0x180009148  lea     rcx, [rsi+rcx*2]; void *
0x18000914c  call    memmove_0
0x180009151  mov     [rsi+rbp*2], r15w
0x180009156  jmp     short loc_18000916B
0x180009158  mov     r9, r13
0x18000915b  mov     [rsp+68h+var_48], rbx; __int64
0x180009160  mov     rdx, rbx
0x180009163  mov     rcx, rdi; Src
0x180009166  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18000916b  mov     rbx, [rsp+68h+arg_0]
0x180009170  mov     rax, rdi
0x180009173  add     rsp, 30h
0x180009177  pop     r15
0x180009179  pop     r14
0x18000917b  pop     r13
0x18000917d  pop     r12
0x18000917f  pop     rdi
0x180009180  pop     rsi
0x180009181  pop     rbp
0x180009182  retn
0x180009183  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
