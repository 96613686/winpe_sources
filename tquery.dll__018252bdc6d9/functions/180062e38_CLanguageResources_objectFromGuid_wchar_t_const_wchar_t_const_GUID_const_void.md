# CLanguageResources::objectFromGuid(wchar_t const *,wchar_t const *,_GUID const &,void * *)

- ea: `0x180062e38`
- end: `0x1800630c1`
- name: `?objectFromGuid@CLanguageResources@@AEAAJPEB_W0AEBU_GUID@@PEAPEAX@Z`
- size: `649`
- prototype: `__int64 __fastcall(CLanguageResources *this, wchar_t *, wchar_t *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180062520`
- `0x180062830`
- `0x1801f4b40`

## callees

- `0x180062e38`
- `0x1800630c8`
- `0x180063848`
- `0x18015aa68`
- `0x180188d90`
- `0x180189280`
- `0x1801f4994`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180062f00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180062f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062fb4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180062f1e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180062f1e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180062ee7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180062ee7`

## string_xrefs

- `0x180062fd2`: `[Index] LoadLibrary for language resource dll %ws failed 0x%x \n`
- `0x180062f9a`: `[Index] GetProcAddress of DllGetClassObject for language resource dll %ws failed 0x%x \n`
- `0x180062ef6`: `DllGetClassObject`
- `0x180062f31`: `[Index] CLSIDFromString for language resource clsid %ws failed 0x%x \n`
- `0x18006304a`: `[Index] Create instance for language resource in dll %ws failed 0x%x \n`

## pseudocode

```c
__int64 __fastcall CLanguageResources::objectFromGuid(
        CLanguageResources *this,
        wchar_t *a2,
        wchar_t *a3,
        const struct _GUID *a4,
        void **a5)
{
  const wchar_t *v8; // rax
  signed __int64 v9; // r8
  int v10; // ecx
  int v11; // edx
  void *v13; // rbx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // r14
  HRESULT v16; // eax
  unsigned int v17; // edi
  signed int LastError; // eax
  signed int v19; // eax
  __int64 v20; // rax
  void *v21; // rax
  int v22; // eax
  __int64 v23; // [rsp+20h] [rbp-E0h]
  void *v24; // [rsp+30h] [rbp-D0h] BYREF
  void *v25; // [rsp+38h] [rbp-C8h]
  GUID pclsid; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+58h] [rbp-A8h]
  _BYTE v29[528]; // [rsp+60h] [rbp-A0h] BYREF

  v8 = L"{00000000-0000-0000-0000-000000000000}";
  v9 = (char *)a2 - (char *)L"{00000000-0000-0000-0000-000000000000}";
  do
  {
    v10 = *(const wchar_t *)((char *)v8 + v9);
    v11 = *v8 - v10;
    if ( v11 )
      break;
    ++v8;
  }
  while ( v10 );
  if ( !v11 )
    return 2147751957LL;
  v24 = 0;
  v13 = 0;
  v25 = 0;
  v27 = 260;
  lpLibFileName = (LPCWSTR)v29;
  XGrowable<wchar_t,260>::SetSize(&v27, 260);
  DllFromClsid(a2, a3, (__int64)&v27);
  LibraryW = LoadLibraryW(lpLibFileName);
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject");
    if ( ProcAddress )
    {
      pclsid = 0;
      v16 = CLSIDFromString(a2, &pclsid);
      v17 = v16;
      if ( v16 >= 0 )
      {
        v17 = ((__int64 (__fastcall *)(GUID *, GUID *, void **))ProcAddress)(&pclsid, &IID_IClassFactory, &v24);
        v13 = v24;
        v25 = v24;
        if ( v17 )
          goto LABEL_27;
        if ( v24 )
        {
LABEL_21:
          v20 = *(_QWORD *)&IID_IClassFactory.Data1 - *(_QWORD *)&a4->Data1;
          if ( *(_QWORD *)&IID_IClassFactory.Data1 == *(_QWORD *)&a4->Data1 )
            v20 = *(_QWORD *)IID_IClassFactory.Data4 - *(_QWORD *)a4->Data4;
          if ( v20 )
          {
            v22 = (*(__int64 (__fastcall **)(void *, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v13 + 24LL))(
                    v13,
                    0,
                    a4,
                    a5);
            v17 = v22;
            if ( v22 < 0 )
            {
              LODWORD(v23) = v22;
              SearchIndexerDebug::Error(
                (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
                (const wchar_t *)0x623,
                (unsigned int)L"[Index] Create instance for language resource in dll %ws failed 0x%x \n",
                lpLibFileName,
                v23);
            }
          }
          else
          {
            v21 = v13;
            v13 = 0;
            *a5 = v21;
          }
          goto LABEL_27;
        }
        v17 = -2147467259;
      }
      else
      {
        SearchIndexerDebug::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
          (const wchar_t *)0x5F1,
          (unsigned int)L"[Index] CLSIDFromString for language resource clsid %ws failed 0x%x \n",
          a2,
          v16);
      }
    }
    else
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
        (const wchar_t *)0x60E,
        (unsigned int)L"[Index] GetProcAddress of DllGetClassObject for language resource dll %ws failed 0x%x \n",
        lpLibFileName,
        v17);
    }
  }
  else
  {
    v19 = GetLastError();
    v17 = v19;
    if ( v19 > 0 )
      v17 = (unsigned __int16)v19 | 0x80070000;
    SearchIndexerDebug::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\filtereg\\languageresources.cxx",
      (const wchar_t *)0x614,
      (unsigned int)L"[Index] LoadLibrary for language resource dll %ws failed 0x%x \n",
      lpLibFileName,
      v17);
    SearchIndexerTelemetryAggregatedLow::ErrorLoadingWordBreaker(v17, a2, lpLibFileName);
  }
  if ( !v17 )
    goto LABEL_21;
