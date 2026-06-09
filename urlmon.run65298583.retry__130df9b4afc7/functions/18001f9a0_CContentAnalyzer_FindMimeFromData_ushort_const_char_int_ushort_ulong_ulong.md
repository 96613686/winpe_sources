# CContentAnalyzer::FindMimeFromData(ushort const *,char *,int,ushort *,ulong,ulong *)

- ea: `0x18001f9a0`
- end: `0x180020e78`
- name: `?FindMimeFromData@CContentAnalyzer@@QEAAPEBGPEBGPEADHPEAGKPEAK@Z`
- size: `5336`
- prototype: `const unsigned __int16 *__usercall@<rax>(CContentAnalyzer *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, char *@<r8>, int@<r9d>, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f000`
- `0x18001f4e0`
- `0x180021604`

## callees

- `0x1800150e0`
- `0x18001e160`
- `0x18001ee14`
- `0x18001f9a0`
- `0x180020e80`
- `0x1800215c0`
- `0x18003b010`
- `0x1800595f4`
- `0x18006076c`
- `0x180060be4`
- `0x180060f7c`
- `0x180073760`
- `0x18007acac`
- `0x18008df68`
- `0x18009ca7c`
- `0x1800a5aac`
- `0x1800a5b1c`
- `0x1800ecc78`
- `0x1800eccf8`
- `0x1800ecd4c`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!bsearch` at `0x180020a0e`
- `msvcrt!bsearch` at `0x180020a0e`
- `msvcrt!wcsrchr` at `0x18001fad4`
- `msvcrt!wcsrchr` at `0x18001fad4`
- `msvcrt!wcsstr` at `0x18001fa7c`
- `msvcrt!wcsstr` at `0x18001fa7c`
- `iertutil!CreateUri` at `0x18002050f`
- `iertutil!CreateUri` at `0x18002050f`
- `iertutil!__imp_IECompatLogEvent` at `0x180020bca`
- `iertutil!__imp_IECompatLogEvent` at `0x180020bca`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001f9fc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18001f9fc`
- `iertutil!__imp_?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ` at `0x18001faf9`
- `iertutil!__imp_?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ` at `0x18001faf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fb4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800204a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800205de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800206ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fb4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800204a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800205de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800206ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fb24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020375`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fb24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020375`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180020857`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180020875`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002088f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800208a9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800208c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800208dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180020857`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180020875`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18002088f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800208a9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800208c3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800208dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x180020041`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x18002045b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x180020041`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x18002045b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800207f3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800209db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800207f3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800209db`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001fe8f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001feae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001fecd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001feec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18002068a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001fe8f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001feae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001fecd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18001feec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNCA` at `0x18002068a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x180020b49`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrA` at `0x180020b49`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001fa9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001ff38`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800202f5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020317`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020343`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020360`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002059b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800205bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020635`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002075f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002078a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800207bc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800207d9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020931`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002094c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020980`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020a79`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020ade`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020aff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020b29`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c09`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c29`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c71`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c81`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020cc6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020d54`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020d69`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020d99`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020ddd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020df6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020e1d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020e35`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020e50`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001fa9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001ff38`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800202f5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020317`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020343`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020360`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002059b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800205bb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020635`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002075f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002078a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800207bc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800207d9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020931`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002094c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020980`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020a79`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020ade`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020aff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020b29`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c09`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c29`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c71`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020c81`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020cc6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020d54`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020d69`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020d99`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020ddd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020df6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020e1d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020e35`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180020e50`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002011d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002014f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002011d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002014f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fdbf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ff77`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ffb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800203ab`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800203f0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001fdbf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ff77`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001ffb4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800203ab`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800203f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800202b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800202b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002008c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002008c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020499`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020cf0`
- `OLEAUT32!__imp_SysFreeString` at `0x180020e69`
- `OLEAUT32!__imp_SysFreeString` at `0x180020e69`

## string_xrefs

- `0x18001fc5b`: `application/xml`
- `0x180020c1f`: `application/xml`
- `0x180020c31`: `application/xml`
- `0x180020210`: `application/x-zip-compressed`
- `0x18002030d`: `application/json`
- `0x1800207cf`: `image/svg+xml`
- `0x180020837`: `image/svg+xml`
- `0x180020dd2`: `image/svg+xml`
- `0x180020581`: `application/rss+xml`
- `0x18002062b`: `text/xml`
- `0x180020717`: `text/xml`
- `0x180020927`: `text/xml`
- `0x180020bff`: `text/xml`
- `0x180020c13`: `text/xml`
- `0x180020128`: `multipart/x-mixed-replace`
- `0x180020ac8`: `application/atom+xml`
- `0x18002093f`: `application/xhtml+xml`
- `0x180020deb`: `application/xhtml+xml`
- `0x180020b8b`: `ImageNotUpgradedToXMLorHTML`

## pseudocode

