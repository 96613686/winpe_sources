# GetLocalizedName

- ea: `0x1800275e8`
- end: `0x1800277d1`
- name: `GetLocalizedName`
- size: `489`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180026360`
- `0x180028220`

## callees

- `0x180024910`
- `0x1800255a4`
- `0x1800272f8`
- `0x1800275e8`
- `0x180027e68`
- `0x1800280d8`
- `0x180028c74`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002766e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002766e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027744`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027744`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002777c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002777c`

## string_xrefs

- `0x18002767c`: `\tzres.dll`

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
  v9 = dword_18003B030 == 0;
  *pszDest = 0;
  if ( !v9 )
    goto LABEL_12;
  dword_18003B030 = 1;
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
        dword_18003B030 = 0;
        v11 = 1;
        *(_OWORD *)v15 = 0;
        v16 = 0;
        StringFromReg = GetStringFromReg(hKey, a3, v15, 0x12u, 18);
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
  if ( dword_18003B030 || v11 )
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
0x1800275e8  mov     [rsp-8+arg_8], rbx
0x1800275ed  push    rbp
0x1800275ee  push    rsi
0x1800275ef  push    rdi
0x1800275f0  push    r12
0x1800275f2  push    r13
0x1800275f4  push    r14
0x1800275f6  push    r15
0x1800275f8  lea     rbp, [rsp-280h]
0x180027600  sub     rsp, 380h
0x180027607  mov     rax, cs:__security_cookie
0x18002760e  xor     rax, rsp
0x180027611  mov     [rbp+2B0h+var_40], rax
0x180027618  mov     r14, [rbp+2B0h+pszDest]
0x18002761f  mov     r15, r8
0x180027622  mov     r12, rcx
0x180027625  mov     ebx, 100h
0x18002762a  mov     r8d, ebx; Size
0x18002762d  lea     rcx, [rsp+3B0h+pszSrc]; void *
0x180027632  xor     edx, edx; Val
0x180027634  mov     r13, r9
0x180027637  call    memset_0
0x18002763c  xor     eax, eax
0x18002763e  mov     [rsp+3B0h+cbData], ebx
0x180027642  cmp     cs:dword_18003B030, eax
0x180027648  mov     [r14], ax
0x18002764c  jnz     loc_180027757
0x180027652  mov     esi, 104h
0x180027657  mov     cs:dword_18003B030, 1
0x180027661  mov     edx, esi; uSize
0x180027663  lea     rcx, [rbp+2B0h+Buffer]; lpBuffer
0x180027667  mov     ebx, 80004005h
0x18002766c  xor     edi, edi
0x18002766e  call    cs:__imp_GetSystemDirectoryW
0x180027674  test    eax, eax
0x180027676  jz      loc_18002774A
0x18002767c  lea     r8, aTzresDll_0; "\\tzres.dll"
0x180027683  mov     edx, esi; cchDest
0x180027685  lea     rcx, [rbp+2B0h+Buffer]; pszDest
0x180027689  call    StringCchCatW
0x18002768e  test    eax, eax
0x180027690  js      loc_18002774A
0x180027696  lea     edx, [rdi+8]; dwLangConvention
0x180027699  mov     r8d, 400h; LangID
0x18002769f  lea     rcx, [rbp+2B0h+Buffer]; pszFullModuleName
0x1800276a3  call    LoadMUILibraryW
0x1800276a8  mov     rsi, rax
0x1800276ab  test    rax, rax
0x1800276ae  jz      loc_18002774A
0x1800276b4  xor     eax, eax
0x1800276b6  lea     r8, [rsp+3B0h+var_378]; pszDest
0x1800276bb  xorps   xmm0, xmm0
0x1800276be  mov     [rsp+3B0h+var_358], eax
0x1800276c2  mov     rdx, r15; lpValueName
0x1800276c5  mov     cs:dword_18003B030, eax
0x1800276cb  mov     rcx, r12; hKey
0x1800276ce  lea     r9d, [rax+12h]; cchDest
0x1800276d2  mov     dword ptr [rsp+3B0h+lpData], r9d; int
0x1800276d7  lea     edi, [rax+1]
0x1800276da  movups  xmmword ptr [rsp+3B0h+var_378], xmm0
0x1800276df  movups  [rsp+3B0h+var_368], xmm0
0x1800276e4  call    GetStringFromReg
0x1800276e9  mov     ebx, eax
0x1800276eb  test    eax, eax
0x1800276ed  js      short loc_180027741
0x1800276ef  lea     rdx, [rsp+3B0h+var_380]
0x1800276f4  mov     [rsp+3B0h+var_380], 0
0x1800276fc  lea     rcx, [rsp+3B0h+var_378]; pszSrc
0x180027701  call    FindResourceId
0x180027706  mov     ebx, eax
0x180027708  test    eax, eax
0x18002770a  js      short loc_180027741
0x18002770c  mov     r8d, [rsp+3B0h+var_380]
0x180027711  lea     r9, [rsp+3B0h+pszSrc]
0x180027716  mov     rcx, rsi; hModule
0x180027719  call    LoadStringResource
0x18002771e  mov     ebx, eax
0x180027720  test    eax, eax
0x180027722  js      short loc_180027741
0x180027724  mov     edx, dword ptr [rbp+2B0h+cchDest]; cchDest
0x18002772a  lea     r8, [rsp+3B0h+pszSrc]; pszSrc
0x18002772f  mov     rcx, r14; pszDest
0x180027732  call    StringCchCopyW
0x180027737  xor     edi, edi
0x180027739  mov     ebx, eax
0x18002773b  test    eax, eax
0x18002773d  sets    dil
0x180027741  mov     rcx, rsi; hLibModule
0x180027744  call    cs:__imp_FreeLibrary
0x18002774a  cmp     cs:dword_18003B030, 0
0x180027751  jnz     short loc_180027757
0x180027753  test    edi, edi
0x180027755  jz      short loc_1800277A5
0x180027757  lea     rax, [rsp+3B0h+cbData]
0x18002775c  xor     r9d, r9d; lpType
0x18002775f  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x180027764  xor     r8d, r8d; lpReserved
0x180027767  lea     rax, [rsp+3B0h+pszSrc]
0x18002776c  mov     rdx, r13; lpValueName
0x18002776f  mov     rcx, r12; hKey
0x180027772  mov     [rsp+3B0h+lpData], rax; lpData
0x180027777  mov     ebx, 80004005h
0x18002777c  call    cs:__imp_RegQueryValueExW
0x180027782  test    eax, eax
0x180027784  jnz     short loc_1800277A5
0x180027786  mov     edx, dword ptr [rbp+2B0h+cchDest]; cchDest
0x18002778c  lea     r8, [rsp+3B0h+pszSrc]; pszSrc
0x180027791  mov     rcx, r14; pszDest
0x180027794  call    StringCchCopyW
0x180027799  mov     ebx, eax
0x18002779b  mov     eax, 40203h
0x1800277a0  test    ebx, ebx
0x1800277a2  cmovns  ebx, eax
0x1800277a5  mov     eax, ebx
0x1800277a7  mov     rcx, [rbp+2B0h+var_40]
0x1800277ae  xor     rcx, rsp; StackCookie
0x1800277b1  call    __security_check_cookie
0x1800277b6  mov     rbx, [rsp+3B0h+arg_8]
0x1800277be  add     rsp, 380h
0x1800277c5  pop     r15
0x1800277c7  pop     r14
0x1800277c9  pop     r13
0x1800277cb  pop     r12
0x1800277cd  pop     rdi
0x1800277ce  pop     rsi
0x1800277cf  pop     rbp
0x1800277d0  retn
```
