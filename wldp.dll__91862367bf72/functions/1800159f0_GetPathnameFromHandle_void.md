# GetPathnameFromHandle(void *)

- ea: `0x1800159f0`
- end: `0x180015bec`
- name: `?GetPathnameFromHandle@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `508`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001cd18`
- `0x18001d9b4`
- `0x18001e1d4`
- `0x18002d4e8`
- `0x18002f728`

## callees

- `0x1800159f0`
- `0x18001f8c4`
- `0x1800202bc`
- `0x180020650`
- `0x180020a9c`
- `0x18002e5d0`
- `0x18002fbd8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015bb6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015bb6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180015a1c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180015b11`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180015a1c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180015b11`

## string_xrefs

- `0x180015b9d`: `onecore\base\ngscb\wldp\dll\utility.cpp`
- `0x180015bda`: `onecore\base\ngscb\wldp\dll\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall GetPathnameFromHandle(__int64 *a1, void *a2)
{
  DWORD FinalPathNameByHandleW; // eax
  const char *v5; // r9
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // r15
  __int64 v10; // rbx
  unsigned __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r12
  unsigned __int64 v14; // r9
  WCHAR *v15; // rdx
  const char *v16; // r9
  __int64 v18; // rbx
  __int64 *v19; // rcx
  __int64 *v20; // rdx
  _WORD *v21; // rdi
  unsigned __int64 i; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a2, 0, 0, 0);
  v6 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\utility.cpp",
      v5);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  std::wstring::_Construct_empty(a1);
  v7 = a1[2];
  if ( v6 <= v7 )
  {
    a1[2] = v6;
    if ( (unsigned __int64)a1[3] <= 7 )
      v19 = a1;
    else
      v19 = (__int64 *)*a1;
    *((_WORD *)v19 + v6) = 0;
  }
  else
  {
    v8 = (unsigned int)v6 - v7;
    v9 = a1[3];
    if ( v8 <= v9 - v7 )
    {
      a1[2] = v6;
      if ( v9 <= 7 )
        v20 = a1;
      else
        v20 = (__int64 *)*a1;
      v21 = (_WORD *)v20 + v7;
      if ( v8 )
      {
        for ( i = v8; i; --i )
          *v21++ = 0;
      }
      *((_WORD *)v20 + v6) = 0;
    }
    else
    {
      v10 = 0x7FFFFFFFFFFFFFFELL;
      if ( 0x7FFFFFFFFFFFFFFELL - v7 < v8 )
        std::_Xlength_error("string too long");
      v11 = v9 >> 1;
      if ( v9 > 0x7FFFFFFFFFFFFFFELL - (v9 >> 1) )
      {
        v12 = 0x7FFFFFFFFFFFFFFFLL;
      }
      else
      {
        v10 = v11 + v9;
        if ( ((unsigned int)v6 | 7uLL) >= v11 + v9 )
          v10 = (unsigned int)v6 | 7LL;
        v12 = v10 + 1;
        if ( (unsigned __int64)(v10 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      v13 = std::_Allocate<16,std::_Default_allocate_traits>(2 * v12);
      a1[2] = v6;
      a1[3] = v10;
      v14 = (unsigned int)v6 - v7;
      if ( v9 > 7 )
      {
        v18 = *a1;
        _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(v13, *a1, v7, v14);
        std::_Deallocate<16>(v18, 2 * v9 + 2);
      }
      else
      {
        _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(v13, a1, v7, v14);
      }
      *a1 = v13;
    }
  }
  if ( (unsigned __int64)a1[3] <= 7 )
    v15 = (WCHAR *)a1;
  else
    v15 = (WCHAR *)*a1;
  if ( !GetFinalPathNameByHandleW(a2, v15, *((_DWORD *)a1 + 4), 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\utility.cpp",
      v16);
  return a1;
}

```

## disassembly

```asm
0x1800159f0  mov     [rsp+arg_0], rcx
0x1800159f5  push    rbx
0x1800159f6  push    rbp
0x1800159f7  push    rsi
0x1800159f8  push    rdi
0x1800159f9  push    r12
0x1800159fb  push    r13
0x1800159fd  push    r14
0x1800159ff  push    r15
0x180015a01  sub     rsp, 48h
0x180015a05  mov     r13, rdx
0x180015a08  mov     rsi, rcx
0x180015a0b  xor     ebx, ebx
0x180015a0d  mov     [rsp+88h+var_58], ebx
0x180015a11  xor     r9d, r9d; dwFlags
0x180015a14  xor     r8d, r8d; cchFilePath
0x180015a17  xor     edx, edx; lpszFilePath
0x180015a19  mov     rcx, r13; hFile
0x180015a1c  call    cs:__imp_GetFinalPathNameByHandleW
0x180015a22  mov     r14d, eax
0x180015a25  mov     rcx, [rsp+88h]; this
0x180015a2d  test    eax, eax
0x180015a2f  jz      loc_180015B9D
0x180015a35  xorps   xmm0, xmm0
0x180015a38  movups  xmmword ptr [rsi], xmm0
0x180015a3b  mov     [rsi+10h], rbx
0x180015a3f  mov     [rsi+18h], rbx
0x180015a43  mov     rcx, rsi
0x180015a46  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180015a4b  mov     [rsp+88h+var_58], 1
0x180015a53  mov     rdi, [rsi+10h]
0x180015a57  cmp     r14, rdi
0x180015a5a  jbe     loc_180015B55
0x180015a60  mov     ebp, r14d
0x180015a63  sub     rbp, rdi
0x180015a66  mov     r15, [rsi+18h]
0x180015a6a  mov     rax, r15
0x180015a6d  sub     rax, rdi
0x180015a70  cmp     rbp, rax
0x180015a73  jbe     loc_180015B6F
0x180015a79  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180015a83  mov     rax, rbx
0x180015a86  sub     rax, rdi
0x180015a89  cmp     rax, rbp
0x180015a8c  jb      loc_180015BAF
0x180015a92  mov     rcx, r15
0x180015a95  shr     rcx, 1
0x180015a98  mov     rax, rbx
0x180015a9b  sub     rax, rcx
0x180015a9e  cmp     r15, rax
0x180015aa1  ja      loc_180015BBD
0x180015aa7  mov     eax, r14d
0x180015aaa  or      rax, 7
0x180015aae  lea     rbx, [rcx+r15]
0x180015ab2  cmp     rax, rbx
0x180015ab5  cmovnb  rbx, rax
0x180015ab9  lea     rcx, [rbx+1]
0x180015abd  mov     rax, 7FFFFFFFFFFFFFFFh
0x180015ac7  cmp     rcx, rax
0x180015aca  ja      loc_180015BCC
0x180015ad0  add     rcx, rcx
0x180015ad3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180015ad8  mov     r12, rax
0x180015adb  mov     [rsi+10h], r14
0x180015adf  mov     [rsi+18h], rbx
0x180015ae3  mov     r9, rbp
0x180015ae6  mov     r8, rdi
0x180015ae9  mov     rcx, rax
0x180015aec  cmp     r15, 7
0x180015af0  ja      short loc_180015B38
0x180015af2  mov     rdx, rsi
0x180015af5  call    ??R_lambda_b70241e9b5ebaad244db3e52d52cab17_@@SA@QEAGQEBG_K2G@Z; _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180015afa  mov     [rsi], r12
0x180015afd  cmp     qword ptr [rsi+18h], 7
0x180015b02  jbe     short loc_180015B33
0x180015b04  mov     rdx, [rsi]; lpszFilePath
0x180015b07  xor     r9d, r9d; dwFlags
0x180015b0a  mov     r8d, [rsi+10h]; cchFilePath
0x180015b0e  mov     rcx, r13; hFile
0x180015b11  call    cs:__imp_GetFinalPathNameByHandleW
0x180015b17  test    eax, eax
0x180015b19  jz      loc_180015BD2
0x180015b1f  mov     rax, rsi
0x180015b22  add     rsp, 48h
0x180015b26  pop     r15
0x180015b28  pop     r14
0x180015b2a  pop     r13
0x180015b2c  pop     r12
0x180015b2e  pop     rdi
0x180015b2f  pop     rsi
0x180015b30  pop     rbp
0x180015b31  pop     rbx
0x180015b32  retn
0x180015b33  mov     rdx, rsi
0x180015b36  jmp     short loc_180015B07
0x180015b38  mov     rbx, [rsi]
0x180015b3b  mov     rdx, rbx
0x180015b3e  call    ??R_lambda_b70241e9b5ebaad244db3e52d52cab17_@@SA@QEAGQEBG_K2G@Z; _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180015b43  lea     rdx, ds:2[r15*2]
0x180015b4b  mov     rcx, rbx
0x180015b4e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015b53  jmp     short loc_180015AFA
0x180015b55  mov     [rsi+10h], r14
0x180015b59  cmp     qword ptr [rsi+18h], 7
0x180015b5e  jbe     short loc_180015B6A
0x180015b60  mov     rcx, [rsi]
0x180015b63  mov     [rcx+r14*2], bx
0x180015b68  jmp     short loc_180015AFD
0x180015b6a  mov     rcx, rsi
0x180015b6d  jmp     short loc_180015B63
0x180015b6f  mov     [rsi+10h], r14
0x180015b73  cmp     r15, 7
0x180015b77  jbe     short loc_180015B98
0x180015b79  mov     rdx, [rsi]
0x180015b7c  lea     rdi, [rdx+rdi*2]
0x180015b80  test    rbp, rbp
0x180015b83  jz      short loc_180015B8E
0x180015b85  movzx   eax, bx
0x180015b88  mov     rcx, rbp
0x180015b8b  rep stosw
0x180015b8e  mov     [rdx+r14*2], bx
0x180015b93  jmp     loc_180015AFD
0x180015b98  mov     rdx, rsi
0x180015b9b  jmp     short loc_180015B7C
0x180015b9d  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\wldp\\dll\\utilit"...
0x180015ba4  mov     edx, 2Fh ; '/'; void *
0x180015ba9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015baf  lea     rcx, aStringTooLong; "string too long"
0x180015bb6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180015bbd  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180015bc7  jmp     loc_180015AD0
0x180015bcc  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180015bd2  mov     rcx, [rsp+88h]; this
0x180015bda  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\wldp\\dll\\utilit"...
0x180015be1  mov     edx, 36h ; '6'; void *
0x180015be6  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