```c
const unsigned __int16 *__fastcall CContentAnalyzer::FindMimeFromData(
        CContentAnalyzer *this,
        const unsigned __int16 *a2,
        char *a3,
        int a4,
        unsigned __int16 *Str,
        unsigned int a6,
        unsigned int *a7)
{
  WCHAR *v8; // rsi
  char *v9; // rdi
  char Bool; // r15
  wchar_t *v11; // rax
  unsigned __int16 *v12; // rbx
  __int64 v13; // rax
  wchar_t *v14; // rax
  CFeatureCache *v15; // r15
  struct IBrowsingEnvironment *CorrectBrowsingEnvironment; // rax
  char v17; // bl
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  int IsFeatureEnabledInternal; // eax
  BOOL v22; // r15d
  int lpVtbl_high; // r15d
  const unsigned __int16 *v24; // r15
  const WCHAR *FileExtensionW; // rdi
  BOOL v26; // r13d
  int v27; // edi
  int v28; // ebx
  __int64 v29; // rdi
  BOOL v30; // ebx
  __int64 v32; // rax
  CHAR *v33; // rbx
  CHAR v34; // al
  int v35; // edx
  const CHAR *v36; // rcx
  unsigned int v37; // r9d
  bool v38; // bl
  unsigned int *v39; // rdi
  int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rax
  CHAR *v42; // r13
  CMediaTypeHolder *v43; // r15
  __int64 *v44; // r15
  __int64 v45; // rdx
  __int64 v46; // rbx
  LPCSTR *v47; // rdi
  int v48; // eax
  IUri *v49; // rcx
  int v50; // ebx
  __int64 v51; // rcx
  __int64 v52; // rax
  const wchar_t *v53; // rax
  const WCHAR *v54; // rax
  const WCHAR *v55; // rbx
  CContentAnalyzer *v56; // rcx
  unsigned __int64 k; // rbx
  int v58; // edi
  CHAR *v59; // rax
  CHAR *v60; // r12
  unsigned int v61; // ebx
  struct CMediaTypeHolder *MediaTypeHolder; // rax
  __int64 *v63; // r15
  __int64 v64; // r13
  __int64 n; // rbx
  LPCSTR *v66; // rdi
  int v67; // ecx
  __int64 v68; // rax
  const WCHAR *v69; // rax
  unsigned __int64 i; // rbx
  unsigned __int64 m; // rbx
  PSTR v72; // rax
  __int64 j; // rbx
  bool v74; // zf
  bool v75; // [rsp+40h] [rbp-C0h]
  unsigned int v76; // [rsp+50h] [rbp-B0h]
  int v77; // [rsp+54h] [rbp-ACh]
  int v79; // [rsp+58h] [rbp-A8h]
  LPCWSTR pszStr1a; // [rsp+60h] [rbp-A0h]
  int v82; // [rsp+68h] [rbp-98h]
  IUri *ppURI; // [rsp+70h] [rbp-90h] BYREF
  BOOL v84; // [rsp+78h] [rbp-88h]
  unsigned int v85; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v86; // [rsp+80h] [rbp-80h]
  __int64 v87; // [rsp+88h] [rbp-78h]
  LPCWCH lpWideCharStr; // [rsp+90h] [rbp-70h]
  _QWORD v89[2]; // [rsp+98h] [rbp-68h] BYREF
  void **v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h]
  int v92; // [rsp+B8h] [rbp-48h]
  BSTR bstrString[2]; // [rsp+C0h] [rbp-40h]
  int v94; // [rsp+D0h] [rbp-30h]
  _QWORD v95[3]; // [rsp+D8h] [rbp-28h] BYREF
  CHAR MultiByteStr[272]; // [rsp+F0h] [rbp-10h] BYREF
  char v97[272]; // [rsp+200h] [rbp+100h] BYREF

  v8 = Str;
  v9 = a3;
  lpWideCharStr = a2;
  Bool = IEConfiguration_GetBool(536870927);
  v75 = Bool;
  if ( dword_1801656C8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801656C8);
    if ( dword_1801656C8 == -1 )
    {
      dword_1801656CC = HelperAddUriDefaultFlags(0x3002B80u, 4u) & 0xFFFFFFFE;
      Init_thread_footer(&dword_1801656C8);
    }
  }
  v90 = &CUString::`vftable';
  v91 = 0;
  v92 = 11;
  v94 = 0;
  v85 = 0;
  *((_DWORD *)this + 16) = a6;
  *(_OWORD *)bstrString = 0;
  if ( Str )
  {
    v11 = wcsstr(Str, L";");
    v12 = v11;
    if ( v11 )
      *v11 = 0;
    if ( Bool && StrCmpICW(Str, L"(null)") )
    {
      if ( !v12 )
      {
        v13 = -1;
        do
          v74 = Str[++v13] == 0;
        while ( !v74 );
        v12 = &Str[v13];
      }
      for ( ; v12 != Str; *v12 = 0 )
      {
        v51 = *--v12;
        if ( (unsigned __int16)(v51 - 32) > 0x3Fu )
          break;
        if ( aVerqueryvaluea[v51] != 1 )
          break;
      }
      v14 = wcsrchr(Str, 0x2Cu);
      if ( v14 )
        v8 = v14 + 1;
    }
  }
  v15 = g_pFeatureCache;
  if ( g_pFeatureCache )
  {
    if ( (*(_BYTE *)g_pFeatureCache & 8) == 0 )
    {
      CorrectBrowsingEnvironment = GetCorrectBrowsingEnvironment();
      v17 = (*(__int64 (__fastcall **)(struct IBrowsingEnvironment *, __int64, __int64 (__fastcall *)(enum _tagINTERNETFEATURELIST)))(*(_QWORD *)CorrectBrowsingEnvironment + 8LL))(
              CorrectBrowsingEnvironment,
              3,
              __CoInternetIsFeatureEnabledInternal_IFL);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 16));
      v18 = *((_QWORD *)v15 + 1);
      v19 = v18 | 8;
      v20 = v18 & 0xFFFFFFFFFFFFFFF7uLL;
      if ( !v17 )
        v19 = v20;
      *(_QWORD *)v15 |= 8uLL;
      *((_QWORD *)v15 + 1) = v19;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 16));
    }
    IsFeatureEnabledInternal = ((unsigned __int8)~*((_BYTE *)v15 + 8) >> 3) & 1;
  }
  else
  {
    IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING);
  }
  v22 = 0;
  if ( (a6 & 2) == 0 )
    v22 = IsFeatureEnabledInternal != 1;
  v84 = v22;
  if ( v9 && a4 > 0 )
  {
    *((_QWORD *)this + 4) = v9;
    *((_DWORD *)this + 1) = a4;
    v52 = (unsigned int)a4;
    if ( a4 > 256 )
      v52 = 256;
    *(_DWORD *)this = v52;
    *((_BYTE *)this + 40) = v9[v52 - 1];
    v9[v52 - 1] = 0;
  }
  if ( (a6 & 0x80u) != 0 )
  {
    *((_QWORD *)this + 7) = L"text/plain";
    *a7 = 16;
    goto LABEL_45;
  }
  v86 = a6 & 0x40;
  if ( v8 && (!StrCmpICW(v8, L"application/json") || v75 && (a6 & 0x40) == 0 && !StrCmpICW(v8, L"text/html")) )
    goto LABEL_185;
  LODWORD(v87) = a6 & 4;
  if ( v22 )
  {
    if ( (a6 & 4) == 0 && v8 && !StrCmpICW(v8, L"text/plain") )
      goto LABEL_185;
  }
  if ( (a6 & 8) != 0 )
  {
    if ( !v75 || a4 <= 0 )
      goto LABEL_185;
    if ( v8 )
    {
      if ( !StrCmpNICW(v8, L"image/", 6)
        || (ppURI = (IUri *)v8, bsearch(&ppURI, off_180124F30, 0x33u, 8u, CContentAnalyzer::s_BinarySearchStringCompare)) )
      {
        if ( CContentAnalyzer::CheckBinaryImageHeaders(this, v75) )
          goto LABEL_46;
      }
    }
    if ( !CContentAnalyzer::IsM3UPlaylistMimeType(v8) )
    {
LABEL_185:
      *((_QWORD *)this + 7) = v8;
      *a7 = 16;
      goto LABEL_45;
    }
  }
  v82 = -2147467259;
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
  v42 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    InternalRegisterDefaultMediaType();
