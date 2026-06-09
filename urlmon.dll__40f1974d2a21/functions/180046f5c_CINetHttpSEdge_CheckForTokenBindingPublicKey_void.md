# CINetHttpSEdge::CheckForTokenBindingPublicKey(void)

- ea: `0x180046f5c`
- end: `0x180047178`
- name: `?CheckForTokenBindingPublicKey@CINetHttpSEdge@@AEAAJXZ`
- size: `540`
- prototype: `__int64 __fastcall(CINetHttpSEdge *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046f00`

## callees

- `0x180046f5c`
- `0x180047180`
- `0x1800471c4`
- `0x1800478b0`
- `0x18009b9dc`
- `0x18009ba00`
- `0x1800a856c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046fe7`
- `CRYPT32!CryptBinaryToStringW` at `0x180047043`
- `CRYPT32!CryptBinaryToStringW` at `0x1800470ea`
- `CRYPT32!CryptBinaryToStringW` at `0x180047043`
- `CRYPT32!CryptBinaryToStringW` at `0x1800470ea`
- `WININET!InternetQueryOptionW` at `0x180046faf`
- `WININET!InternetQueryOptionW` at `0x1800470b7`
- `WININET!InternetQueryOptionW` at `0x180046faf`
- `WININET!InternetQueryOptionW` at `0x1800470b7`

## pseudocode

