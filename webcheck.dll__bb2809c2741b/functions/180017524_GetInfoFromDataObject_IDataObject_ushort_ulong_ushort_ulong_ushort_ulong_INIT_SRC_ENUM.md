# GetInfoFromDataObject(IDataObject *,ushort *,ulong,ushort *,ulong,ushort *,ulong,INIT_SRC_ENUM *)

- ea: `0x180017524`
- end: `0x180017773`
- name: `?GetInfoFromDataObject@@YAJPEAUIDataObject@@PEAGK1K1KPEAW4INIT_SRC_ENUM@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(struct IDataObject *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, LPWSTR lpszBuffer, unsigned int, enum INIT_SRC_ENUM *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180017870`

## callees

- `0x180003950`
- `0x180017524`
- `0x180026684`
- `0x180027384`
- `0x180027718`
- `0x180028650`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!PathStripPathW` at `0x18001763e`
- `SHLWAPI!PathStripPathW` at `0x18001763e`
- `SHLWAPI!PathIsDirectoryW` at `0x180017673`
- `SHLWAPI!PathIsDirectoryW` at `0x180017673`
- `ole32!ReleaseStgMedium` at `0x18001774a`
- `ole32!ReleaseStgMedium` at `0x18001774a`
- `WININET!InternetCanonicalizeUrlW` at `0x180017723`
- `WININET!InternetCanonicalizeUrlW` at `0x180017723`
- `SHELL32!DragQueryFileW` at `0x1800175fd`
- `SHELL32!DragQueryFileW` at `0x1800175fd`

## pseudocode

```c
__int64 __fastcall GetInfoFromDataObject(
        struct IDataObject *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        LPWSTR lpszBuffer,
        unsigned int a7,
        enum INIT_SRC_ENUM *a8)
{
  unsigned int v10; // ebx
  size_t v11; // rdx
  size_t v12; // rdx
  const WCHAR *v13; // rcx
  const WCHAR *v14; // rdx
  ULONG v16; // [rsp+20h] [rbp-E0h]
  DWORD dwBufferLength; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v18; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+3Ah] [rbp-C6h]
  __int16 v20; // [rsp+3Eh] [rbp-C2h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+4Ch] [rbp-B4h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  STGMEDIUM hDrop; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szFile[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR szUrl[2088]; // [rsp+490h] [rbp+390h] BYREF

  v22 = 1;
  v18 = 15;
  v23 = -1;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v24 = 1;
  memset(&hDrop, 0, sizeof(hDrop));
  if ( a2 )
    *a2 = 0;
  if ( a4 )
    *a4 = 0;
  if ( lpszBuffer )
    *lpszBuffer = 0;
  v10 = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a1->lpVtbl->GetData)(a1, &v18, &hDrop);
  if ( !v10 )
  {
    if ( !DragQueryFileW((HDROP)hDrop.hBitmap, 0, szFile, 0x104u) )
      goto LABEL_24;
    if ( a2 )
      StringCchCopyW(a2, 0x104u, szFile);
    StringCchCopyW(pszPath, 0x104u, szFile);
    if ( a4 )
    {
      PathStripPathW(szFile);
      PathCchRemoveExtension(szFile, v11);
      StringCchCopyW(a4, 0x104u, szFile);
    }
    if ( !lpszBuffer && !a8 )
      goto LABEL_25;
    if ( PathIsDirectoryW(pszPath) )
    {
      PathIsUnc2(L"desktop.ini");
      PathCchCombineEx(pszPath, v12, pszPath, L"desktop.ini", v16);
      v13 = L"Channel";
      v14 = L"CDFURL";
      if ( a8 )
        *(_DWORD *)a8 = 2;
    }
    else
    {
      v13 = L"InternetShortcut";
      v14 = L"URL";
      if ( a8 )
        *(_DWORD *)a8 = 1;
    }
    if ( !lpszBuffer )
      goto LABEL_25;
    if ( (unsigned int)g_pfn_SHGetIniStringW(v13, v14, szUrl, 0x824u, pszPath) )
    {
      dwBufferLength = 2084;
      if ( !InternetCanonicalizeUrlW(szUrl, lpszBuffer, &dwBufferLength, 0x20000000u) )
        StringCchCopyW(lpszBuffer, 0x824u, szUrl);
    }
    else
    {
LABEL_24:
      v10 = -2147467259;
    }
LABEL_25:
    ReleaseStgMedium(&hDrop);
  }
  return v10;
}