LABEL_178:
    LeaveCriticalSection(&g_mxsMedia);
    goto LABEL_104;
  }
  if ( !WideCharToMultiByte(0, 0, v8, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    CoTaskMemFree(v42);
    v42 = 0;
  }
  InternalRegisterDefaultMediaType();
  if ( !v42 )
    goto LABEL_178;
  v76 = 0;
  EnterCriticalSection(&g_mxsMedia);
  v43 = g_pCMHolder;
  LeaveCriticalSection(&g_mxsMedia);
  if ( v43 && (v44 = (__int64 *)*((_QWORD *)v43 + 2)) != 0 )
  {
    ppURI = 0;
    v77 = -2147024809;
    do
    {
      v45 = *v44;
      v46 = 0;
      v89[0] = *v44;
      while ( 1 )
      {
        if ( (unsigned int)v46 >= *((_DWORD *)v44 + 4) )
        {
          v48 = v77;
          v49 = ppURI;
          goto LABEL_93;
        }
        v47 = (LPCSTR *)(v45 + 48 * v46);
        if ( !StrCmpICA(v42, *v47) )
          break;
        v45 = v89[0];
        v46 = (unsigned int)(v46 + 1);
      }
      v48 = 0;
      v49 = (IUri *)v47;
      ppURI = (IUri *)v47;
      v77 = 0;
      if ( v47 )
        break;
LABEL_93:
      v44 = (__int64 *)v44[3];
    }
    while ( v44 );
    v50 = v77;
    v9 = a3;
    if ( !v48 )
    {
      lpVtbl_high = HIDWORD(v49[1].lpVtbl);
      v76 = lpVtbl_high;
      goto LABEL_96;
    }
  }
  else
  {
    v50 = -2147467259;
  }
  lpVtbl_high = 0;
LABEL_96:
  CoTaskMemFree(v42);
  LeaveCriticalSection(&g_mxsMedia);
  if ( v50 )
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
      *((_QWORD *)this + 7) = v8;
      *a7 = 64;
      goto LABEL_45;
    }
  }
LABEL_29:
  if ( v9 && a4 > 0 )
  {
    v24 = lpWideCharStr;
    FileExtensionW = 0;
    pszStr1a = 0;
    if ( lpWideCharStr )
    {
      ppURI = 0;
      if ( CreateUri(lpWideCharStr, dword_1801656CC, 0, &ppURI) < 0 )
        goto LABEL_167;
      if ( !(unsigned int)CUString::Set((CUString *)&v90, ppURI, Uri_PROPERTY_EXTENSION) )
        FileExtensionW = bstrString[1];
      pszStr1a = FileExtensionW;
      ((void (*)(void))ppURI->lpVtbl->Release)();
      if ( !FileExtensionW )
      {
LABEL_167:
        FileExtensionW = FindFileExtensionW(v24);
        pszStr1a = FileExtensionW;
      }
    }
    *a7 = 16;
    CContentAnalyzer::SampleData(this);
    if ( (a6 & 0x10) != 0 && v8 && !StrCmpICW(v8, L"text/plain") )
    {
      if ( *((_DWORD *)this + 29) )
      {
        *((_QWORD *)this + 7) = L"application/octet-stream";
        *a7 = 4;
      }
      else
      {
        *((_QWORD *)this + 7) = v8;
      }
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 24) || *((_DWORD *)this + 25) && *((_DWORD *)this + 26) && *((_DWORD *)this + 27) )
    {
      *((_QWORD *)this + 7) = L"application/rss+xml";
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 28) )
    {
      *((_QWORD *)this + 7) = L"application/atom+xml";
      goto LABEL_46;
    }
    if ( v8 )
    {
      if ( !StrCmpICW(v8, L"image/svg+xml") )
      {
        *((_QWORD *)this + 7) = L"image/svg+xml";
        goto LABEL_46;
      }
      if ( !StrCmpNICW(v8, L"image/", 6) )
      {
        if ( (unsigned int)CContentAnalyzer::CheckImageMime(this, v8, v75) )
          goto LABEL_46;
        v26 = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_MIME_TREAT_IMAGE_AS_AUTHORITATIVE) != 1;
        goto LABEL_39;
      }
      if ( !StrCmpICW(v8, L"application/pdf") )
      {
        *((_QWORD *)this + 7) = L"application/pdf";
        goto LABEL_46;
      }
    }
    v26 = 0;
    if ( !v8 )
    {
LABEL_38:
      if ( v75 && v8 && FileExtensionW && !StrCmpICW(v8, L"application/octet-stream") )
      {
        for ( i = 0; i < 0xB; ++i )
        {
          if ( !StrCmpICW(FileExtensionW, off_180124D40[i]) )
            goto LABEL_43;
        }
      }
      goto LABEL_39;
    }
    if ( StrCmpICW(v8, L"text/html") )
    {
      if ( !StrCmpICW(v8, L"application/xml") )
      {
        *((_QWORD *)this + 7) = L"application/xml";
        goto LABEL_46;
      }
      if ( !StrCmpICW(v8, L"text/xml") )
        goto LABEL_199;
      if ( !StrCmpICW(v8, L"application/xhtml+xml") )
      {
        *((_QWORD *)this + 7) = L"application/xhtml+xml";
        goto LABEL_46;
      }
      goto LABEL_38;
    }
    if ( *((_DWORD *)this + 18) )
    {
      *((_QWORD *)this + 7) = L"text/html";
      goto LABEL_46;
    }
