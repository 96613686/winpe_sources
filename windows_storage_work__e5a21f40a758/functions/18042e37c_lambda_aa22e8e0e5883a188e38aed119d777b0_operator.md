# _lambda_aa22e8e0e5883a188e38aed119d777b0_::operator()

- ea: `0x18042e37c`
- end: `0x18042e754`
- name: `_lambda_aa22e8e0e5883a188e38aed119d777b0_::operator()`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180431640`

## callees

- `0x18000d6cc`
- `0x180010110`
- `0x1800432f0`
- `0x18007153c`
- `0x180071568`
- `0x1800c4bc8`
- `0x1800c6184`
- `0x18014c7f0`
- `0x1801c2e38`
- `0x1801ec830`
- `0x1803a4cb0`
- `0x1803ed984`
- `0x18042aba0`
- `0x18042e37c`
- `0x180432f70`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18042e3dd`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18042e3dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e403`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18042e465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e5ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e6e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e70e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e5ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e6e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18042e70e`

## string_xrefs

- `0x18042e3bc`: `s_ReadLinesAsync.MakeAsyncOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lambda_aa22e8e0e5883a188e38aed119d777b0_::operator()(
        _QWORD *a1,
        Windows::Internal::CResultBase *a2,
        __int64 a3)
{
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v6; // rax
  const struct _GUID *v7; // rdx
  const unsigned __int16 *v8; // rax
  const struct _GUID *v9; // rdx
  unsigned int v10; // eax
  const unsigned __int16 *v11; // rax
  const struct _GUID *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int AllTextUsingFileAsync; // eax
  int v16; // eax
  __int64 v17; // rsi
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int EntireFileIntoDataReaderSync; // eax
  int v24; // esi
  int AllTextSync; // eax
  int v26; // eax
  unsigned int v28[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v29; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  void *v31; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[192]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v29 = *((_OWORD *)a1 + 2);
  LOBYTE(a3) = 1;
  WinRTStorageTelemetry::WatchCurrentThread(v33, "s_ReadLinesAsync.MakeAsyncOperation", a3, &v29);
  StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a1[1], 0);
  if ( PathIsURLW(StringRawBuffer) )
  {
    v31 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v6 = WindowsGetStringRawBuffer((HSTRING)a1[1], 0);
    if ( (int)CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v6, v7, &v31) >= 0 )
    {
      *(_QWORD *)v28 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
      if ( (int)CFileIOStatics::s_ReadAllTextUsingFileAsync(
                  v31,
                  *((unsigned int *)a1 + 6),
                  *((unsigned int *)a1 + 7),
                  v28) >= 0 )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v17 = *(_QWORD *)v28;
        v18 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v28);
        if ( v18 >= 0 )
          v18 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 64LL))(v17, &string);
        if ( v18 >= 0 )
        {
          v22 = CLineSplitHSTRINGResult::Set(a2, *a1, string);
        }
        else
        {
          WindowsDeleteString(string);
          string = 0;
          v19 = *(_QWORD *)v28;
          v20 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v28);
          if ( v20 >= 0 )
            v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 64LL))(v19, &string);
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x555,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
            (const char *)(unsigned int)v20,
            v28[0]);
          WindowsDeleteString(string);
          string = 0;
          v21 = *(_QWORD *)v28;
          v22 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v28);
          if ( v22 >= 0 )
            v22 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 64LL))(v21, &string);
        }
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled(a2, v22);
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
        AllTextUsingFileAsync = CFileIOStatics::s_ReadAllTextUsingFileAsync(
                                  v31,
                                  *((unsigned int *)a1 + 6),
                                  *((unsigned int *)a1 + 7),
                                  v28);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x552,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
          (const char *)AllTextUsingFileAsync,
          v28[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
        v16 = CFileIOStatics::s_ReadAllTextUsingFileAsync(
                v31,
                *((unsigned int *)a1 + 6),
                *((unsigned int *)a1 + 7),
                v28);
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled(a2, v16);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v8 = WindowsGetStringRawBuffer((HSTRING)a1[1], 0);
      v10 = CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v8, v9, &v31);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x54F,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)v10,
        v28[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v11 = WindowsGetStringRawBuffer((HSTRING)a1[1], 0);
      v13 = CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v11, v12, &v31);
      v14 = Windows::Internal::CResultBase::MapErrorIfCanceled(a2, v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  }
  else
  {
    v28[0] = anonymous_namespace_::EncodingToByteOrderMark(*((unsigned int *)a1 + 6), *((unsigned int *)a1 + 7));
    LODWORD(string) = 0;
    *(_QWORD *)&v29 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    EntireFileIntoDataReaderSync = CPathIOStatics::s_LoadEntireFileIntoDataReaderSync((HSTRING)a1[1]);
    v24 = EntireFileIntoDataReaderSync;
    if ( EntireFileIntoDataReaderSync >= 0 )
    {
      v32[0] = 0;
      WindowsDeleteString(0);
      v32[0] = 0;
      AllTextSync = anonymous_namespace_::CStorageHelpers::s_ReadAllTextSync(v29, (unsigned int)string, v28[0], v32);
      v24 = AllTextSync;
      if ( AllTextSync >= 0 )
      {
        v26 = CLineSplitHSTRINGResult::Set(a2, *a1, v32[0]);
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled(a2, v26);
        WindowsDeleteString(v32[0]);
        v32[0] = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        goto LABEL_24;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x561,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)(unsigned int)AllTextSync,
        v28[0]);
      WindowsDeleteString(v32[0]);
      v32[0] = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55E,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)(unsigned int)EntireFileIntoDataReaderSync,
        v28[0]);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v14 = v24;
  }
LABEL_24:
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v33);
  return v14;
}

```

