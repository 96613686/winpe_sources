# Vml::MultiByteToWide(char const *,unsigned __int64,uint)

- ea: `0x18001ff4c`
- end: `0x1800200d5`
- name: `?MultiByteToWide@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KI@Z`
- size: `393`
- prototype: `__int64 __fastcall(void *Src, LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e1e0`
- `0x18001e5f0`
- `0x1800266a4`

## callees

- `0x18000ae8c`
- `0x18001d458`
- `0x18001ff4c`
- `0x180021d50`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ffdf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180020089`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ffdf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180020089`

## string_xrefs

- `0x1800200c3`: `onecore\internal\vm\inc\private\common\vml\VmString.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Vml::MultiByteToWide(_QWORD *Src, LPCCH lpMultiByteStr, unsigned __int64 cbMultiByte)
{
  int v3; // esi
  int v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  int cchWideChar; // ebp
  unsigned __int64 v11; // rdi
  _QWORD *v12; // rcx
  unsigned __int64 v13; // rcx
  _QWORD *v14; // r8
  _WORD *v15; // rdi
  WCHAR *v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int lpWideCharStr; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = cbMultiByte;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 7;
  *(_WORD *)Src = 0;
  if ( cbMultiByte )
  {
    if ( cbMultiByte > 0x7FFFFFFF )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"onecore\\internal\\vm\\inc\\private\\common\\vml\\VmString.h",
        (const char *)0x6F,
        lpWideCharStr);
    v7 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, cbMultiByte, 0, 0);
    cchWideChar = v7;
    if ( !v7 )
      wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x2F7, v8, v9);
    v11 = Src[2];
    if ( v7 > v11 )
    {
      v13 = v7 - v11;
      if ( v13 > Src[3] - v11 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
      }
      else
      {
        Src[2] = v7;
        if ( Src[3] <= 7u )
          v14 = Src;
        else
          v14 = (_QWORD *)*Src;
        v15 = (_WORD *)v14 + v11;
        if ( v13 )
        {
          while ( v13 )
          {
            *v15++ = 0;
            --v13;
          }
        }
        *((_WORD *)v14 + v7) = 0;
      }
    }
    else
    {
      Src[2] = v7;
      if ( Src[3] <= 7u )
        v12 = Src;
      else
        v12 = (_QWORD *)*Src;
      *((_WORD *)v12 + v7) = 0;
    }
    if ( Src[3] <= 7u )
      v16 = (WCHAR *)Src;
    else
      v16 = (WCHAR *)*Src;
    if ( !MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v3, v16, cchWideChar) )
      wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x305, v17, v18);
  }
  else
  {
    *(_WORD *)Src = 0;
  }
  return Src;
}

```

## disassembly

