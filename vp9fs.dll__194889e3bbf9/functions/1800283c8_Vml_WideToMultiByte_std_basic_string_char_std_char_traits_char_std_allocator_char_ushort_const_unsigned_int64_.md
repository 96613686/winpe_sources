# Vml::WideToMultiByte(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,ushort const *,unsigned __int64,uint)

- ea: `0x1800283c8`
- end: `0x18002853e`
- name: `?WideToMultiByte@Vml@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG_KI@Z`
- size: `374`
- prototype: `__int64 __fastcall(void *Src, LPCWCH lpWideCharStr, int cchWideChar)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024e50`
- `0x180024f90`
- `0x180025570`
- `0x180027370`
- `0x1800277f0`
- `0x180028384`

## callees

- `0x180004c80`
- `0x18000ae8c`
- `0x180021d50`
- `0x180023ce0`
- `0x1800283c8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002843e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800284f2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002843e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800284f2`

## string_xrefs

- `0x180028526`: `onecore\internal\vm\inc\private\common\vml\VmString.h`

## pseudocode

```c
void __fastcall Vml::WideToMultiByte(_QWORD *Src, LPCWCH lpWideCharStr, unsigned __int64 cchWideChar)
{
  int v3; // ebp
  _QWORD *v5; // rdi
  int v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 cbMultiByte; // r14
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  unsigned __int64 v13; // rsi
  bool v14; // cc
  _QWORD *v15; // rax
  char *v16; // rbx
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int lpMultiByteStr; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = cchWideChar;
  v5 = Src;
  if ( cchWideChar )
  {
    if ( cchWideChar > 0x7FFFFFFF )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecore\\internal\\vm\\inc\\private\\common\\vml\\VmString.h",
        (const char *)0x6F,
        lpMultiByteStr);
    v6 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, cchWideChar, 0, 0, 0, 0);
    cbMultiByte = v6;
    if ( !v6 )
      wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x1A9, v7, v8);
    v10 = v5[2];
    v11 = v6;
    if ( v6 > v10 )
    {
      v13 = v6 - v10;
      if ( v13 > v5[3] - v10 )
      {
        std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(v5);
      }
      else
      {
        v14 = v5[3] <= 0xFu;
        v5[2] = v6;
        if ( v14 )
          v15 = v5;
        else
          v15 = (_QWORD *)*v5;
        v16 = (char *)v15 + v10;
        memset_0((char *)v15 + v10, 0, v11 - v10);
        v16[v13] = 0;
      }
    }
    else
    {
      v5[2] = v6;
      if ( v5[3] <= 0xFu )
        v12 = v5;
      else
        v12 = (_QWORD *)*v5;
      *((_BYTE *)v12 + cbMultiByte) = 0;
    }
    if ( v5[3] > 0xFu )
      v5 = (_QWORD *)*v5;
    if ( !WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v3, (LPSTR)v5, cbMultiByte, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x1B8, v17, v18);
  }
  else
  {
    Src[2] = 0;
    if ( Src[3] > 0xFu )
      v5 = (_QWORD *)*Src;
    *(_BYTE *)v5 = 0;
  }
}

```

## disassembly

