# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char> const &)

- ea: `0x140007240`
- end: `0x140007398`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `344`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009dcc`

## callees

- `0x14000186c`
- `0x140002c38`
- `0x140007240`
- `0x140007bf8`
- `0x14000a25c`
- `0x14000a29c`

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
0x140007240  mov     rax, rsp
0x140007243  mov     [rax+10h], rbx
0x140007247  mov     [rax+18h], rbp
0x14000724b  mov     [rax+8], rcx
0x14000724f  push    rsi
0x140007250  push    rdi
0x140007251  push    r12
0x140007253  push    r14
0x140007255  push    r15
0x140007257  sub     rsp, 40h
0x14000725b  mov     ebp, edx
0x14000725d  mov     rsi, rcx
0x140007260  mov     dword ptr [rax-38h], 0
0x140007267  xorps   xmm0, xmm0
0x14000726a  movups  xmmword ptr [rcx], xmm0
0x14000726d  mov     qword ptr [rcx+10h], 0
0x140007275  mov     qword ptr [rcx+18h], 0Fh
0x14000727d  mov     byte ptr [rcx], 0
0x140007280  mov     dword ptr [rax-38h], 1
0x140007287  cmp     qword ptr [r8+8], 0
0x14000728c  jz      loc_140007368
0x140007292  cmp     qword ptr [r8+8], 7FFFFFFFh
0x14000729a  ja      loc_14000738C
0x1400072a0  mov     r15d, [r8+8]
0x1400072a4  mov     r12, [r8]
0x1400072a7  mov     dword ptr [rax-48h], 0
0x1400072ae  xor     r9d, r9d; lpMultiByteStr
0x1400072b1  mov     r8d, r15d; cchWideChar
0x1400072b4  mov     rdx, r12; lpWideCharStr
0x1400072b7  mov     ecx, ebp; CodePage
0x1400072b9  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1400072be  mov     rbx, rax
0x1400072c1  mov     rcx, rax
0x1400072c4  shr     rcx, 20h
0x1400072c8  test    ecx, ecx
0x1400072ca  jnz     loc_140007392
0x1400072d0  mov     rdx, [rsi+10h]
0x1400072d4  movsxd  rcx, ebx
0x1400072d7  cmp     rcx, rdx
0x1400072da  ja      short loc_1400072F5
0x1400072dc  mov     [rsi+10h], rcx
0x1400072e0  cmp     qword ptr [rsi+18h], 0Fh
0x1400072e5  jbe     short loc_1400072EC
0x1400072e7  mov     rax, [rsi]
0x1400072ea  jmp     short loc_1400072EF
0x1400072ec  mov     rax, rsi
0x1400072ef  mov     byte ptr [rcx+rax], 0
0x1400072f3  jmp     short loc_140007340
0x1400072f5  mov     r14, rcx
0x1400072f8  sub     r14, rdx
0x1400072fb  mov     rax, [rsi+18h]
0x1400072ff  sub     rax, rdx
0x140007302  cmp     r14, rax
0x140007305  ja      short loc_140007332
0x140007307  mov     [rsi+10h], rcx
0x14000730b  cmp     qword ptr [rsi+18h], 0Fh
0x140007310  jbe     short loc_140007317
0x140007312  mov     rax, [rsi]
0x140007315  jmp     short loc_14000731A
0x140007317  mov     rax, rsi
0x14000731a  lea     rdi, [rdx+rax]
0x14000731e  mov     r8, r14; Size
0x140007321  xor     edx, edx; Val
0x140007323  mov     rcx, rdi; void *
0x140007326  call    memset_0
0x14000732b  mov     byte ptr [r14+rdi], 0
0x140007330  jmp     short loc_140007340
0x140007332  mov     r9, r14
0x140007335  mov     rdx, r14
0x140007338  mov     rcx, rsi; Src
0x14000733b  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x140007340  cmp     qword ptr [rsi+18h], 0Fh
0x140007345  jbe     short loc_14000734C
0x140007347  mov     r9, [rsi]
0x14000734a  jmp     short loc_14000734F
0x14000734c  mov     r9, rsi; lpMultiByteStr
0x14000734f  mov     [rsp+68h+var_48], ebx; int
0x140007353  mov     r8d, r15d; cchWideChar
0x140007356  mov     rdx, r12; lpWideCharStr
0x140007359  mov     ecx, ebp; CodePage
0x14000735b  call    __std_fs_convert_wide_to_narrow_replace_chars
0x140007360  shr     rax, 20h
0x140007364  test    eax, eax
0x140007366  jnz     short loc_140007384
0x140007368  mov     rax, rsi
0x14000736b  lea     r11, [rsp+68h+var_28]
0x140007370  mov     rbx, [r11+38h]
0x140007374  mov     rbp, [r11+40h]
0x140007378  mov     rsp, r11
0x14000737b  pop     r15
0x14000737d  pop     r14
0x14000737f  pop     r12
0x140007381  pop     rdi
0x140007382  pop     rsi
0x140007383  retn
0x140007384  mov     ecx, eax
0x140007386  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x14000738c  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x140007392  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
