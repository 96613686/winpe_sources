# SHCleanupUrlForDisplay

- ea: `0x18002628c`
- end: `0x1800263f5`
- name: `SHCleanupUrlForDisplay`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026218`

## callees

- `0x180008320`
- `0x180009018`
- `0x18000bf34`
- `0x18001d3b0`
- `0x18002628c`
- `0x180027c30`

## import_xrefs

- `SHLWAPI!StrPBrkW` at `0x180026388`
- `SHLWAPI!StrPBrkW` at `0x180026388`
- `WININET!InternetCrackUrlW` at `0x180026358`
- `WININET!InternetCrackUrlW` at `0x180026358`
- `WININET!InternetCreateUrlW` at `0x1800263aa`
- `WININET!InternetCreateUrlW` at `0x1800263aa`

## pseudocode

```c
__int64 __fastcall SHCleanupUrlForDisplay(unsigned __int16 *a1, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  PWSTR v7; // rax
  DWORD dwUrlLength[4]; // [rsp+20h] [rbp-E0h] BYREF
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+30h] [rbp-D0h] BYREF
  char v11; // [rsp+A0h] [rbp-60h] BYREF
  char v12; // [rsp+E0h] [rbp-20h] BYREF
  char v13; // [rsp+1E0h] [rbp+E0h] BYREF
  char v14; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v15; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR szUrl[2088]; // [rsp+14E0h] [rbp+13E0h] BYREF

  v2 = a2;
  v4 = 0;
  v5 = GetUrlSchemeW(a1) - 1;
  if ( !v5 || (v6 = v5 - 1) == 0 || v6 == 9 )
  {
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    UrlComponents.lpszUserName = (LPWSTR)&v12;
    UrlComponents.dwSchemeLength = 32;
    UrlComponents.lpszPassword = (LPWSTR)&v13;
    UrlComponents.dwHostNameLength = 256;
    UrlComponents.lpszHostName = (LPWSTR)&v14;
    UrlComponents.dwUrlPathLength = 2048;
    UrlComponents.lpszScheme = (LPWSTR)&v11;
    UrlComponents.lpszUrlPath = (LPWSTR)&v15;
    UrlComponents.dwUserNameLength = 128;
    UrlComponents.dwPasswordLength = 128;
    if ( InternetCrackUrlW(a1, 0, 0, &UrlComponents) )
    {
      UrlComponents.dwUserNameLength = 0;
      UrlComponents.dwPasswordLength = 0;
      UrlComponents.lpszPassword = 0;
      UrlComponents.lpszUserName = 0;
      dwUrlLength[0] = 2084;
      v7 = StrPBrkW(UrlComponents.lpszHostName, &pszSet);
      if ( InternetCreateUrlW(&UrlComponents, v7 != 0 ? 0x2000 : 0, szUrl, dwUrlLength) )
      {
        if ( (unsigned int)v2 > dwUrlLength[0] )
        {
          StringCchCopyW(a1, v2, szUrl);
          return 1;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002628c  mov     [rsp-8+arg_10], rbx
0x180026291  push    rbp
0x180026292  push    rsi
0x180026293  push    rdi
0x180026294  lea     rbp, [rsp-2440h]
0x18002629c  mov     eax, 2540h
0x1800262a1  call    _alloca_probe
0x1800262a6  sub     rsp, rax
0x1800262a9  mov     rax, cs:__security_cookie
0x1800262b0  xor     rax, rsp
0x1800262b3  mov     [rbp+2450h+var_20], rax
0x1800262ba  mov     edi, edx
0x1800262bc  mov     rsi, rcx
0x1800262bf  xor     ebx, ebx
0x1800262c1  call    GetUrlSchemeW
0x1800262c6  sub     eax, 1
0x1800262c9  jz      short loc_1800262D9
0x1800262cb  sub     eax, 1
0x1800262ce  jz      short loc_1800262D9
0x1800262d0  cmp     eax, 9
0x1800262d3  jnz     loc_1800263D1
0x1800262d9  xor     edx, edx; Val
0x1800262db  lea     rcx, [rsp+2550h+UrlComponents]; void *
0x1800262e0  lea     r8d, [rdx+68h]; Size
0x1800262e4  call    memset_0
0x1800262e9  lea     rax, [rbp+2450h+var_2470]
0x1800262ed  mov     [rsp+2550h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800262f5  mov     [rsp+2550h+UrlComponents.lpszUserName], rax
0x1800262fa  lea     r9, [rsp+2550h+UrlComponents]; lpUrlComponents
0x1800262ff  lea     rax, [rbp+2450h+var_2370]
0x180026306  mov     [rsp+2550h+UrlComponents.dwSchemeLength], 20h ; ' '
0x18002630e  mov     [rsp+2550h+UrlComponents.lpszPassword], rax
0x180026313  xor     r8d, r8d; dwFlags
0x180026316  lea     rax, [rbp+2450h+var_2270]
0x18002631d  mov     [rsp+2550h+UrlComponents.dwHostNameLength], 100h
0x180026325  mov     [rsp+2550h+UrlComponents.lpszHostName], rax
0x18002632a  xor     edx, edx; dwUrlLength
0x18002632c  lea     rax, [rbp+2450h+var_24B0]
0x180026330  mov     [rbp+2450h+UrlComponents.dwUrlPathLength], 800h
0x180026337  mov     [rsp+2550h+UrlComponents.lpszScheme], rax
0x18002633c  mov     rcx, rsi; lpszUrl
0x18002633f  lea     rax, [rbp+2450h+var_2070]
0x180026346  mov     [rsp+2550h+UrlComponents.lpszUrlPath], rax
0x18002634b  mov     eax, 80h
0x180026350  mov     [rsp+2550h+UrlComponents.dwUserNameLength], eax
0x180026354  mov     [rsp+2550h+UrlComponents.dwPasswordLength], eax
0x180026358  call    cs:__imp_InternetCrackUrlW
0x18002635e  test    eax, eax
0x180026360  jz      short loc_1800263D1
0x180026362  mov     rcx, [rsp+2550h+UrlComponents.lpszHostName]; psz
0x180026367  lea     rdx, pszSet; pszSet
0x18002636e  mov     [rsp+2550h+UrlComponents.dwUserNameLength], ebx
0x180026372  mov     [rsp+2550h+UrlComponents.dwPasswordLength], ebx
0x180026376  mov     [rsp+2550h+UrlComponents.lpszPassword], rbx
0x18002637b  mov     [rsp+2550h+UrlComponents.lpszUserName], rbx
0x180026380  mov     [rsp+2550h+dwUrlLength], 824h
0x180026388  call    cs:__imp_StrPBrkW
0x18002638e  neg     rax
0x180026391  lea     r9, [rsp+2550h+dwUrlLength]; lpdwUrlLength
0x180026396  lea     r8, [rbp+2450h+szUrl]; lpszUrl
0x18002639d  sbb     edx, edx
0x18002639f  lea     rcx, [rsp+2550h+UrlComponents]; lpUrlComponents
0x1800263a4  and     edx, 2000h; dwFlags
0x1800263aa  call    cs:__imp_InternetCreateUrlW
0x1800263b0  test    eax, eax
0x1800263b2  jz      short loc_1800263D1
0x1800263b4  cmp     edi, [rsp+2550h+dwUrlLength]
0x1800263b8  jbe     short loc_1800263D1
0x1800263ba  mov     rdx, rdi; unsigned __int64
0x1800263bd  lea     r8, [rbp+2450h+szUrl]; unsigned __int16 *
0x1800263c4  mov     rcx, rsi; unsigned __int16 *
0x1800263c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800263cc  mov     ebx, 1
0x1800263d1  mov     eax, ebx
0x1800263d3  mov     rcx, [rbp+2450h+var_20]
0x1800263da  xor     rcx, rsp; StackCookie
0x1800263dd  call    __security_check_cookie
0x1800263e2  mov     rbx, [rsp+2550h+arg_10]
0x1800263ea  add     rsp, 2540h
0x1800263f1  pop     rdi
0x1800263f2  pop     rsi
0x1800263f3  pop     rbp
0x1800263f4  retn
```
