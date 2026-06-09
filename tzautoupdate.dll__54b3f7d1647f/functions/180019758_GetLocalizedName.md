# GetLocalizedName

- ea: `0x180019758`
- end: `0x180019938`
- name: `GetLocalizedName`
- size: `480`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, const WCHAR *, const WCHAR *, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18001859c`
- `0x18001a354`

## callees

- `0x180017cbc`
- `0x180017d24`
- `0x180019468`
- `0x180019758`
- `0x180019fd0`
- `0x18001a218`
- `0x18001ada8`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800198ab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800198ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800198e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800198e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800197de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800197de`

## string_xrefs

- `0x1800197ec`: `\tzres.dll`

## pseudocode

```c
__int64 __fastcall GetLocalizedName(
        HKEY hKey,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        STRSAFE_LPWSTR pszDest,
        size_t cchDest)
{
  bool v9; // zf
  HRESULT StringFromReg; // ebx
  BOOL v11; // edi
  HINSTANCE MUILibraryW; // rsi
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t v15[8]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+48h] [rbp-B8h]
  int v17; // [rsp+58h] [rbp-A8h]
  wchar_t pszSrc[128]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+160h] [rbp+60h] BYREF

  memset_0(pszSrc, 0, sizeof(pszSrc));
  cbData = 256;
  v9 = dword_1800316C0 == 0;
  *pszDest = 0;
  if ( !v9 )
    goto LABEL_12;
  dword_1800316C0 = 1;
  StringFromReg = -2147467259;
  v11 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( StringCchCatW(Buffer, 0x104u, L"\\tzres.dll") >= 0 )
    {
      MUILibraryW = LoadMUILibraryW(Buffer, 8u, 0x400u);
      if ( MUILibraryW )
      {
        v17 = 0;
        dword_1800316C0 = 0;
        v11 = 1;
        *(_OWORD *)v15 = 0;
        v16 = 0;
        StringFromReg = GetStringFromReg(hKey, a3, v15);
        if ( StringFromReg >= 0 )
        {
          StringFromReg = FindResourceId(v15);
          if ( StringFromReg >= 0 )
          {
            StringFromReg = LoadStringResource(MUILibraryW);
            if ( StringFromReg >= 0 )
            {
              StringFromReg = StringCchCopyW(pszDest, (unsigned int)cchDest, pszSrc);
              v11 = StringFromReg < 0;
            }
          }
        }
        FreeLibrary(MUILibraryW);
      }
    }
  }
  if ( dword_1800316C0 || v11 )
  {
LABEL_12:
    StringFromReg = -2147467259;
    if ( !RegQueryValueExW(hKey, a4, 0, 0, (LPBYTE)pszSrc, &cbData) )
    {
      StringFromReg = StringCchCopyW(pszDest, (unsigned int)cchDest, pszSrc);
      if ( StringFromReg >= 0 )
        return 262659;
    }
  }
  return (unsigned int)StringFromReg;
}

```

## disassembly