LABEL_39:
    v79 = 0;
    if ( lpWideCharStr )
    {
      if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, 260, 0, 0) )
        MultiByteStr[0] = 0;
      if ( (a6 & 1) != 0 )
      {
        v72 = StrChrA(MultiByteStr, 1u);
        if ( v72 )
          *v72 = 0;
      }
      v32 = -1;
      do
        ++v32;
      while ( MultiByteStr[v32] );
      v33 = &MultiByteStr[v32];
      if ( &MultiByteStr[v32] )
      {
        while ( v33 >= MultiByteStr )
        {
          v34 = *v33;
          if ( *v33 == 47 )
            break;
          if ( v34 == 46 )
          {
            if ( StrCmpNICA(v33, ".application", 12)
              && StrCmpNICA(v33, ".xbap", 5)
              && StrCmpNICA(v33, ".xps", 4)
              && StrCmpNICA(v33, ".xaml", 5)
              && StrCmpNICA(v33, ".hta", 4)
              && StrCmpNICA(v33, ".htc", 4) )
            {
              break;
            }
            v79 = 1;
            if ( !CContentAnalyzer::FindMimeFromExt(this, FileExtensionW, &v85) )
              break;
            goto LABEL_226;
          }
          if ( v34 == 92 )
            break;
          --v33;
        }
      }
    }
    v27 = 0;
    v28 = 0;
    if ( v8 )
    {
      if ( !StrCmpICW(v8, L"text/html") || !StrCmpICW(v8, L"text/xml") )
        v28 = 1;
      if ( !StrCmpICW(v8, L"text/plain") )
        v27 = 1;
    }
    if ( g_cmptlgs != 1
      && (unsigned int)IECompatLoggingEnabled()
      && (*((_DWORD *)this + 23) || *((_DWORD *)this + 18))
      && v26 )
    {
      v89[1] = v8;
      v95[0] = L"FileName";
      v95[1] = L"SuggestedMimeType";
      v89[0] = lpWideCharStr;
      IECompatLogEvent(3221226536LL, L"ImageNotUpgradedToXMLorHTML", 0, 0, 2, v95, v89);
    }
    if ( *((_DWORD *)this + 21) )
    {
LABEL_43:
      *((_QWORD *)this + 7) = L"application/octet-stream";
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 23) && !v26 && (!v84 || v28) )
    {
LABEL_199:
      *((_QWORD *)this + 7) = L"text/xml";
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 18) && !v26 && (!v84 || (_DWORD)v87 && v27) )
    {
      if ( v8 )
      {
        if ( !StrCmpICW(v8, L"text/xml") )
        {
          v69 = L"text/xml";
          goto LABEL_193;
        }
        v74 = StrCmpICW(v8, L"application/xml") == 0;
        v69 = L"application/xml";
        if ( v74 )
          goto LABEL_193;
      }
      v69 = L"text/html";
LABEL_193:
      *((_QWORD *)this + 7) = v69;
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 20) )
    {
      *((_QWORD *)this + 7) = L"application/macbinhex40";
      goto LABEL_46;
    }
    if ( *((_DWORD *)this + 22) && (!v84 || v8 && (!StrCmpICW(v8, L"text/html") || !StrCmpICW(v8, L"text/scriptlet"))) )
    {
      *((_QWORD *)this + 7) = L"text/scriptlet";
      goto LABEL_46;
    }
    v35 = *((_DWORD *)this + 6);
    if ( v35 && *((_DWORD *)this + 2) + *((_DWORD *)this + 5) < 16 * (v35 + *((_DWORD *)this + 7)) )
    {
      v38 = v75;
      *((_DWORD *)this + 17) = 1;
      if ( !(unsigned int)CContentAnalyzer::CheckBinaryHeaders(this, v75) )
      {
        v39 = a7;
        if ( !(unsigned int)CContentAnalyzer::CheckTextHeaders(this, v75) )
        {
          *((_QWORD *)this + 7) = L"application/octet-stream";
          *a7 = 4;
        }
        goto LABEL_119;
      }
LABEL_118:
      v39 = a7;
      goto LABEL_119;
    }
    v36 = (const CHAR *)*((_QWORD *)this + 4);
    *((_DWORD *)this + 17) = 0;
    if ( StrCmpNCA(v36, "%PDF", 4) )
    {
      if ( StrCmpNCA(*((LPCSTR *)this + 4), "%!", 2) )
      {
        if ( StrCmpNCA(*((LPCSTR *)this + 4), "{\\rtf", 5) )
        {
          v38 = v75;
          if ( StrCmpNCA(*((LPCSTR *)this + 4), "begin", 5) )
          {
            if ( !v75 || StrCmpNCA(*((LPCSTR *)this + 4), "#EXTM3U", 7) || !CContentAnalyzer::IsHlsManifest(this) )
            {
              v39 = a7;
              if ( !(unsigned int)CContentAnalyzer::CheckBinaryHeaders(this, v75) )
              {
                *((_QWORD *)this + 7) = L"text/plain";
                *a7 = 8;
              }
LABEL_119:
              v54 = pszStr1a;
              if ( *((wchar_t **)this + 7) == L"application/x-zip-compressed" && pszStr1a )
              {
                for ( j = 0; (unsigned int)j < 0x1A; j = (unsigned int)(j + 1) )
                {
                  v74 = StrCmpICW(v54, off_180124E60[j]) == 0;
                  v54 = pszStr1a;
                  if ( v74 )
                  {
                    *((_QWORD *)this + 7) = L"application/octet-stream";
                    *v39 = 4;
                    break;
                  }
                }
                v38 = v75;
              }
              if ( *((const WCHAR **)this + 7) == L"application/octet-stream" && v38 && v86 )
              {
                InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
                if ( (dword_18015E75C & 8) != 0 )
                  goto LABEL_46;
                v54 = pszStr1a;
                if ( pszStr1a )
                {
                  for ( k = 0; k < 0xB; ++k )
                  {
                    if ( !StrCmpICW(v54, off_180124D40[k]) )
                      goto LABEL_46;
                    v54 = pszStr1a;
                  }
                }
              }
              v55 = (const WCHAR *)*((_QWORD *)this + 7);
              if ( !v55 )
              {
LABEL_122:
                v56 = (CContentAnalyzer *)v76;
                switch ( v76 )
                {
                  case 1u:
                    goto LABEL_123;
                  case 3u:
                    v74 = *((_DWORD *)this + 17) == 0;
                    break;
                  case 4u:
                    v74 = *((_DWORD *)this + 17) == 1;
                    break;
                  case 5u:
LABEL_162:
                    *((_QWORD *)this + 7) = v8;
                    *a7 = 32;
                    goto LABEL_46;
                  default:
LABEL_123:
                    if ( lpWideCharStr && !v79 )
                    {
                      if ( CContentAnalyzer::FindMimeFromExt(this, v54, &v85) )
                      {
                        if ( v8 && StrCmpICW(v8, L"message/rfc822") && !StrCmpICW((LPCWSTR)this + 60, L"message/rfc822") )
                        {
                          *((_QWORD *)this + 7) = v8;
                          *a7 = 64;
                        }
                        else
                        {
                          if ( v75 && v8 && !StrCmpICW(v8, L"application/octet-stream") )
                          {
                            for ( m = 0; m < 0x17; ++m )
                            {
                              if ( !StrCmpICW((LPCWSTR)this + 60, off_180124DA0[m]) )
                              {
                                *((_QWORD *)this + 7) = v8;
                                *a7 = 16;
                                goto LABEL_46;
                              }
                            }
                          }
                          if ( !v85
                            || !v8
                            && (!StrCmpICW((LPCWSTR)this + 60, L"image/svg+xml")
                             || !StrCmpICW((LPCWSTR)this + 60, L"application/xhtml+xml")) )
                          {
LABEL_226:
                            *((_QWORD *)this + 7) = (char *)this + 120;
                            *a7 = 2;
                          }
                        }
                        goto LABEL_46;
                      }
                      v54 = pszStr1a;
                    }
                    if ( v54 && CContentAnalyzer::FindAppFromExt(v56, v54, v97, v37) )
                    {
                      *((_QWORD *)this + 7) = L"application/octet-stream";
                      *a7 = 4;
                    }
LABEL_46:
                    *(_BYTE *)(*((_QWORD *)this + 4) + *(int *)this - 1LL) = *((_BYTE *)this + 40);
                    goto LABEL_47;
                }
                if ( v74 )
                  goto LABEL_162;
                goto LABEL_123;
              }
              if ( StrCmpICW(*((LPCWSTR *)this + 7), L"(null)") )
              {
                EnterCriticalSection(&g_mxsMedia);
                v58 = WideCharToMultiByte(0, 0, v55, -1, 0, 0, 0, 0) + 1;
                v59 = (CHAR *)operator new(v58);
                v60 = v59;
                if ( v59 )
                {
                  if ( !WideCharToMultiByte(0, 0, v55, -1, v59, v58, 0, 0) )
                  {
                    CoTaskMemFree(v60);
                    v60 = 0;
                  }
                  InternalRegisterDefaultMediaType();
                  if ( v60 )
                  {
                    v61 = 0;
                    v86 = 0;
                    MediaTypeHolder = GetMediaTypeHolder();
                    if ( MediaTypeHolder )
                    {
                      v63 = (__int64 *)*((_QWORD *)MediaTypeHolder + 2);
                      if ( v63 )
                      {
                        v87 = 0;
                        v82 = -2147024809;
                        do
                        {
                          v64 = *v63;
                          for ( n = 0; ; n = (unsigned int)(n + 1) )
                          {
                            if ( (unsigned int)n >= *((_DWORD *)v63 + 4) )
                            {
                              v68 = v87;
                              v67 = v82;
                              goto LABEL_153;
                            }
                            v66 = (LPCSTR *)(v64 + 48 * n);
                            if ( !StrCmpICA(v60, *v66) )
                              break;
                          }
                          v67 = 0;
                          v68 = v64 + 48 * n;
                          v87 = v68;
                          v82 = 0;
                          if ( v66 )
                            break;
LABEL_153:
                          v63 = (__int64 *)v63[3];
                        }
                        while ( v63 );
                        if ( v67 )
                          v61 = v86;
                        else
                          v61 = *(_DWORD *)(v68 + 12);
                      }
                    }
                    else
                    {
                      v82 = -2147467259;
                    }
                    CoTaskMemFree(v60);
                    LeaveCriticalSection(&g_mxsMedia);
                    if ( v82 || v61 != 1 )
                      goto LABEL_46;
                    goto LABEL_158;
                  }
                }
                else
                {
                  InternalRegisterDefaultMediaType();
                }
                LeaveCriticalSection(&g_mxsMedia);
                goto LABEL_46;
              }
LABEL_158:
              v54 = pszStr1a;
              goto LABEL_122;
            }
            v53 = L"application/vnd.apple.mpegurl";
          }
          else
          {
            v53 = L"application/base64";
          }
        }
        else
        {
          v38 = v75;
          v53 = L"text/richtext";
        }
        goto LABEL_117;
      }
      v53 = L"application/postscript";
    }
    else
    {
      v53 = L"application/pdf";
    }
    v38 = v75;