```c
__int64 __fastcall CINetHttpSEdge::CheckForTokenBindingPublicKey(HINTERNET *this)
{
  const char *v2; // r9
  void *v3; // rcx
  unsigned int v4; // edi
  DWORD LastError; // eax
  int v7; // eax
  WCHAR *v8; // rax
  const char *v9; // r9
  _WORD *v10; // rcx
  DWORD i; // eax
  BYTE *v12; // rax
  const char *v13; // r9
  BYTE *v14; // rsi
  char v15; // r14
  const char *v16; // r9
  int pcchString; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD dwBufferLength; // [rsp+68h] [rbp+38h] BYREF
  DWORD v20; // [rsp+70h] [rbp+40h] BYREF
  SIZE_T cb; // [rsp+78h] [rbp+48h] BYREF

  if ( !CINetEdge::IsLocalStateLockHeld((CINetEdge *)this) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnethttpsedge.cxx",
      v2);
  v3 = this[47];
  dwBufferLength = 0;
  v4 = -2147467259;
  if ( !InternetQueryOptionW(v3, 0xB5u, 0, &dwBufferLength) )
  {
    if ( GetLastError() != 122 || !dwBufferLength )
      goto LABEL_5;
    v12 = (BYTE *)CoTaskMemAlloc(dwBufferLength);
    v14 = v12;
    if ( !v12 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnethttpsedge.cxx",
        v13);
    if ( InternetQueryOptionW(this[47], 0xB5u, v12, &dwBufferLength) )
    {
      v20 = 0;
      v15 = 1;
      if ( CryptBinaryToStringW(v14, dwBufferLength, 0x40000001u, 0, &v20) )
      {
        if ( this[252] )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x78,
            (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnethttpsedge.cxx",
            v16);
        LODWORD(cb) = 0;
        v7 = LongLongToULong(2LL * v20, (unsigned int *)&cb);
        if ( v7 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnethttpsedge.cxx",
            (const char *)(unsigned int)v7,
            pcchString);
        v8 = (WCHAR *)CoTaskMemAlloc((unsigned int)cb);
        this[252] = v8;
        if ( !v8 )
          wil::details::in1diag3::_FailFast_NullAlloc(
            retaddr,
            (void *)0x80,
            (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnethttpsedge.cxx",
            v9);
        if ( CryptBinaryToStringW(v14, dwBufferLength, 0x40000001u, v8, &v20) )
        {
          v10 = this[252];
          for ( i = 0; i < v20; ++i )
          {
            switch ( *v10 )
            {
              case '+':
                *v10 = 45;
                break;
              case '/':
                *v10 = 95;
                break;
              case '=':
                *v10 = 0;
                goto LABEL_30;
            }
            ++v10;
          }
LABEL_30:
          v4 = 0;
        }
      }
    }
    else
    {
      v15 = 0;
    }
    CoTaskMemFree(v14);
    if ( !v15 )
    {
LABEL_5:
      LastError = GetLastError();
      return (unsigned int)GetInetError(LastError);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180046f5c  push    rbp
0x180046f5e  push    rbx
0x180046f5f  push    rsi
0x180046f60  push    rdi
0x180046f61  push    r14
0x180046f63  mov     rbp, rsp
0x180046f66  sub     rsp, 30h
0x180046f6a  mov     rbx, rcx
0x180046f6d  call    ?IsLocalStateLockHeld@CINetEdge@@IEAA_NXZ; CINetEdge::IsLocalStateLockHeld(void)
0x180046f72  test    al, al
0x180046f74  jnz     short loc_180046F8C
0x180046f76  mov     rcx, [rbp+28h]; this
0x180046f7a  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180046f81  mov     edx, 54h ; 'T'; void *
0x180046f86  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180046f8c  mov     rcx, [rbx+178h]; hInternet
0x180046f93  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x180046f97  mov     r14d, 0B5h
0x180046f9d  mov     [rbp+dwBufferLength], 0
0x180046fa4  mov     edx, r14d; dwOption
0x180046fa7  xor     r8d, r8d; lpBuffer
0x180046faa  mov     edi, 80004005h
0x180046faf  call    cs:__imp_InternetQueryOptionW
0x180046fb5  test    eax, eax
0x180046fb7  jnz     short loc_180046FD7
0x180046fb9  call    cs:__imp_GetLastError
0x180046fbf  cmp     eax, 7Ah ; 'z'
0x180046fc2  jz      loc_180047077
0x180046fc8  call    cs:__imp_GetLastError
0x180046fce  mov     ecx, eax; unsigned int
0x180046fd0  call    ?GetInetError@@YAJK@Z; GetInetError(ulong)
0x180046fd5  mov     edi, eax
0x180046fd7  mov     eax, edi
0x180046fd9  add     rsp, 30h
0x180046fdd  pop     r14
0x180046fdf  pop     rdi
0x180046fe0  pop     rsi
0x180046fe1  pop     rbx
0x180046fe2  pop     rbp
0x180046fe3  retn
0x180046fe4  mov     rcx, rsi; pv
0x180046fe7  call    cs:__imp_CoTaskMemFree
0x180046fed  test    r14b, r14b
0x180046ff0  jz      short loc_180046FC8
0x180046ff2  jmp     short loc_180046FD7
0x180046ff4  mov     ecx, [rbp+arg_10]
0x180046ff7  lea     rdx, [rbp+cb]; unsigned int *
0x180046ffb  add     rcx, rcx; __int64
0x180046ffe  mov     dword ptr [rbp+cb], 0
0x180047005  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18004700a  test    eax, eax
0x18004700c  js      loc_18004711B
0x180047012  mov     ecx, dword ptr [rbp+cb]; cb
0x180047015  call    cs:__imp_CoTaskMemAlloc
0x18004701b  mov     [rbx+7E0h], rax
0x180047022  test    rax, rax
0x180047025  jz      loc_180047134
0x18004702b  mov     edx, [rbp+dwBufferLength]; cbBinary
0x18004702e  lea     rcx, [rbp+arg_10]
0x180047032  mov     qword ptr [rsp+30h+pcchString], rcx; pcchString
0x180047037  mov     r9, rax; pszString
0x18004703a  mov     rcx, rsi; pbBinary
0x18004703d  mov     r8d, 40000001h; dwFlags
0x180047043  call    cs:__imp_CryptBinaryToStringW
0x180047049  test    eax, eax
0x18004704b  jz      short loc_180046FE4
0x18004704d  mov     rcx, [rbx+7E0h]
0x180047054  xor     eax, eax
0x180047056  cmp     eax, [rbp+arg_10]
0x180047059  jnb     loc_180047169
0x18004705f  cmp     word ptr [rcx], 2Bh ; '+'
0x180047063  jnz     loc_18004714A
0x180047069  mov     word ptr [rcx], 2Dh ; '-'
0x18004706e  add     eax, r14d
0x180047071  add     rcx, 2
0x180047075  jmp     short loc_180047056
0x180047077  mov     eax, [rbp+dwBufferLength]
0x18004707a  test    eax, eax
0x18004707c  jz      loc_180046FC8
0x180047082  mov     ecx, eax; cb
0x180047084  call    cs:__imp_CoTaskMemAlloc
0x18004708a  mov     rsi, rax
0x18004708d  test    rax, rax
0x180047090  jnz     short loc_1800470A6
0x180047092  mov     rcx, [rbp+28h]; this
0x180047096  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x18004709d  lea     edx, [rax+66h]; void *
0x1800470a0  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800470a6  mov     rcx, [rbx+178h]; hInternet
0x1800470ad  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800470b1  mov     r8, rsi; lpBuffer
0x1800470b4  mov     edx, r14d; dwOption
0x1800470b7  call    cs:__imp_InternetQueryOptionW
0x1800470bd  test    eax, eax
0x1800470bf  jz      loc_180047170
0x1800470c5  mov     edx, [rbp+dwBufferLength]; cbBinary
0x1800470c8  lea     rax, [rbp+arg_10]
0x1800470cc  xor     r9d, r9d; pszString
0x1800470cf  mov     qword ptr [rsp+30h+pcchString], rax; int
0x1800470d4  mov     r8d, 40000001h; dwFlags
0x1800470da  mov     [rbp+arg_10], 0
0x1800470e1  mov     rcx, rsi; pbBinary
0x1800470e4  mov     r14d, 1
0x1800470ea  call    cs:__imp_CryptBinaryToStringW
0x1800470f0  test    eax, eax
0x1800470f2  jz      loc_180046FE4
0x1800470f8  cmp     qword ptr [rbx+7E0h], 0
0x180047100  jz      loc_180046FF4
0x180047106  mov     rcx, [rbp+28h]; this
0x18004710a  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180047111  lea     edx, [r14+77h]; void *
0x180047115  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004711b  mov     rcx, [rbp+28h]; this
0x18004711f  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180047126  mov     r9d, eax; char *
0x180047129  mov     edx, 7Ch ; '|'; void *
0x18004712e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180047134  mov     rcx, [rbp+28h]; this
0x180047138  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x18004713f  mov     edx, 80h; void *
0x180047144  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18004714a  cmp     word ptr [rcx], 2Fh ; '/'
0x18004714e  jnz     short loc_18004715A
0x180047150  mov     word ptr [rcx], 5Fh ; '_'
0x180047155  jmp     loc_18004706E
0x18004715a  cmp     word ptr [rcx], 3Dh ; '='
0x18004715e  jnz     loc_18004706E
0x180047164  xor     eax, eax
0x180047166  mov     [rcx], ax
0x180047169  xor     edi, edi
0x18004716b  jmp     loc_180046FE4
0x180047170  xor     r14b, r14b
0x180047173  jmp     loc_180046FE4
```