## disassembly

```asm
0x18042e37c  mov     [rsp-8+arg_10], rbx
0x18042e381  mov     [rsp-8+arg_18], rsi
0x18042e386  push    rbp
0x18042e387  push    rdi
0x18042e388  push    r14
0x18042e38a  lea     rbp, [rsp-30h]
0x18042e38f  sub     rsp, 130h
0x18042e396  mov     rax, cs:__security_cookie
0x18042e39d  xor     rax, rsp
0x18042e3a0  mov     [rbp+40h+var_20], rax
0x18042e3a4  mov     rdi, rdx
0x18042e3a7  mov     rbx, rcx
0x18042e3aa  movups  xmm0, xmmword ptr [rcx+20h]
0x18042e3ae  movdqu  [rsp+140h+var_110], xmm0
0x18042e3b4  lea     r9, [rsp+140h+var_110]
0x18042e3b9  mov     r8b, 1
0x18042e3bc  lea     rdx, aSReadlinesasyn_0; "s_ReadLinesAsync.MakeAsyncOperation"
0x18042e3c3  lea     rcx, [rsp+140h+var_E0]
0x18042e3c8  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_NU_GUID@@@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool,_GUID)
0x18042e3cd  nop
0x18042e3ce  xor     edx, edx; length
0x18042e3d0  mov     rcx, [rbx+8]; string
0x18042e3d4  call    cs:__imp_WindowsGetStringRawBuffer
0x18042e3da  mov     rcx, rax; pszPath
0x18042e3dd  call    cs:__imp_PathIsURLW
0x18042e3e3  xor     r14d, r14d
0x18042e3e6  test    eax, eax
0x18042e3e8  jz      loc_18042E627
0x18042e3ee  mov     [rsp+140h+var_F8], r14
0x18042e3f3  lea     rcx, [rsp+140h+var_F8]
0x18042e3f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e3fd  xor     edx, edx; length
0x18042e3ff  mov     rcx, [rbx+8]; string
0x18042e403  call    cs:__imp_WindowsGetStringRawBuffer
0x18042e409  lea     r8, [rsp+140h+var_F8]; void **
0x18042e40e  mov     rcx, rax; unsigned __int16 *
0x18042e411  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18042e416  test    eax, eax
0x18042e418  jns     short loc_18042E489
0x18042e41a  lea     rcx, [rsp+140h+var_F8]
0x18042e41f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e424  xor     edx, edx; length
0x18042e426  mov     rcx, [rbx+8]; string
0x18042e42a  call    cs:__imp_WindowsGetStringRawBuffer
0x18042e430  lea     r8, [rsp+140h+var_F8]; void **
0x18042e435  mov     rcx, rax; unsigned __int16 *
0x18042e438  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18042e43d  mov     rcx, [rbp+48h]; this
0x18042e441  mov     r9d, eax; char *
0x18042e444  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042e44b  mov     edx, 54Fh; void *
0x18042e450  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18042e455  lea     rcx, [rsp+140h+var_F8]
0x18042e45a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e45f  xor     edx, edx; length
0x18042e461  mov     rcx, [rbx+8]; string
0x18042e465  call    cs:__imp_WindowsGetStringRawBuffer
0x18042e46b  lea     r8, [rsp+140h+var_F8]; void **
0x18042e470  mov     rcx, rax; unsigned __int16 *
0x18042e473  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18042e478  mov     edx, eax; int
0x18042e47a  mov     rcx, rdi; this
0x18042e47d  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042e482  mov     ebx, eax
0x18042e484  jmp     loc_18042E618
0x18042e489  mov     qword ptr [rsp+140h+var_120], r14; int
0x18042e48e  lea     rcx, [rsp+140h+var_120]
0x18042e493  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e498  lea     r9, [rsp+140h+var_120]
0x18042e49d  mov     r8d, [rbx+1Ch]
0x18042e4a1  mov     edx, [rbx+18h]
0x18042e4a4  mov     rcx, [rsp+140h+var_F8]
0x18042e4a9  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18042e4ae  test    eax, eax
0x18042e4b0  jns     short loc_18042E51B
0x18042e4b2  lea     rcx, [rsp+140h+var_120]
0x18042e4b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e4bc  lea     r9, [rsp+140h+var_120]
0x18042e4c1  mov     r8d, [rbx+1Ch]
0x18042e4c5  mov     edx, [rbx+18h]
0x18042e4c8  mov     rcx, [rsp+140h+var_F8]
0x18042e4cd  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18042e4d2  mov     rcx, [rbp+48h]; this
0x18042e4d6  mov     r9d, eax; char *
0x18042e4d9  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042e4e0  mov     edx, 552h; void *
0x18042e4e5  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18042e4ea  lea     rcx, [rsp+140h+var_120]
0x18042e4ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e4f4  lea     r9, [rsp+140h+var_120]
0x18042e4f9  mov     r8d, [rbx+1Ch]
0x18042e4fd  mov     edx, [rbx+18h]
0x18042e500  mov     rcx, [rsp+140h+var_F8]
0x18042e505  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18042e50a  mov     edx, eax; int
0x18042e50c  mov     rcx, rdi; this
0x18042e50f  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042e514  mov     ebx, eax
0x18042e516  jmp     loc_18042E60D
0x18042e51b  mov     [rsp+140h+string], r14
0x18042e520  xor     ecx, ecx; string
0x18042e522  call    cs:__imp_WindowsDeleteString
0x18042e528  mov     [rsp+140h+string], r14
0x18042e52d  mov     rsi, qword ptr [rsp+140h+var_120]
0x18042e532  mov     rcx, rsi
0x18042e535  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18042e53a  test    eax, eax
0x18042e53c  js      short loc_18042E553
0x18042e53e  mov     rax, [rsi]
0x18042e541  lea     rdx, [rsp+140h+string]
0x18042e546  mov     rcx, rsi
0x18042e549  mov     rax, [rax+40h]
0x18042e54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042e552  nop
0x18042e553  test    eax, eax
0x18042e555  jns     loc_18042E5E1
0x18042e55b  mov     rcx, [rsp+140h+string]; string
0x18042e560  call    cs:__imp_WindowsDeleteString
0x18042e566  mov     [rsp+140h+string], r14
0x18042e56b  mov     rbx, qword ptr [rsp+140h+var_120]
0x18042e570  mov     rcx, rbx
0x18042e573  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18042e578  test    eax, eax
0x18042e57a  js      short loc_18042E591
0x18042e57c  mov     rax, [rbx]
0x18042e57f  lea     rdx, [rsp+140h+string]
0x18042e584  mov     rcx, rbx
0x18042e587  mov     rax, [rax+40h]
0x18042e58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042e590  nop
0x18042e591  mov     rcx, [rbp+48h]; this
0x18042e595  mov     r9d, eax; char *
0x18042e598  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042e59f  mov     edx, 555h; void *
0x18042e5a4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18042e5a9  mov     rcx, [rsp+140h+string]; string
0x18042e5ae  call    cs:__imp_WindowsDeleteString
0x18042e5b4  mov     [rsp+140h+string], r14
0x18042e5b9  mov     rbx, qword ptr [rsp+140h+var_120]
0x18042e5be  mov     rcx, rbx
0x18042e5c1  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18042e5c6  test    eax, eax
0x18042e5c8  js      short loc_18042E5DF
0x18042e5ca  mov     rax, [rbx]
0x18042e5cd  lea     rdx, [rsp+140h+string]
0x18042e5d2  mov     rcx, rbx
0x18042e5d5  mov     rax, [rax+40h]
0x18042e5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042e5de  nop
0x18042e5df  jmp     short loc_18042E5F1
0x18042e5e1  mov     r8, [rsp+140h+string]
0x18042e5e6  mov     rdx, [rbx]
0x18042e5e9  mov     rcx, rdi
0x18042e5ec  call    ?Set@CLineSplitHSTRINGResult@@QEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAUHSTRING__@@@Z; CLineSplitHSTRINGResult::Set(Windows::Foundation::Collections::IVector<HSTRING__ *> *,HSTRING__ *)
0x18042e5f1  mov     edx, eax; int
0x18042e5f3  mov     rcx, rdi; this
0x18042e5f6  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042e5fb  mov     ebx, eax
0x18042e5fd  mov     rcx, [rsp+140h+string]; string
0x18042e602  call    cs:__imp_WindowsDeleteString
0x18042e608  mov     [rsp+140h+string], r14
0x18042e60d  lea     rcx, [rsp+140h+var_120]
0x18042e612  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e617  nop
0x18042e618  lea     rcx, [rsp+140h+var_F8]
0x18042e61d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e622  jmp     loc_18042E724
0x18042e627  mov     edx, [rbx+1Ch]
0x18042e62a  mov     ecx, [rbx+18h]
0x18042e62d  call    _anonymous_namespace___EncodingToByteOrderMark
0x18042e632  mov     [rsp+140h+var_120], eax; int
0x18042e636  mov     dword ptr [rsp+140h+string], r14d
0x18042e63b  mov     qword ptr [rsp+140h+var_110], r14
0x18042e640  lea     rcx, [rsp+140h+var_110]
0x18042e645  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e64a  lea     r9, [rsp+140h+var_120]
0x18042e64f  lea     r8, [rsp+140h+var_110]
0x18042e654  lea     rdx, [rsp+140h+string]
0x18042e659  mov     rcx, [rbx+8]; HSTRING
0x18042e65d  call    CPathIOStatics__s_LoadEntireFileIntoDataReaderSync
0x18042e662  mov     esi, eax
0x18042e664  test    eax, eax
0x18042e666  jns     short loc_18042E692
0x18042e668  mov     rcx, [rbp+48h]; this
0x18042e66c  mov     r9d, eax; char *
0x18042e66f  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042e676  mov     edx, 55Eh; void *
0x18042e67b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18042e680  nop
0x18042e681  lea     rcx, [rsp+140h+var_110]
0x18042e686  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e68b  mov     ebx, esi
0x18042e68d  jmp     loc_18042E724
0x18042e692  mov     [rsp+140h+var_F0], r14
0x18042e697  xor     ecx, ecx; string
0x18042e699  call    cs:__imp_WindowsDeleteString
0x18042e69f  mov     [rsp+140h+var_F0], r14
0x18042e6a4  lea     r9, [rsp+140h+var_F0]
0x18042e6a9  mov     r8d, [rsp+140h+var_120]
0x18042e6ae  mov     edx, dword ptr [rsp+140h+string]
0x18042e6b2  mov     rcx, qword ptr [rsp+140h+var_110]
0x18042e6b7  call    _anonymous_namespace___CStorageHelpers__s_ReadAllTextSync
0x18042e6bc  mov     esi, eax
0x18042e6be  test    eax, eax
0x18042e6c0  jns     short loc_18042E6ED
0x18042e6c2  mov     rcx, [rbp+48h]; this
0x18042e6c6  mov     r9d, eax; char *
0x18042e6c9  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18042e6d0  mov     edx, 561h; void *
0x18042e6d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18042e6da  nop
0x18042e6db  mov     rcx, [rsp+140h+var_F0]; string
0x18042e6e0  call    cs:__imp_WindowsDeleteString
0x18042e6e6  mov     [rsp+140h+var_F0], r14
0x18042e6eb  jmp     short loc_18042E681
0x18042e6ed  mov     r8, [rsp+140h+var_F0]
0x18042e6f2  mov     rdx, [rbx]
0x18042e6f5  mov     rcx, rdi
0x18042e6f8  call    ?Set@CLineSplitHSTRINGResult@@QEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAUHSTRING__@@@Z; CLineSplitHSTRINGResult::Set(Windows::Foundation::Collections::IVector<HSTRING__ *> *,HSTRING__ *)
0x18042e6fd  mov     edx, eax; int
0x18042e6ff  mov     rcx, rdi; this
0x18042e702  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18042e707  mov     ebx, eax
0x18042e709  mov     rcx, [rsp+140h+var_F0]; string
0x18042e70e  call    cs:__imp_WindowsDeleteString
0x18042e714  mov     [rsp+140h+var_F0], r14
0x18042e719  lea     rcx, [rsp+140h+var_110]
0x18042e71e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18042e723  nop
0x18042e724  lea     rcx, [rsp+140h+var_E0]; this
0x18042e729  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18042e72e  mov     eax, ebx
0x18042e730  mov     rcx, [rbp+40h+var_20]
0x18042e734  xor     rcx, rsp; StackCookie
0x18042e737  call    __security_check_cookie
0x18042e73c  lea     r11, [rsp+140h+var_10]
0x18042e744  mov     rbx, [r11+30h]
0x18042e748  mov     rsi, [r11+38h]
0x18042e74c  mov     rsp, r11
0x18042e74f  pop     r14
0x18042e751  pop     rdi
0x18042e752  pop     rbp
0x18042e753  retn
```