```asm
0x180019758  mov     [rsp-8+arg_8], rbx
0x18001975d  push    rbp
0x18001975e  push    rsi
0x18001975f  push    rdi
0x180019760  push    r12
0x180019762  push    r13
0x180019764  push    r14
0x180019766  push    r15
0x180019768  lea     rbp, [rsp-280h]
0x180019770  sub     rsp, 380h
0x180019777  mov     rax, cs:__security_cookie
0x18001977e  xor     rax, rsp
0x180019781  mov     [rbp+2B0h+var_40], rax
0x180019788  mov     r14, [rbp+2B0h+pszDest]
0x18001978f  mov     r15, r8
0x180019792  mov     r12, rcx
0x180019795  mov     ebx, 100h
0x18001979a  mov     r8d, ebx; Size
0x18001979d  lea     rcx, [rsp+3B0h+pszSrc]; void *
0x1800197a2  xor     edx, edx; Val
0x1800197a4  mov     r13, r9
0x1800197a7  call    memset_0
0x1800197ac  xor     eax, eax
0x1800197ae  mov     [rsp+3B0h+cbData], ebx
0x1800197b2  cmp     cs:dword_1800316C0, eax
0x1800197b8  mov     [r14], ax
0x1800197bc  jnz     loc_1800198BE
0x1800197c2  mov     esi, 104h
0x1800197c7  mov     cs:dword_1800316C0, 1
0x1800197d1  mov     edx, esi; uSize
0x1800197d3  lea     rcx, [rbp+2B0h+Buffer]; lpBuffer
0x1800197d7  mov     ebx, 80004005h
0x1800197dc  xor     edi, edi
0x1800197de  call    cs:__imp_GetSystemDirectoryW
0x1800197e4  test    eax, eax
0x1800197e6  jz      loc_1800198B1
0x1800197ec  lea     r8, aTzresDll_0; "\\tzres.dll"
0x1800197f3  mov     edx, esi; cchDest
0x1800197f5  lea     rcx, [rbp+2B0h+Buffer]; pszDest
0x1800197f9  call    StringCchCatW
0x1800197fe  test    eax, eax
0x180019800  js      loc_1800198B1
0x180019806  lea     edx, [rdi+8]; dwLangConvention
0x180019809  mov     r8d, 400h; LangID
0x18001980f  lea     rcx, [rbp+2B0h+Buffer]; pszFullModuleName
0x180019813  call    LoadMUILibraryW
0x180019818  mov     rsi, rax
0x18001981b  test    rax, rax
0x18001981e  jz      loc_1800198B1
0x180019824  xor     eax, eax
0x180019826  lea     r8, [rsp+3B0h+var_378]; pszDest
0x18001982b  xorps   xmm0, xmm0
0x18001982e  mov     [rsp+3B0h+var_358], eax
0x180019832  mov     rdx, r15; lpValueName
0x180019835  mov     cs:dword_1800316C0, eax
0x18001983b  mov     rcx, r12; hKey
0x18001983e  lea     edi, [rax+1]
0x180019841  movups  xmmword ptr [rsp+3B0h+var_378], xmm0
0x180019846  movups  [rsp+3B0h+var_368], xmm0
0x18001984b  call    GetStringFromReg
0x180019850  mov     ebx, eax
0x180019852  test    eax, eax
0x180019854  js      short loc_1800198A8
0x180019856  lea     rdx, [rsp+3B0h+var_380]
0x18001985b  mov     [rsp+3B0h+var_380], 0
0x180019863  lea     rcx, [rsp+3B0h+var_378]; pszSrc
0x180019868  call    FindResourceId
0x18001986d  mov     ebx, eax
0x18001986f  test    eax, eax
0x180019871  js      short loc_1800198A8
0x180019873  mov     r8d, [rsp+3B0h+var_380]
0x180019878  lea     r9, [rsp+3B0h+pszSrc]
0x18001987d  mov     rcx, rsi; hModule
0x180019880  call    LoadStringResource
0x180019885  mov     ebx, eax
0x180019887  test    eax, eax
0x180019889  js      short loc_1800198A8
0x18001988b  mov     edx, dword ptr [rbp+2B0h+cchDest]; cchDest
0x180019891  lea     r8, [rsp+3B0h+pszSrc]; pszSrc
0x180019896  mov     rcx, r14; pszDest
0x180019899  call    StringCchCopyW
0x18001989e  xor     edi, edi
0x1800198a0  mov     ebx, eax
0x1800198a2  test    eax, eax
0x1800198a4  sets    dil
0x1800198a8  mov     rcx, rsi; hLibModule
0x1800198ab  call    cs:__imp_FreeLibrary
0x1800198b1  cmp     cs:dword_1800316C0, 0
0x1800198b8  jnz     short loc_1800198BE
0x1800198ba  test    edi, edi
0x1800198bc  jz      short loc_18001990C
0x1800198be  lea     rax, [rsp+3B0h+cbData]
0x1800198c3  xor     r9d, r9d; lpType
0x1800198c6  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x1800198cb  xor     r8d, r8d; lpReserved
0x1800198ce  lea     rax, [rsp+3B0h+pszSrc]
0x1800198d3  mov     rdx, r13; lpValueName
0x1800198d6  mov     rcx, r12; hKey
0x1800198d9  mov     [rsp+3B0h+lpData], rax; lpData
0x1800198de  mov     ebx, 80004005h
0x1800198e3  call    cs:__imp_RegQueryValueExW
0x1800198e9  test    eax, eax
0x1800198eb  jnz     short loc_18001990C
0x1800198ed  mov     edx, dword ptr [rbp+2B0h+cchDest]; cchDest
0x1800198f3  lea     r8, [rsp+3B0h+pszSrc]; pszSrc
0x1800198f8  mov     rcx, r14; pszDest
0x1800198fb  call    StringCchCopyW
0x180019900  mov     ebx, eax
0x180019902  mov     eax, 40203h
0x180019907  test    ebx, ebx
0x180019909  cmovns  ebx, eax
0x18001990c  mov     eax, ebx
0x18001990e  mov     rcx, [rbp+2B0h+var_40]
0x180019915  xor     rcx, rsp; StackCookie
0x180019918  call    __security_check_cookie
0x18001991d  mov     rbx, [rsp+3B0h+arg_8]
0x180019925  add     rsp, 380h
0x18001992c  pop     r15
0x18001992e  pop     r14
0x180019930  pop     r13
0x180019932  pop     r12
0x180019934  pop     rdi
0x180019935  pop     rsi
0x180019936  pop     rbp
0x180019937  retn
```
