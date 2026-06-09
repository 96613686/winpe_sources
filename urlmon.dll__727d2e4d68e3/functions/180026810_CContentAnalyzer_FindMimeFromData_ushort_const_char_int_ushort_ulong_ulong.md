# CContentAnalyzer::FindMimeFromData(ushort const *,char *,int,ushort *,ulong,ulong *)

- ea: `0x180026810`
- end: `0x180027d01`
- name: `?FindMimeFromData@CContentAnalyzer@@QEAAPEBGPEBGPEADHPEAGKPEAK@Z`
- size: `5361`
- prototype: `const unsigned __int16 *__fastcall(CContentAnalyzer *this, const unsigned __int16 *, const WCHAR *, int, unsigned __int16 *Str, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025e40`
- `0x180026330`
- `0x18002855c`

## callees

- `0x18001db50`
- `0x180025a18`
- `0x180025c30`
- `0x180026810`
- `0x180027d10`
- `0x180028510`
- `0x180031480`
- `0x18003e100`
- `0x180064fc8`
- `0x180065464`
- `0x18006585c`
- `0x180078538`
- `0x1800807f0`
- `0x1800940e4`
- `0x1800a36b4`
- `0x1800ac8ec`
- `0x1800ac95c`
- `0x1800f6c9c`
- `0x1800f6d20`
- `0x1800f6d7c`
- `0x1800f6dfc`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!bsearch` at `0x18002783a`
- `msvcrt!bsearch` at `0x18002783a`
- `msvcrt!wcsrchr` at `0x180026961`
- `msvcrt!wcsrchr` at `0x180026961`
- `msvcrt!wcsstr` at `0x1800268fe`
- `msvcrt!wcsstr` at `0x1800268fe`
- `iertutil!CreateUri` at `0x1800272da`
- `iertutil!CreateUri` at `0x1800272da`
- `iertutil!__imp_IECompatLogEvent` at `0x180027a39`
- `iertutil!__imp_IECompatLogEvent` at `0x180027a39`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002686d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18002686d`
- `iertutil!__imp_?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ` at `0x18002698c`
- `iertutil!__imp_?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ` at `0x18002698c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026eba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800269ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026eba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026f77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800269bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ea0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800269bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026ea0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002763b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002765f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180027683`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800276a3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800276c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800276e3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002763b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002765f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180027683`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800276a3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800276c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800276e3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x180026f11`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x180026f11`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800275cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180027801`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800275cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180027801`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d1f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d44`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d69`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d8e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180027469`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d1f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d44`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d69`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180026d8e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x180027469`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x1800279ac`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x1800279ac`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180026925`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180026dea`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800271dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027200`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027234`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027257`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027365`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027388`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002740e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027525`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027556`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002758c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800275af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002773e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002775c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002779d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800278b5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027924`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002794b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002797f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027a85`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027aae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027af8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027b0e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027baf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027bca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027bfe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027c48`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027c67`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027c8a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027ca8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027ccd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180026925`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180026dea`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800271dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027200`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027234`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027257`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027365`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027388`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002740e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027525`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027556`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002758c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800275af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002773e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002775c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002779d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800278b5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027924`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002794b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002797f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027a85`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027aae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027af8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027b0e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027baf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027bca`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027bfe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027c48`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027c67`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027c8a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027ca8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180027ccd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ff8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027029`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ff8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027029`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026c4a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026e32`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026e72`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026c4a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026e32`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026e72`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002719d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002719d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002787f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002787f`
- `OLEAUT32!__imp_SysFreeString` at `0x180027cec`
- `OLEAUT32!__imp_SysFreeString` at `0x180027cec`

## string_xrefs

- `0x1800270f8`: `application/x-zip-compressed`
- `0x1800271f6`: `application/json`
- `0x1800275a5`: `image/svg+xml`
- `0x18002761b`: `image/svg+xml`
- `0x180027c3d`: `image/svg+xml`
- `0x18002734b`: `application/rss+xml`
- `0x180027404`: `text/xml`
- `0x1800274e6`: `text/xml`
- `0x180027734`: `text/xml`
- `0x180027a7b`: `text/xml`
- `0x180027a95`: `text/xml`
- `0x180027009`: `multipart/x-mixed-replace`
- `0x18002790e`: `application/atom+xml`
- `0x180027975`: `application/xml`
- `0x180027993`: `application/xml`
- `0x180027aa1`: `application/xml`
- `0x180027752`: `application/xhtml+xml`
- `0x180027770`: `application/xhtml+xml`
- `0x180027c5c`: `application/xhtml+xml`
- `0x1800279f9`: `ImageNotUpgradedToXMLorHTML`

## pseudocode

```c
const unsigned __int16 *__fastcall CContentAnalyzer::FindMimeFromData(
        CContentAnalyzer *this,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        int a4,
        unsigned __int16 *Str,
        unsigned int a6,
        unsigned int *a7)
{
  WCHAR *v8; // rsi
  LPCWSTR v9; // r13
  char Bool; // r15
  _QWORD *ThreadLocalStoragePointer; // rcx
  __int64 v12; // rdi
  wchar_t *v13; // rax
  unsigned __int16 *v14; // rbx
  __int64 v15; // rax
  wchar_t *v16; // rax
  CFeatureCache *v17; // r15
  struct IBrowsingEnvironment *CorrectBrowsingEnvironment; // rax
  char v19; // bl
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned __int64 v22; // rdx
  int IsFeatureEnabledInternal; // eax
  int v24; // ebx
  BOOL v25; // r15d
  int lpVtbl_high; // r15d
  const unsigned __int16 *v27; // r15
  const WCHAR *FileExtensionW; // r13
  unsigned __int64 v29; // rbx
  int v30; // edi
  int v31; // ebx
  int v32; // r12d
  unsigned int *v33; // rbx
  __int64 v34; // rdi
  BOOL v35; // ebx
  CHAR *v37; // rbx
  CHAR v38; // al
  int v39; // edx
  const CHAR *v40; // rcx
  CContentAnalyzer *v41; // rcx
  char v42; // r12
  unsigned int *v43; // rbx
  int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rax
  CHAR *v46; // r13
  CMediaTypeHolder *v47; // r15
  __int64 *v48; // r15
  __int64 v49; // rdx
  __int64 v50; // rbx
  LPCSTR *v51; // rdi
  int v52; // eax
  IUri *v53; // rcx
  int v54; // ebx
  __int64 v55; // rcx
  unsigned int *v56; // rax
  __int64 v57; // rax
  char v58; // dl
  const wchar_t *v59; // rax
  const WCHAR *v60; // rdi
  const WCHAR *v61; // rbx
  unsigned int *v62; // rax
  unsigned __int64 i; // rbx
  unsigned int *v64; // rax
  unsigned int *v65; // rax
  const WCHAR *v66; // rax
  unsigned __int64 j; // rbx
  unsigned int *v68; // rax
  PSTR v69; // rax
  bool v70; // zf
  unsigned int *v71; // rax
  unsigned int *v72; // rax
  unsigned __int16 v73; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v74; // [rsp+48h] [rbp-B8h]
  int v75; // [rsp+50h] [rbp-B0h]
  int v76; // [rsp+54h] [rbp-ACh]
  int v77; // [rsp+58h] [rbp-A8h]
  unsigned int v78; // [rsp+5Ch] [rbp-A4h] BYREF
  LPCWSTR pszStr1; // [rsp+60h] [rbp-A0h]
  IUri *ppURI; // [rsp+68h] [rbp-98h] BYREF
  BOOL v81; // [rsp+70h] [rbp-90h]
  unsigned int v82; // [rsp+74h] [rbp-8Ch] BYREF
  LPCWCH lpWideCharStr; // [rsp+78h] [rbp-88h]
  unsigned int v84; // [rsp+80h] [rbp-80h]
  _QWORD v85[2]; // [rsp+88h] [rbp-78h] BYREF
  void **v86; // [rsp+98h] [rbp-68h] BYREF
  __int64 v87; // [rsp+A0h] [rbp-60h]
  int v88; // [rsp+A8h] [rbp-58h]
  BSTR bstrString[2]; // [rsp+B0h] [rbp-50h]
  int v90; // [rsp+C0h] [rbp-40h]
  _QWORD v91[3]; // [rsp+C8h] [rbp-38h] BYREF
  CHAR MultiByteStr[272]; // [rsp+E0h] [rbp-20h] BYREF
  char v93[272]; // [rsp+1F0h] [rbp+F0h] BYREF

  v8 = Str;
  v74 = a7;
  v9 = a3;
  v77 = a4;
  pszStr1 = a3;
  lpWideCharStr = a2;
  Bool = IEConfiguration_GetBool(536870927);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  LOBYTE(v73) = Bool;
  if ( dword_180172698 > *(_DWORD *)(ThreadLocalStoragePointer[tls_index] + 4LL) )
  {
    Init_thread_header(&dword_180172698);
    if ( dword_180172698 == -1 )
    {
      dword_18017269C = HelperAddUriDefaultFlags(0x3002B80u, 4u) & 0xFFFFFFFE;
      Init_thread_footer(&dword_180172698);
    }
  }
  v86 = &CUString::`vftable';
  v87 = 0;
  v12 = -1;
  v88 = 11;
  v90 = 0;
  v82 = 0;
  *((_DWORD *)this + 16) = a6;
  *(_OWORD *)bstrString = 0;
  if ( Str )
  {
    v13 = wcsstr(Str, L";");
    v14 = v13;
    if ( v13 )
      *v13 = 0;
    if ( Bool && StrCmpICW(Str, L"(null)") )
    {
      if ( !v14 )
      {
        v15 = -1;
        do
          v70 = Str[++v15] == 0;
        while ( !v70 );
        v14 = &Str[v15];
      }
      for ( ; v14 != Str; *v14 = 0 )
      {
        v55 = *--v14;
        if ( (unsigned __int16)(v55 - 32) > 0x3Fu )
          break;
        if ( *((_BYTE *)L"ms-local-stream" + v55) != 1 )
          break;
      }
      v16 = wcsrchr(Str, 0x2Cu);
      if ( v16 )
        v8 = v16 + 1;
    }
  }
  v17 = g_pFeatureCache;
  if ( g_pFeatureCache )
  {
    if ( (*(_BYTE *)g_pFeatureCache & 8) == 0 )
    {
      CorrectBrowsingEnvironment = GetCorrectBrowsingEnvironment();
      v19 = (*(__int64 (__fastcall **)(struct IBrowsingEnvironment *, __int64, __int64 (__fastcall *)(enum _tagINTERNETFEATURELIST)))(*(_QWORD *)CorrectBrowsingEnvironment + 8LL))(
              CorrectBrowsingEnvironment,
              3,
              __CoInternetIsFeatureEnabledInternal_IFL);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v17 + 16));
      v20 = *((_QWORD *)v17 + 1);
      v21 = v20 | 8;
      v22 = v20 & 0xFFFFFFFFFFFFFFF7uLL;
      if ( !v19 )
        v21 = v22;
      *(_QWORD *)v17 |= 8uLL;
      *((_QWORD *)v17 + 1) = v21;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v17 + 16));
    }
    IsFeatureEnabledInternal = ((unsigned __int8)~*((_BYTE *)v17 + 8) >> 3) & 1;
  }
  else
  {
    IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING);
  }
  v24 = v77;
  v25 = 0;
  if ( (a6 & 2) == 0 )
    v25 = IsFeatureEnabledInternal != 1;
  v81 = v25;
  if ( v9 && v77 > 0 )
  {
    *((_QWORD *)this + 4) = v9;
    *((_DWORD *)this + 1) = v24;
    v57 = (unsigned int)v24;
    if ( v24 > 256 )
      v57 = 256;
    *(_DWORD *)this = v57;
    *((_BYTE *)this + 40) = *((_BYTE *)v9 + v57 - 1);
    *((_BYTE *)v9 + v57 - 1) = 0;
  }
  if ( (a6 & 0x80u) != 0 )
  {
    *((_QWORD *)this + 7) = L"text/plain";
    *v74 = 16;
    goto LABEL_46;
  }
  v78 = a6 & 0x40;
  if ( v8 && (!StrCmpICW(v8, L"application/json") || (_BYTE)v73 && !v78 && !StrCmpICW(v8, L"text/html")) )
    goto LABEL_169;
  v84 = a6 & 4;
  if ( v25 )
  {
    if ( (a6 & 4) == 0 && v8 && !StrCmpICW(v8, L"text/plain") )
      goto LABEL_169;
  }
  if ( (a6 & 8) != 0 )
  {
    if ( !(_BYTE)v73 || v24 <= 0 )
      goto LABEL_169;
    if ( v8 )
    {
      if ( !StrCmpNICW(v8, L"image/", 6)
        || (ppURI = (IUri *)v8,
            bsearch(
              &ppURI,
              off_180131F30,
              0x33u,
              8u,
              (_CoreCrtNonSecureSearchSortCompareFunction)CContentAnalyzer::s_BinarySearchStringCompare)) )
      {
        if ( CContentAnalyzer::CheckBinaryImageHeaders((LPCSTR *)this, v73) )
          goto LABEL_47;
      }
    }
    if ( !CContentAnalyzer::IsM3UPlaylistMimeType(v8) )
    {
LABEL_169:
      v65 = v74;
      *((_QWORD *)this + 7) = v8;
      *v65 = 16;
      goto LABEL_46;
    }
  }
  if ( !v8 || !StrCmpICW(v8, L"(null)") )
  {
    lpVtbl_high = 1;
    v76 = 1;
    goto LABEL_29;
  }
  EnterCriticalSection(&g_mxsMedia);
  lpVtbl_high = 0;
  cbMultiByte = WideCharToMultiByte(0, 0, v8, -1, 0, 0, 0, 0) + 1;
  lpMultiByteStr = (CHAR *)operator new(cbMultiByte);
  v46 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    InternalRegisterDefaultMediaType();
LABEL_162:
    LeaveCriticalSection(&g_mxsMedia);
    goto LABEL_104;
  }
  if ( !WideCharToMultiByte(0, 0, v8, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    CoTaskMemFree(v46);
    v46 = 0;
  }
  InternalRegisterDefaultMediaType();
  if ( !v46 )
    goto LABEL_162;
  v76 = 0;
  EnterCriticalSection(&g_mxsMedia);
  v47 = g_pCMHolder;
  LeaveCriticalSection(&g_mxsMedia);
  if ( v47 && (v48 = (__int64 *)*((_QWORD *)v47 + 2)) != 0 )
  {
    ppURI = 0;
    v75 = -2147024809;
    do
    {
      v49 = *v48;
      v50 = 0;
      v85[0] = *v48;
      while ( 1 )
      {
        if ( (unsigned int)v50 >= *((_DWORD *)v48 + 4) )
        {
          v52 = v75;
          v53 = ppURI;
          goto LABEL_93;
        }
        v51 = (LPCSTR *)(v49 + 48 * v50);
        if ( !StrCmpICA(v46, *v51) )
          break;
        v49 = v85[0];
        v50 = (unsigned int)(v50 + 1);
      }
      v52 = 0;
      v53 = (IUri *)v51;
      ppURI = (IUri *)v51;
      v75 = 0;
      if ( v51 )
        break;
LABEL_93:
      v48 = (__int64 *)v48[3];
    }
    while ( v48 );
    v54 = v75;
    v12 = -1;
    if ( !v52 )
    {
      lpVtbl_high = HIDWORD(v53[1].lpVtbl);
      v76 = lpVtbl_high;
      goto LABEL_96;
    }
  }
  else
  {
    v54 = -2147467259;
  }
  lpVtbl_high = v76;
LABEL_96:
  CoTaskMemFree(v46);
  LeaveCriticalSection(&g_mxsMedia);
  if ( v54 )
  {
    lpVtbl_high = 0;
LABEL_104:
    v76 = 0;
    goto LABEL_105;
  }
  if ( !lpVtbl_high )
  {
LABEL_105:
    if ( CompareStringW(0x7Fu, 0x1001u, v8, -1, L"multipart/mixed", -1) != 2
      && CompareStringW(0x7Fu, 0x1001u, v8, -1, L"multipart/x-mixed-replace", -1) != 2 )
    {
      v56 = v74;
      *((_QWORD *)this + 7) = v8;
      *v56 = 64;
      goto LABEL_46;
    }
  }
  v9 = pszStr1;
LABEL_29:
  if ( v9 && v77 > 0 )
  {
    v27 = lpWideCharStr;
    FileExtensionW = 0;
    pszStr1 = 0;
    if ( lpWideCharStr )
    {
      ppURI = 0;
      if ( CreateUri(lpWideCharStr, dword_18017269C, 0, &ppURI) < 0 )
        goto LABEL_152;
      if ( !(unsigned int)CUString::Set((CUString *)&v86, ppURI, Uri_PROPERTY_EXTENSION) )
        FileExtensionW = bstrString[1];
      pszStr1 = FileExtensionW;
      ((void (*)(void))ppURI->lpVtbl->Release)();
      if ( !FileExtensionW )
      {
LABEL_152:
        FileExtensionW = FindFileExtensionW(v27);
        pszStr1 = FileExtensionW;
      }
    }
    *v74 = 16;
    CContentAnalyzer::SampleData(this);
    if ( (a6 & 0x10) != 0 && v8 && !StrCmpICW(v8, L"text/plain") )
    {
      if ( *((_DWORD *)this + 29) )
      {
        v68 = v74;
        *((_QWORD *)this + 7) = L"application/octet-stream";
        *v68 = 4;
      }
      else
      {
        *((_QWORD *)this + 7) = v8;
      }
      goto LABEL_47;
    }
    if ( *((_DWORD *)this + 24) || *((_DWORD *)this + 25) && *((_DWORD *)this + 26) && *((_DWORD *)this + 27) )
    {
      *((_QWORD *)this + 7) = L"application/rss+xml";
      goto LABEL_47;
    }
    if ( *((_DWORD *)this + 28) )
    {
      *((_QWORD *)this + 7) = L"application/atom+xml";
      goto LABEL_47;
    }
    if ( v8 )
    {
      if ( !StrCmpICW(v8, L"image/svg+xml") )
      {
        *((_QWORD *)this + 7) = L"image/svg+xml";
        goto LABEL_47;
      }
      if ( !StrCmpNICW(v8, L"image/", 6) )
      {
        if ( (unsigned int)CContentAnalyzer::CheckImageMime((LPCSTR *)this, v8, v73) )
          goto LABEL_47;
        v75 = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_MIME_TREAT_IMAGE_AS_AUTHORITATIVE) != 1;
        goto LABEL_39;
      }
      if ( !StrCmpICW(v8, L"application/pdf") )
      {
        *((_QWORD *)this + 7) = L"application/pdf";
        goto LABEL_47;
      }
    }
    v29 = 0;
    v75 = 0;
    if ( !v8 )
    {
LABEL_38:
      if ( (_BYTE)v73 && v8 && FileExtensionW && !StrCmpICW(v8, L"application/octet-stream") )
      {
        while ( v29 < 0xB )
        {
          if ( !StrCmpICW(FileExtensionW, off_180131D40[v29]) )
            goto LABEL_44;
          ++v29;
        }
      }
      goto LABEL_39;
    }
    if ( StrCmpICW(v8, L"text/html") )
    {
      if ( !StrCmpICW(v8, L"application/xml") )
      {
        *((_QWORD *)this + 7) = L"application/xml";
        goto LABEL_47;
      }
      if ( !StrCmpICW(v8, L"text/xml") )
        goto LABEL_181;
      if ( !StrCmpICW(v8, L"application/xhtml+xml") )
      {
        *((_QWORD *)this + 7) = L"application/xhtml+xml";
        goto LABEL_47;
      }
      goto LABEL_38;
    }
    if ( *((_DWORD *)this + 18) )
    {
      *((_QWORD *)this + 7) = L"text/html";
      goto LABEL_47;
    }
LABEL_39:
    v77 = 0;
    if ( lpWideCharStr )
    {
      if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, 260, 0, 0) )
        MultiByteStr[0] = 0;
      if ( (a6 & 1) != 0 )
      {
        v69 = StrChrA(MultiByteStr, 1u);
        if ( v69 )
          *v69 = 0;
      }
      do
        ++v12;
      while ( MultiByteStr[v12] );
      v37 = &MultiByteStr[v12];
      if ( &MultiByteStr[v12] )
      {
        while ( v37 >= MultiByteStr )
        {
          v38 = *v37;
          if ( *v37 == 47 )
            break;
          if ( v38 == 46 )
          {
            if ( StrCmpNICA(v37, ".application", 12)
              && StrCmpNICA(v37, ".xbap", 5)
              && StrCmpNICA(v37, ".xps", 4)
              && StrCmpNICA(v37, ".xaml", 5)
              && StrCmpNICA(v37, ".hta", 4)
              && StrCmpNICA(v37, ".htc", 4) )
            {
              break;
            }
            v77 = 1;
            if ( !(unsigned int)CContentAnalyzer::FindMimeFromExt(this, pszStr1, &v82) )
              break;
            goto LABEL_207;
          }
          if ( v38 == 92 )
            break;
          --v37;
        }
      }
    }
    v30 = 0;
    v31 = 0;
    if ( v8 )
    {
      if ( !StrCmpICW(v8, L"text/html") || !StrCmpICW(v8, L"text/xml") )
        v31 = 1;
      if ( !StrCmpICW(v8, L"text/plain") )
        v30 = 1;
    }
    if ( g_cmptlgs == 1 )
    {
      v32 = v75;
    }
    else if ( (unsigned int)IECompatLoggingEnabled() && (*((_DWORD *)this + 23) || *((_DWORD *)this + 18)) )
    {
      v32 = v75;
      if ( v75 )
      {
        v85[1] = v8;
        v91[0] = L"FileName";
        v91[1] = L"SuggestedMimeType";
        v85[0] = lpWideCharStr;
        IECompatLogEvent(3221226536LL, L"ImageNotUpgradedToXMLorHTML", 0, 0, 2, v91, v85);
      }
    }
    else
    {
      v32 = v75;
    }
    if ( *((_DWORD *)this + 21) )
    {
LABEL_44:
      *((_QWORD *)this + 7) = L"application/octet-stream";
LABEL_47:
      *(_BYTE *)(*((_QWORD *)this + 4) + *(int *)this - 1LL) = *((_BYTE *)this + 40);
      goto LABEL_48;
    }
    if ( *((_DWORD *)this + 23) && !v32 && (!v81 || v31) )
    {
LABEL_181:
      *((_QWORD *)this + 7) = L"text/xml";
      goto LABEL_47;
    }
    if ( *((_DWORD *)this + 18) && !v32 && (!v81 || v84 && v30) )
    {
      if ( v8 )
      {
        if ( !StrCmpICW(v8, L"text/xml") )
        {
          v66 = L"text/xml";
          goto LABEL_177;
        }
        v70 = StrCmpICW(v8, L"application/xml") == 0;
        v66 = L"application/xml";
        if ( v70 )
          goto LABEL_177;
      }
      v66 = L"text/html";
LABEL_177:
      *((_QWORD *)this + 7) = v66;
      goto LABEL_47;
    }
    if ( *((_DWORD *)this + 20) )
    {
      *((_QWORD *)this + 7) = L"application/macbinhex40";
      goto LABEL_47;
    }
    if ( *((_DWORD *)this + 22) && (!v81 || v8 && (!StrCmpICW(v8, L"text/html") || !StrCmpICW(v8, L"text/scriptlet"))) )
    {
      *((_QWORD *)this + 7) = L"text/scriptlet";
      goto LABEL_47;
    }
    v39 = *((_DWORD *)this + 6);
    if ( v39 && *((_DWORD *)this + 2) + *((_DWORD *)this + 5) < 16 * (v39 + *((_DWORD *)this + 7)) )
    {
      v42 = v73;
      v58 = v73;
      *((_DWORD *)this + 17) = 1;
      if ( !(unsigned int)CContentAnalyzer::CheckBinaryHeaders(this, v58) )
      {
        v43 = v74;
        if ( !(unsigned int)CContentAnalyzer::CheckTextHeaders((LPCSTR *)this, v42) )
        {
          *((_QWORD *)this + 7) = L"application/octet-stream";
          *v43 = 4;
        }
        goto LABEL_119;
      }
LABEL_118:
      v43 = v74;
      goto LABEL_119;
    }
    v40 = (const CHAR *)*((_QWORD *)this + 4);
    *((_DWORD *)this + 17) = 0;
    if ( StrCmpNCA(v40, "%PDF", 4) )
    {
      if ( StrCmpNCA(*((LPCSTR *)this + 4), "%!", 2) )
      {
        if ( StrCmpNCA(*((LPCSTR *)this + 4), "{\\rtf", 5) )
        {
          v42 = v73;
          if ( StrCmpNCA(*((LPCSTR *)this + 4), "begin", 5) )
          {
            if ( !(_BYTE)v73 || StrCmpNCA(*((LPCSTR *)this + 4), "#EXTM3U", 7) || !CContentAnalyzer::IsHlsManifest(this) )
            {
              v43 = v74;
              if ( !(unsigned int)CContentAnalyzer::CheckBinaryHeaders(this, v73) )
              {
                *((_QWORD *)this + 7) = L"text/plain";
                *v43 = 8;
              }
LABEL_119:
              v60 = pszStr1;
              if ( *((wchar_t **)this + 7) == L"application/x-zip-compressed"
                && pszStr1
                && (unsigned int)CContentAnalyzer::IsZipBasedFileExt(v41, pszStr1) )
              {
                *((_QWORD *)this + 7) = L"application/octet-stream";
                *v43 = 4;
              }
              if ( *((const WCHAR **)this + 7) == L"application/octet-stream" && v42 && v78 )
              {
                InitOnceExecuteOnce(&stru_18016AF28, GlobalInitOnceUrlMon, 0, 0);
                if ( (dword_18016B858 & 8) != 0 )
                  goto LABEL_47;
                if ( v60 )
                {
                  for ( i = 0; i < 0xB; ++i )
                  {
                    if ( !StrCmpICW(v60, off_180131D40[i]) )
                      goto LABEL_47;
                  }
                }
              }
              v61 = (const WCHAR *)*((_QWORD *)this + 7);
              v73 = 0;
              v78 = 0;
              if ( v61 && StrCmpICW(v61, L"(null)") && ((unsigned int)FindMediaTypeFormat(v61, &v73, &v78) || v78 != 1) )
                goto LABEL_47;
              switch ( v76 )
              {
                case 1:
LABEL_123:
                  if ( lpWideCharStr && !v77 && (unsigned int)CContentAnalyzer::FindMimeFromExt(this, v60, &v82) )
                  {
                    if ( v8 && StrCmpICW(v8, L"message/rfc822") && !StrCmpICW((LPCWSTR)this + 60, L"message/rfc822") )
                    {
                      v71 = v74;
                      *((_QWORD *)this + 7) = v8;
                      *v71 = 64;
                    }
                    else
                    {
                      if ( v42 && v8 && !StrCmpICW(v8, L"application/octet-stream") )
                      {
                        for ( j = 0; j < 0x17; ++j )
                        {
                          if ( !StrCmpICW((LPCWSTR)this + 60, off_180131DA0[j]) )
                          {
                            v72 = v74;
                            *((_QWORD *)this + 7) = v8;
                            *v72 = 16;
                            goto LABEL_47;
                          }
                        }
                      }
                      if ( !v82
                        || !v8
                        && (!StrCmpICW((LPCWSTR)this + 60, L"image/svg+xml")
                         || !StrCmpICW((LPCWSTR)this + 60, L"application/xhtml+xml")) )
                      {
LABEL_207:
                        *((_QWORD *)this + 7) = (char *)this + 120;
                        *v74 = 2;
                      }
                    }
                  }
                  else if ( v60 && (unsigned int)CContentAnalyzer::FindAppFromExt(v41, v60, v93) )
                  {
                    v62 = v74;
                    *((_QWORD *)this + 7) = L"application/octet-stream";
                    *v62 = 4;
                  }
                  goto LABEL_47;
                case 3:
                  v70 = *((_DWORD *)this + 17) == 0;
                  break;
                case 4:
                  v70 = *((_DWORD *)this + 17) == 1;
                  break;
                case 5:
LABEL_147:
                  v64 = v74;
                  *((_QWORD *)this + 7) = v8;
                  *v64 = 32;
                  goto LABEL_47;
                default:
                  goto LABEL_123;
              }
              if ( !v70 )
                goto LABEL_123;
              goto LABEL_147;
            }
            v59 = L"application/vnd.apple.mpegurl";
          }
          else
          {
            v59 = L"application/base64";
          }
        }
        else
        {
          v42 = v73;
          v59 = L"text/richtext";
        }
        goto LABEL_117;
      }
      v59 = L"application/postscript";
    }
    else
    {
      v59 = L"application/pdf";
    }
    v42 = v73;
LABEL_117:
    *((_QWORD *)this + 7) = v59;
    goto LABEL_118;
  }
  v33 = v74;
  *((_QWORD *)this + 7) = v8;
  *v33 = 16;
  if ( lpVtbl_high == 1 )
  {
    if ( v8 && StrCmpICW(v8, L"(null)") )
    {
      if ( StrCmpICW(v8, L"application/octet-stream") )
      {
        if ( !StrCmpICW(v8, L"text/plain") )
          *v33 = 8;
      }
      else
      {
        *v33 = 4;
      }
    }
    else
    {
      *v33 = 1;
    }
  }
LABEL_46:
  if ( v77 > 0 )
    goto LABEL_47;
LABEL_48:
  v34 = *((_QWORD *)this + 7);
  v86 = &CUString::`vftable';
  v35 = v87 != 0;
  if ( v87 || v88 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v90 = 0;
    if ( v35 && v87 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
  }
  return (const unsigned __int16 *)v34;
}

```

## disassembly

```asm
0x180026810  mov     [rsp-8+arg_10], rbx
0x180026815  push    rbp
0x180026816  push    rsi
0x180026817  push    rdi
0x180026818  push    r12
0x18002681a  push    r13
0x18002681c  push    r14
0x18002681e  push    r15
0x180026820  lea     rbp, [rsp-210h]
0x180026828  sub     rsp, 310h
0x18002682f  mov     rax, cs:__security_cookie
0x180026836  xor     rax, rsp
0x180026839  mov     [rbp+240h+var_40], rax
0x180026840  mov     rax, [rbp+240h+arg_30]
0x180026847  mov     r14, rcx
0x18002684a  mov     rsi, [rbp+240h+Str]
0x180026851  mov     ecx, 2000000Fh
0x180026856  mov     [rsp+340h+var_2F8], rax
0x18002685b  mov     r13, r8
0x18002685e  mov     [rsp+340h+var_2E8], r9d
0x180026863  mov     [rsp+340h+pszStr1], r8
0x180026868  mov     [rsp+340h+lpWideCharStr], rdx
0x18002686d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180026874  nop     dword ptr [rax+rax+00h]
0x180026879  mov     edx, cs:_tls_index
0x18002687f  movzx   r15d, al
0x180026883  mov     rcx, gs:58h
0x18002688c  mov     byte ptr [rsp+340h+var_300], al
0x180026890  mov     eax, 4
0x180026895  mov     rcx, [rcx+rdx*8]
0x180026899  mov     ecx, [rax+rcx]
0x18002689c  cmp     cs:dword_180172698, ecx
0x1800268a2  jg      loc_1800273C2
0x1800268a8  mov     r12d, [rbp+240h+arg_28]
0x1800268af  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x1800268b6  mov     [rbp+240h+var_2A8], rax
0x1800268ba  xorps   xmm0, xmm0
0x1800268bd  mov     [rbp+240h+var_2A0], 0
0x1800268c5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800268cc  mov     [rbp+240h+var_298], 0Bh
0x1800268d3  mov     [rbp+240h+var_280], 0
0x1800268da  mov     [rsp+340h+var_2CC], 0
0x1800268e2  mov     [r14+40h], r12d
0x1800268e6  movdqu  xmmword ptr [rbp+240h+bstrString], xmm0
0x1800268eb  test    rsi, rsi
0x1800268ee  jz      loc_180026976
0x1800268f4  lea     rdx, SubStr; ";"
0x1800268fb  mov     rcx, rsi; Str
0x1800268fe  call    cs:__imp_wcsstr
0x180026905  nop     dword ptr [rax+rax+00h]
0x18002690a  mov     rbx, rax
0x18002690d  test    rax, rax
0x180026910  jnz     loc_1800277B6
0x180026916  test    r15b, r15b
0x180026919  jz      short loc_180026976
0x18002691b  lea     rdx, aNull_2; "(null)"
0x180026922  mov     rcx, rsi; pszStr1
0x180026925  call    cs:__imp_StrCmpICW
0x18002692c  nop     dword ptr [rax+rax+00h]
0x180026931  test    eax, eax
0x180026933  jz      short loc_180026976
0x180026935  test    rbx, rbx
0x180026938  jnz     short loc_180026950
0x18002693a  mov     rax, rdi
0x18002693d  nop     dword ptr [rax]
0x180026940  cmp     word ptr [rsi+rax*2+2], 0
0x180026946  lea     rax, [rax+1]
0x18002694a  jnz     short loc_180026940
0x18002694c  lea     rbx, [rsi+rax*2]
0x180026950  cmp     rbx, rsi
0x180026953  jnz     loc_180026F96
0x180026959  mov     edx, 2Ch ; ','; Ch
0x18002695e  mov     rcx, rsi; Str
0x180026961  call    cs:__imp_wcsrchr
0x180026968  nop     dword ptr [rax+rax+00h]
0x18002696d  test    rax, rax
0x180026970  jnz     loc_1800277C0
0x180026976  mov     r15, cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA; CFeatureCache * g_pFeatureCache
0x18002697d  test    r15, r15
0x180026980  jz      loc_180026C14
0x180026986  test    byte ptr [r15], 8
0x18002698a  jnz     short loc_1800269F6
0x18002698c  call    cs:__imp_?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x180026993  nop     dword ptr [rax+rax+00h]
0x180026998  lea     r8, ?__CoInternetIsFeatureEnabledInternal_IFL@@YAJW4_tagINTERNETFEATURELIST@@@Z; __CoInternetIsFeatureEnabledInternal_IFL(_tagINTERNETFEATURELIST)
0x18002699f  mov     edx, 3
0x1800269a4  mov     r9, rax
0x1800269a7  mov     rcx, [rax]
0x1800269aa  mov     rax, [rcx+8]
0x1800269ae  mov     rcx, r9
0x1800269b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269b6  lea     rcx, [r15+10h]; lpCriticalSection
0x1800269ba  movzx   ebx, al
0x1800269bd  call    cs:__imp_EnterCriticalSection
0x1800269c4  nop     dword ptr [rax+rax+00h]
0x1800269c9  mov     r8, [r15+8]
0x1800269cd  lea     rcx, [r15+10h]; lpCriticalSection
0x1800269d1  mov     rdx, r8
0x1800269d4  or      r8, 8
0x1800269d8  and     rdx, 0FFFFFFFFFFFFFFF7h
0x1800269dc  test    bl, bl
0x1800269de  cmovz   r8, rdx
0x1800269e2  or      qword ptr [r15], 8
0x1800269e6  mov     [r15+8], r8
0x1800269ea  call    cs:__imp_LeaveCriticalSection
0x1800269f1  nop     dword ptr [rax+rax+00h]
0x1800269f6  movzx   eax, byte ptr [r15+8]
0x1800269fb  not     al
0x1800269fd  movzx   eax, al
0x180026a00  shr     eax, 3
0x180026a03  and     eax, 1
0x180026a06  mov     ebx, [rsp+340h+var_2E8]
0x180026a0a  xor     ecx, ecx
0x180026a0c  cmp     eax, 1
0x180026a0f  setnz   cl
0x180026a12  xor     r15d, r15d
0x180026a15  test    r12b, 2
0x180026a19  cmovz   r15d, ecx
0x180026a1d  mov     [rsp+340h+var_2D0], r15d
0x180026a22  test    r13, r13
0x180026a25  jnz     loc_180027052
0x180026a2b  test    r12b, r12b
0x180026a2e  js      loc_1800277C9
0x180026a34  mov     eax, r12d
0x180026a37  and     eax, 40h
0x180026a3a  mov     [rsp+340h+var_2E4], eax
0x180026a3e  test    rsi, rsi
0x180026a41  jnz     loc_1800271F6
0x180026a47  mov     eax, r12d
0x180026a4a  and     eax, 4
0x180026a4d  mov     [rbp+240h+var_2C0], eax
0x180026a50  test    r15d, r15d
0x180026a53  jnz     loc_18002750A
0x180026a59  test    r12b, 8
0x180026a5d  jnz     loc_180027435
0x180026a63  test    rsi, rsi
0x180026a66  jnz     loc_180026DE0
0x180026a6c  mov     r15d, 1
0x180026a72  mov     [rsp+340h+var_2EC], r15d
0x180026a77  test    r13, r13
0x180026a7a  jz      loc_180026B5E
0x180026a80  cmp     [rsp+340h+var_2E8], 0
0x180026a85  jle     loc_180026B5E
0x180026a8b  mov     r15, [rsp+340h+lpWideCharStr]
0x180026a90  xor     r13d, r13d
0x180026a93  mov     ebx, r12d
0x180026a96  mov     [rsp+340h+pszStr1], r13
0x180026a9b  and     ebx, 10h
0x180026a9e  test    r15, r15
0x180026aa1  jnz     loc_1800272C4
0x180026aa7  mov     rax, [rsp+340h+var_2F8]
0x180026aac  mov     rcx, r14; this
0x180026aaf  mov     dword ptr [rax], 10h
0x180026ab5  call    ?SampleData@CContentAnalyzer@@AEAAXXZ; CContentAnalyzer::SampleData(void)
0x180026aba  test    ebx, ebx
0x180026abc  jnz     loc_1800278A2
0x180026ac2  cmp     dword ptr [r14+60h], 0
0x180026ac7  jnz     loc_18002734B
0x180026acd  cmp     dword ptr [r14+64h], 0
0x180026ad2  jnz     loc_1800278F3
0x180026ad8  cmp     dword ptr [r14+70h], 0
0x180026add  jnz     loc_18002790E
0x180026ae3  lea     r15, aApplicationOct_1; "application/octet-stream"
0x180026aea  lea     rbx, aApplicationPdf_0; "application/pdf"
0x180026af1  test    rsi, rsi
0x180026af4  jnz     loc_1800275A5
0x180026afa  xor     ebx, ebx
0x180026afc  mov     [rsp+340h+var_2F0], ebx
0x180026b00  test    rsi, rsi
0x180026b03  jnz     loc_180027941
0x180026b09  cmp     byte ptr [rsp+340h+var_300], bl
0x180026b0d  jnz     loc_18002753E
0x180026b13  mov     rax, [rsp+340h+lpWideCharStr]
0x180026b18  mov     r13d, ebx
0x180026b1b  mov     [rsp+340h+var_2E8], ebx
0x180026b1f  test    rax, rax
0x180026b22  jnz     loc_180026C25
0x180026b28  xor     edi, edi
0x180026b2a  xor     ebx, ebx
0x180026b2c  test    rsi, rsi
0x180026b2f  jnz     loc_18002735B
0x180026b35  mov     r8d, 1
0x180026b3b  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x180026b42  jnz     loc_1800279C9
0x180026b48  mov     r12d, [rsp+340h+var_2F0]
0x180026b4d  cmp     dword ptr [r14+54h], 0
0x180026b52  jz      loc_180026CCA
0x180026b58  mov     [r14+38h], r15
0x180026b5c  jmp     short loc_180026B7E
0x180026b5e  mov     rbx, [rsp+340h+var_2F8]
0x180026b63  mov     [r14+38h], rsi
0x180026b67  mov     dword ptr [rbx], 10h
0x180026b6d  cmp     r15d, 1
0x180026b71  jz      loc_1800274F6
0x180026b77  cmp     [rsp+340h+var_2E8], 0
0x180026b7c  jle     short loc_180026B8E
0x180026b7e  movsxd  rdx, dword ptr [r14]
0x180026b81  mov     rcx, [r14+20h]
0x180026b85  movzx   eax, byte ptr [r14+28h]
0x180026b8a  mov     [rcx+rdx-1], al
0x180026b8e  mov     rdi, [r14+38h]
0x180026b92  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180026b99  xor     esi, esi
0x180026b9b  mov     [rbp+240h+var_2A8], rax
0x180026b9f  mov     ebx, esi
0x180026ba1  mov     eax, esi
0x180026ba3  cmp     [rbp+240h+var_2A0], rbx
0x180026ba7  setnz   bl
0x180026baa  cmp     [rbp+240h+var_298], 0Bh
0x180026bae  setnz   al
0x180026bb1  test    ebx, ebx
0x180026bb3  jz      loc_180026CBD
0x180026bb9  mov     rcx, [rbp+240h+bstrString]; bstrString
0x180026bbd  test    rcx, rcx
0x180026bc0  jnz     loc_180027CEC
0x180026bc6  mov     [rbp+240h+bstrString+8], rsi
0x180026bca  mov     [rbp+240h+var_280], esi
0x180026bcd  test    ebx, ebx
0x180026bcf  jz      short loc_180026BE6
0x180026bd1  mov     rcx, [rbp+240h+var_2A0]
0x180026bd5  test    rcx, rcx
0x180026bd8  jz      short loc_180026BE6
0x180026bda  mov     rax, [rcx]
0x180026bdd  mov     rax, [rax+10h]
0x180026be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026be6  mov     rax, rdi
0x180026be9  mov     rcx, [rbp+240h+var_40]
0x180026bf0  xor     rcx, rsp; StackCookie
0x180026bf3  call    __security_check_cookie
0x180026bf8  mov     rbx, [rsp+340h+arg_10]
0x180026c00  add     rsp, 310h
0x180026c07  pop     r15
0x180026c09  pop     r14
0x180026c0b  pop     r13
0x180026c0d  pop     r12
0x180026c0f  pop     rdi
0x180026c10  pop     rsi
0x180026c11  pop     rbp
0x180026c12  retn
0x180026c14  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING@FCK@@3VCFeatureControlKey@@A; this
0x180026c1b  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180026c20  jmp     loc_180026A06
0x180026c25  mov     [rsp+340h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x180026c2a  lea     rcx, [rbp+240h+MultiByteStr]
0x180026c2e  mov     [rsp+340h+lpDefaultChar], rbx; lpDefaultChar
0x180026c33  mov     r9d, edi; cchWideChar
0x180026c36  mov     [rsp+340h+cbMultiByte], 104h; cbMultiByte
0x180026c3e  mov     r8, rax; lpWideCharStr
0x180026c41  mov     [rsp+340h+lpMultiByteStr], rcx; lpMultiByteStr
0x180026c46  xor     edx, edx; dwFlags
0x180026c48  xor     ecx, ecx; CodePage
0x180026c4a  call    cs:__imp_WideCharToMultiByte
0x180026c51  nop     dword ptr [rax+rax+00h]
0x180026c56  test    eax, eax
0x180026c58  jz      loc_180027086
0x180026c5e  test    r12b, 1
0x180026c62  jnz     loc_1800279A3
0x180026c68  lea     rax, [rbp+240h+MultiByteStr]
0x180026c6c  nop     dword ptr [rax+00h]
0x180026c70  inc     rdi
0x180026c73  cmp     byte ptr [rax+rdi], 0
0x180026c77  jnz     short loc_180026C70
0x180026c79  lea     rbx, [rbp+240h+MultiByteStr]
0x180026c7d  add     rbx, rdi
0x180026c80  jz      loc_180026B28
0x180026c86  nop     word ptr [rax+rax+00000000h]
0x180026c90  lea     rax, [rbp+240h+MultiByteStr]
0x180026c94  cmp     rbx, rax
0x180026c97  jb      loc_180026B28
0x180026c9d  movzx   eax, byte ptr [rbx]
0x180026ca0  cmp     al, 2Fh ; '/'
0x180026ca2  jz      loc_180026B28
0x180026ca8  cmp     al, 2Eh ; '.'
0x180026caa  jz      loc_18002762B
0x180026cb0  cmp     al, 5Ch ; '\'
0x180026cb2  jz      loc_180026B28
0x180026cb8  dec     rbx
0x180026cbb  jmp     short loc_180026C90
0x180026cbd  test    eax, eax
0x180026cbf  jz      loc_180026BE6
0x180026cc5  jmp     loc_180026BB9
0x180026cca  cmp     dword ptr [r14+5Ch], 0
0x180026ccf  mov     eax, [rsp+340h+var_2D0]
0x180026cd3  jnz     loc_1800274D5
0x180026cd9  cmp     dword ptr [r14+48h], 0
0x180026cde  jnz     loc_180027499
0x180026ce4  cmp     dword ptr [r14+50h], 0
0x180026ce9  jnz     loc_180027ACA
0x180026cef  cmp     dword ptr [r14+58h], 0
0x180026cf4  jnz     loc_180027ADA
0x180026cfa  mov     edx, [r14+18h]
0x180026cfe  test    edx, edx
0x180026d00  jnz     loc_18002708F
0x180026d06  mov     rcx, [r14+20h]; pszStr1
0x180026d0a  lea     rdx, aPdf; "%PDF"
0x180026d11  mov     r8d, 4; nChar
0x180026d17  mov     dword ptr [r14+44h], 0
0x180026d1f  call    cs:__imp_StrCmpNCA
0x180026d26  nop     dword ptr [rax+rax+00h]
0x180026d2b  test    eax, eax
  ... truncated ...
```