```asm
0x1800283c8  push    rbx
0x1800283ca  push    rbp
0x1800283cb  push    rsi
0x1800283cc  push    rdi
0x1800283cd  push    r14
0x1800283cf  push    r15
0x1800283d1  sub     rsp, 48h
0x1800283d5  mov     rbp, r8
0x1800283d8  mov     r15, rdx
0x1800283db  mov     rdi, rcx
0x1800283de  test    r8, r8
0x1800283e1  jnz     short loc_180028401
0x1800283e3  mov     [rcx+10h], r8
0x1800283e7  cmp     qword ptr [rcx+18h], 0Fh
0x1800283ec  jbe     short loc_1800283F1
0x1800283ee  mov     rdi, [rcx]
0x1800283f1  mov     byte ptr [rdi], 0
0x1800283f4  add     rsp, 48h
0x1800283f8  pop     r15
0x1800283fa  pop     r14
0x1800283fc  pop     rdi
0x1800283fd  pop     rsi
0x1800283fe  pop     rbp
0x1800283ff  pop     rbx
0x180028400  retn
0x180028401  cmp     rbp, 7FFFFFFFh
0x180028408  ja      loc_180028521
0x18002840e  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180028417  mov     r9d, ebp; cchWideChar
0x18002841a  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180028423  mov     r8, r15; lpWideCharStr
0x180028426  mov     [rsp+78h+cbMultiByte], 0; cbMultiByte
0x18002842e  xor     edx, edx; dwFlags
0x180028430  mov     ecx, 0FDE9h; CodePage
0x180028435  mov     [rsp+78h+lpMultiByteStr], 0; lpMultiByteStr
0x18002843e  call    cs:__imp_WideCharToMultiByte
0x180028444  movsxd  r14, eax
0x180028447  test    eax, eax
0x180028449  jz      loc_180028501
0x18002844f  mov     rdx, [rdi+10h]
0x180028453  mov     rcx, r14
0x180028456  cmp     r14, rdx
0x180028459  ja      short loc_180028475
0x18002845b  mov     [rdi+10h], rcx
0x18002845f  cmp     qword ptr [rdi+18h], 0Fh
0x180028464  jbe     short loc_18002846B
0x180028466  mov     rax, [rdi]
0x180028469  jmp     short loc_18002846E
0x18002846b  mov     rax, rdi
0x18002846e  mov     byte ptr [r14+rax], 0
0x180028473  jmp     short loc_1800284BF
0x180028475  mov     rax, [rdi+18h]
0x180028479  mov     rsi, rcx
0x18002847c  sub     rsi, rdx
0x18002847f  sub     rax, rdx
0x180028482  cmp     rsi, rax
0x180028485  ja      short loc_1800284B1
0x180028487  cmp     qword ptr [rdi+18h], 0Fh
0x18002848c  mov     [rdi+10h], rcx
0x180028490  jbe     short loc_180028497
0x180028492  mov     rax, [rdi]
0x180028495  jmp     short loc_18002849A
0x180028497  mov     rax, rdi
0x18002849a  lea     rbx, [rdx+rax]
0x18002849e  mov     r8, rsi; Size
0x1800284a1  mov     rcx, rbx; void *
0x1800284a4  xor     edx, edx; Val
0x1800284a6  call    memset_0
0x1800284ab  mov     byte ptr [rsi+rbx], 0
0x1800284af  jmp     short loc_1800284BF
0x1800284b1  mov     r9, rsi
0x1800284b4  mov     rdx, rsi
0x1800284b7  mov     rcx, rdi; Src
0x1800284ba  call    ??$_Reallocate_grow_by@V_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_e1befb086ad3257e3f042a63030725f7_@@_KD@Z; std::string::_Reallocate_grow_by<_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char>(unsigned __int64,_lambda_e1befb086ad3257e3f042a63030725f7_,unsigned __int64,char)
0x1800284bf  cmp     qword ptr [rdi+18h], 0Fh
0x1800284c4  jbe     short loc_1800284C9
0x1800284c6  mov     rdi, [rdi]
0x1800284c9  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800284d2  mov     r9d, ebp; cchWideChar
0x1800284d5  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x1800284de  mov     r8, r15; lpWideCharStr
0x1800284e1  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x1800284e6  xor     edx, edx; dwFlags
0x1800284e8  mov     ecx, 0FDE9h; CodePage
0x1800284ed  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800284f2  call    cs:__imp_WideCharToMultiByte
0x1800284f8  test    eax, eax
0x1800284fa  jz      short loc_180028511
0x1800284fc  jmp     loc_1800283F4
0x180028501  mov     rcx, [rsp+78h]; this
0x180028506  mov     edx, 1A9h; void *
0x18002850b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180028511  mov     rcx, [rsp+78h]; this
0x180028516  mov     edx, 1B8h; void *
0x18002851b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180028521  mov     rcx, [rsp+78h]; this
0x180028526  lea     r8, aOnecoreInterna_4; "onecore\\internal\\vm\\inc\\private\\co"...
0x18002852d  mov     r9d, 6Fh ; 'o'; char *
0x180028533  mov     edx, 197h; void *
0x180028538  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
