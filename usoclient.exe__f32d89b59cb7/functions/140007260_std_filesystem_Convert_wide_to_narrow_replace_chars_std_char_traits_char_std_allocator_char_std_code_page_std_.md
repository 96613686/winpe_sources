# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char> const &)

- ea: `0x140007260`
- end: `0x1400073b8`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `344`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009d9c`

## callees

- `0x14000186c`
- `0x140002c58`
- `0x140007260`
- `0x140007c18`
- `0x14000a22c`
- `0x14000a26c`

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
0x140007260  mov     rax, rsp
0x140007263  mov     [rax+10h], rbx
0x140007267  mov     [rax+18h], rbp
0x14000726b  mov     [rax+8], rcx
0x14000726f  push    rsi
0x140007270  push    rdi
0x140007271  push    r12
0x140007273  push    r14
0x140007275  push    r15
0x140007277  sub     rsp, 40h
0x14000727b  mov     ebp, edx
0x14000727d  mov     rsi, rcx
0x140007280  mov     dword ptr [rax-38h], 0
0x140007287  xorps   xmm0, xmm0
0x14000728a  movups  xmmword ptr [rcx], xmm0
0x14000728d  mov     qword ptr [rcx+10h], 0
0x140007295  mov     qword ptr [rcx+18h], 0Fh
0x14000729d  mov     byte ptr [rcx], 0
0x1400072a0  mov     dword ptr [rax-38h], 1
0x1400072a7  cmp     qword ptr [r8+8], 0
0x1400072ac  jz      loc_140007388
0x1400072b2  cmp     qword ptr [r8+8], 7FFFFFFFh
0x1400072ba  ja      loc_1400073AC
0x1400072c0  mov     r15d, [r8+8]
0x1400072c4  mov     r12, [r8]
0x1400072c7  mov     dword ptr [rax-48h], 0
0x1400072ce  xor     r9d, r9d; lpMultiByteStr
0x1400072d1  mov     r8d, r15d; cchWideChar
0x1400072d4  mov     rdx, r12; lpWideCharStr
0x1400072d7  mov     ecx, ebp; CodePage
0x1400072d9  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1400072de  mov     rbx, rax
0x1400072e1  mov     rcx, rax
0x1400072e4  shr     rcx, 20h
0x1400072e8  test    ecx, ecx
0x1400072ea  jnz     loc_1400073B2
0x1400072f0  mov     rdx, [rsi+10h]
0x1400072f4  movsxd  rcx, ebx
0x1400072f7  cmp     rcx, rdx
0x1400072fa  ja      short loc_140007315
0x1400072fc  mov     [rsi+10h], rcx
0x140007300  cmp     qword ptr [rsi+18h], 0Fh
0x140007305  jbe     short loc_14000730C
0x140007307  mov     rax, [rsi]
0x14000730a  jmp     short loc_14000730F
0x14000730c  mov     rax, rsi
0x14000730f  mov     byte ptr [rcx+rax], 0
0x140007313  jmp     short loc_140007360
0x140007315  mov     r14, rcx
0x140007318  sub     r14, rdx
0x14000731b  mov     rax, [rsi+18h]
0x14000731f  sub     rax, rdx
0x140007322  cmp     r14, rax
0x140007325  ja      short loc_140007352
0x140007327  mov     [rsi+10h], rcx
0x14000732b  cmp     qword ptr [rsi+18h], 0Fh
0x140007330  jbe     short loc_140007337
0x140007332  mov     rax, [rsi]
0x140007335  jmp     short loc_14000733A
0x140007337  mov     rax, rsi
0x14000733a  lea     rdi, [rdx+rax]
0x14000733e  mov     r8, r14; Size
0x140007341  xor     edx, edx; Val
0x140007343  mov     rcx, rdi; void *
0x140007346  call    memset_0
0x14000734b  mov     byte ptr [r14+rdi], 0
0x140007350  jmp     short loc_140007360
0x140007352  mov     r9, r14
0x140007355  mov     rdx, r14
0x140007358  mov     rcx, rsi; Src
0x14000735b  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x140007360  cmp     qword ptr [rsi+18h], 0Fh
0x140007365  jbe     short loc_14000736C
0x140007367  mov     r9, [rsi]
0x14000736a  jmp     short loc_14000736F
0x14000736c  mov     r9, rsi; lpMultiByteStr
0x14000736f  mov     [rsp+68h+var_48], ebx; int
0x140007373  mov     r8d, r15d; cchWideChar
0x140007376  mov     rdx, r12; lpWideCharStr
0x140007379  mov     ecx, ebp; CodePage
0x14000737b  call    __std_fs_convert_wide_to_narrow_replace_chars
0x140007380  shr     rax, 20h
0x140007384  test    eax, eax
0x140007386  jnz     short loc_1400073A4
0x140007388  mov     rax, rsi
0x14000738b  lea     r11, [rsp+68h+var_28]
0x140007390  mov     rbx, [r11+38h]
0x140007394  mov     rbp, [r11+40h]
0x140007398  mov     rsp, r11
0x14000739b  pop     r15
0x14000739d  pop     r14
0x14000739f  pop     r12
0x1400073a1  pop     rdi
0x1400073a2  pop     rsi
0x1400073a3  retn
0x1400073a4  mov     ecx, eax
0x1400073a6  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x1400073ac  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x1400073b2  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
