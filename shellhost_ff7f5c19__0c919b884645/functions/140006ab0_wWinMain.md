# wWinMain

- ea: `0x140006ab0`
- end: `0x140007fd5`
- name: `wWinMain`
- size: `5413`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000f630`

## callees

- `0x140006ab0`
- `0x140009d6c`
- `0x14000a310`
- `0x14000ab50`
- `0x14000b360`
- `0x14000b420`
- `0x14000c16c`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fab8`
- `0x140010620`
- `0x14001062c`
- `0x140046a30`
- `0x14004a824`
- `0x14004a834`
- `0x14004a9e0`
- `0x14004afcc`
- `0x14004b970`
- `0x14004e6b0`
- `0x140051114`
- `0x140053190`
- `0x140054550`
- `0x140057044`
- `0x140058bec`
- `0x140059d70`
- `0x14005b270`
- `0x14005beb0`
- `0x14005cd64`
- `0x14005d180`
- `0x14005d1a8`
- `0x14005d2e0`
- `0x14005d8dc`
- `0x14005eafc`
- `0x140067010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140006d6b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140006d6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e54`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e54`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400076b3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400076b3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140007659`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140007659`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140006ed7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140006ed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007dd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007dd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400076cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400076cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400077b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400077b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140007187`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140007187`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400071d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400071d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000719e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000719e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007bfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007d07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007bfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007d07`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140006fff`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140007906`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140006fff`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140007906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006eed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006eed`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006ec8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006ec8`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140006ee7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140006ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400071bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000787c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007b99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007df1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400071bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000787c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007b99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007df1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007c9a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007cac`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007d8c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007d9e`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007c9a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007cac`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007d8c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140007d9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006e6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006e6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007dac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007cba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007dac`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x140006efd`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x140006efd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140006c4f`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400077e7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140007b17`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1400077e7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x140007b17`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140007e2f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140007e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006ce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006e8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006ce4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006e8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006f6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006f6c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006f0a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006f0a`

## string_xrefs

