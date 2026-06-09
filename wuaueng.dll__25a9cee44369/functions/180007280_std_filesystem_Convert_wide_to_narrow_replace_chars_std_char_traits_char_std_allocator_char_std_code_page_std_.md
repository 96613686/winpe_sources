# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::allocator<char> const &)

- ea: `0x180007280`
- end: `0x1800073d4`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `340`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800077f8`

## callees

- `0x180006cac`
- `0x180006cec`
- `0x180007240`
- `0x180007280`
- `0x18000f220`
- `0x180015a30`

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
0x180007280  mov     rax, rsp
0x180007283  mov     [rax+10h], rbx
0x180007287  mov     [rax+18h], rbp
0x18000728b  mov     [rax+8], rcx
0x18000728f  push    rsi
0x180007290  push    rdi
0x180007291  push    r12
0x180007293  push    r14
0x180007295  push    r15
0x180007297  sub     rsp, 40h
0x18000729b  mov     r14d, edx
0x18000729e  mov     rsi, rcx
0x1800072a1  mov     dword ptr [rax-38h], 0
0x1800072a8  xorps   xmm0, xmm0
0x1800072ab  movups  xmmword ptr [rcx], xmm0
0x1800072ae  mov     qword ptr [rcx+10h], 0
0x1800072b6  mov     qword ptr [rcx+18h], 0Fh
0x1800072be  mov     byte ptr [rcx], 0
0x1800072c1  mov     dword ptr [rax-38h], 1
0x1800072c8  cmp     qword ptr [r8+8], 0
0x1800072cd  jz      loc_1800073A4
0x1800072d3  cmp     qword ptr [r8+8], 7FFFFFFFh
0x1800072db  ja      loc_1800073C8
0x1800072e1  mov     r15d, [r8+8]
0x1800072e5  mov     r12, [r8]
0x1800072e8  mov     dword ptr [rax-48h], 0
0x1800072ef  xor     r9d, r9d; lpMultiByteStr
0x1800072f2  mov     r8d, r15d; cchWideChar
0x1800072f5  mov     rdx, r12; lpWideCharStr
0x1800072f8  mov     ecx, r14d; CodePage
0x1800072fb  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180007300  mov     rbx, rax
0x180007303  mov     rcx, rax
0x180007306  shr     rcx, 20h
0x18000730a  test    ecx, ecx
0x18000730c  jnz     loc_1800073CE
0x180007312  mov     rdx, [rsi+10h]
0x180007316  movsxd  rcx, ebx
0x180007319  cmp     rcx, rdx
0x18000731c  ja      short loc_180007335
0x18000731e  mov     [rsi+10h], rcx
0x180007322  mov     rax, rsi
0x180007325  cmp     qword ptr [rsi+18h], 0Fh
0x18000732a  jbe     short loc_18000732F
0x18000732c  mov     rax, [rsi]
0x18000732f  mov     byte ptr [rcx+rax], 0
0x180007333  jmp     short loc_18000737D
0x180007335  mov     rbp, rcx
0x180007338  sub     rbp, rdx
0x18000733b  mov     rax, [rsi+18h]
0x18000733f  sub     rax, rdx
0x180007342  cmp     rbp, rax
0x180007345  ja      short loc_18000736F
0x180007347  mov     [rsi+10h], rcx
0x18000734b  mov     rax, rsi
0x18000734e  cmp     qword ptr [rsi+18h], 0Fh
0x180007353  jbe     short loc_180007358
0x180007355  mov     rax, [rsi]
0x180007358  lea     rdi, [rax+rdx]
0x18000735c  mov     r8, rbp; Size
0x18000735f  xor     edx, edx; Val
0x180007361  mov     rcx, rdi; void *
0x180007364  call    memset
0x180007369  mov     byte ptr [rdi+rbp], 0
0x18000736d  jmp     short loc_18000737D
0x18000736f  mov     r9, rbp
0x180007372  mov     rdx, rbp
0x180007375  mov     rcx, rsi; Src
0x180007378  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x18000737d  mov     r9, rsi
0x180007380  cmp     qword ptr [rsi+18h], 0Fh
0x180007385  jbe     short loc_18000738A
0x180007387  mov     r9, [rsi]; lpMultiByteStr
0x18000738a  mov     [rsp+68h+var_48], ebx; int
0x18000738e  mov     r8d, r15d; cchWideChar
0x180007391  mov     rdx, r12; lpWideCharStr
0x180007394  mov     ecx, r14d; CodePage
0x180007397  call    __std_fs_convert_wide_to_narrow_replace_chars
0x18000739c  shr     rax, 20h
0x1800073a0  test    eax, eax
0x1800073a2  jnz     short loc_1800073C0
0x1800073a4  mov     rax, rsi
0x1800073a7  lea     r11, [rsp+68h+var_28]
0x1800073ac  mov     rbx, [r11+38h]
0x1800073b0  mov     rbp, [r11+40h]
0x1800073b4  mov     rsp, r11
0x1800073b7  pop     r15
0x1800073b9  pop     r14
0x1800073bb  pop     r12
0x1800073bd  pop     rdi
0x1800073be  pop     rsi
0x1800073bf  retn
0x1800073c0  mov     ecx, eax
0x1800073c2  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x1800073c8  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1800073ce  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