LABEL_27:
  if ( lpLibFileName != (LPCWSTR)v29 )
  {
    operator delete((void *)lpLibFileName);
    lpLibFileName = (LPCWSTR)v29;
    v27 = 260;
  }
  if ( v13 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  return v17;
}

```

## disassembly

```asm
0x180062e38  push    rbp
0x180062e3a  push    rbx
0x180062e3b  push    rsi
0x180062e3c  push    rdi
0x180062e3d  push    r12
0x180062e3f  push    r14
0x180062e41  push    r15
0x180062e43  lea     rbp, [rsp-180h]
0x180062e4b  sub     rsp, 280h
0x180062e52  mov     rax, cs:__security_cookie
0x180062e59  xor     rax, rsp
0x180062e5c  mov     [rbp+1B0h+var_40], rax
0x180062e63  mov     r15, r9
0x180062e66  mov     rdi, r8
0x180062e69  mov     rsi, rdx
0x180062e6c  mov     r12, [rbp+1B0h+arg_20]
0x180062e73  lea     rax, a00000000000000_1; "{00000000-0000-0000-0000-000000000000}"
0x180062e7a  mov     r8, rdx
0x180062e7d  sub     r8, rax
0x180062e80  movzx   edx, word ptr [rax]
0x180062e83  movzx   ecx, word ptr [rax+r8]
0x180062e88  sub     edx, ecx
0x180062e8a  jnz     short loc_180062E94
0x180062e8c  add     rax, 2
0x180062e90  test    ecx, ecx
0x180062e92  jnz     short loc_180062E80
0x180062e94  test    edx, edx
0x180062e96  jnz     short loc_180062EA2
0x180062e98  mov     eax, 80041815h
0x180062e9d  jmp     loc_1800630A0
0x180062ea2  mov     [rsp+2B0h+var_280], 0
0x180062eab  xor     ebx, ebx
0x180062ead  mov     [rsp+2B0h+var_278], rbx
0x180062eb2  mov     ecx, 104h
0x180062eb7  mov     [rsp+2B0h+var_260], ecx
0x180062ebb  lea     rax, [rsp+2B0h+var_250]
0x180062ec0  mov     [rsp+2B0h+lpLibFileName], rax
0x180062ec5  mov     edx, ecx
0x180062ec7  lea     rcx, [rsp+2B0h+var_260]
0x180062ecc  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x180062ed1  nop
0x180062ed2  lea     r8, [rsp+2B0h+var_260]
0x180062ed7  mov     rdx, rdi; wchar_t *
0x180062eda  mov     rcx, rsi; wchar_t *
0x180062edd  call    ?DllFromClsid@@YAXPEB_W0AEAV?$XGrowable@_W$0BAE@@@@Z; DllFromClsid(wchar_t const *,wchar_t const *,XGrowable<wchar_t,260> &)
0x180062ee2  mov     rcx, [rsp+2B0h+lpLibFileName]; lpLibFileName
0x180062ee7  call    cs:__imp_LoadLibraryW
0x180062eed  test    rax, rax
0x180062ef0  jz      loc_180062FB4
0x180062ef6  lea     rdx, ProcName; "DllGetClassObject"
0x180062efd  mov     rcx, rax; hModule
0x180062f00  call    cs:__imp_GetProcAddress
0x180062f06  mov     r14, rax
0x180062f09  test    rax, rax
0x180062f0c  jz      short loc_180062F7C
0x180062f0e  xorps   xmm0, xmm0
0x180062f11  movups  xmmword ptr [rsp+2B0h+pclsid.Data1], xmm0
0x180062f16  lea     rdx, [rsp+2B0h+pclsid]; pclsid
0x180062f1b  mov     rcx, rsi; lpsz
0x180062f1e  call    cs:__imp_CLSIDFromString
0x180062f24  mov     edi, eax
0x180062f26  test    eax, eax
0x180062f28  jns     short loc_180062F3F
0x180062f2a  mov     [rsp+2B0h+var_290], eax
0x180062f2e  mov     r9, rsi
0x180062f31  lea     r8, aIndexClsidfrom; "[Index] CLSIDFromString for language re"...
0x180062f38  mov     edx, 5F1h
0x180062f3d  jmp     short loc_180062FA6
0x180062f3f  lea     r8, [rsp+2B0h+var_280]
0x180062f44  lea     rdx, IID_IClassFactory
0x180062f4b  lea     rcx, [rsp+2B0h+pclsid]
0x180062f50  mov     rax, r14
0x180062f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f58  mov     edi, eax
0x180062f5a  mov     rbx, [rsp+2B0h+var_280]
0x180062f5f  mov     [rsp+2B0h+var_278], rbx
0x180062f64  test    eax, eax
0x180062f66  jnz     loc_180063063
0x180062f6c  test    rbx, rbx
0x180062f6f  jnz     loc_180062FFD
0x180062f75  mov     edi, 80004005h
0x180062f7a  jmp     short loc_180062FF9
0x180062f7c  call    cs:__imp_GetLastError
0x180062f82  mov     edi, eax
0x180062f84  test    eax, eax
0x180062f86  jle     short loc_180062F91
0x180062f88  movzx   edi, ax
0x180062f8b  or      edi, 80070000h
0x180062f91  mov     [rsp+2B0h+var_290], edi
0x180062f95  mov     r9, [rsp+2B0h+lpLibFileName]; wchar_t *
0x180062f9a  lea     r8, aIndexGetprocad; "[Index] GetProcAddress of DllGetClassOb"...
0x180062fa1  mov     edx, 60Eh; wchar_t *
0x180062fa6  lea     rcx, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180062fad  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180062fb2  jmp     short loc_180062FF9
0x180062fb4  call    cs:__imp_GetLastError
0x180062fba  mov     edi, eax
0x180062fbc  test    eax, eax
0x180062fbe  jle     short loc_180062FC9
0x180062fc0  movzx   edi, ax
0x180062fc3  or      edi, 80070000h
0x180062fc9  mov     [rsp+2B0h+var_290], edi
0x180062fcd  mov     r9, [rsp+2B0h+lpLibFileName]; wchar_t *
0x180062fd2  lea     r8, aIndexLoadlibra; "[Index] LoadLibrary for language resour"...
0x180062fd9  mov     edx, 614h; wchar_t *
0x180062fde  lea     rcx, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180062fe5  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180062fea  mov     r8, [rsp+2B0h+lpLibFileName]; wchar_t *
0x180062fef  mov     rdx, rsi; wchar_t *
0x180062ff2  mov     ecx, edi; int
0x180062ff4  call    ?ErrorLoadingWordBreaker@SearchIndexerTelemetryAggregatedLow@@SAXJPEB_W0@Z; SearchIndexerTelemetryAggregatedLow::ErrorLoadingWordBreaker(long,wchar_t const *,wchar_t const *)
0x180062ff9  test    edi, edi
0x180062ffb  jnz     short loc_180063063
0x180062ffd  mov     rax, qword ptr cs:IID_IClassFactory.Data1
0x180063004  sub     rax, [r15]
0x180063007  jnz     short loc_180063014
0x180063009  mov     rax, qword ptr cs:IID_IClassFactory.Data4
0x180063010  sub     rax, [r15+8]
0x180063014  test    rax, rax
0x180063017  jnz     short loc_180063024
0x180063019  mov     rax, rbx
0x18006301c  xor     ebx, ebx
0x18006301e  mov     [r12], rax
0x180063022  jmp     short loc_180063063
0x180063024  mov     rax, [rbx]
0x180063027  mov     r9, r12
0x18006302a  mov     r8, r15
0x18006302d  xor     edx, edx
0x18006302f  mov     rcx, rbx
0x180063032  mov     rax, [rax+18h]
0x180063036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006303b  mov     edi, eax
0x18006303d  test    eax, eax
0x18006303f  jns     short loc_180063063
0x180063041  mov     [rsp+2B0h+var_290], eax
0x180063045  mov     r9, [rsp+2B0h+lpLibFileName]; wchar_t *
0x18006304a  lea     r8, aIndexCreateIns; "[Index] Create instance for language re"...
0x180063051  mov     edx, 623h; wchar_t *
0x180063056  lea     rcx, aOnecoreuapBase_161; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18006305d  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180063062  nop
0x180063063  lea     rax, [rsp+2B0h+var_250]
0x180063068  mov     rcx, [rsp+2B0h+lpLibFileName]; Block
0x18006306d  cmp     rcx, rax
0x180063070  jz      short loc_180063089
0x180063072  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180063077  lea     rax, [rsp+2B0h+var_250]
0x18006307c  mov     [rsp+2B0h+lpLibFileName], rax
0x180063081  mov     [rsp+2B0h+var_260], 104h
0x180063089  test    rbx, rbx
0x18006308c  jz      short loc_18006309E
0x18006308e  mov     rax, [rbx]
0x180063091  mov     rcx, rbx
0x180063094  mov     rax, [rax+10h]
0x180063098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006309d  nop
0x18006309e  mov     eax, edi
0x1800630a0  mov     rcx, [rbp+1B0h+var_40]
0x1800630a7  xor     rcx, rsp; StackCookie
0x1800630aa  call    __security_check_cookie
0x1800630af  add     rsp, 280h
0x1800630b6  pop     r15
0x1800630b8  pop     r14
0x1800630ba  pop     r12
0x1800630bc  pop     rdi
0x1800630bd  pop     rsi
0x1800630be  pop     rbx
0x1800630bf  pop     rbp
0x1800630c0  retn
```
