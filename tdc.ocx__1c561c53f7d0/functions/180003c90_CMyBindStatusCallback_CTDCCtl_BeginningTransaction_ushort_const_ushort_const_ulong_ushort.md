# CMyBindStatusCallback<CTDCCtl>::BeginningTransaction(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180003c90`
- end: `0x180003ee3`
- name: `?BeginningTransaction@?$CMyBindStatusCallback@VCTDCCtl@@@@UEAAJPEBG0KPEAPEAG@Z`
- size: `595`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c90`
- `0x180005bd4`
- `0x180009460`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `urlmon!CoInternetParseUrl` at `0x180003d26`
- `urlmon!CoInternetParseUrl` at `0x180003db2`
- `urlmon!CoInternetParseUrl` at `0x180003d26`
- `urlmon!CoInternetParseUrl` at `0x180003db2`
- `ole32!CoTaskMemAlloc` at `0x180003e23`
- `ole32!CoTaskMemAlloc` at `0x180003e23`
- `ole32!CoTaskMemFree` at `0x180003eb4`
- `ole32!CoTaskMemFree` at `0x180003eb4`
- `SHLWAPI!StrCmpNIW` at `0x180003d46`
- `SHLWAPI!StrCmpNIW` at `0x180003d60`
- `SHLWAPI!StrCmpNIW` at `0x180003d80`
- `SHLWAPI!StrCmpNIW` at `0x180003dd4`
- `SHLWAPI!StrCmpNIW` at `0x180003d46`
- `SHLWAPI!StrCmpNIW` at `0x180003d60`
- `SHLWAPI!StrCmpNIW` at `0x180003d80`
- `SHLWAPI!StrCmpNIW` at `0x180003dd4`

## pseudocode

```c
__int64 __fastcall CMyBindStatusCallback<CTDCCtl>::BeginningTransaction(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  HRESULT HostURL; // edi
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  __int64 v10; // rcx
  const wchar_t *v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int16 *v13; // rcx
  DWORD cchResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchResult; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR pwzUrl; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszResult[2088]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR psz1[2088]; // [rsp+10B0h] [rbp+FB0h] BYREF

  cchResult = 2084;
  pcchResult = 2084;
  pwzUrl = 0;
  *a5 = 0;
  HostURL = GetHostURL(*(struct IOleClientSite **)(a1 + 72), (unsigned __int16 **)&pwzUrl);
  if ( HostURL >= 0 )
  {
    HostURL = CoInternetParseUrl(pwzUrl, PARSE_CANONICALIZE, 0, pszResult, cchResult, &cchResult, 0);
    if ( HostURL >= 0
      && (!StrCmpNIW(pszResult, L"https:", 6) || !StrCmpNIW(pszResult, L"http:", 5))
      && (StrCmpNIW(pszResult, L"https:", 6)
       || (HostURL = CoInternetParseUrl(a2, PARSE_CANONICALIZE, 0, psz1, pcchResult, &pcchResult, 0)) == 0
       && StrCmpNIW(psz1, L"http:", 5)) )
    {
      v7 = -1;
      do
        ++v7;
      while ( pwzUrl[v7] );
      if ( v7 + 2 >= v7 )
      {
        v8 = v7 + 11;
        if ( v7 + 11 >= v7 + 2 && is_mul_ok(v8, 2u) )
        {
          v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
          *a5 = v9;
          if ( v9 )
          {
            if ( v8 )
            {
              if ( v8 <= 0x7FFFFFFF )
              {
                v10 = 2147483646;
                v11 = L"Referer: ";
                v12 = v8;
                do
                {
                  if ( !v10 )
                    break;
                  if ( !*v11 )
                    break;
                  *v9++ = *v11++;
                  --v10;
                  --v12;
                }
                while ( v12 );
                v13 = v9 - 1;
                if ( v12 )
                  v13 = v9;
                *v13 = 0;
                if ( v12 && (int)StringCchCatW(*a5, v8, pwzUrl) >= 0 )
                  StringCchCatW(*a5, v8, L"\r\n");
              }
              else
              {
                *v9 = 0;
              }
            }
          }
        }
      }
    }
  }
  CoTaskMemFree((LPVOID)pwzUrl);
  return (unsigned int)HostURL;
}

