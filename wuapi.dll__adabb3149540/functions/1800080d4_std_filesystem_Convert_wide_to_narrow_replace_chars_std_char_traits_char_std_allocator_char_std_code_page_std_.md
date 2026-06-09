# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::allocator<char> const &)

- ea: `0x1800080d4`
- end: `0x180008228`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `340`
- prototype: `__int64 __fastcall(void *Src, UINT CodePage)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006518`

## callees

- `0x180005a98`
- `0x180005e1c`
- `0x1800080d4`
- `0x180009614`
- `0x18000f270`
- `0x180015a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int64 v10; // rbp
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
        v11 = Src;
        if ( Src[3] > 0xFu )
          v11 = (_QWORD *)*Src;
        v12 = (char *)v11 + v8;
        memset((char *)v11 + v8, 0, (int)v7 - v8);
        v12[v10] = 0;
      }
    }
    else
    {
      Src[2] = (int)v7;
      v9 = Src;
      if ( Src[3] > 0xFu )
        v9 = (_QWORD *)*Src;
      *((_BYTE *)v9 + (int)v7) = 0;
    }
    v13 = (CHAR *)Src;
    if ( Src[3] > 0xFu )
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
0x1800080d4  mov     rax, rsp
0x1800080d7  mov     [rax+10h], rbx
0x1800080db  mov     [rax+18h], rbp
0x1800080df  mov     [rax+8], rcx
0x1800080e3  push    rsi
0x1800080e4  push    rdi
0x1800080e5  push    r12
0x1800080e7  push    r14
0x1800080e9  push    r15
0x1800080eb  sub     rsp, 40h
0x1800080ef  mov     r14d, edx
0x1800080f2  mov     rsi, rcx
0x1800080f5  mov     dword ptr [rax-38h], 0
0x1800080fc  xorps   xmm0, xmm0
0x1800080ff  movups  xmmword ptr [rcx], xmm0
0x180008102  mov     qword ptr [rcx+10h], 0
0x18000810a  mov     qword ptr [rcx+18h], 0Fh
0x180008112  mov     byte ptr [rcx], 0
0x180008115  mov     dword ptr [rax-38h], 1
0x18000811c  cmp     qword ptr [r8+8], 0
0x180008121  jz      loc_1800081F8
0x180008127  cmp     qword ptr [r8+8], 7FFFFFFFh
0x18000812f  ja      loc_18000821C
0x180008135  mov     r15d, [r8+8]
0x180008139  mov     r12, [r8]
0x18000813c  mov     dword ptr [rax-48h], 0
0x180008143  xor     r9d, r9d; lpMultiByteStr
0x180008146  mov     r8d, r15d; cchWideChar
0x180008149  mov     rdx, r12; lpWideCharStr
0x18000814c  mov     ecx, r14d; CodePage
0x18000814f  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180008154  mov     rbx, rax
0x180008157  mov     rcx, rax
0x18000815a  shr     rcx, 20h
0x18000815e  test    ecx, ecx
0x180008160  jnz     loc_180008222
0x180008166  mov     rdx, [rsi+10h]
0x18000816a  movsxd  rcx, ebx
0x18000816d  cmp     rcx, rdx
0x180008170  ja      short loc_180008189
0x180008172  mov     [rsi+10h], rcx
0x180008176  mov     rax, rsi
0x180008179  cmp     qword ptr [rsi+18h], 0Fh
0x18000817e  jbe     short loc_180008183
0x180008180  mov     rax, [rsi]
0x180008183  mov     byte ptr [rcx+rax], 0
0x180008187  jmp     short loc_1800081D1
0x180008189  mov     rbp, rcx
0x18000818c  sub     rbp, rdx
0x18000818f  mov     rax, [rsi+18h]
0x180008193  sub     rax, rdx
0x180008196  cmp     rbp, rax
0x180008199  ja      short loc_1800081C3
0x18000819b  mov     [rsi+10h], rcx
0x18000819f  mov     rax, rsi
0x1800081a2  cmp     qword ptr [rsi+18h], 0Fh
0x1800081a7  jbe     short loc_1800081AC
0x1800081a9  mov     rax, [rsi]
0x1800081ac  lea     rdi, [rax+rdx]
0x1800081b0  mov     r8, rbp; Size
0x1800081b3  xor     edx, edx; Val
0x1800081b5  mov     rcx, rdi; void *
0x1800081b8  call    memset
0x1800081bd  mov     byte ptr [rdi+rbp], 0
0x1800081c1  jmp     short loc_1800081D1
0x1800081c3  mov     r9, rbp
0x1800081c6  mov     rdx, rbp
0x1800081c9  mov     rcx, rsi; Src
0x1800081cc  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x1800081d1  mov     r9, rsi
0x1800081d4  cmp     qword ptr [rsi+18h], 0Fh
0x1800081d9  jbe     short loc_1800081DE
0x1800081db  mov     r9, [rsi]; lpMultiByteStr
0x1800081de  mov     [rsp+68h+var_48], ebx; int
0x1800081e2  mov     r8d, r15d; cchWideChar
0x1800081e5  mov     rdx, r12; lpWideCharStr
0x1800081e8  mov     ecx, r14d; CodePage
0x1800081eb  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1800081f0  shr     rax, 20h
0x1800081f4  test    eax, eax
0x1800081f6  jnz     short loc_180008214
0x1800081f8  mov     rax, rsi
0x1800081fb  lea     r11, [rsp+68h+var_28]
0x180008200  mov     rbx, [r11+38h]
0x180008204  mov     rbp, [r11+40h]
0x180008208  mov     rsp, r11
0x18000820b  pop     r15
0x18000820d  pop     r14
0x18000820f  pop     r12
0x180008211  pop     rdi
0x180008212  pop     rsi
0x180008213  retn
0x180008214  mov     ecx, eax
0x180008216  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x18000821c  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180008222  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
