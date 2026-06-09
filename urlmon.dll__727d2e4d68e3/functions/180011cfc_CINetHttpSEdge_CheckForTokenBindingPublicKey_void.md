# CINetHttpSEdge::CheckForTokenBindingPublicKey(void)

- ea: `0x180011cfc`
- end: `0x180011f4f`
- name: `?CheckForTokenBindingPublicKey@CINetHttpSEdge@@AEAAJXZ`
- size: `595`
- prototype: `__int64 __fastcall(HINTERNET *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011ca0`

## callees

- `0x180011cfc`
- `0x180011f58`
- `0x180011fa8`
- `0x180088604`
- `0x1800a25dc`
- `0x1800a2600`
- `0x1800af5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011e49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011e49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011d9a`
- `CRYPT32!CryptBinaryToStringW` at `0x180011e02`
- `CRYPT32!CryptBinaryToStringW` at `0x180011ebb`
- `CRYPT32!CryptBinaryToStringW` at `0x180011e02`
- `CRYPT32!CryptBinaryToStringW` at `0x180011ebb`
- `WININET!InternetQueryOptionW` at `0x180011d4f`
- `WININET!InternetQueryOptionW` at `0x180011e82`
- `WININET!InternetQueryOptionW` at `0x180011d4f`
- `WININET!InternetQueryOptionW` at `0x180011e82`

## pseudocode