LABEL_117:
    *((_QWORD *)this + 7) = v53;
    goto LABEL_118;
  }
  *((_QWORD *)this + 7) = v8;
  *a7 = 16;
  if ( lpVtbl_high == 1 )
  {
    if ( v8 && StrCmpICW(v8, L"(null)") )
    {
      if ( StrCmpICW(v8, L"application/octet-stream") )
      {
        if ( !StrCmpICW(v8, L"text/plain") )
          *a7 = 8;
      }
      else
      {
        *a7 = 4;
      }
    }
    else
    {
      *a7 = 1;
    }
  }
LABEL_45:
  if ( a4 > 0 )
    goto LABEL_46;
LABEL_47:
  v29 = *((_QWORD *)this + 7);
  v90 = &CUString::`vftable';
  v30 = v91 != 0;
  if ( v91 || v92 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v94 = 0;
    if ( v30 && v91 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
  }
  return (const unsigned __int16 *)v29;
}

```

## disassembly

```asm
0x18001f9a0  mov     [rsp-8+arg_10], rbx
0x18001f9a5  push    rbp
0x18001f9a6  push    rsi
0x18001f9a7  push    rdi
0x18001f9a8  push    r12
0x18001f9aa  push    r13
0x18001f9ac  push    r14
0x18001f9ae  push    r15
0x18001f9b0  lea     rbp, [rsp-220h]
0x18001f9b8  sub     rsp, 320h
0x18001f9bf  mov     rax, cs:__security_cookie
0x18001f9c6  xor     rax, rsp
0x18001f9c9  mov     [rbp+250h+var_40], rax
0x18001f9d0  mov     r13, [rbp+250h+arg_30]
0x18001f9d7  mov     r14, rcx
0x18001f9da  mov     rsi, [rbp+250h+Str]
0x18001f9e1  mov     ecx, 2000000Fh
0x18001f9e6  mov     [rsp+350h+var_308], r13
0x18001f9eb  mov     rdi, r8
0x18001f9ee  mov     [rsp+350h+var_2F8], r9d
0x18001f9f3  mov     [rsp+350h+pszStr1], r8
0x18001f9f8  mov     [rbp+250h+lpWideCharStr], rdx
0x18001f9fc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18001fa02  mov     edx, cs:_tls_index
0x18001fa08  movzx   r15d, al
0x18001fa0c  mov     rcx, gs:58h
0x18001fa15  mov     [rsp+350h+var_310], al
0x18001fa19  mov     eax, 4
0x18001fa1e  mov     rcx, [rcx+rdx*8]
0x18001fa22  mov     ecx, [rax+rcx]
0x18001fa25  cmp     cs:dword_1801656C8, ecx
0x18001fa2b  jg      loc_1800205E9
0x18001fa31  mov     r12d, [rbp+250h+arg_28]
0x18001fa38  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001fa3f  mov     [rbp+250h+var_2A8], rax
0x18001fa43  xorps   xmm0, xmm0
0x18001fa46  mov     [rbp+250h+var_2A0], 0
0x18001fa4e  mov     [rbp+250h+var_298], 0Bh
0x18001fa55  mov     [rbp+250h+var_280], 0
0x18001fa5c  mov     [rsp+350h+var_2D4], 0
0x18001fa64  mov     [r14+40h], r12d
0x18001fa68  movdqu  xmmword ptr [rbp+250h+bstrString], xmm0
0x18001fa6d  test    rsi, rsi
0x18001fa70  jz      short loc_18001FAE3
0x18001fa72  lea     rdx, SubStr; ";"
0x18001fa79  mov     rcx, rsi; Str
0x18001fa7c  call    cs:__imp_wcsstr
0x18001fa82  mov     rbx, rax
0x18001fa85  test    rax, rax
0x18001fa88  jnz     loc_180020993
0x18001fa8e  test    r15b, r15b
0x18001fa91  jz      short loc_18001FAE3
0x18001fa93  lea     rdx, aNull_2; "(null)"
0x18001fa9a  mov     rcx, rsi; pszStr1
0x18001fa9d  call    cs:__imp_StrCmpICW
0x18001faa3  test    eax, eax
0x18001faa5  jz      short loc_18001FAE3
0x18001faa7  test    rbx, rbx
0x18001faaa  jnz     short loc_18001FAC3
0x18001faac  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001fab3  cmp     word ptr [rsi+rax*2+2], 0
0x18001fab9  lea     rax, [rax+1]
0x18001fabd  jnz     short loc_18001FAB3
0x18001fabf  lea     rbx, [rsi+rax*2]
0x18001fac3  cmp     rbx, rsi
0x18001fac6  jnz     loc_1800200B4
0x18001facc  mov     edx, 2Ch ; ','; Ch
0x18001fad1  mov     rcx, rsi; Str
0x18001fad4  call    cs:__imp_wcsrchr
0x18001fada  test    rax, rax
0x18001fadd  jnz     loc_18002099D
0x18001fae3  mov     r15, cs:?g_pFeatureCache@@3PEAVCFeatureCache@@EA; CFeatureCache * g_pFeatureCache
0x18001faea  test    r15, r15
0x18001faed  jz      loc_18001FD86
0x18001faf3  test    byte ptr [r15], 8
0x18001faf7  jnz     short loc_18001FB51
0x18001faf9  call    cs:__imp_?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x18001faff  lea     r8, ?__CoInternetIsFeatureEnabledInternal_IFL@@YAJW4_tagINTERNETFEATURELIST@@@Z; __CoInternetIsFeatureEnabledInternal_IFL(_tagINTERNETFEATURELIST)
0x18001fb06  mov     edx, 3
0x18001fb0b  mov     r9, rax
0x18001fb0e  mov     rcx, [rax]
0x18001fb11  mov     rax, [rcx+8]
0x18001fb15  mov     rcx, r9
0x18001fb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb1d  lea     rcx, [r15+10h]; lpCriticalSection
0x18001fb21  movzx   ebx, al
0x18001fb24  call    cs:__imp_EnterCriticalSection
0x18001fb2a  mov     r8, [r15+8]
0x18001fb2e  lea     rcx, [r15+10h]; lpCriticalSection
0x18001fb32  mov     rdx, r8
0x18001fb35  or      r8, 8
0x18001fb39  and     rdx, 0FFFFFFFFFFFFFFF7h
0x18001fb3d  test    bl, bl
0x18001fb3f  cmovz   r8, rdx
0x18001fb43  or      qword ptr [r15], 8
0x18001fb47  mov     [r15+8], r8
0x18001fb4b  call    cs:__imp_LeaveCriticalSection
0x18001fb51  movzx   eax, byte ptr [r15+8]
0x18001fb56  not     al
0x18001fb58  movzx   eax, al
0x18001fb5b  shr     eax, 3
0x18001fb5e  and     eax, 1
0x18001fb61  mov     ebx, [rsp+350h+var_2F8]
0x18001fb65  xor     ecx, ecx
0x18001fb67  cmp     eax, 1
0x18001fb6a  setnz   cl
0x18001fb6d  xor     r15d, r15d
0x18001fb70  test    r12b, 2
0x18001fb74  cmovz   r15d, ecx
0x18001fb78  mov     [rsp+350h+var_2D8], r15d
0x18001fb7d  test    rdi, rdi
0x18001fb80  jnz     loc_180020172
0x18001fb86  test    r12b, r12b
0x18001fb89  js      loc_1800209A6
0x18001fb8f  mov     r13d, r12d
0x18001fb92  and     r13d, 40h
0x18001fb96  mov     [rbp+250h+var_2D0], r13d
0x18001fb9a  test    rsi, rsi
0x18001fb9d  jnz     loc_18002030D
0x18001fba3  mov     eax, r12d
0x18001fba6  lea     r13, aTextPlain_0; "text/plain"
0x18001fbad  and     eax, 4
0x18001fbb0  mov     dword ptr [rbp+250h+var_2C8], eax
0x18001fbb3  test    r15d, r15d
0x18001fbb6  jnz     loc_180020748
0x18001fbbc  test    r12b, 8
0x18001fbc0  jnz     loc_180020656
0x18001fbc6  mov     [rsp+350h+var_2E8], 80004005h
0x18001fbce  test    rsi, rsi
0x18001fbd1  jnz     loc_18001FF2E
0x18001fbd7  mov     r15d, 1
0x18001fbdd  mov     dword ptr [rsp+350h+var_300], r15d
0x18001fbe2  test    rdi, rdi
0x18001fbe5  jz      loc_18001FCD1
0x18001fbeb  cmp     [rsp+350h+var_2F8], 0
0x18001fbf0  jle     loc_18001FCD1
0x18001fbf6  mov     r15, [rbp+250h+lpWideCharStr]
0x18001fbfa  xor     edi, edi
0x18001fbfc  mov     ebx, r12d
0x18001fbff  mov     [rsp+350h+pszStr1], rdi
0x18001fc04  and     ebx, 10h
0x18001fc07  test    r15, r15
0x18001fc0a  jnz     loc_1800204F9
0x18001fc10  mov     r15, [rsp+350h+var_308]
0x18001fc15  mov     rcx, r14; this
0x18001fc18  mov     dword ptr [r15], 10h
0x18001fc1f  call    ?SampleData@CContentAnalyzer@@AEAAXXZ; CContentAnalyzer::SampleData(void)
0x18001fc24  test    ebx, ebx
0x18001fc26  jnz     loc_180020A6A
0x18001fc2c  cmp     dword ptr [r14+60h], 0
0x18001fc31  jnz     loc_180020581
0x18001fc37  cmp     dword ptr [r14+64h], 0
0x18001fc3c  jnz     loc_180020AAD
0x18001fc42  cmp     dword ptr [r14+70h], 0
0x18001fc47  jnz     loc_180020AC8
0x18001fc4d  lea     r15, aApplicationOct_1; "application/octet-stream"
0x18001fc54  lea     r13, aApplicationPdf_0; "application/pdf"
0x18001fc5b  lea     rbx, ?g_vwzApplicationXML@@3QBGB; "application/xml"
0x18001fc62  test    rsi, rsi
0x18001fc65  jnz     loc_1800207CF
0x18001fc6b  xor     r13d, r13d
0x18001fc6e  test    rsi, rsi
0x18001fc71  jnz     loc_180020AF5
0x18001fc77  cmp     [rsp+350h+var_310], r13b
0x18001fc7c  jnz     loc_180020772
0x18001fc82  xor     ecx, ecx
0x18001fc84  mov     rax, [rbp+250h+lpWideCharStr]
0x18001fc88  mov     dword ptr [rsp+350h+var_300+4], ecx
0x18001fc8c  mov     [rsp+350h+var_2F8], ecx
0x18001fc90  test    rax, rax
0x18001fc93  jnz     loc_18001FD97
0x18001fc99  xor     edi, edi
0x18001fc9b  xor     ebx, ebx
0x18001fc9d  test    rsi, rsi
0x18001fca0  jnz     loc_180020591
0x18001fca6  lea     r12, aTextPlain_0; "text/plain"
0x18001fcad  mov     r8d, 1
0x18001fcb3  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x18001fcba  jnz     loc_180020B60
0x18001fcc0  cmp     dword ptr [r14+54h], 0
0x18001fcc5  jz      loc_18001FE3A
0x18001fccb  mov     [r14+38h], r15
0x18001fccf  jmp     short loc_18001FCF1
0x18001fcd1  mov     rbx, [rsp+350h+var_308]
0x18001fcd6  mov     [r14+38h], rsi
0x18001fcda  mov     dword ptr [rbx], 10h
0x18001fce0  cmp     r15d, 1
0x18001fce4  jz      loc_180020734
0x18001fcea  cmp     [rsp+350h+var_2F8], 0
0x18001fcef  jle     short loc_18001FD01
0x18001fcf1  movsxd  rdx, dword ptr [r14]
0x18001fcf4  mov     rcx, [r14+20h]
0x18001fcf8  movzx   eax, byte ptr [r14+28h]
0x18001fcfd  mov     [rcx+rdx-1], al
0x18001fd01  mov     rdi, [r14+38h]
0x18001fd05  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18001fd0c  xor     esi, esi
0x18001fd0e  mov     [rbp+250h+var_2A8], rax
0x18001fd12  mov     ebx, esi
0x18001fd14  mov     eax, esi
0x18001fd16  cmp     [rbp+250h+var_2A0], rbx
0x18001fd1a  setnz   bl
0x18001fd1d  cmp     [rbp+250h+var_298], 0Bh
0x18001fd21  setnz   al
0x18001fd24  test    ebx, ebx
0x18001fd26  jz      loc_18001FE2D
0x18001fd2c  mov     rcx, [rbp+250h+bstrString]; bstrString
0x18001fd30  test    rcx, rcx
0x18001fd33  jnz     loc_180020E69
0x18001fd39  mov     [rbp+250h+bstrString+8], rsi
0x18001fd3d  mov     [rbp+250h+var_280], esi
0x18001fd40  test    ebx, ebx
0x18001fd42  jz      short loc_18001FD59
0x18001fd44  mov     rcx, [rbp+250h+var_2A0]
0x18001fd48  test    rcx, rcx
0x18001fd4b  jz      short loc_18001FD59
0x18001fd4d  mov     rax, [rcx]
0x18001fd50  mov     rax, [rax+10h]
0x18001fd54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd59  mov     rax, rdi
0x18001fd5c  mov     rcx, [rbp+250h+var_40]
0x18001fd63  xor     rcx, rsp; StackCookie
0x18001fd66  call    __security_check_cookie
0x18001fd6b  mov     rbx, [rsp+350h+arg_10]
0x18001fd73  add     rsp, 320h
0x18001fd7a  pop     r15
0x18001fd7c  pop     r14
0x18001fd7e  pop     r13
0x18001fd80  pop     r12
0x18001fd82  pop     rdi
0x18001fd83  pop     rsi
0x18001fd84  pop     rbp
0x18001fd85  retn
0x18001fd86  lea     rcx, ?PRIVATE_INTERNETFEATURELIST_FEATURE_MIME_SNIFFING@FCK@@3VCFeatureControlKey@@A; this
0x18001fd8d  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18001fd92  jmp     loc_18001FB61
0x18001fd97  mov     [rsp+350h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x18001fd9c  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18001fda2  mov     [rsp+350h+lpDefaultChar], rcx; lpDefaultChar
0x18001fda7  mov     r8, rax; lpWideCharStr
0x18001fdaa  lea     rcx, [rbp+250h+MultiByteStr]
0x18001fdae  mov     [rsp+350h+cbMultiByte], 104h; cbMultiByte
0x18001fdb6  mov     [rsp+350h+lpMultiByteStr], rcx; lpMultiByteStr
0x18001fdbb  xor     edx, edx; dwFlags
0x18001fdbd  xor     ecx, ecx; CodePage
0x18001fdbf  call    cs:__imp_WideCharToMultiByte
0x18001fdc5  test    eax, eax
0x18001fdc7  jz      loc_1800201A6
0x18001fdcd  test    r12b, 1
0x18001fdd1  jnz     loc_180020B40
0x18001fdd7  lea     rcx, [rbp+250h+MultiByteStr]
0x18001fddb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001fde2  inc     rax
0x18001fde5  cmp     byte ptr [rcx+rax], 0
0x18001fde9  jnz     short loc_18001FDE2
0x18001fdeb  lea     rbx, [rbp+250h+MultiByteStr]
0x18001fdef  add     rbx, rax
0x18001fdf2  jz      loc_18001FC99
0x18001fdf8  nop     dword ptr [rax+rax+00000000h]
0x18001fe00  lea     rax, [rbp+250h+MultiByteStr]
0x18001fe04  cmp     rbx, rax
0x18001fe07  jb      loc_18001FC99
0x18001fe0d  movzx   eax, byte ptr [rbx]
0x18001fe10  cmp     al, 2Fh ; '/'
0x18001fe12  jz      loc_18001FC99
0x18001fe18  cmp     al, 2Eh ; '.'
0x18001fe1a  jz      loc_180020847
0x18001fe20  cmp     al, 5Ch ; '\'
0x18001fe22  jz      loc_18001FC99
0x18001fe28  dec     rbx
0x18001fe2b  jmp     short loc_18001FE00
0x18001fe2d  test    eax, eax
0x18001fe2f  jz      loc_18001FD59
0x18001fe35  jmp     loc_18001FD2C
0x18001fe3a  cmp     dword ptr [r14+5Ch], 0
0x18001fe3f  mov     eax, [rsp+350h+var_2D8]
0x18001fe43  jnz     loc_180020706
0x18001fe49  cmp     dword ptr [r14+48h], 0
0x18001fe4e  jnz     loc_1800206B4
0x18001fe54  cmp     dword ptr [r14+50h], 0
0x18001fe59  jnz     loc_180020C43
0x18001fe5f  cmp     dword ptr [r14+58h], 0
0x18001fe64  jnz     loc_180020C53
0x18001fe6a  mov     edx, [r14+18h]
0x18001fe6e  test    edx, edx
0x18001fe70  jnz     loc_1800201AF
0x18001fe76  mov     rcx, [r14+20h]; pszStr1
0x18001fe7a  lea     rdx, aPdf; "%PDF"
0x18001fe81  mov     r8d, 4; nChar
0x18001fe87  mov     dword ptr [r14+44h], 0
0x18001fe8f  call    cs:__imp_StrCmpNCA
0x18001fe95  test    eax, eax
0x18001fe97  jz      loc_180020570
0x18001fe9d  mov     rcx, [r14+20h]; pszStr1
0x18001fea1  lea     rdx, asc_18012B544; "%!"
0x18001fea8  mov     r8d, 2; nChar
0x18001feae  call    cs:__imp_StrCmpNCA
0x18001feb4  test    eax, eax
0x18001feb6  jz      loc_180020C9F
0x18001febc  mov     rcx, [r14+20h]; pszStr1
  ... truncated ...
```