```asm
0x18001ff4c  mov     rax, rsp
0x18001ff4f  mov     [rax+10h], rbx
0x18001ff53  mov     [rax+18h], rbp
0x18001ff57  mov     [rax+8], rcx
0x18001ff5b  push    rsi
0x18001ff5c  push    rdi
0x18001ff5d  push    r14
0x18001ff5f  sub     rsp, 40h
0x18001ff63  mov     rsi, r8
0x18001ff66  mov     r14, rdx
0x18001ff69  mov     rbx, rcx
0x18001ff6c  mov     dword ptr [rax-28h], 0
0x18001ff73  xorps   xmm0, xmm0
0x18001ff76  movups  xmmword ptr [rcx], xmm0
0x18001ff79  mov     qword ptr [rcx+10h], 0
0x18001ff81  mov     qword ptr [rcx+18h], 7
0x18001ff89  xor     eax, eax
0x18001ff8b  mov     [rcx], ax
0x18001ff8e  mov     [rsp+58h+var_28], 1
0x18001ff96  test    r8, r8
0x18001ff99  jnz     short loc_18001FFB4
0x18001ff9b  mov     [rcx], ax
0x18001ff9e  mov     rax, rbx
0x18001ffa1  mov     rbx, [rsp+58h+arg_8]
0x18001ffa6  mov     rbp, [rsp+58h+arg_10]
0x18001ffab  add     rsp, 40h
0x18001ffaf  pop     r14
0x18001ffb1  pop     rdi
0x18001ffb2  pop     rsi
0x18001ffb3  retn
0x18001ffb4  cmp     rsi, 7FFFFFFFh
0x18001ffbb  ja      loc_1800200B8
0x18001ffc1  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x18001ffc9  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x18001ffd2  mov     r9d, esi; cbMultiByte
0x18001ffd5  mov     r8, r14; lpMultiByteStr
0x18001ffd8  xor     edx, edx; dwFlags
0x18001ffda  mov     ecx, 0FDE9h; CodePage
0x18001ffdf  call    cs:__imp_MultiByteToWideChar
0x18001ffe5  movsxd  rbp, eax
0x18001ffe8  test    eax, eax
0x18001ffea  jz      loc_180020098
0x18001fff0  mov     rdi, [rbx+10h]
0x18001fff4  mov     rdx, rbp
0x18001fff7  cmp     rbp, rdi
0x18001fffa  ja      short loc_180020017
0x18001fffc  mov     [rbx+10h], rdx
0x180020000  cmp     qword ptr [rbx+18h], 7
0x180020005  jbe     short loc_18002000C
0x180020007  mov     rcx, [rbx]
0x18002000a  jmp     short loc_18002000F
0x18002000c  mov     rcx, rbx
0x18002000f  xor     eax, eax
0x180020011  mov     [rcx+rbp*2], ax
0x180020015  jmp     short loc_180020064
0x180020017  mov     rcx, rdx
0x18002001a  sub     rcx, rdi
0x18002001d  mov     rax, [rbx+18h]
0x180020021  sub     rax, rdi
0x180020024  cmp     rcx, rax
0x180020027  ja      short loc_180020056
0x180020029  mov     [rbx+10h], rdx
0x18002002d  cmp     qword ptr [rbx+18h], 7
0x180020032  jbe     short loc_180020039
0x180020034  mov     r8, [rbx]
0x180020037  jmp     short loc_18002003C
0x180020039  mov     r8, rbx
0x18002003c  lea     rdi, [r8+rdi*2]
0x180020040  test    rcx, rcx
0x180020043  jz      short loc_18002004D
0x180020045  xor     eax, eax
0x180020047  movzx   eax, ax
0x18002004a  rep stosw
0x18002004d  xor     eax, eax
0x18002004f  mov     [r8+rbp*2], ax
0x180020054  jmp     short loc_180020064
0x180020056  mov     r9, rcx
0x180020059  mov     rdx, rcx
0x18002005c  mov     rcx, rbx; Src
0x18002005f  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x180020064  cmp     qword ptr [rbx+18h], 7
0x180020069  jbe     short loc_180020070
0x18002006b  mov     rax, [rbx]
0x18002006e  jmp     short loc_180020073
0x180020070  mov     rax, rbx
0x180020073  mov     [rsp+58h+cchWideChar], ebp; cchWideChar
0x180020077  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18002007c  mov     r9d, esi; cbMultiByte
0x18002007f  mov     r8, r14; lpMultiByteStr
0x180020082  xor     edx, edx; dwFlags
0x180020084  mov     ecx, 0FDE9h; CodePage
0x180020089  call    cs:__imp_MultiByteToWideChar
0x18002008f  test    eax, eax
0x180020091  jz      short loc_1800200A8
0x180020093  jmp     loc_18001FF9E
0x180020098  mov     rcx, [rsp+58h]; this
0x18002009d  mov     edx, 2F7h; void *
0x1800200a2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800200a8  mov     rcx, [rsp+58h]; this
0x1800200ad  mov     edx, 305h; void *
0x1800200b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800200b8  mov     rcx, [rsp+58h]; this
0x1800200bd  mov     r9d, 6Fh ; 'o'; char *
0x1800200c3  lea     r8, aOnecoreInterna_4; "onecore\\internal\\vm\\inc\\private\\co"...
0x1800200ca  mov     edx, 2E7h; void *
0x1800200cf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