```c
__int64 __fastcall CINetHttpSEdge::CheckForTokenBindingPublicKey(HINTERNET *this)
{
  const char *v2; // r9
  void *v3; // rcx
  unsigned int v4; // edi
  DWORD LastError; // eax
  int v7; // eax
  void *v8; // rax
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
        v8 = CoTaskMemAlloc((unsigned int)cb);
        this[252] = v8;
        if ( !v8 )
          wil::details::in1diag3::_FailFast_NullAlloc(
            retaddr,
            (void *)0x80,
            (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnethttpsedge.cxx",
            v9);
        if ( CryptBinaryToStringW(v14, dwBufferLength, 0x40000001u, (LPWSTR)v8, &v20) )
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
0x180011cfc  push    rbp
0x180011cfe  push    rbx
0x180011cff  push    rsi
0x180011d00  push    rdi
0x180011d01  push    r14
0x180011d03  mov     rbp, rsp
0x180011d06  sub     rsp, 30h
0x180011d0a  mov     rbx, rcx
0x180011d0d  call    ?IsLocalStateLockHeld@CINetEdge@@IEAA_NXZ; CINetEdge::IsLocalStateLockHeld(void)
0x180011d12  test    al, al
0x180011d14  jnz     short loc_180011D2C
0x180011d16  mov     rcx, [rbp+28h]; this
0x180011d1a  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180011d21  mov     edx, 54h ; 'T'; void *
0x180011d26  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180011d2c  mov     rcx, [rbx+178h]; hInternet
0x180011d33  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x180011d37  mov     r14d, 0B5h
0x180011d3d  mov     [rbp+dwBufferLength], 0
0x180011d44  mov     edx, r14d; dwOption
0x180011d47  xor     r8d, r8d; lpBuffer
0x180011d4a  mov     edi, 80004005h
0x180011d4f  call    cs:__imp_InternetQueryOptionW
0x180011d56  nop     dword ptr [rax+rax+00h]
0x180011d5b  test    eax, eax
0x180011d5d  jnz     short loc_180011D89
0x180011d5f  call    cs:__imp_GetLastError
0x180011d66  nop     dword ptr [rax+rax+00h]
0x180011d6b  cmp     eax, 7Ah ; 'z'
0x180011d6e  jz      loc_180011E3C
0x180011d74  call    cs:__imp_GetLastError
0x180011d7b  nop     dword ptr [rax+rax+00h]
0x180011d80  mov     ecx, eax; unsigned int
0x180011d82  call    ?GetInetError@@YAJK@Z; GetInetError(ulong)
0x180011d87  mov     edi, eax
0x180011d89  mov     eax, edi
0x180011d8b  add     rsp, 30h
0x180011d8f  pop     r14
0x180011d91  pop     rdi
0x180011d92  pop     rsi
0x180011d93  pop     rbx
0x180011d94  pop     rbp
0x180011d95  retn
0x180011d97  mov     rcx, rsi; pv
0x180011d9a  call    cs:__imp_CoTaskMemFree
0x180011da1  nop     dword ptr [rax+rax+00h]
0x180011da6  test    r14b, r14b
0x180011da9  jz      short loc_180011D74
0x180011dab  jmp     short loc_180011D89
0x180011dad  mov     ecx, [rbp+arg_10]
0x180011db0  lea     rdx, [rbp+cb]; unsigned int *
0x180011db4  add     rcx, rcx; __int64
0x180011db7  mov     dword ptr [rbp+cb], 0
0x180011dbe  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180011dc3  test    eax, eax
0x180011dc5  js      loc_180011EF2
0x180011dcb  mov     ecx, dword ptr [rbp+cb]; cb
0x180011dce  call    cs:__imp_CoTaskMemAlloc
0x180011dd5  nop     dword ptr [rax+rax+00h]
0x180011dda  mov     [rbx+7E0h], rax
0x180011de1  test    rax, rax
0x180011de4  jz      loc_180011F0B
0x180011dea  mov     edx, [rbp+dwBufferLength]; cbBinary
0x180011ded  lea     rcx, [rbp+arg_10]
0x180011df1  mov     qword ptr [rsp+30h+pcchString], rcx; pcchString
0x180011df6  mov     r9, rax; pszString
0x180011df9  mov     rcx, rsi; pbBinary
0x180011dfc  mov     r8d, 40000001h; dwFlags
0x180011e02  call    cs:__imp_CryptBinaryToStringW
0x180011e09  nop     dword ptr [rax+rax+00h]
0x180011e0e  test    eax, eax
0x180011e10  jz      short loc_180011D97
0x180011e12  mov     rcx, [rbx+7E0h]
0x180011e19  xor     eax, eax
0x180011e1b  cmp     eax, [rbp+arg_10]
0x180011e1e  jnb     loc_180011F40
0x180011e24  cmp     word ptr [rcx], 2Bh ; '+'
0x180011e28  jnz     loc_180011F21
0x180011e2e  mov     word ptr [rcx], 2Dh ; '-'
0x180011e33  add     eax, r14d
0x180011e36  add     rcx, 2
0x180011e3a  jmp     short loc_180011E1B
0x180011e3c  mov     eax, [rbp+dwBufferLength]
0x180011e3f  test    eax, eax
0x180011e41  jz      loc_180011D74
0x180011e47  mov     ecx, eax; cb
0x180011e49  call    cs:__imp_CoTaskMemAlloc
0x180011e50  nop     dword ptr [rax+rax+00h]
0x180011e55  mov     rsi, rax
0x180011e58  test    rax, rax
0x180011e5b  jnz     short loc_180011E71
0x180011e5d  mov     rcx, [rbp+28h]; this
0x180011e61  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180011e68  lea     edx, [rax+66h]; void *
0x180011e6b  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180011e71  mov     rcx, [rbx+178h]; hInternet
0x180011e78  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x180011e7c  mov     r8, rsi; lpBuffer
0x180011e7f  mov     edx, r14d; dwOption
0x180011e82  call    cs:__imp_InternetQueryOptionW
0x180011e89  nop     dword ptr [rax+rax+00h]
0x180011e8e  test    eax, eax
0x180011e90  jz      loc_180011F47
0x180011e96  mov     edx, [rbp+dwBufferLength]; cbBinary
0x180011e99  lea     rax, [rbp+arg_10]
0x180011e9d  xor     r9d, r9d; pszString
0x180011ea0  mov     qword ptr [rsp+30h+pcchString], rax; int
0x180011ea5  mov     r8d, 40000001h; dwFlags
0x180011eab  mov     [rbp+arg_10], 0
0x180011eb2  mov     rcx, rsi; pbBinary
0x180011eb5  mov     r14d, 1
0x180011ebb  call    cs:__imp_CryptBinaryToStringW
0x180011ec2  nop     dword ptr [rax+rax+00h]
0x180011ec7  test    eax, eax
0x180011ec9  jz      loc_180011D97
0x180011ecf  cmp     qword ptr [rbx+7E0h], 0
0x180011ed7  jz      loc_180011DAD
0x180011edd  mov     rcx, [rbp+28h]; this
0x180011ee1  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180011ee8  lea     edx, [r14+77h]; void *
0x180011eec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180011ef2  mov     rcx, [rbp+28h]; this
0x180011ef6  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180011efd  mov     r9d, eax; char *
0x180011f00  mov     edx, 7Ch ; '|'; void *
0x180011f05  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180011f0b  mov     rcx, [rbp+28h]; this
0x180011f0f  lea     r8, aOnecoreuapInet_33; "onecoreuap\\inetcore\\urlmon\\iapp\\edg"...
0x180011f16  mov     edx, 80h; void *
0x180011f1b  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180011f21  cmp     word ptr [rcx], 2Fh ; '/'
0x180011f25  jnz     short loc_180011F31
0x180011f27  mov     word ptr [rcx], 5Fh ; '_'
0x180011f2c  jmp     loc_180011E33
0x180011f31  cmp     word ptr [rcx], 3Dh ; '='
0x180011f35  jnz     loc_180011E33
0x180011f3b  xor     eax, eax
0x180011f3d  mov     [rcx], ax
0x180011f40  xor     edi, edi
0x180011f42  jmp     loc_180011D97
0x180011f47  xor     r14b, r14b
0x180011f4a  jmp     loc_180011D97
```
