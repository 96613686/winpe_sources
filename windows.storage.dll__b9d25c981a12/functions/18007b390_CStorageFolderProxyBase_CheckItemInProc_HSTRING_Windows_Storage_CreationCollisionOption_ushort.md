# CStorageFolderProxyBase::_CheckItemInProc(HSTRING__ *,Windows::Storage::CreationCollisionOption,ushort * *)

- ea: `0x18007b390`
- end: `0x18007b9bb`
- name: `?_CheckItemInProc@CStorageFolderProxyBase@@IEAAJPEAUHSTRING__@@W4CreationCollisionOption@Storage@Windows@@PEAPEAG@Z`
- size: `1579`
- prototype: `int __high(HSTRING, enum Windows::Storage::CreationCollisionOption, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024944`
- `0x180025794`
- `0x180025ba4`

## callees

- `0x180009fc0`
- `0x180038f50`
- `0x18003d600`
- `0x18007b390`
- `0x18007b9d0`
- `0x18007bbf0`
- `0x18007c300`
- `0x18007c510`
- `0x18007dcf0`
- `0x18013c3bc`
- `0x18013c5e4`
- `0x1803b1f60`
- `0x1803b66ac`
- `0x1803b6714`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007b4d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007b4d3`
- `ntdll!EtwEventActivityIdControl` at `0x18007b3e0`
- `ntdll!EtwEventActivityIdControl` at `0x18007b3e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18007b6b4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18007b6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b85c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b8bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b85c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b8bf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007b63c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007b63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18007b6dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x18007b6dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b4ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b4ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b6a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b96e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b96e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007b7a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007b7a7`

## string_xrefs

- `0x18007b809`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007b840`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007b88e`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007b8f1`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007b917`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18007b954`: `onecoreuap\shell\windows.storage\dataaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStorageFolderProxyBase::_CheckItemInProc(__int64 a1, HSTRING a2, int a3, const WCHAR **a4)
{
  __int64 v8; // rcx
  GUID v9; // xmm6
  __int64 v10; // rax
  __int64 v11; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  unsigned int v16; // ebx
  unsigned __int64 v17; // rdi
  WCHAR *v18; // r14
  HRESULT v19; // esi
  __int64 v20; // rbx
  int v21; // eax
  unsigned int v22; // ebx
  HSTRING v23; // rbx
  const WCHAR *StringRawBuffer; // rax
  BOOL IsRootW; // eax
  PCWSTR v26; // rax
  __int64 v27; // r8
  int v28; // eax
  const WCHAR *v29; // rsi
  HRESULT v30; // eax
  const unsigned __int16 *v31; // rdx
  Windows::Internal::StringReference *v32; // rcx
  WCHAR *v33; // rcx
  HSTRING v34; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR sourceString[3]; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING newString[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v38; // [rsp+60h] [rbp-A0h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  void **v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h]
  char v44; // [rsp+B0h] [rbp-50h]
  _QWORD v45[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v46; // [rsp+D0h] [rbp-30h]
  int *v47; // [rsp+D8h] [rbp-28h]
  char v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  __int64 v50; // [rsp+F0h] [rbp-10h]
  GUID v51; // [rsp+F8h] [rbp-8h]
  __int64 v52; // [rsp+108h] [rbp+8h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  const char *v54; // [rsp+118h] [rbp+18h]
  const char *v55; // [rsp+120h] [rbp+20h]
  const char *v56; // [rsp+128h] [rbp+28h]
  const char *v57; // [rsp+130h] [rbp+30h]
  char v58; // [rsp+138h] [rbp+38h]
  const char *v59; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_OWORD *)newString = 0;
  if ( (unsigned int)EtwEventActivityIdControl(1, newString) )
  {
    v9 = GUID_NULL;
    *(GUID *)newString = GUID_NULL;
  }
  else
  {
    v9 = *(GUID *)newString;
  }
  v10 = wil::details::static_lazy<WinRTStorageTelemetry>::get(
          v8,
          _lambda_6185f7d59584f69b5a44cbef7cf75836_::_lambda_invoker_cdecl_);
  v11 = v10 + 40;
  if ( !v10 )
    v11 = 0;
  v40 = &StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::`vftable';
  v44 = 0;
  v41 = 0;
  v42 = "_CheckItemInProc";
  v43 = 0;
  v45[0] = 0;
  v45[1] = &v40;
  v45[2] = 0;
  v46 = 0;
  v47 = &v41;
  v48 = 0;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v45);
  v49 = 0;
  v50 = v11;
  v51 = v9;
  v52 = 0;
  v53 = 0;
  v54 = word_180713EEA;
  v55 = word_180713EEA;
  v56 = word_180713EEA;
  v57 = word_180713EEA;
  v59 = "_CheckItemInProc";
  v58 = 0;
  *a4 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 56LL))(a1 + 48) || !a3 )
  {
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v40);
    return 2147500033LL;
  }
  v36[0] = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)(a1 + 192) + 24LL))(
          a1 + 192,
          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
          v36);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v15,
      (int)v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
    StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v40);
    return v16;
  }
  v17 = -1;
  sourceString[1] = (PCWSTR)-1LL;
  sourceString[2] = (PCWSTR)-1LL;
  v18 = 0;
  sourceString[0] = 0;
  LOWORD(hstringHeader.Reserved.Reserved1) = 0;
  *(_OWORD *)newString = PKEY_FileAPI_Path;
  v38 = 3;
  v19 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *, HSTRING_HEADER *))(*(_QWORD *)v36[0] + 40LL))(
          v36[0],
          newString,
          &hstringHeader);
  if ( v19 >= 0 && !LOWORD(hstringHeader.Reserved.Reserved1) )
  {
    v19 = -2147023728;
    goto LABEL_19;
  }
  v20 = 0;
  if ( v19 < 0 )
    goto LABEL_20;
  v18 = 0;
  sourceString[0] = 0;
  if ( LOWORD(hstringHeader.Reserved.Reserved1) != 31 || (v20 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]) == 0 )
  {
    v19 = -2147352571;
LABEL_19:
    v20 = 0;
    goto LABEL_20;
  }
  v18 = *(WCHAR **)&hstringHeader.Reserved.Reserved2[8];
  sourceString[0] = *(PCWSTR *)&hstringHeader.Reserved.Reserved2[8];
  memset(&hstringHeader, 0, sizeof(hstringHeader));
