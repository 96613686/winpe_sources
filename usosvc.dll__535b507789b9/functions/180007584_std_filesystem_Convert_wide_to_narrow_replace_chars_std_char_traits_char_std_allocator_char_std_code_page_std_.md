# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char> const &)

- ea: `0x180007584`
- end: `0x1800076dc`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `344`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009e38`

## callees

- `0x180001d50`
- `0x180003198`
- `0x180007584`
- `0x180007f3c`
- `0x18000a2c8`
- `0x18000a308`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
        _QWORD *Src,
        UINT CodePage,
        __int64 a3)
{
  int v5; // r15d
  const WCHAR *v6; // r12
  __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  _QWORD *v9; // rax
  unsigned __int64 v10; // r14
  _QWORD *v11; // rax
  char *v12; // rdi
  CHAR *v13; // r9
  unsigned __int64 v14; // rax

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  if ( *(_QWORD *)(a3 + 8) )
  {
    if ( *(_QWORD *)(a3 + 8) > 0x7FFFFFFFu )
      std::_Throw_system_error();
    v5 = *(_DWORD *)(a3 + 8);
    v6 = *(const WCHAR **)a3;
    v7 = _std_fs_convert_wide_to_narrow_replace_chars(CodePage, *(LPCWCH *)a3, v5, 0, 0);
    if ( HIDWORD(v7) )
      ((void (__noreturn *)(void))std::_Throw_system_error_from_std_win_error)();
    v8 = Src[2];
    if ( (int)v7 > v8 )
    {
      v10 = (int)v7 - v8;
      if ( v10 > Src[3] - v8 )
      {
        std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(Src);
      }
      else
      {
        Src[2] = (int)v7;
        if ( Src[3] <= 0xFu )
          v11 = Src;
        else
          v11 = (_QWORD *)*Src;
        v12 = (char *)v11 + v8;
        memset_0((char *)v11 + v8, 0, (int)v7 - v8);
        v12[v10] = 0;
      }
    }
    else
    {
      Src[2] = (int)v7;
      if ( Src[3] <= 0xFu )
        v9 = Src;
      else
        v9 = (_QWORD *)*Src;
      *((_BYTE *)v9 + (int)v7) = 0;
    }
    if ( Src[3] <= 0xFu )
      v13 = (CHAR *)Src;
    else
      v13 = (CHAR *)*Src;
    v14 = (unsigned __int64)_std_fs_convert_wide_to_narrow_replace_chars(CodePage, v6, v5, v13, v7) >> 32;
    if ( (_DWORD)v14 )
      std::_Throw_system_error_from_std_win_error((unsigned int)v14);
  }
  return Src;
}

```

## disassembly

```asm
0x180007584  mov     rax, rsp
0x180007587  mov     [rax+10h], rbx
0x18000758b  mov     [rax+18h], rbp
0x18000758f  mov     [rax+8], rcx
0x180007593  push    rsi
0x180007594  push    rdi
0x180007595  push    r12
0x180007597  push    r14
0x180007599  push    r15
0x18000759b  sub     rsp, 40h
0x18000759f  mov     ebp, edx
0x1800075a1  mov     rsi, rcx
0x1800075a4  mov     dword ptr [rax-38h], 0
0x1800075ab  xorps   xmm0, xmm0
0x1800075ae  movups  xmmword ptr [rcx], xmm0
0x1800075b1  mov     qword ptr [rcx+10h], 0
0x1800075b9  mov     qword ptr [rcx+18h], 0Fh
0x1800075c1  mov     byte ptr [rcx], 0
0x1800075c4  mov     dword ptr [rax-38h], 1
0x1800075cb  cmp     qword ptr [r8+8], 0
0x1800075d0  jz      loc_1800076AC
0x1800075d6  cmp     qword ptr [r8+8], 7FFFFFFFh
0x1800075de  ja      loc_1800076D0
0x1800075e4  mov     r15d, [r8+8]
0x1800075e8  mov     r12, [r8]
0x1800075eb  mov     dword ptr [rax-48h], 0
0x1800075f2  xor     r9d, r9d; lpMultiByteStr
0x1800075f5  mov     r8d, r15d; cchWideChar
0x1800075f8  mov     rdx, r12; lpWideCharStr
0x1800075fb  mov     ecx, ebp; CodePage
0x1800075fd  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180007602  mov     rbx, rax
0x180007605  mov     rcx, rax
0x180007608  shr     rcx, 20h
0x18000760c  test    ecx, ecx
0x18000760e  jnz     loc_1800076D6
0x180007614  mov     rdx, [rsi+10h]
0x180007618  movsxd  rcx, ebx
0x18000761b  cmp     rcx, rdx
0x18000761e  ja      short loc_180007639
0x180007620  mov     [rsi+10h], rcx
0x180007624  cmp     qword ptr [rsi+18h], 0Fh
0x180007629  jbe     short loc_180007630
0x18000762b  mov     rax, [rsi]
0x18000762e  jmp     short loc_180007633
0x180007630  mov     rax, rsi
0x180007633  mov     byte ptr [rcx+rax], 0
0x180007637  jmp     short loc_180007684
0x180007639  mov     r14, rcx
0x18000763c  sub     r14, rdx
0x18000763f  mov     rax, [rsi+18h]
0x180007643  sub     rax, rdx
0x180007646  cmp     r14, rax
0x180007649  ja      short loc_180007676
0x18000764b  mov     [rsi+10h], rcx
0x18000764f  cmp     qword ptr [rsi+18h], 0Fh
0x180007654  jbe     short loc_18000765B
0x180007656  mov     rax, [rsi]
0x180007659  jmp     short loc_18000765E
0x18000765b  mov     rax, rsi
0x18000765e  lea     rdi, [rdx+rax]
0x180007662  mov     r8, r14; Size
0x180007665  xor     edx, edx; Val
0x180007667  mov     rcx, rdi; void *
0x18000766a  call    memset_0
0x18000766f  mov     byte ptr [r14+rdi], 0
0x180007674  jmp     short loc_180007684
0x180007676  mov     r9, r14
0x180007679  mov     rdx, r14
0x18000767c  mov     rcx, rsi; Src
0x18000767f  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x180007684  cmp     qword ptr [rsi+18h], 0Fh
0x180007689  jbe     short loc_180007690
0x18000768b  mov     r9, [rsi]
0x18000768e  jmp     short loc_180007693
0x180007690  mov     r9, rsi; lpMultiByteStr
0x180007693  mov     [rsp+68h+var_48], ebx; int
0x180007697  mov     r8d, r15d; cchWideChar
0x18000769a  mov     rdx, r12; lpWideCharStr
0x18000769d  mov     ecx, ebp; CodePage
0x18000769f  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1800076a4  shr     rax, 20h
0x1800076a8  test    eax, eax
0x1800076aa  jnz     short loc_1800076C8
0x1800076ac  mov     rax, rsi
0x1800076af  lea     r11, [rsp+68h+var_28]
0x1800076b4  mov     rbx, [r11+38h]
0x1800076b8  mov     rbp, [r11+40h]
0x1800076bc  mov     rsp, r11
0x1800076bf  pop     r15
0x1800076c1  pop     r14
0x1800076c3  pop     r12
0x1800076c5  pop     rdi
0x1800076c6  pop     rsi
0x1800076c7  retn
0x1800076c8  mov     ecx, eax
0x1800076ca  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x1800076d0  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800076d6  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