```

## disassembly

```asm
0x180017524  push    rbp
0x180017526  push    rbx
0x180017527  push    rsi
0x180017528  push    rdi
0x180017529  push    r12
0x18001752b  push    r14
0x18001752d  push    r15
0x18001752f  lea     rbp, [rsp-13F0h]
0x180017537  mov     eax, 14F0h
0x18001753c  call    _alloca_probe
0x180017541  sub     rsp, rax
0x180017544  mov     rax, cs:__security_cookie
0x18001754b  xor     rax, rsp
0x18001754e  mov     [rbp+1420h+var_40], rax
0x180017555  mov     rdi, [rbp+1420h+lpszBuffer]
0x18001755c  xor     eax, eax
0x18001755e  mov     rsi, [rbp+1420h+arg_38]
0x180017565  xorps   xmm0, xmm0
0x180017568  mov     [rsp+1520h+var_14B8], rax
0x18001756d  mov     r14, r9
0x180017570  mov     eax, 0Fh
0x180017575  mov     [rsp+1520h+var_14D8], 1
0x18001757d  mov     [rsp+1520h+var_14E8], ax
0x180017582  mov     r15, rdx
0x180017585  xor     eax, eax
0x180017587  mov     [rsp+1520h+var_14D4], 0FFFFFFFFh
0x18001758f  mov     [rsp+1520h+var_14E6], eax
0x180017593  mov     [rsp+1520h+var_14E2], ax
0x180017598  mov     [rsp+1520h+var_14E0], rax
0x18001759d  mov     [rsp+1520h+var_14D0], 1
0x1800175a6  movups  xmmword ptr [rsp+1520h+hDrop], xmm0
0x1800175ab  test    rdx, rdx
0x1800175ae  jz      short loc_1800175B3
0x1800175b0  mov     [rdx], ax
0x1800175b3  test    r14, r14
0x1800175b6  jz      short loc_1800175BE
0x1800175b8  xor     eax, eax
0x1800175ba  mov     [r9], ax
0x1800175be  test    rdi, rdi
0x1800175c1  jz      short loc_1800175C8
0x1800175c3  xor     eax, eax
0x1800175c5  mov     [rdi], ax
0x1800175c8  mov     rax, [rcx]
0x1800175cb  lea     r8, [rsp+1520h+hDrop]
0x1800175d0  lea     rdx, [rsp+1520h+var_14E8]
0x1800175d5  mov     rax, [rax+18h]
0x1800175d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175de  mov     ebx, eax
0x1800175e0  test    eax, eax
0x1800175e2  jnz     loc_180017750
0x1800175e8  mov     rcx, [rsp+1520h+hDrop+8]; hDrop
0x1800175ed  lea     r8, [rsp+1520h+szFile]; lpszFile
0x1800175f2  mov     r12d, 104h
0x1800175f8  xor     edx, edx; iFile
0x1800175fa  mov     r9d, r12d; cch
0x1800175fd  call    cs:__imp_DragQueryFileW
0x180017603  test    eax, eax
0x180017605  jz      loc_180017740
0x18001760b  test    r15, r15
0x18001760e  jz      short loc_180017620
0x180017610  lea     r8, [rsp+1520h+szFile]; unsigned __int16 *
0x180017615  mov     edx, r12d; unsigned __int64
0x180017618  mov     rcx, r15; unsigned __int16 *
0x18001761b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017620  lea     r8, [rsp+1520h+szFile]; unsigned __int16 *
0x180017625  mov     rdx, r12; unsigned __int64
0x180017628  lea     rcx, [rbp+1420h+pszPath]; unsigned __int16 *
0x18001762f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017634  test    r14, r14
0x180017637  jz      short loc_18001765E
0x180017639  lea     rcx, [rsp+1520h+szFile]; pszPath
0x18001763e  call    cs:__imp_PathStripPathW
0x180017644  lea     rcx, [rsp+1520h+szFile]; pszPath
0x180017649  call    PathCchRemoveExtension
0x18001764e  lea     r8, [rsp+1520h+szFile]; unsigned __int16 *
0x180017653  mov     rdx, r12; unsigned __int64
0x180017656  mov     rcx, r14; unsigned __int16 *
0x180017659  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001765e  test    rdi, rdi
0x180017661  jnz     short loc_18001766C
0x180017663  test    rsi, rsi
0x180017666  jz      loc_180017745
0x18001766c  lea     rcx, [rbp+1420h+pszPath]; pszPath
0x180017673  call    cs:__imp_PathIsDirectoryW
0x180017679  test    eax, eax
0x18001767b  jz      short loc_1800176C7
0x18001767d  lea     r8, IsBackslash
0x180017684  xor     edx, edx
0x180017686  lea     rcx, pszMore; "desktop.ini"
0x18001768d  call    PathIsUnc2
0x180017692  lea     r9, pszMore; "desktop.ini"
0x180017699  lea     r8, [rbp+1420h+pszPath]; pszPathIn
0x1800176a0  lea     rcx, [rbp+1420h+pszPath]; pszPathOut
0x1800176a7  call    PathCchCombineEx
0x1800176ac  lea     rcx, aChannel; "Channel"
0x1800176b3  lea     rdx, aCdfurl; "CDFURL"
0x1800176ba  test    rsi, rsi
0x1800176bd  jz      short loc_1800176E0
0x1800176bf  mov     dword ptr [rsi], 2
0x1800176c5  jmp     short loc_1800176E0
0x1800176c7  lea     rcx, AppName; "InternetShortcut"
0x1800176ce  lea     rdx, KeyName; "URL"
0x1800176d5  test    rsi, rsi
0x1800176d8  jz      short loc_1800176E0
0x1800176da  mov     dword ptr [rsi], 1
0x1800176e0  test    rdi, rdi
0x1800176e3  jz      short loc_180017745
0x1800176e5  lea     rax, [rbp+1420h+pszPath]
0x1800176ec  mov     esi, 824h
0x1800176f1  mov     r9d, esi; cwchBuf
0x1800176f4  mov     qword ptr [rsp+1520h+var_1500], rax; LPCWSTR
0x1800176f9  lea     r8, [rbp+1420h+szUrl]; lpReturnedString
0x180017700  call    cs:g_pfn_SHGetIniStringW
0x180017706  test    eax, eax
0x180017708  jz      short loc_180017740
0x18001770a  mov     r9d, 20000000h; dwFlags
0x180017710  mov     [rsp+1520h+dwBufferLength], esi
0x180017714  lea     r8, [rsp+1520h+dwBufferLength]; lpdwBufferLength
0x180017719  mov     rdx, rdi; lpszBuffer
0x18001771c  lea     rcx, [rbp+1420h+szUrl]; lpszUrl
0x180017723  call    cs:__imp_InternetCanonicalizeUrlW
0x180017729  test    eax, eax
0x18001772b  jnz     short loc_180017745
0x18001772d  lea     r8, [rbp+1420h+szUrl]; unsigned __int16 *
0x180017734  mov     edx, esi; unsigned __int64
0x180017736  mov     rcx, rdi; unsigned __int16 *
0x180017739  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001773e  jmp     short loc_180017745
0x180017740  mov     ebx, 80004005h
0x180017745  lea     rcx, [rsp+1520h+hDrop]; LPSTGMEDIUM
0x18001774a  call    cs:__imp_ReleaseStgMedium
0x180017750  mov     eax, ebx
0x180017752  mov     rcx, [rbp+1420h+var_40]
0x180017759  xor     rcx, rsp; StackCookie
0x18001775c  call    __security_check_cookie
0x180017761  add     rsp, 14F0h
0x180017768  pop     r15
0x18001776a  pop     r14
0x18001776c  pop     r12
0x18001776e  pop     rdi
0x18001776f  pop     rsi
0x180017770  pop     rbx
0x180017771  pop     rbp
0x180017772  retn
```