- `0x140007e4d`: `kernelbase.dll`
- `0x140007ebc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140007ca0`: `CommunicationHWND`
- `0x140007d92`: `CommunicationHWND`
- `0x140007c89`: `ProcessId`
- `0x140007d7b`: `ProcessId`
- `0x140006ef6`: `ShellHost main thread`
- `0x140007eaa`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x140006cf7`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x140006d3b`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x140006e01`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x140007f65`: `shellcommon\internal\shell\inc\SingletonHelpers.h`
- `0x140007f77`: `shellcommon\internal\shell\inc\SingletonHelpers.h`
- `0x140007f89`: `shellcommon\internal\shell\inc\SingletonHelpers.h`
- `0x140007f9b`: `shellcommon\internal\shell\inc\SingletonHelpers.h`
- `0x140007fad`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  void *v5; // rdi
  int v6; // ebx
  const char *v7; // r9
  char *v8; // rax
  __int64 v9; // rcx
  char *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // r14
  _WORD *v14; // rax
  _WORD *v15; // rbx
  __int64 v16; // rdx
  void *v17; // rbx
  unsigned __int64 v18; // r15
  __int64 v19; // rax
  __int64 v20; // rsi
  _WORD *v21; // rax
  void *v22; // r14
  DWORD LastError; // esi
  int v24; // esi
  wchar_t *v25; // rax
  wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  void *v29; // rbx
  HANDLE CurrentThread; // rax
  int *v32; // rbx
  LPVOID v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // rcx
  char *v38; // rdx
  unsigned __int64 v39; // rbx
  size_t v40; // rbx
  char *v41; // r14
  char *v42; // r15
  void *v43; // rax
  size_t v44; // rbx
  char *v45; // r12
  char *v46; // r13
  void *v47; // rax
  char *Event; // rbx
  void *v49; // rdx
  unsigned int v50; // r8d
  const char *v51; // r9
  HANDLE v52; // rdi
  DWORD v53; // esi
  unsigned int v54; // r8d
  const char *v55; // r9
  char *v56; // r15
  __int64 v57; // rdi
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // rdx
  unsigned __int64 v60; // rsi
  size_t v61; // rsi
  _QWORD *v62; // rbx
  void *v63; // rax
  unsigned __int64 v64; // rdx
  char *v65; // rcx
  _QWORD *v66; // rdi
  _QWORD *v67; // rbx
  __int64 v68; // rax
  __int64 v69; // rsi
  unsigned __int64 v70; // rcx
  unsigned int v71; // r8d
  unsigned __int64 v72; // rax
  unsigned __int64 v73; // rcx
  unsigned __int64 v74; // rax
  char *v75; // r15
  void *v76; // rax
  struct winrt::impl::hstring_header *hstring_on_heap; // rax
  char *v78; // rsi
  unsigned __int64 v79; // rdx
  char *v80; // rcx
  HKEY v81; // rax
  char *v82; // r9
  __int64 v83; // r15
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rdx
  unsigned __int64 v86; // r13
  size_t v87; // r13
  _QWORD *v88; // rsi
  void *v89; // rax
  unsigned __int64 v90; // rdx
  char *v91; // rcx
  void *v92; // rdx
  unsigned int v93; // r8d
  const char *v94; // r9
  char *v95; // rax
  PSRWLOCK v96; // r15
  __int64 v97; // rbx
  RTL_SRWLOCK *v98; // rdi
  char *Ptr; // rbx
  char *i; // rsi
  char *v101; // rcx
  unsigned __int64 v102; // rdx
  _BYTE *v103; // rax
  _BYTE *v104; // rsi
  _QWORD *v105; // rax
  unsigned __int64 v106; // r15
  HRESULT v107; // eax
  _QWORD *j; // rbx
  char v109; // al
  char *v110; // rcx
  char *k; // rbx
  __int64 v112; // rcx
  unsigned __int64 v113; // rax
  unsigned __int64 v114; // rdi
  HKEY *v115; // rbx
  HKEY *v116; // rdi
  HKEY v117; // rax
  HKEY *v118; // r12
  unsigned __int128 v119; // kr00_16
  HKEY *v120; // r15
  HKEY v121; // rax
  signed __int64 v122; // rbx
  __int64 v123; // r13
  unsigned __int64 v124; // rdi
  unsigned __int64 v125; // rcx
  unsigned __int64 v126; // r14
  size_t v127; // r14
  _QWORD *v128; // rsi
  void *v129; // rax
  unsigned __int64 v130; // rbx
  HRESULT v131; // eax
  unsigned int v132; // r8d
  _QWORD *v133; // rsi
  _QWORD *v134; // r14
  _QWORD *m; // rbx
  char *v136; // rcx
  char *v137; // rdi
  const char *v138; // r9
  _QWORD *v139; // rcx
  __int64 v140; // r13
  __int64 v141; // rax
  _QWORD *v142; // rax
  HKEY v143; // rbx
  char *v144; // rdi
  const char *v145; // r9
  _QWORD *v146; // rax
  __int64 v147; // rcx
  _QWORD *v148; // rax
  __int64 v149; // rcx
  HKEY v150; // rbx
  void *v151; // rcx
  unsigned int v152; // r8d
  const char *v153; // r9
  void *v154; // rcx
  unsigned int v155; // r8d
  const char *v156; // r9
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwindex; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  char *v166; // [rsp+58h] [rbp-A8h] BYREF
  char *v167; // [rsp+60h] [rbp-A0h] BYREF
  BOOL fPending[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v169[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v170; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v171[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v172[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v173; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v174[13]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *v175; // [rsp+158h] [rbp+58h]
  int v176; // [rsp+160h] [rbp+60h] BYREF
  __int64 v177; // [rsp+168h] [rbp+68h]
  int v178; // [rsp+170h] [rbp+70h]
  __int64 v179; // [rsp+178h] [rbp+78h]
  int v180; // [rsp+180h] [rbp+80h]
  __int64 v181; // [rsp+188h] [rbp+88h]
  _OWORD v182[3]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE Source[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  while ( 1 )
  {
    v5 = 0;
    v167 = 0;
    v166 = 0;
    v174[0] = &wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
    v174[1] = &v166;
    v174[2] = &v167;
    v175 = (wil::details::in1diag3 *)v174;
    memset_0(Source, 0, sizeof(Source));
    pv = 0;
    v171[0] = &pv;
    v169[0] = 128;
    hKey = (HKEY)Source;
    v6 = wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
           v174,
           &hKey,
           v169,
           v171);
    if ( v6 < 0 )
      goto LABEL_28;
    v8 = (char *)pv;
    if ( (unsigned __int64)pv > 0x80 )
    {
      v17 = 0;
      while ( 1 )
      {
        v18 = (unsigned __int64)v8;
        v19 = (__int64)(v8 - 1);
        if ( v19 == -1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF89,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v7);
        v20 = v19;
        v21 = CoTaskMemAlloc(2 * v19 + 2);
        v22 = v21;
        if ( v21 )
        {
          *v21 = 0;
          v21[v20] = 0;
        }
        if ( v17 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v17);
          SetLastError(LastError);
        }
        if ( !v22 )
          break;
        hKey = (HKEY)&pv;
        v169[0] = v18;
        v171[0] = v22;
        if ( !v175 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
        v6 = (*(__int64 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, _QWORD *, HKEY *))(*(_QWORD *)v175 + 32LL))(
               v175,
               v171,
               v169,
               &hKey);
        if ( v6 < 0 )
        {
          CoTaskMemFree(v22);
          goto LABEL_28;
        }
        v17 = v22;
        v8 = (char *)pv;
        if ( (unsigned __int64)pv <= v18 )
        {
          v5 = v22;
          v6 = 0;
          goto LABEL_28;
        }
      }
      v16 = 378;
      goto LABEL_27;
    }
    v9 = (__int64)pv - 1;
    v10 = Source;
    if ( (char *)pv - 1 >= (char *)0x7FFFFFFF )
    {
      v11 = 0x7FFFFFFF;
      do
      {
LABEL_7:
        if ( !*(_WORD *)v10 )
          break;
        v10 += 2;
        --v11;
      }
      while ( v11 );
      goto LABEL_9;
    }
    v11 = (__int64)pv - 1;
    if ( pv != (LPVOID)1 )
      goto LABEL_7;
LABEL_9:
    v12 = (v10 - Source) >> 1;
    if ( !pv )
      v9 = v12;
    v13 = v9;
    v14 = CoTaskMemAlloc(2 * v9 + 2);
    v15 = v14;
    if ( v14 )
    {
      memcpy_s(v14, v13 * 2 + 2, Source, 2 * v12);
      v15[v12] = 0;
      v15[v13] = 0;
      v5 = v15;
      v6 = 0;
      goto LABEL_28;
    }
    v16 = 367;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      (const char *)0x8007000ELL,
      pdwType);
    v6 = -2147024882;
LABEL_28:
    v24 = 0;
    if ( v175 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v175 + 24LL))(v175);
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A7,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
        (const char *)(unsigned int)v6,
        pdwType);
LABEL_32:
      if ( v5 )
        CoTaskMemFree(v5);
      goto LABEL_50;
    }
    v25 = wcsrchr((const wchar_t *)v5, 0x5Cu);
    if ( v25 )
    {
      v26 = v25 + 1;
      pv = 0;
      if ( v25 == (wchar_t *)-2LL )
      {
        v27 = 0;
      }
      else
      {
        v27 = -1;
        do
          ++v27;
        while ( v26[v27] );
      }
      *(_QWORD *)&v172[0] = v26;
      *((_QWORD *)&v172[0] + 1) = v27;
      *(_QWORD *)&v170 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\";
      *((_QWORD *)&v170 + 1) = 74;
      v172[2] = 0u;
      v182[0] = 0u;
      v182[1] = v170;
      v182[2] = v172[0];
      v28 = wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pv,
              v182,
              3);
      v6 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AD,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
          (const char *)(unsigned int)v28,
          pdwType);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_32;
      }
      fPending[0] = 0;
      dwindex = 4;
      v29 = pv;
      if ( !RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv, L"WaitForDebuggerPresent", 0x10010u, 0, fPending, &dwindex) )
        v24 = fPending[0];
      if ( v29 )
        CoTaskMemFree(v29);
    }
    if ( v5 )
      CoTaskMemFree(v5);
    v6 = 0;
LABEL_50:
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v6,
        pdwType);
    if ( !v24 )
      goto LABEL_60;
    if ( wil::g_fIsDebuggerPresent )
      break;
    if ( !(wil::g_pfnIsDebuggerPresent
         ? (unsigned __int8)wil::g_pfnIsDebuggerPresent(retaddr) == 0
         : !IsDebuggerPresent()) )
      break;
    Sleep(0x1F4u);
  }
  if ( v24 == 2 )
    DebugBreak();