```

## disassembly

```asm
0x180003c90  mov     [rsp-8+arg_10], rbx
0x180003c95  mov     [rsp-8+arg_18], rsi
0x180003c9a  push    rbp
0x180003c9b  push    rdi
0x180003c9c  push    r14
0x180003c9e  lea     rbp, [rsp-2010h]
0x180003ca6  mov     eax, 2110h
0x180003cab  call    _alloca_probe
0x180003cb0  sub     rsp, rax
0x180003cb3  mov     rax, cs:__security_cookie
0x180003cba  xor     rax, rsp
0x180003cbd  mov     [rbp+2020h+var_20], rax
0x180003cc4  mov     rsi, [rbp+2020h+arg_20]
0x180003ccb  mov     eax, 824h
0x180003cd0  xor     r14d, r14d
0x180003cd3  mov     [rsp+2120h+var_20E0], eax
0x180003cd7  mov     rbx, rdx
0x180003cda  mov     [rsp+2120h+var_20DC], eax
0x180003cde  lea     rdx, [rsp+2120h+pwzUrl]; unsigned __int16 **
0x180003ce3  mov     [rsp+2120h+pwzUrl], r14
0x180003ce8  mov     [rsi], r14
0x180003ceb  mov     rcx, [rcx+48h]; struct IOleClientSite *
0x180003cef  call    ?GetHostURL@@YAJPEAUIOleClientSite@@PEAPEAG@Z; GetHostURL(IOleClientSite *,ushort * *)
0x180003cf4  mov     edi, eax
0x180003cf6  test    eax, eax
0x180003cf8  js      loc_180003EAF
0x180003cfe  mov     rcx, [rsp+2120h+pwzUrl]; pwzUrl
0x180003d03  lea     rax, [rsp+2120h+var_20E0]
0x180003d08  mov     [rsp+2120h+dwReserved], r14d; dwReserved
0x180003d0d  lea     r9, [rsp+2120h+pszResult]; pszResult
0x180003d12  mov     [rsp+2120h+pcchResult], rax; pcchResult
0x180003d17  lea     edx, [r14+1]; ParseAction
0x180003d1b  mov     eax, [rsp+2120h+var_20E0]
0x180003d1f  xor     r8d, r8d; dwFlags
0x180003d22  mov     [rsp+2120h+cchResult], eax; cchResult
0x180003d26  call    cs:__imp_CoInternetParseUrl
0x180003d2c  mov     edi, eax
0x180003d2e  test    eax, eax
0x180003d30  js      loc_180003EAF
0x180003d36  lea     r8d, [r14+6]; nChar
0x180003d3a  lea     rdx, psz2; "https:"
0x180003d41  lea     rcx, [rsp+2120h+pszResult]; psz1
0x180003d46  call    cs:__imp_StrCmpNIW
0x180003d4c  test    eax, eax
0x180003d4e  jz      short loc_180003D6E
0x180003d50  lea     r8d, [r14+5]; nChar
0x180003d54  lea     rdx, aHttp; "http:"
0x180003d5b  lea     rcx, [rsp+2120h+pszResult]; psz1
0x180003d60  call    cs:__imp_StrCmpNIW
0x180003d66  test    eax, eax
0x180003d68  jnz     loc_180003EAF
0x180003d6e  mov     r8d, 6; nChar
0x180003d74  lea     rdx, psz2; "https:"
0x180003d7b  lea     rcx, [rsp+2120h+pszResult]; psz1
0x180003d80  call    cs:__imp_StrCmpNIW
0x180003d86  test    eax, eax
0x180003d88  jnz     short loc_180003DE2
0x180003d8a  lea     rax, [rsp+2120h+var_20DC]
0x180003d8f  mov     [rsp+2120h+dwReserved], r14d; dwReserved
0x180003d94  mov     [rsp+2120h+pcchResult], rax; pcchResult
0x180003d99  lea     r9, [rbp+2020h+psz1]; pszResult
0x180003da0  mov     eax, [rsp+2120h+var_20DC]
0x180003da4  xor     r8d, r8d; dwFlags
0x180003da7  mov     rcx, rbx; pwzUrl
0x180003daa  mov     [rsp+2120h+cchResult], eax; cchResult
0x180003dae  lea     edx, [r8+1]; ParseAction
0x180003db2  call    cs:__imp_CoInternetParseUrl
0x180003db8  mov     edi, eax
0x180003dba  test    eax, eax
0x180003dbc  jnz     loc_180003EAF
0x180003dc2  lea     r8d, [rax+5]; nChar
0x180003dc6  lea     rdx, aHttp; "http:"
0x180003dcd  lea     rcx, [rbp+2020h+psz1]; psz1
0x180003dd4  call    cs:__imp_StrCmpNIW
0x180003dda  test    eax, eax
0x180003ddc  jz      loc_180003EAF
0x180003de2  mov     rcx, [rsp+2120h+pwzUrl]
0x180003de7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003deb  inc     rax
0x180003dee  cmp     [rcx+rax*2], r14w
0x180003df3  jnz     short loc_180003DEB
0x180003df5  lea     rcx, [rax+2]
0x180003df9  cmp     rcx, rax
0x180003dfc  jb      loc_180003EAF
0x180003e02  lea     rbx, [rcx+9]
0x180003e06  cmp     rbx, rcx
0x180003e09  jb      loc_180003EAF
0x180003e0f  mov     eax, 2
0x180003e14  mul     rbx
0x180003e17  test    rdx, rdx
0x180003e1a  jnz     loc_180003EAF
0x180003e20  mov     rcx, rax; cb
0x180003e23  call    cs:__imp_CoTaskMemAlloc
0x180003e29  mov     [rsi], rax
0x180003e2c  test    rax, rax
0x180003e2f  jz      short loc_180003EAF
0x180003e31  test    rbx, rbx
0x180003e34  jz      short loc_180003EAF
0x180003e36  cmp     rbx, 7FFFFFFFh
0x180003e3d  jbe     short loc_180003E45
0x180003e3f  mov     [rax], r14w
0x180003e43  jmp     short loc_180003EAF
0x180003e45  mov     ecx, 7FFFFFFEh
0x180003e4a  lea     r8, aReferer; "Referer: "
0x180003e51  mov     rdx, rbx
0x180003e54  test    rcx, rcx
0x180003e57  jz      short loc_180003E78
0x180003e59  movzx   r9d, word ptr [r8]
0x180003e5d  test    r9w, r9w
0x180003e61  jz      short loc_180003E78
0x180003e63  mov     [rax], r9w
0x180003e67  add     r8, 2
0x180003e6b  add     rax, 2
0x180003e6f  dec     rcx
0x180003e72  sub     rdx, 1
0x180003e76  jnz     short loc_180003E54
0x180003e78  test    rdx, rdx
0x180003e7b  lea     rcx, [rax-2]
0x180003e7f  cmovnz  rcx, rax
0x180003e83  mov     [rcx], r14w
0x180003e87  jz      short loc_180003EAF
0x180003e89  mov     r8, [rsp+2120h+pwzUrl]; unsigned __int16 *
0x180003e8e  mov     rdx, rbx; unsigned __int64
0x180003e91  mov     rcx, [rsi]; unsigned __int16 *
0x180003e94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003e99  test    eax, eax
0x180003e9b  js      short loc_180003EAF
0x180003e9d  mov     rcx, [rsi]; unsigned __int16 *
0x180003ea0  lea     r8, asc_1800184AC; "\r\n"
0x180003ea7  mov     rdx, rbx; unsigned __int64
0x180003eaa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003eaf  mov     rcx, [rsp+2120h+pwzUrl]; pv
0x180003eb4  call    cs:__imp_CoTaskMemFree
0x180003eba  mov     eax, edi
0x180003ebc  mov     rcx, [rbp+2020h+var_20]
0x180003ec3  xor     rcx, rsp; StackCookie
0x180003ec6  call    __security_check_cookie
0x180003ecb  lea     r11, [rsp+2120h+var_10]
0x180003ed3  mov     rbx, [r11+30h]
0x180003ed7  mov     rsi, [r11+38h]
0x180003edb  mov     rsp, r11
0x180003ede  pop     r14
0x180003ee0  pop     rdi
0x180003ee1  pop     rbp
0x180003ee2  retn
```
