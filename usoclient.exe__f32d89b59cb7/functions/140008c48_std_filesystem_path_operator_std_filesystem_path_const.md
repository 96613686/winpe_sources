# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x140008c48`
- end: `0x140008f19`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `721`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140008a04`

## callees

- `0x1400073c0`
- `0x140007710`
- `0x140007ad8`
- `0x140008c48`
- `0x140009ca4`
- `0x14000a2c4`
- `0x14000aa58`
- `0x14000ac60`

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
        (void **)Src,
        v33,
        v6,
        v23,
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
0x140008c48  mov     [rsp+arg_0], rbx
0x140008c4d  push    rbp
0x140008c4e  push    rsi
0x140008c4f  push    rdi
0x140008c50  push    r12
0x140008c52  push    r13
0x140008c54  push    r14
0x140008c56  push    r15
0x140008c58  sub     rsp, 30h
0x140008c5c  cmp     qword ptr [rdx+18h], 7
0x140008c61  mov     rsi, rdx
0x140008c64  mov     rdi, rcx
0x140008c67  jbe     short loc_140008C6E
0x140008c69  mov     rcx, [rdx]
0x140008c6c  jmp     short loc_140008C71
0x140008c6e  mov     rcx, rsi; this
0x140008c71  mov     r11, [rdx+10h]
0x140008c75  mov     r8d, 5Ch ; '\'; unsigned __int16 *
0x140008c7b  lea     r14, [r11+r11]
0x140008c7f  mov     rdx, r14
0x140008c82  sar     rdx, 1
0x140008c85  cmp     rdx, 2
0x140008c89  jl      short loc_140008CBA
0x140008c8b  mov     eax, [rcx]
0x140008c8d  and     eax, 0FFFFFFDFh
0x140008c90  sub     eax, 3A0041h
0x140008c95  cmp     eax, 1Ah
0x140008c98  jnb     short loc_140008CBA
0x140008c9a  cmp     rdx, 3
0x140008c9e  jl      short loc_140008CAE
0x140008ca0  cmp     [rcx+4], r8w
0x140008ca5  jz      short loc_140008CC8
0x140008ca7  cmp     word ptr [rcx+4], 2Fh ; '/'
0x140008cac  jz      short loc_140008CC8
0x140008cae  cmp     qword ptr [rdi+18h], 7
0x140008cb3  jbe     short loc_140008D22
0x140008cb5  mov     r12, [rdi]
0x140008cb8  jmp     short loc_140008D25
0x140008cba  lea     rdx, [r14+rcx]; unsigned __int16 *
0x140008cbe  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x140008cc3  cmp     rcx, rax
0x140008cc6  jz      short loc_140008CAE
0x140008cc8  cmp     rdi, rsi
0x140008ccb  jz      loc_140008EFB
0x140008cd1  cmp     qword ptr [rsi+18h], 7
0x140008cd6  jbe     short loc_140008CDB
0x140008cd8  mov     rsi, [rsi]
0x140008cdb  cmp     r11, [rdi+18h]
0x140008cdf  ja      short loc_140008D0F
0x140008ce1  cmp     qword ptr [rdi+18h], 7
0x140008ce6  jbe     short loc_140008CED
0x140008ce8  mov     rbx, [rdi]
0x140008ceb  jmp     short loc_140008CF0
0x140008ced  mov     rbx, rdi
0x140008cf0  mov     r8, r14; Size
0x140008cf3  mov     [rdi+10h], r11
0x140008cf7  mov     rdx, rsi; Src
0x140008cfa  mov     rcx, rbx; void *
0x140008cfd  call    memmove_0
0x140008d02  xor     r15d, r15d
0x140008d05  mov     [r14+rbx], r15w
0x140008d0a  jmp     loc_140008EFB
0x140008d0f  mov     rdx, r11
0x140008d12  mov     r9, rsi
0x140008d15  mov     rcx, rdi
0x140008d18  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140008d1d  jmp     loc_140008EFB
0x140008d22  mov     r12, rdi
0x140008d25  cmp     qword ptr [rsi+18h], 7
0x140008d2a  mov     rax, [rdi+10h]
0x140008d2e  lea     rdx, [r12+rax*2]; unsigned __int16 *
0x140008d32  mov     [rsp+68h+arg_18], rdx
0x140008d3a  jbe     short loc_140008D41
0x140008d3c  mov     r11, [rsi]
0x140008d3f  jmp     short loc_140008D44
0x140008d41  mov     r11, rsi
0x140008d44  mov     rcx, r12; this
0x140008d47  lea     rbx, [r14+r11]
0x140008d4b  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x140008d50  mov     rdx, rbx; unsigned __int16 *
0x140008d53  mov     rcx, r11; this
0x140008d56  mov     rbp, rax
0x140008d59  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x140008d5e  mov     r14, rbp
0x140008d61  xor     r15d, r15d
0x140008d64  sub     r14, r12
0x140008d67  mov     r13, rax
0x140008d6a  cmp     r11, rax
0x140008d6d  jz      loc_140008E06
0x140008d73  sub     rax, r11
0x140008d76  mov     rcx, r14
0x140008d79  sar     rcx, 1
0x140008d7c  mov     rdx, r11; S2
0x140008d7f  sar     rax, 1
0x140008d82  mov     r8, rcx
0x140008d85  cmp     rax, rcx
0x140008d88  mov     [rsp+68h+arg_10], rcx
0x140008d90  mov     rcx, r12; S1
0x140008d93  mov     [rsp+68h+arg_8], rax
0x140008d98  cmovb   r8, rax; N
0x140008d9c  call    wmemcmp
0x140008da1  test    eax, eax
0x140008da3  jnz     short loc_140008DB6
0x140008da5  mov     rax, [rsp+68h+arg_8]
0x140008daa  cmp     [rsp+68h+arg_10], rax
0x140008db2  jb      short loc_140008DB6
0x140008db4  jbe     short loc_140008E06
0x140008db6  cmp     rdi, rsi
0x140008db9  jz      loc_140008EFB
0x140008dbf  cmp     qword ptr [rsi+18h], 7
0x140008dc4  mov     rdx, [rsi+10h]
0x140008dc8  jbe     short loc_140008DCD
0x140008dca  mov     rsi, [rsi]
0x140008dcd  cmp     rdx, [rdi+18h]
0x140008dd1  ja      loc_140008D12
0x140008dd7  cmp     qword ptr [rdi+18h], 7
0x140008ddc  jbe     short loc_140008DE3
0x140008dde  mov     rbp, [rdi]
0x140008de1  jmp     short loc_140008DE6
0x140008de3  mov     rbp, rdi
0x140008de6  lea     rbx, [rdx+rdx]
0x140008dea  mov     [rdi+10h], rdx
0x140008dee  mov     r8, rbx; Size
0x140008df1  mov     rdx, rsi; Src
0x140008df4  mov     rcx, rbp; void *
0x140008df7  call    memmove_0
0x140008dfc  mov     [rbx+rbp], r15w
0x140008e01  jmp     loc_140008EFB
0x140008e06  mov     edx, 5Ch ; '\'
0x140008e0b  cmp     r13, rbx
0x140008e0e  jz      short loc_140008E49
0x140008e10  cmp     [r13+0], dx
0x140008e15  jz      short loc_140008E1F
0x140008e17  cmp     word ptr [r13+0], 2Fh ; '/'
0x140008e1d  jnz     short loc_140008E49
0x140008e1f  sub     rbp, r12
0x140008e22  sar     rbp, 1
0x140008e25  cmp     [rdi+10h], rbp
0x140008e29  jb      loc_140008F13
0x140008e2f  mov     [rdi+10h], rbp
0x140008e33  cmp     qword ptr [rdi+18h], 7
0x140008e38  jbe     short loc_140008E3F
0x140008e3a  mov     rax, [rdi]
0x140008e3d  jmp     short loc_140008E42
0x140008e3f  mov     rax, rdi
0x140008e42  mov     [rax+rbp*2], r15w
0x140008e47  jmp     short loc_140008EA4
0x140008e49  mov     rax, [rsp+68h+arg_18]
0x140008e51  cmp     rbp, rax
0x140008e54  jnz     short loc_140008E62
0x140008e56  and     r14, 0FFFFFFFFFFFFFFFEh
0x140008e5a  cmp     r14, 6
0x140008e5e  jl      short loc_140008EA4
0x140008e60  jmp     short loc_140008E6F
0x140008e62  cmp     [rax-2], dx
0x140008e66  jz      short loc_140008EA4
0x140008e68  cmp     word ptr [rax-2], 2Fh ; '/'
0x140008e6d  jz      short loc_140008EA4
0x140008e6f  mov     rcx, [rdi+10h]
0x140008e73  cmp     rcx, [rdi+18h]
0x140008e77  jnb     short loc_140008E99
0x140008e79  lea     rax, [rcx+1]
0x140008e7d  mov     [rdi+10h], rax
0x140008e81  cmp     qword ptr [rdi+18h], 7
0x140008e86  jbe     short loc_140008E8D
0x140008e88  mov     rax, [rdi]
0x140008e8b  jmp     short loc_140008E90
0x140008e8d  mov     rax, rdi
0x140008e90  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x140008e97  jmp     short loc_140008EA4
0x140008e99  mov     r9d, edx
0x140008e9c  mov     rcx, rdi; Src
0x140008e9f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140008ea4  mov     rcx, [rdi+10h]
0x140008ea8  sub     rbx, r13
0x140008eab  mov     rax, [rdi+18h]
0x140008eaf  sar     rbx, 1
0x140008eb2  sub     rax, rcx
0x140008eb5  cmp     rbx, rax
0x140008eb8  ja      short loc_140008EE8
0x140008eba  cmp     qword ptr [rdi+18h], 7
0x140008ebf  lea     rbp, [rbx+rcx]
0x140008ec3  mov     [rdi+10h], rbp
0x140008ec7  jbe     short loc_140008ECE
0x140008ec9  mov     rsi, [rdi]
0x140008ecc  jmp     short loc_140008ED1
0x140008ece  mov     rsi, rdi
0x140008ed1  lea     r8, [rbx+rbx]; Size
0x140008ed5  mov     rdx, r13; Src
0x140008ed8  lea     rcx, [rsi+rcx*2]; void *
0x140008edc  call    memmove_0
0x140008ee1  mov     [rsi+rbp*2], r15w
0x140008ee6  jmp     short loc_140008EFB
0x140008ee8  mov     r9, r13
0x140008eeb  mov     [rsp+68h+var_48], rbx; __int64
0x140008ef0  mov     rdx, rbx
0x140008ef3  mov     rcx, rdi; Src
0x140008ef6  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x140008efb  mov     rbx, [rsp+68h+arg_0]
0x140008f00  mov     rax, rdi
0x140008f03  add     rsp, 30h
0x140008f07  pop     r15
0x140008f09  pop     r14
0x140008f0b  pop     r13
0x140008f0d  pop     r12
0x140008f0f  pop     rdi
0x140008f10  pop     rsi
0x140008f11  pop     rbp
0x140008f12  retn
0x140008f13  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