LABEL_60:
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"ShellHost main thread");
  CoInitializeEx(0, 2u);
  v176 = 1;
  v177 = 2;
  v178 = 4;
  v179 = 536;
  v180 = 5;
  v181 = 1;
  pv = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &pv) >= 0 )
  {
    v32 = &v176;
    do
    {
      (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)pv + 24LL))(
        pv,
        (unsigned int)*v32,
        *((_QWORD *)v32 + 1));
      v32 += 4;
    }
    while ( v32 != (int *)v182 );
  }
  v33 = pv;
  if ( pv )
  {
    pv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  }
  ParseCommandLine(0, lpCmdLine);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    if ( qword_1400841A8 || (g_shellHostConfigurationFlags & 1) != 0 )
      SetProcessShutdownParameters(2u, 0);
LABEL_69:
    v37 = 0x1FFFFFFFFFFFFFFFLL;
    while ( qword_1400841A8 || (g_shellHostConfigurationFlags & 1) != 0 )
    {
      v172[0] = 0;
      v38 = 0;
      v167 = 0;
      v39 = qword_1400841A8 + 1;
      if ( qword_1400841A8 == -1 )
      {
        v42 = (char *)*((_QWORD *)&v172[0] + 1);
        v41 = *(char **)&v172[0];
      }
      else
      {
        if ( v39 > 0x1FFFFFFFFFFFFFFFLL )
          goto LABEL_299;
        v40 = 8 * v39;
        if ( v40 )
        {
          if ( v40 < 0x1000 )
          {
            v41 = (char *)operator new(v40);
          }
          else
          {
            if ( v40 + 39 < v40 )
              goto LABEL_298;
            v43 = operator new(v40 + 39);
            if ( !v43 )
              goto LABEL_252;
            v41 = (char *)(((unsigned __int64)v43 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v41 - 1) = v43;
          }
          v37 = 0x1FFFFFFFFFFFFFFFLL;
          v42 = v41;
          v38 = &v41[v40];
          v167 = &v41[v40];
        }
        else
        {
          v41 = 0;
          v42 = 0;
          v38 = 0;
          v167 = 0;
        }
      }
      v173 = 0;
      pv = 0;
      if ( qword_1400841A8 )
      {
        if ( (unsigned __int64)qword_1400841A8 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_293:
          std::vector<void *>::_Xlength(v37, v38, v35);
        v44 = 8 * qword_1400841A8;
        if ( 8 * qword_1400841A8 )
        {
          if ( v44 < 0x1000 )
          {
            v45 = (char *)operator new(v44);
            v46 = v45;
            pv = &v45[v44];
          }
          else
          {
            if ( v44 + 39 < v44 )
              goto LABEL_298;
            v47 = operator new(v44 + 39);
            if ( !v47 )
              goto LABEL_252;
            v45 = (char *)(((unsigned __int64)v47 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v45 - 1) = v47;
            v46 = v45;
            pv = &v45[v44];
          }
        }
        else
        {
          v45 = 0;
          v46 = 0;
          pv = 0;
        }
      }
      else
      {
        v46 = (char *)*((_QWORD *)&v173 + 1);
        v45 = (char *)v173;
      }
      Event = (char *)g_refreshWaitArrayEvent;
      v166 = (char *)g_refreshWaitArrayEvent;
      if ( !g_refreshWaitArrayEvent )
      {
        Event = (char *)CreateEventExW(0, 0, 0, 0x1F0003u);
        v166 = Event;
        if ( !Event )
          wil::details::in1diag3::Throw_GetLastError(retaddr, v49, v50, v51);
        GetLastError();
        v52 = g_refreshWaitArrayEvent;
        if ( g_refreshWaitArrayEvent )
        {
          v53 = GetLastError();
          if ( !CloseHandle(v52) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v54, v55);
          SetLastError(v53);
        }
        g_refreshWaitArrayEvent = Event;
      }
      v37 = (__int64)v167;
      if ( v42 == v167 )
      {
        v57 = (v42 - v41) >> 3;
        if ( v57 == 0x1FFFFFFFFFFFFFFFLL )
LABEL_299:
          std::vector<void *>::_Xlength(v37, v38, v35);
        v58 = (v167 - v41) >> 3;
        v59 = v58 >> 1;
        if ( v58 > 0x1FFFFFFFFFFFFFFFLL - (v58 >> 1) )
          goto LABEL_298;
        v60 = v57 + 1;
        if ( v59 + v58 >= v57 + 1 )
          v60 = v59 + v58;
        if ( v60 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_298:
          std::_Throw_bad_array_new_length();
        v61 = 8 * v60;
        if ( v61 )
        {
          if ( v61 < 0x1000 )
          {
            v62 = operator new(v61);
          }
          else
          {
            if ( v61 + 39 < v61 )
              goto LABEL_298;
            v63 = operator new(v61 + 39);
            if ( !v63 )
              goto LABEL_252;
            v62 = (_QWORD *)(((unsigned __int64)v63 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v62 - 1) = v63;
          }
        }
        else
        {
          v62 = 0;
        }
        v62[v57] = v166;
        memmove_0(v62, v41, v42 - v41);
        if ( v41 )
        {
          v64 = 8 * ((v167 - v41) >> 3);
          if ( v64 < 0x1000 )
          {
            v65 = v41;
          }
          else
          {
            v65 = (char *)*((_QWORD *)v41 - 1);
            if ( (unsigned __int64)(v41 - v65 - 8) > 0x1F )
              goto LABEL_252;
            v64 += 39LL;
          }
          operator delete(v65, v64);
        }
        v41 = (char *)v62;
        v56 = (char *)&v62[v57 + 1];
        v167 = (char *)&v62[v61 / 8];
      }
      else
      {
        *(_QWORD *)v42 = Event;
        v56 = v42 + 8;
      }
      v166 = v56;
      v66 = g_componentRuntimeInfoList;
      v67 = *(_QWORD **)g_componentRuntimeInfoList;
      while ( v67 != v66 )
      {
        v38 = (char *)pv;
        if ( v46 == pv )
        {
          v69 = (v46 - v45) >> 3;
          if ( v69 == 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_293;
          v70 = ((_BYTE *)pv - v45) >> 3;
          if ( v70 > 0x1FFFFFFFFFFFFFFFLL - (v70 >> 1) )
            goto LABEL_298;
          v71 = v69 + 1;
          hKey = (HKEY)(v69 + 1);
          v72 = (v70 >> 1) + v70;
          v73 = v69 + 1;
          if ( v72 >= v69 + 1 )
            v73 = v72;
          if ( v73 > 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_298;
          v74 = 8 * v73;
          v169[0] = 8 * v73;
          if ( 8 * v73 )
          {
            if ( v74 < 0x1000 )
            {
              v75 = (char *)operator new(8 * v73);
            }
            else
            {
              if ( v74 + 39 < v74 )
                goto LABEL_298;
              v76 = operator new(v74 + 39);
              if ( !v76 )
                goto LABEL_252;
              v75 = (char *)(((unsigned __int64)v76 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v75 - 1) = v76;
            }
          }
          else
          {
            v75 = 0;
          }
          hstring_on_heap = (struct winrt::impl::hstring_header *)v67[3];
          if ( hstring_on_heap )
          {
            if ( (*(_BYTE *)hstring_on_heap & 1) != 0 )
              hstring_on_heap = winrt::impl::create_hstring_on_heap(
                                  *((winrt::impl **)hstring_on_heap + 2),
                                  (winrt::impl *)*((unsigned int *)hstring_on_heap + 1),
                                  v71);
            else
              _InterlockedIncrement((volatile signed __int32 *)hstring_on_heap + 6);
          }
          *(_QWORD *)&v75[8 * v69] = hstring_on_heap;
          std::_Uninitialized_move<winrt::hstring *>(v45, v46, v75);
          if ( v45 )
          {
            if ( v45 != v46 )
            {
              v78 = v45;
              do
              {
                std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(v78);
                v78 += 8;
              }
              while ( v78 != v46 );
            }
            v79 = 8 * (((_BYTE *)pv - v45) >> 3);
            if ( v79 < 0x1000 )
            {
              v80 = v45;
            }
            else
            {
              v80 = (char *)*((_QWORD *)v45 - 1);
              if ( (unsigned __int64)(v45 - v80 - 8) > 0x1F )
                goto LABEL_252;
              v79 += 39LL;
            }
            operator delete(v80, v79);
          }
          v45 = v75;
          *(_QWORD *)fPending = &v75[8 * (_QWORD)hKey];
          pv = &v75[v169[0]];
        }
        else
        {
          v68 = v67[3];
          if ( v68 )
          {
            if ( (*(_BYTE *)v68 & 1) != 0 )
            {
              *(_QWORD *)v46 = winrt::impl::create_hstring_on_heap(
                                 *(winrt::impl **)(v68 + 16),
                                 (winrt::impl *)*(unsigned int *)(v68 + 4),
                                 v35);
            }
            else
            {
              _InterlockedIncrement((volatile signed __int32 *)(v68 + 24));
              *(_QWORD *)v46 = v68;
            }
            *(_QWORD *)fPending = v46 + 8;
          }
          else
          {
            *(_QWORD *)v46 = 0;
            *(_QWORD *)fPending = v46 + 8;
          }
        }
        v81 = (HKEY)v67[2];
        hKey = v81;
        v37 = (__int64)v167;
        v82 = v166;
        if ( v166 == v167 )
        {
          v83 = (v166 - v41) >> 3;
          if ( v83 == 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_299;
          v84 = (v167 - v41) >> 3;
          v85 = v84 >> 1;
          if ( v84 > 0x1FFFFFFFFFFFFFFFLL - (v84 >> 1) )
            goto LABEL_298;
          v86 = v83 + 1;
          if ( v85 + v84 >= v83 + 1 )
            v86 = v85 + v84;
          if ( v86 > 0x1FFFFFFFFFFFFFFFLL )
            goto LABEL_298;
          v87 = 8 * v86;
          if ( v87 )
          {
            if ( v87 < 0x1000 )
            {
              v88 = operator new(v87);
            }
            else
            {
              if ( v87 + 39 < v87 )
                goto LABEL_298;
              v89 = operator new(v87 + 39);
              if ( !v89 )
                goto LABEL_252;
              v88 = (_QWORD *)(((unsigned __int64)v89 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *(v88 - 1) = v89;
            }
            v82 = v166;
          }
          else
          {
            v88 = 0;
          }
          v88[v83] = hKey;
          memmove_0(v88, v41, v82 - v41);
          if ( v41 )
          {
            v90 = 8 * ((v167 - v41) >> 3);
            if ( v90 < 0x1000 )
            {
              v91 = v41;
            }
            else
            {
              v91 = (char *)*((_QWORD *)v41 - 1);
              if ( (unsigned __int64)(v41 - v91 - 8) > 0x1F )
                goto LABEL_252;
              v90 += 39LL;
            }
            operator delete(v91, v90);
          }
          v41 = (char *)v88;
          v166 = (char *)&v88[v83 + 1];
          v167 = (char *)&v88[v87 / 8];
          v67 = (_QWORD *)*v67;
          v46 = *(char **)fPending;
        }
        else
        {
          *(_QWORD *)v166 = v81;
          v166 = v82 + 8;
          v67 = (_QWORD *)*v67;
          v46 = *(char **)fPending;
        }
      }
      fPending[0] = 0;
      if ( !InitOnceBeginInitialize(&DebugData::s_instanceInitOnce, 0, fPending, 0) )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, v92, v93, v94);
      if ( fPending[0] )
      {
        v95 = (char *)operator new(0x30u);
        *(_DWORD *)(v95 + 41) = 0;
        *(_WORD *)(v95 + 45) = 0;
        v95[47] = 0;
        *(_QWORD *)v95 = 0;
        *((_QWORD *)v95 + 1) = 0;
        *((_QWORD *)v95 + 2) = 0;
        *((_QWORD *)v95 + 3) = 0;
        *((_QWORD *)v95 + 4) = 0;
        v95[40] = 0;
        DebugData::s_instance = (PSRWLOCK)v95;
        InitOnceComplete(&DebugData::s_instanceInitOnce, 0, 0);
      }
      v96 = DebugData::s_instance;
      v97 = g_shellHostConfigurationFlags & 1;
      AcquireSRWLockExclusive(DebugData::s_instance);
      LOBYTE(v96[5].Ptr) = v97;
      v98 = v96 + 1;
      if ( &v96[1] == (RTL_SRWLOCK *)&v173 )
      {
        v104 = pv;
      }
      else
      {
        Ptr = (char *)v98->Ptr;
        if ( v98->Ptr )
        {
          for ( i = (char *)v96[2].Ptr; Ptr != i; Ptr += 8 )
            std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(Ptr);
          v101 = (char *)v98->Ptr;
          v102 = 8 * (((char *)v96[3].Ptr - (char *)v96[1].Ptr) >> 3);
          if ( v102 < 0x1000 )
          {
            v103 = v98->Ptr;
          }
          else
          {
            v103 = (_BYTE *)*((_QWORD *)v101 - 1);
            if ( (unsigned __int64)(v101 - v103 - 8) > 0x1F )
              goto LABEL_252;
            v102 += 39LL;
          }
          operator delete(v103, v102);
        }
        v98->Ptr = v45;
        v96[2].Ptr = v46;
        v96[3].Ptr = pv;
        v104 = 0;
        v46 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v45 = 0;
      }
      v105 = operator new(0x40u);
      v105[7] = v96;
      *v105 = DebugData::PublishShellHostProperties__ResumeCoro_1;
      *((_DWORD *)v105 + 2) = 65538;
      *((_BYTE *)v105 + 48) = 0;
      DebugData::PublishShellHostProperties__ResumeCoro_1(v105);
      ReleaseSRWLockExclusive(v96);
      dwindex = 0;
      v106 = (v166 - v41) >> 3;
      v107 = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, v106, (LPHANDLE)v41, &dwindex);
      if ( v107 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x343, v35, (const char *)(unsigned int)v107, pdwTypea);
      if ( dwindex >= v106 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x345,
          (unsigned int)"pcshell\\shell\\shellhost\\exe\\main.cpp",
          v36);
      if ( dwindex )
      {
        for ( j = *(_QWORD **)g_componentRuntimeInfoList; j != g_componentRuntimeInfoList; j = (_QWORD *)*j )
        {
          if ( j[2] == *(_QWORD *)&v41[8 * dwindex] )
          {
            v109 = 0;
            goto LABEL_200;
          }
        }
        v109 = 1;
LABEL_200:
        if ( v109 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x353,
            (unsigned int)"pcshell\\shell\\shellhost\\exe\\main.cpp",
            v36);
        *(_QWORD *)j[1] = *j;
        *(_QWORD *)(*j + 8LL) = j[1];
        --qword_1400841A8;
        std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(j + 3);
        v110 = (char *)j[2];
        if ( (unsigned __int64)(v110 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v110);
        std::_Deallocate<16>(j, 32);
      }
      if ( v45 )
      {
        for ( k = v45; k != v46; k += 8 )
          std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(k);
        std::_Deallocate<16>(v45, (v104 - v45) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      v37 = 0x1FFFFFFFFFFFFFFFLL;
      if ( v41 )
      {
        std::_Deallocate<16>(v41, (v167 - v41) & 0xFFFFFFFFFFFFFFF8uLL);
        goto LABEL_69;
      }
    }
  }
  else
  {
    if ( (_QWORD)g_componentWaitHandles != *((_QWORD *)&g_componentWaitHandles + 1) )
      SetProcessShutdownParameters(2u, 0);
    while ( 1 )
    {
      v112 = g_componentWaitHandles;
      if ( (_QWORD)g_componentWaitHandles == *((_QWORD *)&g_componentWaitHandles + 1) )
        break;
      dwindex = 0;
      v113 = (__int64)(*((_QWORD *)&g_componentWaitHandles + 1) - g_componentWaitHandles) >> 3;
      if ( v113 )
      {
        if ( v113 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_301:
          std::vector<void *>::_Xlength(v112, v34, 0x1FFFFFFFFFFFFFFFLL);
        v114 = 8 * v113;
        if ( 8 * v113 )
        {
          if ( v114 < 0x1000 )
          {
            v115 = (HKEY *)operator new(8 * v113);
            v116 = &v115[v114 / 8];
          }
          else
          {
            if ( v114 + 39 < v114 )
LABEL_300:
              std::_Throw_bad_array_new_length();
            v117 = (HKEY)operator new(v114 + 39);
            if ( !v117 )
LABEL_252:
              __fastfail(5u);
            v115 = (HKEY *)(((unsigned __int64)v117 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v115 - 1) = v117;
            v116 = &v115[v114 / 8];
          }
        }
        else
        {
          v115 = 0;
          v116 = 0;
        }
      }
      else
      {
        v116 = 0;
        v115 = 0;
      }
      v119 = g_componentWaitHandles;
      v169[0] = v119 >> 64;
      v118 = (HKEY *)v119;
      v120 = v115;
      if ( (_QWORD)g_componentWaitHandles != *((_QWORD *)&g_componentWaitHandles + 1) )
      {
        do
        {
          v121 = *v118;
          hKey = *v118;
          if ( v115 == v116 )
          {
            v122 = (char *)v115 - (char *)v120;
            v123 = v122 >> 3;
            if ( v122 >> 3 == 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_301;
            v124 = v116 - v120;
            v125 = v124 >> 1;
            if ( v124 > 0x1FFFFFFFFFFFFFFFLL - (v124 >> 1) )
              goto LABEL_300;
            v126 = v123 + 1;
            if ( v125 + v124 >= v123 + 1 )
              v126 = v125 + v124;
            if ( v126 > 0x1FFFFFFFFFFFFFFFLL )
              goto LABEL_300;
            v127 = 8 * v126;
            if ( v127 )
            {
              if ( v127 < 0x1000 )
              {
                v128 = operator new(v127);
              }
              else
              {
                if ( v127 + 39 < v127 )
                  goto LABEL_300;
                v129 = operator new(v127 + 39);
                if ( !v129 )
                  goto LABEL_252;
                v128 = (_QWORD *)(((unsigned __int64)v129 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                *(v128 - 1) = v129;
              }
            }
            else
            {
              v128 = 0;
            }
            v128[v123] = hKey;
            memmove_0(v128, v120, v122);
            if ( v120 )
              std::_Deallocate<16>(v120, 8 * v124);
            v120 = (HKEY *)v128;
            v115 = (HKEY *)&v128[v123 + 1];
            v116 = (HKEY *)&v128[v127 / 8];
          }
          else
          {
            *v115++ = v121;
          }
          ++v118;
        }
        while ( v118 != (HKEY *)v169[0] );
      }
      v130 = v115 - v120;
      v131 = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, v130, (LPHANDLE)v120, &dwindex);
      if ( v131 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x36E, v132, (const char *)(unsigned int)v131, pdwTypeb);
      if ( dwindex >= v130 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x370,
          (unsigned int)"pcshell\\shell\\shellhost\\exe\\main.cpp",
          v36);
      v133 = (_QWORD *)(g_componentWaitHandles + 8LL * dwindex);
      v134 = (_QWORD *)*((_QWORD *)&g_componentWaitHandles + 1);
      for ( m = v133 + 1; m != v134; ++m )
      {
        if ( v133 != m )
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            v133,
            *m);
          *m = 0;
        }
        ++v133;
      }
      v136 = *(char **)(*((_QWORD *)&g_componentWaitHandles + 1) - 8LL);
      if ( (unsigned __int64)(v136 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v136);
      *((_QWORD *)&g_componentWaitHandles + 1) -= 8LL;
      if ( v120 )
        std::_Deallocate<16>(v120, ((char *)v116 - (char *)v120) & 0xFFFFFFFFFFFFFFF8uLL);
    }
  }
  v137 = (char *)g_singletonHelper;
  if ( g_singletonHelper )
  {
    if ( !*((_QWORD *)g_singletonHelper + 14) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1F6,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
        v36);
    if ( *((_DWORD *)v137 + 30) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
        v138);
    v139 = v137 + 40;
    if ( *((_QWORD *)v137 + 8) > 7u )
      v139 = (_QWORD *)*v139;
    *(_QWORD *)&v172[0] = v139;
    v140 = -1;
    v141 = -1;
    do
      ++v141;
    while ( *((_WORD *)v139 + v141) );
    *((_QWORD *)&v172[0] + 1) = v141;
    v142 = v137 + 8;
    if ( *((_QWORD *)v137 + 4) > 7u )
      v142 = (_QWORD *)*v142;
    *(_QWORD *)&v170 = v142;
    do
      ++v140;
    while ( *((_WORD *)v142 + v140) );
    *((_QWORD *)&v170 + 1) = v140;
    if ( !*((_QWORD *)v137 + 14) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
        v138);
    SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, &v170, v172, 131078);
    v143 = hKey;
    RegDeleteKeyValueW(hKey, 0, L"ProcessId");
    RegDeleteKeyValueW(v143, 0, L"CommunicationHWND");
    if ( v143 )
      RegCloseKey(v143);
    FlowEndpointBase::Uninitialize((FlowEndpointBase *)(v137 + 128));
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v137 + 112,
      0);
    v144 = (char *)g_singletonHelper;
    g_singletonHelper = 0;
    if ( v144 )
    {
      *(_QWORD *)v144 = &SingletonHelpers::SingletonHelper::`vftable';
      if ( *((_QWORD *)v144 + 14) )
      {
        if ( *((_DWORD *)v144 + 30) != GetCurrentThreadId() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x136,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
            v145);
        v146 = v144 + 40;
        v147 = *((_QWORD *)v144 + 7);
        if ( *((_QWORD *)v144 + 8) > 7u )
          v146 = (_QWORD *)*v146;
        *(_QWORD *)&v172[0] = v146;
        *((_QWORD *)&v172[0] + 1) = v147;
        v148 = v144 + 8;
        v149 = *((_QWORD *)v144 + 3);
        if ( *((_QWORD *)v144 + 4) > 7u )
          v148 = (_QWORD *)*v148;
        *(_QWORD *)&v170 = v148;
        *((_QWORD *)&v170 + 1) = v149;
        if ( !*((_QWORD *)v144 + 14) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xD1,
            (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
            v145);
        SingletonHelpers::details::GetSingletonSessionSubKey(&hKey, &v170, v172, 131078);
        v150 = hKey;
        RegDeleteKeyValueW(hKey, 0, L"ProcessId");
        RegDeleteKeyValueW(v150, 0, L"CommunicationHWND");
        if ( v150 )
          RegCloseKey(v150);
      }
      std::_Func_class<void,>::~_Func_class<void,>(v144 + 264);
      FlowEndpointBase::~FlowEndpointBase((FlowEndpointBase *)(v144 + 128));
      v151 = (void *)*((_QWORD *)v144 + 14);
      if ( v151 && !ReleaseMutex(v151) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v152, v153);
      v154 = (void *)*((_QWORD *)v144 + 13);
      if ( v154 && !CloseHandle(v154) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v155, v156);
      std::wstring::~wstring(v144 + 72);
      std::wstring::~wstring(v144 + 40);
      std::wstring::~wstring(v144 + 8);
      operator delete(v144, 0x148u);
    }
  }
  CoUninitialize();
  ProcAddress = (FARPROC)`TestControlReporting'::`2'::s_pfnTestControlReporting;
  if ( `TestControlReporting'::`2'::s_pfnTestControlReporting )
    goto LABEL_286;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestControlReporting");
  `TestControlReporting'::`2'::s_pfnTestControlReporting = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_286:
    LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x140006ab0  push    rbp
0x140006ab2  push    rbx
0x140006ab3  push    rsi
0x140006ab4  push    rdi
0x140006ab5  push    r12
0x140006ab7  push    r13
0x140006ab9  push    r14
0x140006abb  push    r15
0x140006abd  lea     rbp, [rsp-1D8h]
0x140006ac5  sub     rsp, 2D8h
0x140006acc  mov     rax, cs:__security_cookie
0x140006ad3  xor     rax, rsp
0x140006ad6  mov     [rbp+210h+var_50], rax
0x140006add  mov     r12, r8
0x140006ae0  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140006ae7  lea     r14, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140006aee  lea     rax, ??_7?$__func@V_lambda_21f43f16d02b49269b53009b18da9143_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140006af5  xor     edi, edi
0x140006af7  mov     [rsp+310h+var_2B0], rdi
0x140006afc  mov     [rsp+310h+var_2B8], rdi
0x140006b01  mov     [rbp+210h+var_220], rax
0x140006b05  lea     rax, [rsp+310h+var_2B8]
0x140006b0a  mov     [rbp+210h+var_218], rax
0x140006b0e  lea     rax, [rsp+310h+var_2B0]
0x140006b13  mov     [rbp+210h+var_210], rax
0x140006b17  lea     rax, [rbp+210h+var_220]
0x140006b1b  mov     [rbp+210h+var_1B8], rax
0x140006b1f  xor     edx, edx; Val
0x140006b21  mov     r8d, 100h; Size
0x140006b27  lea     rcx, [rbp+210h+Source]; void *
0x140006b2e  call    memset_0
0x140006b33  mov     [rsp+310h+pv], rdi
0x140006b38  lea     rax, [rsp+310h+pv]
0x140006b3d  mov     [rbp+210h+var_280], rax
0x140006b41  mov     [rsp+310h+var_2A0], 80h
0x140006b4a  lea     rax, [rbp+210h+Source]
0x140006b51  mov     [rsp+310h+hKey], rax
0x140006b56  lea     r9, [rbp+210h+var_280]
0x140006b5a  lea     r8, [rsp+310h+var_2A0]
0x140006b5f  lea     rdx, [rsp+310h+hKey]
0x140006b64  lea     rcx, [rbp+210h+var_220]
0x140006b68  call    ??R?$__func@V_lambda_21f43f16d02b49269b53009b18da9143_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z; wistd::__function::__func<_lambda_21f43f16d02b49269b53009b18da9143_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)
0x140006b6d  mov     ebx, eax
0x140006b6f  test    eax, eax
0x140006b71  js      loc_140006D16
0x140006b77  mov     rax, [rsp+310h+pv]
0x140006b7c  cmp     rax, 80h
0x140006b82  ja      loc_140006C24
0x140006b88  lea     rcx, [rax-1]
0x140006b8c  lea     rsi, [rbp+210h+Source]
0x140006b93  cmp     rcx, 7FFFFFFFh
0x140006b9a  jnb     short loc_140006BA6
0x140006b9c  mov     rax, rcx
0x140006b9f  test    rcx, rcx
0x140006ba2  jz      short loc_140006BC0
0x140006ba4  jmp     short loc_140006BB0
0x140006ba6  mov     eax, 7FFFFFFFh
0x140006bab  nop     dword ptr [rax+rax+00h]
0x140006bb0  cmp     word ptr [rsi], 0
0x140006bb4  jz      short loc_140006BC0
0x140006bb6  add     rsi, 2
0x140006bba  sub     rax, 1
0x140006bbe  jnz     short loc_140006BB0
0x140006bc0  lea     rax, [rbp+210h+Source]
0x140006bc7  sub     rsi, rax
0x140006bca  sar     rsi, 1
0x140006bcd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140006bd1  cmovz   rcx, rsi
0x140006bd5  lea     r14, [rcx+rcx]
0x140006bd9  lea     rcx, [r14+2]; cb
0x140006bdd  call    cs:__imp_CoTaskMemAlloc
0x140006be3  mov     rbx, rax
0x140006be6  test    rax, rax
0x140006be9  jz      short loc_140006C1A
0x140006beb  lea     rdi, [rsi+rsi]
0x140006bef  mov     r9, rdi; SourceSize
0x140006bf2  lea     r8, [rbp+210h+Source]; Source
0x140006bf9  lea     rdx, [r14+2]; DestinationSize
0x140006bfd  mov     rcx, rax; Destination
0x140006c00  call    memcpy_s
0x140006c05  xor     eax, eax
0x140006c07  mov     [rbx+rdi], ax
0x140006c0b  mov     [rbx+r14], ax
0x140006c10  mov     rdi, rbx
0x140006c13  xor     ebx, ebx
0x140006c15  jmp     loc_140006D0F
0x140006c1a  mov     edx, 16Fh
0x140006c1f  jmp     loc_140006CF1
0x140006c24  xor     ebx, ebx
0x140006c26  nop     word ptr [rax+rax+00000000h]
0x140006c30  mov     r15, rax
0x140006c33  dec     rax
0x140006c36  mov     rcx, [rbp+218h]; this
0x140006c3d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006c41  jz      loc_140007EBC
0x140006c47  lea     rsi, [rax+rax]
0x140006c4b  lea     rcx, [rsi+2]; cb
0x140006c4f  call    cs:__imp_CoTaskMemAlloc
0x140006c55  mov     r14, rax
0x140006c58  test    rax, rax
0x140006c5b  jz      short loc_140006C66
0x140006c5d  xor     ecx, ecx
0x140006c5f  mov     [rax], cx
0x140006c62  mov     [rax+rsi], cx
0x140006c66  test    rbx, rbx
0x140006c69  jz      short loc_140006C84
0x140006c6b  call    cs:__imp_GetLastError
0x140006c71  mov     esi, eax
0x140006c73  mov     rcx, rbx; pv
0x140006c76  call    cs:__imp_CoTaskMemFree
0x140006c7c  mov     ecx, esi; dwErrCode
0x140006c7e  call    cs:__imp_SetLastError
0x140006c84  test    r14, r14
0x140006c87  jz      short loc_140006CEC
0x140006c89  lea     rax, [rsp+310h+pv]
0x140006c8e  mov     [rsp+310h+hKey], rax
0x140006c93  mov     [rsp+310h+var_2A0], r15
0x140006c98  mov     [rbp+210h+var_280], r14
0x140006c9c  mov     rcx, [rbp+210h+var_1B8]; this
0x140006ca0  test    rcx, rcx
0x140006ca3  jz      loc_140007ECE
0x140006ca9  mov     rax, [rcx]
0x140006cac  lea     r9, [rsp+310h+hKey]
0x140006cb1  lea     r8, [rsp+310h+var_2A0]
0x140006cb6  lea     rdx, [rbp+210h+var_280]
0x140006cba  mov     rax, [rax+20h]
0x140006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cc3  mov     ebx, eax
0x140006cc5  test    eax, eax
0x140006cc7  js      short loc_140006CE1
0x140006cc9  mov     rbx, r14
0x140006ccc  mov     rax, [rsp+310h+pv]
0x140006cd1  cmp     rax, r15
0x140006cd4  ja      loc_140006C30
0x140006cda  mov     rdi, rbx
0x140006cdd  xor     ebx, ebx
0x140006cdf  jmp     short loc_140006D0F
0x140006ce1  mov     rcx, r14; pv
0x140006ce4  call    cs:__imp_CoTaskMemFree
0x140006cea  jmp     short loc_140006D0F
0x140006cec  mov     edx, 17Ah; void *
0x140006cf1  mov     r9d, 8007000Eh; char *
0x140006cf7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006cfe  mov     rcx, [rbp+218h]; this
0x140006d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006d0a  mov     ebx, 8007000Eh
0x140006d0f  lea     r14, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140006d16  xor     esi, esi
0x140006d18  mov     rcx, [rbp+210h+var_1B8]
0x140006d1c  test    rcx, rcx
0x140006d1f  jz      short loc_140006D2D
0x140006d21  mov     rax, [rcx]
0x140006d24  mov     rax, [rax+18h]
0x140006d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d2d  test    ebx, ebx
0x140006d2f  jns     short loc_140006D63
0x140006d31  mov     rcx, [rbp+218h]; this
0x140006d38  mov     r9d, ebx; char *
0x140006d3b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006d42  mov     edx, 2A7h; void *
0x140006d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006d4c  test    rdi, rdi
0x140006d4f  jz      loc_140006E97
0x140006d55  mov     rcx, rdi; pv
0x140006d58  call    cs:__imp_CoTaskMemFree
0x140006d5e  jmp     loc_140006E97
0x140006d63  mov     edx, 5Ch ; '\'; Ch
0x140006d68  mov     rcx, rdi; Str
0x140006d6b  call    cs:__imp_wcsrchr
0x140006d71  test    rax, rax
0x140006d74  jz      loc_140006E87
0x140006d7a  lea     rcx, [rax+2]
0x140006d7e  mov     [rsp+310h+pv], rsi
0x140006d83  test    rcx, rcx
0x140006d86  jz      short loc_140006D9B
0x140006d88  mov     rax, r13
0x140006d8b  nop     dword ptr [rax+rax+00h]
0x140006d90  inc     rax
0x140006d93  cmp     [rcx+rax*2], si
0x140006d97  jnz     short loc_140006D90
0x140006d99  jmp     short loc_140006D9D
0x140006d9b  xor     eax, eax
0x140006d9d  mov     qword ptr [rbp+210h+var_270], rcx
0x140006da1  mov     qword ptr [rbp+210h+var_270+8], rax
0x140006da5  mov     qword ptr [rbp+210h+var_290], r14
0x140006da9  mov     qword ptr [rbp+210h+var_290+8], 4Ah ; 'J'
0x140006db1  mov     qword ptr [rbp+210h+var_250], rsi
0x140006db5  mov     qword ptr [rbp+210h+var_250+8], rsi
0x140006db9  movaps  xmm0, [rbp+210h+var_250]
0x140006dbd  movups  [rbp+210h+var_180], xmm0
0x140006dc4  movaps  xmm1, [rbp+210h+var_290]
0x140006dc8  movups  [rbp+210h+var_170], xmm1
0x140006dcf  movaps  xmm0, [rbp+210h+var_270]
0x140006dd3  movups  [rbp+210h+var_160], xmm0
0x140006dda  mov     r8d, 3
0x140006de0  lea     rdx, [rbp+210h+var_180]
0x140006de7  lea     rcx, [rsp+310h+pv]
0x140006dec  call    ??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z; wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)
0x140006df1  mov     ebx, eax
0x140006df3  test    eax, eax
0x140006df5  jns     short loc_140006E2B
0x140006df7  mov     rcx, [rbp+218h]; this
0x140006dfe  mov     r9d, eax; char *
0x140006e01  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140006e08  mov     edx, 2ADh; void *
0x140006e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006e12  mov     rcx, [rsp+310h+pv]; pv
0x140006e17  test    rcx, rcx
0x140006e1a  jz      loc_140006D4C
0x140006e20  call    cs:__imp_CoTaskMemFree
0x140006e26  jmp     loc_140006D4C
0x140006e2b  mov     [rsp+310h+fPending], esi
0x140006e2f  mov     [rsp+310h+dwindex], 4
0x140006e37  lea     rax, [rsp+310h+dwindex]
0x140006e3c  mov     [rsp+310h+pcbData], rax; pcbData
0x140006e41  lea     rax, [rsp+310h+fPending]
0x140006e46  mov     [rsp+310h+pvData], rax; pvData
0x140006e4b  mov     [rsp+310h+pdwType], rsi; int
0x140006e50  mov     r9d, 10010h; dwFlags
0x140006e56  lea     r8, Value; "WaitForDebuggerPresent"
0x140006e5d  mov     rbx, [rsp+310h+pv]
0x140006e62  mov     rdx, rbx; lpSubKey
0x140006e65  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140006e6c  call    cs:__imp_RegGetValueW
0x140006e72  test    eax, eax
0x140006e74  cmovz   esi, [rsp+310h+fPending]
0x140006e79  test    rbx, rbx
0x140006e7c  jz      short loc_140006E87
0x140006e7e  mov     rcx, rbx; pv
0x140006e81  call    cs:__imp_CoTaskMemFree
0x140006e87  test    rdi, rdi
0x140006e8a  jz      short loc_140006E95
0x140006e8c  mov     rcx, rdi; pv
0x140006e8f  call    cs:__imp_CoTaskMemFree
0x140006e95  xor     ebx, ebx
0x140006e97  mov     rcx, [rbp+218h]; this
0x140006e9e  test    ebx, ebx
0x140006ea0  js      loc_140007EA7
0x140006ea6  test    esi, esi
0x140006ea8  jz      short loc_140006EED
0x140006eaa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x140006eb1  jnz     short loc_140006EE2
0x140006eb3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006eba  test    rax, rax
0x140006ebd  jz      short loc_140006EC8
0x140006ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ec4  test    al, al
0x140006ec6  jmp     short loc_140006ED0
0x140006ec8  call    cs:__imp_IsDebuggerPresent
0x140006ece  test    eax, eax
0x140006ed0  jnz     short loc_140006EE2
0x140006ed2  mov     ecx, 1F4h; dwMilliseconds
0x140006ed7  call    cs:__imp_Sleep
0x140006edd  jmp     loc_140006AEE
0x140006ee2  cmp     esi, 2
0x140006ee5  jnz     short loc_140006EED
0x140006ee7  call    cs:__imp_DebugBreak
0x140006eed  call    cs:__imp_GetCurrentThread
0x140006ef3  mov     rcx, rax; hThread
0x140006ef6  lea     rdx, ThreadDescription; "ShellHost main thread"
0x140006efd  call    cs:__imp_SetThreadDescription
0x140006f03  mov     edx, 2; dwCoInit
0x140006f08  xor     ecx, ecx; pvReserved
0x140006f0a  call    cs:__imp_CoInitializeEx
0x140006f10  mov     [rbp+210h+var_1B0], 1
0x140006f17  mov     [rbp+210h+var_1A8], 2
0x140006f1f  mov     [rbp+210h+var_1A0], 4
0x140006f26  mov     [rbp+210h+var_198], 218h
0x140006f2e  mov     [rbp+210h+var_190], 5
0x140006f38  mov     [rbp+210h+var_188], 1
0x140006f43  mov     [rsp+310h+pv], 0
0x140006f4c  lea     rax, [rsp+310h+pv]
0x140006f51  mov     [rsp+310h+pdwType], rax; ppv
0x140006f56  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140006f5d  xor     edx, edx; pUnkOuter
0x140006f5f  mov     r8d, 1; dwClsContext
0x140006f65  lea     rcx, CLSID_GlobalOptions; rclsid
0x140006f6c  call    cs:__imp_CoCreateInstance
0x140006f72  test    eax, eax
0x140006f74  js      short loc_140006FA7
0x140006f76  lea     rbx, [rbp+210h+var_1B0]
0x140006f7a  nop     word ptr [rax+rax+00h]
0x140006f80  mov     rcx, [rsp+310h+pv]
0x140006f85  mov     rax, [rcx]
0x140006f88  mov     r8, [rbx+8]
0x140006f8c  mov     edx, [rbx]
0x140006f8e  mov     rax, [rax+18h]
0x140006f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f97  add     rbx, 10h
0x140006f9b  lea     rax, [rbp+210h+var_180]
0x140006fa2  cmp     rbx, rax
0x140006fa5  jnz     short loc_140006F80
0x140006fa7  mov     rcx, [rsp+310h+pv]
0x140006fac  test    rcx, rcx
0x140006faf  jz      short loc_140006FC7
0x140006fb1  mov     [rsp+310h+pv], 0
0x140006fba  mov     rax, [rcx]
0x140006fbd  mov     rax, [rax+10h]
0x140006fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fc6  nop
  ... truncated ...
```