LABEL_20:
  PropVariantClear(&hstringHeader.Reserved.Reserved1);
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v19,
      (int)v34);
    if ( !v20 )
      goto LABEL_48;
    v33 = v18;
    goto LABEL_47;
  }
  v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
          sourceString,
          L"\\",
          1);
  v22 = v21;
  if ( v21 >= 0 )
  {
    v23 = 0;
    v34 = 0;
    if ( dword_18082C178 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 8LL) )
    {
      Init_thread_header(&dword_18082C178);
      if ( dword_18082C178 == -1 )
      {
        Windows::Internal::StringReference::StringReference(v32, (const unsigned __int16 (*)[3])v31);
        Init_thread_footer(&dword_18082C178);
      }
    }
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    IsRootW = PathIsRootW(StringRawBuffer);
    newString[0] = 0;
    if ( IsRootW )
    {
      v30 = WindowsDuplicateString(a2, newString);
      v19 = Windows::Internal::String::FreeAndAssignOnSuccess(v30, newString[0], &v34);
      v23 = v34;
    }
    else
    {
      v19 = WindowsTrimStringEnd(a2, string, newString);
      if ( v19 >= 0 )
      {
        v23 = newString[0];
        v34 = newString[0];
        WindowsDeleteString(0);
      }
    }
    if ( v19 >= 0 )
    {
      v26 = WindowsGetStringRawBuffer(v23, 0);
      if ( v26 )
      {
        v27 = -1;
        do
          ++v27;
        while ( v26[v27] );
      }
      else
      {
        v27 = 0;
      }
      v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
              sourceString,
              v26,
              v27);
      v19 = v28;
      if ( v28 >= 0 )
      {
        v29 = sourceString[0];
        do
          ++v17;
        while ( sourceString[0][v17] );
        if ( v17 > 0xFFFFFFFF )
        {
          LODWORD(v17) = -1;
          RaiseException(0xC000000D, 1u, 0, 0);
        }
        WindowsCreateStringReference(
          v29,
          v17,
          (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
          (HSTRING *)&hstringHeader);
        v13 = StorageItemHelpers::ValidateCanonicalPath(hstringHeader.Reserved.Reserved1, 1);
        v14 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCC8,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
            (const char *)(unsigned int)v13,
            (int)v34);
          if ( v23 )
            WindowsDeleteString(v23);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
          StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v40);
          return v14;
        }
        else
        {
          *a4 = v29;
          if ( v23 )
            WindowsDeleteString(v23);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
          StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v40);
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC7,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
        (const char *)(unsigned int)v28,
        (int)v34);
      if ( v23 )
        WindowsDeleteString(v23);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
      StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v40);
      return (unsigned int)v19;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC6,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
      (const char *)(unsigned int)v19,
      (int)v34);
    if ( v23 )
      WindowsDeleteString(v23);
    v33 = (WCHAR *)sourceString[0];
    if ( !sourceString[0] )
      goto LABEL_48;
