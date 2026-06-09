# CombineBaseAndRelativeURLs(ushort const *,ushort const *,ushort * *)

- ea: `0x18001eae4`
- end: `0x18001eca8`
- name: `?CombineBaseAndRelativeURLs@@YAJPEBG0PEAPEAG@Z`
- size: `452`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021070`

## callees

- `0x180003950`
- `0x180008648`
- `0x18001eae4`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `SHLWAPI!UrlCombineW` at `0x18001eb7a`
- `SHLWAPI!UrlCombineW` at `0x18001ec5f`
- `SHLWAPI!UrlCombineW` at `0x18001eb7a`
- `SHLWAPI!UrlCombineW` at `0x18001ec5f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eb89`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ec70`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eb89`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ec70`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eb9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eb9f`
- `urlmon!IsValidURL` at `0x18001eb3d`
- `urlmon!IsValidURL` at `0x18001eb5b`
- `urlmon!IsValidURL` at `0x18001ebbb`
- `urlmon!IsValidURL` at `0x18001eb3d`
- `urlmon!IsValidURL` at `0x18001eb5b`
- `urlmon!IsValidURL` at `0x18001ebbb`

## pseudocode

```c
__int64 __fastcall CombineBaseAndRelativeURLs(const unsigned __int16 *a1, const unsigned __int16 *a2, LPCWSTR *a3)
{
  unsigned __int16 *v7; // rdi
  __int64 v8; // r11
  int v9; // r11d
  __int64 v10; // rcx
  const unsigned __int16 *v11; // r8
  WCHAR *v12; // rdx
  DWORD pcchCombined[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszCombined[2088]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR psz[2088]; // [rsp+1090h] [rbp+F90h] BYREF

  pcchCombined[0] = 2084;
  if ( a3 )
  {
    if ( !IsValidURL(0, *a3, 0) )
      return 0;
    if ( a2 )
    {
      if ( !IsValidURL(0, a2, 0) && UrlCombineW(a2, *a3, pszCombined, pcchCombined, 0) >= 0 )
      {
        v7 = SysAllocString(pszCombined);
        if ( v7 )
          goto LABEL_28;
      }
    }
    if ( a1 && !IsValidURL(0, a1, 0) )
    {
      if ( a2 )
      {
        if ( *a3 )
        {
          v8 = -1;
          do
            ++v8;
          while ( (*a3)[v8] );
        }
        StringCchCopyW(pszCombined, 0x824u, a2);
        v10 = (unsigned int)(v9 - 1);
        if ( !v9 || (v11 = *a3, (*a3)[v10] != 92) )
        {
          v11 = *a3;
          if ( (*a3)[v10] != 47 )
          {
            StringCchCatW(pszCombined, 0x824u, L"/");
            v11 = *a3;
          }
        }
        StringCchCatW(pszCombined, 0x824u, v11);
        v12 = pszCombined;
      }
      else
      {
        v12 = (WCHAR *)*a3;
      }
      pcchCombined[0] = 2084;
      if ( UrlCombineW(a1, v12, psz, pcchCombined, 0) >= 0 )
      {
        v7 = SysAllocString(psz);
        if ( v7 )
        {
LABEL_28:
          if ( *a3 )
            SysFreeString((BSTR)*a3);
          *a3 = v7;
          return 0;
        }
      }
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001eae4  push    rbp
0x18001eae6  push    rbx
0x18001eae7  push    rsi
0x18001eae8  push    rdi
0x18001eae9  push    r12
0x18001eaeb  push    r14
0x18001eaed  push    r15
0x18001eaef  lea     rbp, [rsp-1FF0h]
0x18001eaf7  mov     eax, 20F0h
0x18001eafc  call    _alloca_probe
0x18001eb01  sub     rsp, rax
0x18001eb04  mov     rax, cs:__security_cookie
0x18001eb0b  xor     rax, rsp
0x18001eb0e  mov     [rbp+2020h+var_40], rax
0x18001eb15  xor     r15d, r15d
0x18001eb18  mov     r12d, 824h
0x18001eb1e  mov     [rsp+2120h+pcchCombined], r12d
0x18001eb23  mov     rbx, r8
0x18001eb26  mov     rsi, rdx
0x18001eb29  mov     r14, rcx
0x18001eb2c  test    r8, r8
0x18001eb2f  jz      loc_18001EC82
0x18001eb35  mov     rdx, [rbx]; szURL
0x18001eb38  xor     r8d, r8d; dwReserved
0x18001eb3b  xor     ecx, ecx; pBC
0x18001eb3d  call    cs:__imp_IsValidURL
0x18001eb43  test    eax, eax
0x18001eb45  jnz     short loc_18001EB4E
0x18001eb47  xor     eax, eax
0x18001eb49  jmp     loc_18001EC87
0x18001eb4e  test    rsi, rsi
0x18001eb51  jz      short loc_18001EBAA
0x18001eb53  xor     r8d, r8d; dwReserved
0x18001eb56  mov     rdx, rsi; szURL
0x18001eb59  xor     ecx, ecx; pBC
0x18001eb5b  call    cs:__imp_IsValidURL
0x18001eb61  test    eax, eax
0x18001eb63  jnz     short loc_18001EBAA
0x18001eb65  mov     rdx, [rbx]; pszRelative
0x18001eb68  lea     r9, [rsp+2120h+pcchCombined]; pcchCombined
0x18001eb6d  lea     r8, [rsp+2120h+pszCombined]; pszCombined
0x18001eb72  mov     [rsp+2120h+dwFlags], r15d; dwFlags
0x18001eb77  mov     rcx, rsi; pszBase
0x18001eb7a  call    cs:__imp_UrlCombineW
0x18001eb80  test    eax, eax
0x18001eb82  js      short loc_18001EBAA
0x18001eb84  lea     rcx, [rsp+2120h+pszCombined]; psz
0x18001eb89  call    cs:__imp_SysAllocString
0x18001eb8f  mov     rdi, rax
0x18001eb92  test    rax, rax
0x18001eb95  jz      short loc_18001EBAA
0x18001eb97  mov     rcx, [rbx]; bstrString
0x18001eb9a  test    rcx, rcx
0x18001eb9d  jz      short loc_18001EBA5
0x18001eb9f  call    cs:__imp_SysFreeString
0x18001eba5  mov     [rbx], rdi
0x18001eba8  jmp     short loc_18001EB47
0x18001ebaa  test    r14, r14
0x18001ebad  jz      loc_18001EC82
0x18001ebb3  xor     r8d, r8d; dwReserved
0x18001ebb6  mov     rdx, r14; szURL
0x18001ebb9  xor     ecx, ecx; pBC
0x18001ebbb  call    cs:__imp_IsValidURL
0x18001ebc1  test    eax, eax
0x18001ebc3  jnz     loc_18001EC82
0x18001ebc9  test    rsi, rsi
0x18001ebcc  jz      short loc_18001EC43
0x18001ebce  mov     rax, [rbx]
0x18001ebd1  test    rax, rax
0x18001ebd4  jz      short loc_18001EBE6
0x18001ebd6  or      r11, 0FFFFFFFFFFFFFFFFh
0x18001ebda  inc     r11
0x18001ebdd  cmp     [rax+r11*2], r15w
0x18001ebe2  jnz     short loc_18001EBDA
0x18001ebe4  jmp     short loc_18001EBE9
0x18001ebe6  mov     r11d, r15d
0x18001ebe9  mov     r8, rsi; unsigned __int16 *
0x18001ebec  lea     rcx, [rsp+2120h+pszCombined]; unsigned __int16 *
0x18001ebf1  mov     rdx, r12; unsigned __int64
0x18001ebf4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ebf9  lea     ecx, [r11-1]
0x18001ebfd  test    r11d, r11d
0x18001ec00  jz      short loc_18001EC0D
0x18001ec02  mov     r8, [rbx]
0x18001ec05  cmp     word ptr [r8+rcx*2], 5Ch ; '\'
0x18001ec0b  jz      short loc_18001EC2F
0x18001ec0d  mov     r8, [rbx]
0x18001ec10  cmp     word ptr [r8+rcx*2], 2Fh ; '/'
0x18001ec16  jz      short loc_18001EC2F
0x18001ec18  lea     r8, asc_18002E67C; "/"
0x18001ec1f  mov     rdx, r12; unsigned __int64
0x18001ec22  lea     rcx, [rsp+2120h+pszCombined]; unsigned __int16 *
0x18001ec27  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ec2c  mov     r8, [rbx]; unsigned __int16 *
0x18001ec2f  mov     rdx, r12; unsigned __int64
0x18001ec32  lea     rcx, [rsp+2120h+pszCombined]; unsigned __int16 *
0x18001ec37  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ec3c  lea     rdx, [rsp+2120h+pszCombined]
0x18001ec41  jmp     short loc_18001EC46
0x18001ec43  mov     rdx, [rbx]; pszRelative
0x18001ec46  lea     r9, [rsp+2120h+pcchCombined]; pcchCombined
0x18001ec4b  mov     [rsp+2120h+pcchCombined], r12d
0x18001ec50  lea     r8, [rbp+2020h+psz]; pszCombined
0x18001ec57  mov     [rsp+2120h+dwFlags], r15d; dwFlags
0x18001ec5c  mov     rcx, r14; pszBase
0x18001ec5f  call    cs:__imp_UrlCombineW
0x18001ec65  test    eax, eax
0x18001ec67  js      short loc_18001EC82
0x18001ec69  lea     rcx, [rbp+2020h+psz]; psz
0x18001ec70  call    cs:__imp_SysAllocString
0x18001ec76  mov     rdi, rax
0x18001ec79  test    rax, rax
0x18001ec7c  jnz     loc_18001EB97
0x18001ec82  mov     eax, 80004005h
0x18001ec87  mov     rcx, [rbp+2020h+var_40]
0x18001ec8e  xor     rcx, rsp; StackCookie
0x18001ec91  call    __security_check_cookie
0x18001ec96  add     rsp, 20F0h
0x18001ec9d  pop     r15
0x18001ec9f  pop     r14
0x18001eca1  pop     r12
0x18001eca3  pop     rdi
0x18001eca4  pop     rsi
0x18001eca5  pop     rbx
0x18001eca6  pop     rbp
0x18001eca7  retn
```
