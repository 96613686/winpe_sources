# std::filesystem::path::operator/=(std::filesystem::path const &)

- ea: `0x140008c78`
- end: `0x140008f49`
- name: `??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z`
- size: `721`
- prototype: `std::filesystem *__fastcall(std::filesystem *Src, std::filesystem *this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140008a34`

## callees

- `0x1400073a0`
- `0x1400076f0`
- `0x140007ab8`
- `0x140008c78`
- `0x140009cd4`
- `0x14000a2f4`
- `0x14000aa78`
- `0x14000ac80`

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
0x140008c78  mov     [rsp+arg_0], rbx
0x140008c7d  push    rbp
0x140008c7e  push    rsi
0x140008c7f  push    rdi
0x140008c80  push    r12
0x140008c82  push    r13
0x140008c84  push    r14
0x140008c86  push    r15
0x140008c88  sub     rsp, 30h
0x140008c8c  cmp     qword ptr [rdx+18h], 7
0x140008c91  mov     rsi, rdx
0x140008c94  mov     rdi, rcx
0x140008c97  jbe     short loc_140008C9E
0x140008c99  mov     rcx, [rdx]
0x140008c9c  jmp     short loc_140008CA1
0x140008c9e  mov     rcx, rsi; this
0x140008ca1  mov     r11, [rdx+10h]
0x140008ca5  mov     r8d, 5Ch ; '\'; unsigned __int16 *
0x140008cab  lea     r14, [r11+r11]
0x140008caf  mov     rdx, r14
0x140008cb2  sar     rdx, 1
0x140008cb5  cmp     rdx, 2
0x140008cb9  jl      short loc_140008CEA
0x140008cbb  mov     eax, [rcx]
0x140008cbd  and     eax, 0FFFFFFDFh
0x140008cc0  sub     eax, 3A0041h
0x140008cc5  cmp     eax, 1Ah
0x140008cc8  jnb     short loc_140008CEA
0x140008cca  cmp     rdx, 3
0x140008cce  jl      short loc_140008CDE
0x140008cd0  cmp     [rcx+4], r8w
0x140008cd5  jz      short loc_140008CF8
0x140008cd7  cmp     word ptr [rcx+4], 2Fh ; '/'
0x140008cdc  jz      short loc_140008CF8
0x140008cde  cmp     qword ptr [rdi+18h], 7
0x140008ce3  jbe     short loc_140008D52
0x140008ce5  mov     r12, [rdi]
0x140008ce8  jmp     short loc_140008D55
0x140008cea  lea     rdx, [r14+rcx]; unsigned __int16 *
0x140008cee  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x140008cf3  cmp     rcx, rax
0x140008cf6  jz      short loc_140008CDE
0x140008cf8  cmp     rdi, rsi
0x140008cfb  jz      loc_140008F2B
0x140008d01  cmp     qword ptr [rsi+18h], 7
0x140008d06  jbe     short loc_140008D0B
0x140008d08  mov     rsi, [rsi]
0x140008d0b  cmp     r11, [rdi+18h]
0x140008d0f  ja      short loc_140008D3F
0x140008d11  cmp     qword ptr [rdi+18h], 7
0x140008d16  jbe     short loc_140008D1D
0x140008d18  mov     rbx, [rdi]
0x140008d1b  jmp     short loc_140008D20
0x140008d1d  mov     rbx, rdi
0x140008d20  mov     r8, r14; Size
0x140008d23  mov     [rdi+10h], r11
0x140008d27  mov     rdx, rsi; Src
0x140008d2a  mov     rcx, rbx; void *
0x140008d2d  call    memmove_0
0x140008d32  xor     r15d, r15d
0x140008d35  mov     [r14+rbx], r15w
0x140008d3a  jmp     loc_140008F2B
0x140008d3f  mov     rdx, r11
0x140008d42  mov     r9, rsi
0x140008d45  mov     rcx, rdi
0x140008d48  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x140008d4d  jmp     loc_140008F2B
0x140008d52  mov     r12, rdi
0x140008d55  cmp     qword ptr [rsi+18h], 7
0x140008d5a  mov     rax, [rdi+10h]
0x140008d5e  lea     rdx, [r12+rax*2]; unsigned __int16 *
0x140008d62  mov     [rsp+68h+arg_18], rdx
0x140008d6a  jbe     short loc_140008D71
0x140008d6c  mov     r11, [rsi]
0x140008d6f  jmp     short loc_140008D74
0x140008d71  mov     r11, rsi
0x140008d74  mov     rcx, r12; this
0x140008d77  lea     rbx, [r14+r11]
0x140008d7b  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x140008d80  mov     rdx, rbx; unsigned __int16 *
0x140008d83  mov     rcx, r11; this
0x140008d86  mov     rbp, rax
0x140008d89  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x140008d8e  mov     r14, rbp
0x140008d91  xor     r15d, r15d
0x140008d94  sub     r14, r12
0x140008d97  mov     r13, rax
0x140008d9a  cmp     r11, rax
0x140008d9d  jz      loc_140008E36
0x140008da3  sub     rax, r11
0x140008da6  mov     rcx, r14
0x140008da9  sar     rcx, 1
0x140008dac  mov     rdx, r11; S2
0x140008daf  sar     rax, 1
0x140008db2  mov     r8, rcx
0x140008db5  cmp     rax, rcx
0x140008db8  mov     [rsp+68h+arg_10], rcx
0x140008dc0  mov     rcx, r12; S1
0x140008dc3  mov     [rsp+68h+arg_8], rax
0x140008dc8  cmovb   r8, rax; N
0x140008dcc  call    wmemcmp
0x140008dd1  test    eax, eax
0x140008dd3  jnz     short loc_140008DE6
0x140008dd5  mov     rax, [rsp+68h+arg_8]
0x140008dda  cmp     [rsp+68h+arg_10], rax
0x140008de2  jb      short loc_140008DE6
0x140008de4  jbe     short loc_140008E36
0x140008de6  cmp     rdi, rsi
0x140008de9  jz      loc_140008F2B
0x140008def  cmp     qword ptr [rsi+18h], 7
0x140008df4  mov     rdx, [rsi+10h]
0x140008df8  jbe     short loc_140008DFD
0x140008dfa  mov     rsi, [rsi]
0x140008dfd  cmp     rdx, [rdi+18h]
0x140008e01  ja      loc_140008D42
0x140008e07  cmp     qword ptr [rdi+18h], 7
0x140008e0c  jbe     short loc_140008E13
0x140008e0e  mov     rbp, [rdi]
0x140008e11  jmp     short loc_140008E16
0x140008e13  mov     rbp, rdi
0x140008e16  lea     rbx, [rdx+rdx]
0x140008e1a  mov     [rdi+10h], rdx
0x140008e1e  mov     r8, rbx; Size
0x140008e21  mov     rdx, rsi; Src
0x140008e24  mov     rcx, rbp; void *
0x140008e27  call    memmove_0
0x140008e2c  mov     [rbx+rbp], r15w
0x140008e31  jmp     loc_140008F2B
0x140008e36  mov     edx, 5Ch ; '\'
0x140008e3b  cmp     r13, rbx
0x140008e3e  jz      short loc_140008E79
0x140008e40  cmp     [r13+0], dx
0x140008e45  jz      short loc_140008E4F
0x140008e47  cmp     word ptr [r13+0], 2Fh ; '/'
0x140008e4d  jnz     short loc_140008E79
0x140008e4f  sub     rbp, r12
0x140008e52  sar     rbp, 1
0x140008e55  cmp     [rdi+10h], rbp
0x140008e59  jb      loc_140008F43
0x140008e5f  mov     [rdi+10h], rbp
0x140008e63  cmp     qword ptr [rdi+18h], 7
0x140008e68  jbe     short loc_140008E6F
0x140008e6a  mov     rax, [rdi]
0x140008e6d  jmp     short loc_140008E72
0x140008e6f  mov     rax, rdi
0x140008e72  mov     [rax+rbp*2], r15w
0x140008e77  jmp     short loc_140008ED4
0x140008e79  mov     rax, [rsp+68h+arg_18]
0x140008e81  cmp     rbp, rax
0x140008e84  jnz     short loc_140008E92
0x140008e86  and     r14, 0FFFFFFFFFFFFFFFEh
0x140008e8a  cmp     r14, 6
0x140008e8e  jl      short loc_140008ED4
0x140008e90  jmp     short loc_140008E9F
0x140008e92  cmp     [rax-2], dx
0x140008e96  jz      short loc_140008ED4
0x140008e98  cmp     word ptr [rax-2], 2Fh ; '/'
0x140008e9d  jz      short loc_140008ED4
0x140008e9f  mov     rcx, [rdi+10h]
0x140008ea3  cmp     rcx, [rdi+18h]
0x140008ea7  jnb     short loc_140008EC9
0x140008ea9  lea     rax, [rcx+1]
0x140008ead  mov     [rdi+10h], rax
0x140008eb1  cmp     qword ptr [rdi+18h], 7
0x140008eb6  jbe     short loc_140008EBD
0x140008eb8  mov     rax, [rdi]
0x140008ebb  jmp     short loc_140008EC0
0x140008ebd  mov     rax, rdi
0x140008ec0  mov     dword ptr [rax+rcx*2], 5Ch ; '\'
0x140008ec7  jmp     short loc_140008ED4
0x140008ec9  mov     r9d, edx
0x140008ecc  mov     rcx, rdi; Src
0x140008ecf  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x140008ed4  mov     rcx, [rdi+10h]
0x140008ed8  sub     rbx, r13
0x140008edb  mov     rax, [rdi+18h]
0x140008edf  sar     rbx, 1
0x140008ee2  sub     rax, rcx
0x140008ee5  cmp     rbx, rax
0x140008ee8  ja      short loc_140008F18
0x140008eea  cmp     qword ptr [rdi+18h], 7
0x140008eef  lea     rbp, [rbx+rcx]
0x140008ef3  mov     [rdi+10h], rbp
0x140008ef7  jbe     short loc_140008EFE
0x140008ef9  mov     rsi, [rdi]
0x140008efc  jmp     short loc_140008F01
0x140008efe  mov     rsi, rdi
0x140008f01  lea     r8, [rbx+rbx]; Size
0x140008f05  mov     rdx, r13; Src
0x140008f08  lea     rcx, [rsi+rcx*2]; void *
0x140008f0c  call    memmove_0
0x140008f11  mov     [rsi+rbp*2], r15w
0x140008f16  jmp     short loc_140008F2B
0x140008f18  mov     r9, r13
0x140008f1b  mov     [rsp+68h+var_48], rbx; __int64
0x140008f20  mov     rdx, rbx
0x140008f23  mov     rcx, rdi; Src
0x140008f26  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x140008f2b  mov     rbx, [rsp+68h+arg_0]
0x140008f30  mov     rax, rdi
0x140008f33  add     rsp, 30h
0x140008f37  pop     r15
0x140008f39  pop     r14
0x140008f3b  pop     r13
0x140008f3d  pop     r12
0x140008f3f  pop     rdi
0x140008f40  pop     rsi
0x140008f41  pop     rbp
0x140008f42  retn
0x140008f43  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