LABEL_47:
    CoTaskMemFree(v33);
    goto LABEL_48;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC4,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\dataaccess.cpp",
    (const char *)(unsigned int)v21,
    (int)v34);
  if ( sourceString[0] )
    CoTaskMemFree((LPVOID)sourceString[0]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)&v40);
  return v22;
}

```

## disassembly

```asm
0x18007b390  mov     [rsp-8+arg_8], rbx
0x18007b395  push    rbp
0x18007b396  push    rsi
0x18007b397  push    rdi
0x18007b398  push    r12
0x18007b39a  push    r13
0x18007b39c  push    r14
0x18007b39e  push    r15
0x18007b3a0  lea     rbp, [rsp-70h]
0x18007b3a5  sub     rsp, 170h
0x18007b3ac  movaps  [rsp+1A0h+var_40], xmm6
0x18007b3b4  mov     rax, cs:__security_cookie
0x18007b3bb  xor     rax, rsp
0x18007b3be  mov     [rbp+0A0h+var_50], rax
0x18007b3c2  mov     r12, r9
0x18007b3c5  mov     esi, r8d
0x18007b3c8  mov     r15, rdx
0x18007b3cb  mov     rdi, rcx
0x18007b3ce  xorps   xmm0, xmm0
0x18007b3d1  movups  xmmword ptr [rsp+1A0h+newString], xmm0
0x18007b3d6  lea     rdx, [rsp+1A0h+newString]
0x18007b3db  mov     ecx, 1
0x18007b3e0  call    cs:__imp_EtwEventActivityIdControl
0x18007b3e7  nop     dword ptr [rax+rax+00h]
0x18007b3ec  test    eax, eax
0x18007b3ee  jnz     loc_18007B9A1
0x18007b3f4  movups  xmm6, xmmword ptr [rsp+1A0h+newString]
0x18007b3f9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_6185f7d59584f69b5a44cbef7cf75836_@@CA@XZ; _lambda_6185f7d59584f69b5a44cbef7cf75836_::_lambda_invoker_cdecl_(void)
0x18007b400  call    ?get@?$static_lazy@VWinRTStorageTelemetry@@@details@wil@@QEAAPEAVWinRTStorageTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WinRTStorageTelemetry>::get(void (*)(void))
0x18007b405  lea     rbx, [rax+28h]
0x18007b409  xor     r13d, r13d
0x18007b40c  test    rax, rax
0x18007b40f  cmovz   rbx, r13
0x18007b413  lea     rax, ??_7ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@6B@; const StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::`vftable'
0x18007b41a  mov     [rbp+0A0h+var_110], rax
0x18007b41e  mov     [rbp+0A0h+var_F0], r13b
0x18007b422  mov     [rbp+0A0h+var_108], r13d
0x18007b426  lea     r14, aCheckiteminpro; "_CheckItemInProc"
0x18007b42d  mov     [rbp+0A0h+var_100], r14
0x18007b431  mov     [rbp+0A0h+var_F8], r13
0x18007b435  mov     [rbp+0A0h+var_E8], r13
0x18007b439  lea     rax, [rbp+0A0h+var_110]
0x18007b43d  mov     [rbp+0A0h+var_E0], rax
0x18007b441  mov     [rbp+0A0h+var_D8], r13
0x18007b445  mov     [rbp+0A0h+var_D0], r13d
0x18007b449  lea     rax, [rbp+0A0h+var_108]
0x18007b44d  mov     [rbp+0A0h+var_C8], rax
0x18007b451  mov     [rbp+0A0h+var_C0], r13b
0x18007b455  lea     rcx, [rbp+0A0h+var_E8]; this
0x18007b459  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18007b45e  nop
0x18007b45f  mov     [rbp+0A0h+var_B8], r13
0x18007b463  mov     [rbp+0A0h+var_B0], rbx
0x18007b467  movups  [rbp+0A0h+var_A8], xmm6
0x18007b46b  mov     [rbp+0A0h+var_98], r13
0x18007b46f  mov     [rbp+0A0h+var_90], r13
0x18007b473  lea     rax, word_180713EEA
0x18007b47a  mov     [rbp+0A0h+var_88], rax
0x18007b47e  mov     [rbp+0A0h+var_80], rax
0x18007b482  mov     [rbp+0A0h+var_78], rax
0x18007b486  mov     [rbp+0A0h+var_70], rax
0x18007b48a  mov     [rbp+0A0h+var_60], r14
0x18007b48e  mov     [rbp+0A0h+var_68], r13b
0x18007b492  mov     [r12], r13
0x18007b496  lea     rcx, [rdi+30h]
0x18007b49a  mov     rax, [rcx]
0x18007b49d  mov     rax, [rax+38h]
0x18007b4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4a6  test    al, al
0x18007b4a8  jz      loc_18007B572
0x18007b4ae  lea     rcx, [rbp+0A0h+var_110]; this
0x18007b4b2  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18007b4b7  mov     eax, 80004001h
0x18007b4bc  jmp     loc_18007B542
0x18007b4c1  mov     edi, eax
0x18007b4c3  xor     r9d, r9d; lpArguments
0x18007b4c6  xor     r8d, r8d; nNumberOfArguments
0x18007b4c9  mov     edx, 1; dwExceptionFlags
0x18007b4ce  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007b4d3  call    cs:__imp_RaiseException
0x18007b4da  nop     dword ptr [rax+rax+00h]
0x18007b4df  lea     r9, [rsp+1A0h+hstringHeader]; string
0x18007b4e4  lea     r8, [rsp+1A0h+hstringHeader.Reserved+8]; hstringHeader
0x18007b4e9  mov     edx, edi; length
0x18007b4eb  mov     rcx, rsi; sourceString
0x18007b4ee  call    cs:__imp_WindowsCreateStringReference
0x18007b4f5  nop     dword ptr [rax+rax+00h]
0x18007b4fa  mov     edx, 1
0x18007b4ff  mov     rcx, qword ptr [rsp+1A0h+hstringHeader.Reserved]
0x18007b504  call    ?ValidateCanonicalPath@StorageItemHelpers@@YAJPEAUHSTRING__@@W4CANONICALIZE_FLAGS@@@Z; StorageItemHelpers::ValidateCanonicalPath(HSTRING__ *,CANONICALIZE_FLAGS)
0x18007b509  mov     edi, eax
0x18007b50b  test    eax, eax
0x18007b50d  js      loc_18007B94A
0x18007b513  mov     [r12], rsi
0x18007b517  test    rbx, rbx
0x18007b51a  jz      short loc_18007B52C
0x18007b51c  mov     rcx, rbx; string
0x18007b51f  call    cs:__imp_WindowsDeleteString
0x18007b526  nop     dword ptr [rax+rax+00h]
0x18007b52b  nop
0x18007b52c  lea     rcx, [rsp+1A0h+var_160]
0x18007b531  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b536  nop
0x18007b537  lea     rcx, [rbp+0A0h+var_110]; this
0x18007b53b  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18007b540  xor     eax, eax
0x18007b542  mov     rcx, [rbp+0A0h+var_50]
0x18007b546  xor     rcx, rsp; StackCookie
0x18007b549  call    __security_check_cookie
0x18007b54e  mov     rbx, [rsp+1A0h+arg_8]
0x18007b556  movaps  xmm6, [rsp+1A0h+var_40]
0x18007b55e  add     rsp, 170h
0x18007b565  pop     r15
0x18007b567  pop     r14
0x18007b569  pop     r13
0x18007b56b  pop     r12
0x18007b56d  pop     rdi
0x18007b56e  pop     rsi
0x18007b56f  pop     rbp
0x18007b570  retn
0x18007b572  test    esi, esi
0x18007b574  jz      loc_18007B4AE
0x18007b57a  mov     [rsp+1A0h+var_160], r13
0x18007b57f  lea     rcx, [rdi+0C0h]
0x18007b586  mov     rax, [rcx]
0x18007b589  lea     r8, [rsp+1A0h+var_160]
0x18007b58e  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18007b595  mov     rax, [rax+18h]
0x18007b599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b59e  mov     ebx, eax
0x18007b5a0  test    eax, eax
0x18007b5a2  js      loc_18007B7FF
0x18007b5a8  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18007b5af  mov     [rsp+1A0h+var_170], rdi
0x18007b5b4  mov     [rsp+1A0h+var_168], rdi
0x18007b5b9  movups  xmm0, cs:PKEY_FileAPI_Path
0x18007b5c0  mov     ecx, cs:dword_18073AB10
0x18007b5c6  mov     r14, r13
0x18007b5c9  mov     [rsp+1A0h+sourceString], r13
0x18007b5ce  mov     word ptr [rsp+1A0h+hstringHeader.Reserved], r13w
0x18007b5d4  movaps  xmmword ptr [rsp+1A0h+newString], xmm0
0x18007b5d9  mov     [rsp+1A0h+var_140], ecx
0x18007b5dd  mov     rcx, [rsp+1A0h+var_160]
0x18007b5e2  mov     rax, [rcx]
0x18007b5e5  lea     r8, [rsp+1A0h+hstringHeader]
0x18007b5ea  lea     rdx, [rsp+1A0h+newString]
0x18007b5ef  mov     rax, [rax+28h]
0x18007b5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b5f8  mov     esi, eax
0x18007b5fa  movzx   eax, word ptr [rsp+1A0h+hstringHeader.Reserved]
0x18007b5ff  test    esi, esi
0x18007b601  js      short loc_18007B60C
0x18007b603  test    ax, ax
0x18007b606  jz      loc_18007B77D
0x18007b60c  mov     rbx, r13
0x18007b60f  test    esi, esi
0x18007b611  js      short loc_18007B637
0x18007b613  mov     r14, r13
0x18007b616  mov     [rsp+1A0h+sourceString], r13
0x18007b61b  cmp     ax, 1Fh
0x18007b61f  jnz     short loc_18007B62F
0x18007b621  mov     rbx, qword ptr [rsp+1A0h+hstringHeader.Reserved+8]
0x18007b626  test    rbx, rbx
0x18007b629  jnz     loc_18007B787
0x18007b62f  mov     esi, 80020005h
0x18007b634  mov     rbx, r13
0x18007b637  lea     rcx, [rsp+1A0h+hstringHeader]; pvar
0x18007b63c  call    cs:__imp_PropVariantClear
0x18007b643  nop     dword ptr [rax+rax+00h]
0x18007b648  test    esi, esi
0x18007b64a  js      loc_18007B8E7
0x18007b650  mov     r8d, 1
0x18007b656  lea     rdx, pszSrc; "\\"
0x18007b65d  lea     rcx, [rsp+1A0h+sourceString]
0x18007b662  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18007b667  mov     ebx, eax
0x18007b669  test    eax, eax
0x18007b66b  js      loc_18007B836
0x18007b671  mov     rbx, r13
0x18007b674  mov     [rsp+1A0h+var_180], rbx
0x18007b679  mov     ecx, cs:_tls_index
0x18007b67f  mov     rax, gs:58h
0x18007b688  mov     edx, 8
0x18007b68d  mov     rax, [rax+rcx*8]
0x18007b691  mov     ecx, [rdx+rax]
0x18007b694  cmp     cs:dword_18082C178, ecx
0x18007b69a  jg      loc_18007B7D0
0x18007b6a0  xor     edx, edx; length
0x18007b6a2  mov     rcx, r15; string
0x18007b6a5  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b6ac  nop     dword ptr [rax+rax+00h]
0x18007b6b1  mov     rcx, rax; pszPath
0x18007b6b4  call    cs:__imp_PathIsRootW
0x18007b6bb  nop     dword ptr [rax+rax+00h]
0x18007b6c0  mov     [rsp+1A0h+newString], r13
0x18007b6c5  mov     rcx, r15; string
0x18007b6c8  test    eax, eax
0x18007b6ca  jnz     loc_18007B7A2
0x18007b6d0  lea     r8, [rsp+1A0h+newString]; newString
0x18007b6d5  mov     rdx, cs:string; trimString
0x18007b6dc  call    cs:__imp_WindowsTrimStringEnd
0x18007b6e3  nop     dword ptr [rax+rax+00h]
0x18007b6e8  mov     esi, eax
0x18007b6ea  test    eax, eax
0x18007b6ec  js      short loc_18007B706
0x18007b6ee  mov     rbx, [rsp+1A0h+newString]
0x18007b6f3  mov     [rsp+1A0h+var_180], rbx; int
0x18007b6f8  xor     ecx, ecx; string
0x18007b6fa  call    cs:__imp_WindowsDeleteString
0x18007b701  nop     dword ptr [rax+rax+00h]
0x18007b706  test    esi, esi
0x18007b708  js      loc_18007B884
0x18007b70e  xor     edx, edx; length
0x18007b710  mov     rcx, rbx; string
0x18007b713  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b71a  nop     dword ptr [rax+rax+00h]
0x18007b71f  test    rax, rax
0x18007b722  jz      loc_18007B9B2
0x18007b728  mov     r8, rdi
0x18007b72b  nop     dword ptr [rax+rax+00h]
0x18007b730  inc     r8
0x18007b733  cmp     word ptr [rax+r8*2], 0
0x18007b739  jnz     short loc_18007B730
0x18007b73b  mov     rdx, rax
0x18007b73e  lea     rcx, [rsp+1A0h+sourceString]
0x18007b743  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18007b748  mov     esi, eax
0x18007b74a  test    eax, eax
0x18007b74c  js      loc_18007B90D
0x18007b752  mov     rsi, [rsp+1A0h+sourceString]
0x18007b757  nop     word ptr [rax+rax+00000000h]
0x18007b760  inc     rdi
0x18007b763  cmp     word ptr [rsi+rdi*2], 0
0x18007b768  jnz     short loc_18007B760
0x18007b76a  mov     eax, 0FFFFFFFFh
0x18007b76f  cmp     rdi, rax
0x18007b772  jbe     loc_18007B4DF
0x18007b778  jmp     loc_18007B4C1
0x18007b77d  mov     esi, 80070490h
0x18007b782  jmp     loc_18007B634
0x18007b787  mov     r14, rbx
0x18007b78a  mov     [rsp+1A0h+sourceString], rbx
0x18007b78f  xorps   xmm0, xmm0
0x18007b792  xor     eax, eax
0x18007b794  movups  xmmword ptr [rsp+1A0h+hstringHeader.Reserved], xmm0
0x18007b799  mov     qword ptr [rbp+0A0h+hstringHeader.Reserved+10h], rax
0x18007b79d  jmp     loc_18007B637
0x18007b7a2  lea     rdx, [rsp+1A0h+newString]; newString
0x18007b7a7  call    cs:__imp_WindowsDuplicateString
0x18007b7ae  nop     dword ptr [rax+rax+00h]
0x18007b7b3  lea     r8, [rsp+1A0h+var_180]; HSTRING *
0x18007b7b8  mov     rdx, [rsp+1A0h+newString]; HSTRING
0x18007b7bd  mov     ecx, eax; int
0x18007b7bf  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18007b7c4  mov     esi, eax
0x18007b7c6  mov     rbx, [rsp+1A0h+var_180]
0x18007b7cb  jmp     loc_18007B706
0x18007b7d0  lea     rcx, dword_18082C178
0x18007b7d7  call    _Init_thread_header
0x18007b7dc  cmp     cs:dword_18082C178, 0FFFFFFFFh
0x18007b7e3  jnz     loc_18007B6A0
0x18007b7e9  call    ??$?0$02@StringReference@Internal@Windows@@QEAA@AEAY02$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[3])
0x18007b7ee  lea     rcx, dword_18082C178
0x18007b7f5  call    _Init_thread_footer
0x18007b7fa  jmp     loc_18007B6A0
0x18007b7ff  mov     rcx, [rbp+0A8h]; this
0x18007b806  mov     r9d, ebx; char *
0x18007b809  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18007b810  mov     edx, 0CC1h; void *
0x18007b815  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b81a  nop
0x18007b81b  lea     rcx, [rsp+1A0h+var_160]
0x18007b820  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b825  nop
0x18007b826  lea     rcx, [rbp+0A0h+var_110]; this
0x18007b82a  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18007b82f  mov     eax, ebx
0x18007b831  jmp     loc_18007B542
0x18007b836  mov     rcx, [rbp+0A8h]; this
0x18007b83d  mov     r9d, ebx; char *
0x18007b840  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
0x18007b847  mov     edx, 0CC4h; void *
0x18007b84c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b851  nop
0x18007b852  mov     rcx, [rsp+1A0h+sourceString]; pv
0x18007b857  test    rcx, rcx
0x18007b85a  jz      short loc_18007B869
0x18007b85c  call    cs:__imp_CoTaskMemFree
0x18007b863  nop     dword ptr [rax+rax+00h]
0x18007b868  nop
0x18007b869  lea     rcx, [rsp+1A0h+var_160]
0x18007b86e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b873  nop
0x18007b874  lea     rcx, [rbp+0A0h+var_110]; this
0x18007b878  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18007b87d  mov     eax, ebx
0x18007b87f  jmp     loc_18007B542
0x18007b884  mov     rcx, [rbp+0A8h]; this
0x18007b88b  mov     r9d, esi; char *
0x18007b88e  lea     r8, aOnecoreuapShel_30; "onecoreuap\\shell\\windows.storage\\dat"...
  ... truncated ...
```
