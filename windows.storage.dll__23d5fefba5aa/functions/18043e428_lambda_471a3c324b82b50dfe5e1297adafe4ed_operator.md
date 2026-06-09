# _lambda_471a3c324b82b50dfe5e1297adafe4ed_::operator()

- ea: `0x18043e428`
- end: `0x18043e823`
- name: `_lambda_471a3c324b82b50dfe5e1297adafe4ed_::operator()`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1804424b0`

## callees

- `0x180009fc0`
- `0x18001e7e0`
- `0x18001f748`
- `0x18002368c`
- `0x180023734`
- `0x180024038`
- `0x180038f50`
- `0x18007bbf0`
- `0x1801bb424`
- `0x1801f7aa8`
- `0x1803b1f60`
- `0x1803fce64`
- `0x18043b830`
- `0x18043e428`
- `0x180443fe0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18043e488`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x18043e488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e479`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e4de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e51e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e479`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e4de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18043e51e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e6db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e7db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e5e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e6db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e769`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18043e7db`

## string_xrefs

- `0x18043e462`: `s_ReadAllTextAsync.MakeAsyncOperation`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lambda_471a3c324b82b50dfe5e1297adafe4ed_::operator()(__int64 a1, HSTRING *a2, __int64 a3)
{
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v6; // rax
  const struct _GUID *v7; // rdx
  const unsigned __int16 *v8; // rax
  const struct _GUID *v9; // rdx
  unsigned int StorageItemFromPathOrMsUri_PartialTrustCaller; // eax
  const unsigned __int16 *v11; // rax
  const struct _GUID *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int AllTextUsingFileAsync; // eax
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  int EntireFileIntoDataReaderSync; // eax
  int AllTextSync; // eax
  int v25; // eax
  unsigned int v27[4]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v30; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[192]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  *(_OWORD *)v28 = *(_OWORD *)(a1 + 24);
  LOBYTE(a3) = 1;
  WinRTStorageTelemetry::WatchCurrentThread(v32, "s_ReadAllTextAsync.MakeAsyncOperation", a3, v28);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
  if ( PathIsURLW(StringRawBuffer) )
  {
    v30 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v6 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
    if ( (int)CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v6, v7, (void **)&v30) >= 0 )
    {
      *(_QWORD *)v27 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
      if ( (int)CFileIOStatics::s_ReadAllTextUsingFileAsync(
                  v30,
                  *(unsigned int *)(a1 + 16),
                  *(unsigned int *)(a1 + 20),
                  v27) >= 0 )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v17 = *(_QWORD *)v27;
        v18 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v27);
        if ( v18 >= 0 )
          v18 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 64LL))(v17, &string);
        if ( v18 >= 0 )
        {
          v28[0] = string;
          v22 = Microsoft::WRL::Wrappers::HString::Set(a2 + 2, v28);
        }
        else
        {
          WindowsDeleteString(string);
          string = 0;
          v19 = *(_QWORD *)v27;
          v20 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v27);
          if ( v20 >= 0 )
            v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 64LL))(v19, &string);
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x4D3,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
            (const char *)(unsigned int)v20,
            v27[0]);
          WindowsDeleteString(string);
          string = 0;
          v21 = *(_QWORD *)v27;
          v22 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(*(_QWORD *)v27);
          if ( v22 >= 0 )
            v22 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 64LL))(v21, &string);
        }
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v22);
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
        AllTextUsingFileAsync = CFileIOStatics::s_ReadAllTextUsingFileAsync(
                                  v30,
                                  *(unsigned int *)(a1 + 16),
                                  *(unsigned int *)(a1 + 20),
                                  v27);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x4D0,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
          (const char *)AllTextUsingFileAsync,
          v27[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
        v16 = CFileIOStatics::s_ReadAllTextUsingFileAsync(
                v30,
                *(unsigned int *)(a1 + 16),
                *(unsigned int *)(a1 + 20),
                v27);
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v16);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v27);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      v8 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
      StorageItemFromPathOrMsUri_PartialTrustCaller = CreateStorageItemFromPathOrMsUri_PartialTrustCaller(
                                                        v8,
                                                        v9,
                                                        (void **)&v30);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x4CD,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)StorageItemFromPathOrMsUri_PartialTrustCaller,
        v27[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      v11 = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
      v13 = CreateStorageItemFromPathOrMsUri_PartialTrustCaller(v11, v12, (void **)&v30);
      v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  }
  else
  {
    v27[0] = anonymous_namespace_::EncodingToByteOrderMark(*(unsigned int *)(a1 + 16), *(unsigned int *)(a1 + 20));
    LODWORD(string) = 0;
    v28[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
    EntireFileIntoDataReaderSync = CPathIOStatics::s_LoadEntireFileIntoDataReaderSync(*(HSTRING *)a1);
    v14 = EntireFileIntoDataReaderSync;
    if ( EntireFileIntoDataReaderSync >= 0 )
    {
      v31[0] = 0;
      WindowsDeleteString(0);
      v31[0] = 0;
      AllTextSync = anonymous_namespace_::CStorageHelpers::s_ReadAllTextSync(v28[0], (unsigned int)string, v27[0], v31);
      v14 = AllTextSync;
      if ( AllTextSync >= 0 )
      {
        v30 = v31[0];
        v25 = Microsoft::WRL::Wrappers::HString::Set(a2 + 2, &v30);
        v14 = Windows::Internal::CResultBase::MapErrorIfCanceled((Windows::Internal::CResultBase *)a2, v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4DF,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
          (const char *)(unsigned int)AllTextSync,
          v27[0]);
      }
      WindowsDeleteString(v31[0]);
      v31[0] = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4DC,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagehelpers.cpp",
        (const char *)(unsigned int)EntireFileIntoDataReaderSync,
        v27[0]);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
  }
  StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit((StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit *)v32);
  return v14;
}

```

## disassembly

```asm
0x18043e428  mov     [rsp-8+arg_10], rbx
0x18043e42d  push    rbp
0x18043e42e  push    rsi
0x18043e42f  push    rdi
0x18043e430  lea     rbp, [rsp-30h]
0x18043e435  sub     rsp, 130h
0x18043e43c  mov     rax, cs:__security_cookie
0x18043e443  xor     rax, rsp
0x18043e446  mov     [rbp+40h+var_20], rax
0x18043e44a  mov     rdi, rdx
0x18043e44d  mov     rbx, rcx
0x18043e450  movups  xmm0, xmmword ptr [rcx+18h]
0x18043e454  movdqu  xmmword ptr [rsp+140h+var_110], xmm0
0x18043e45a  lea     r9, [rsp+140h+var_110]
0x18043e45f  mov     r8b, 1
0x18043e462  lea     rdx, aSReadalltextas_0; "s_ReadAllTextAsync.MakeAsyncOperation"
0x18043e469  lea     rcx, [rsp+140h+var_E0]
0x18043e46e  call    ?WatchCurrentThread@WinRTStorageTelemetry@@SA?AVActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@PEBD_NU_GUID@@@Z; WinRTStorageTelemetry::WatchCurrentThread(char const *,bool,_GUID)
0x18043e473  nop
0x18043e474  xor     edx, edx; length
0x18043e476  mov     rcx, [rbx]; string
0x18043e479  call    cs:__imp_WindowsGetStringRawBuffer
0x18043e480  nop     dword ptr [rax+rax+00h]
0x18043e485  mov     rcx, rax; pszPath
0x18043e488  call    cs:__imp_PathIsURLW
0x18043e48f  nop     dword ptr [rax+rax+00h]
0x18043e494  xor     esi, esi
0x18043e496  test    eax, eax
0x18043e498  jz      loc_18043E706
0x18043e49e  mov     [rsp+140h+var_F8], rsi
0x18043e4a3  lea     rcx, [rsp+140h+var_F8]
0x18043e4a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e4ad  xor     edx, edx; length
0x18043e4af  mov     rcx, [rbx]; string
0x18043e4b2  call    cs:__imp_WindowsGetStringRawBuffer
0x18043e4b9  nop     dword ptr [rax+rax+00h]
0x18043e4be  lea     r8, [rsp+140h+var_F8]; void **
0x18043e4c3  mov     rcx, rax; unsigned __int16 *
0x18043e4c6  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18043e4cb  test    eax, eax
0x18043e4cd  jns     short loc_18043E548
0x18043e4cf  lea     rcx, [rsp+140h+var_F8]
0x18043e4d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e4d9  xor     edx, edx; length
0x18043e4db  mov     rcx, [rbx]; string
0x18043e4de  call    cs:__imp_WindowsGetStringRawBuffer
0x18043e4e5  nop     dword ptr [rax+rax+00h]
0x18043e4ea  lea     r8, [rsp+140h+var_F8]; void **
0x18043e4ef  mov     rcx, rax; unsigned __int16 *
0x18043e4f2  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18043e4f7  mov     rcx, [rbp+48h]; this
0x18043e4fb  mov     r9d, eax; char *
0x18043e4fe  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18043e505  mov     edx, 4CDh; void *
0x18043e50a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18043e50f  lea     rcx, [rsp+140h+var_F8]
0x18043e514  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e519  xor     edx, edx; length
0x18043e51b  mov     rcx, [rbx]; string
0x18043e51e  call    cs:__imp_WindowsGetStringRawBuffer
0x18043e525  nop     dword ptr [rax+rax+00h]
0x18043e52a  lea     r8, [rsp+140h+var_F8]; void **
0x18043e52f  mov     rcx, rax; unsigned __int16 *
0x18043e532  call    ?CreateStorageItemFromPathOrMsUri_PartialTrustCaller@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateStorageItemFromPathOrMsUri_PartialTrustCaller(ushort const *,_GUID const &,void * *)
0x18043e537  mov     edx, eax; int
0x18043e539  mov     rcx, rdi; this
0x18043e53c  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18043e541  mov     ebx, eax
0x18043e543  jmp     loc_18043E6F7
0x18043e548  mov     qword ptr [rsp+140h+var_120], rsi; int
0x18043e54d  lea     rcx, [rsp+140h+var_120]
0x18043e552  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e557  lea     r9, [rsp+140h+var_120]
0x18043e55c  mov     r8d, [rbx+14h]
0x18043e560  mov     edx, [rbx+10h]
0x18043e563  mov     rcx, [rsp+140h+var_F8]
0x18043e568  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18043e56d  test    eax, eax
0x18043e56f  jns     short loc_18043E5DA
0x18043e571  lea     rcx, [rsp+140h+var_120]
0x18043e576  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e57b  lea     r9, [rsp+140h+var_120]
0x18043e580  mov     r8d, [rbx+14h]
0x18043e584  mov     edx, [rbx+10h]
0x18043e587  mov     rcx, [rsp+140h+var_F8]
0x18043e58c  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18043e591  mov     rcx, [rbp+48h]; this
0x18043e595  mov     r9d, eax; char *
0x18043e598  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18043e59f  mov     edx, 4D0h; void *
0x18043e5a4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18043e5a9  lea     rcx, [rsp+140h+var_120]
0x18043e5ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e5b3  lea     r9, [rsp+140h+var_120]
0x18043e5b8  mov     r8d, [rbx+14h]
0x18043e5bc  mov     edx, [rbx+10h]
0x18043e5bf  mov     rcx, [rsp+140h+var_F8]
0x18043e5c4  call    CFileIOStatics__s_ReadAllTextUsingFileAsync
0x18043e5c9  mov     edx, eax; int
0x18043e5cb  mov     rcx, rdi; this
0x18043e5ce  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18043e5d3  mov     ebx, eax
0x18043e5d5  jmp     loc_18043E6EC
0x18043e5da  mov     [rsp+140h+string], rsi
0x18043e5df  xor     ecx, ecx; string
0x18043e5e1  call    cs:__imp_WindowsDeleteString
0x18043e5e8  nop     dword ptr [rax+rax+00h]
0x18043e5ed  mov     [rsp+140h+string], rsi
0x18043e5f2  mov     rbx, qword ptr [rsp+140h+var_120]
0x18043e5f7  mov     rcx, rbx
0x18043e5fa  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18043e5ff  test    eax, eax
0x18043e601  js      short loc_18043E618
0x18043e603  mov     rax, [rbx]
0x18043e606  lea     rdx, [rsp+140h+string]
0x18043e60b  mov     rcx, rbx
0x18043e60e  mov     rax, [rax+40h]
0x18043e612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043e617  nop
0x18043e618  test    eax, eax
0x18043e61a  jns     loc_18043E6B2
0x18043e620  mov     rcx, [rsp+140h+string]; string
0x18043e625  call    cs:__imp_WindowsDeleteString
0x18043e62c  nop     dword ptr [rax+rax+00h]
0x18043e631  mov     [rsp+140h+string], rsi
0x18043e636  mov     rbx, qword ptr [rsp+140h+var_120]
0x18043e63b  mov     rcx, rbx
0x18043e63e  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18043e643  test    eax, eax
0x18043e645  js      short loc_18043E65C
0x18043e647  mov     rax, [rbx]
0x18043e64a  lea     rdx, [rsp+140h+string]
0x18043e64f  mov     rcx, rbx
0x18043e652  mov     rax, [rax+40h]
0x18043e656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043e65b  nop
0x18043e65c  mov     rcx, [rbp+48h]; this
0x18043e660  mov     r9d, eax; char *
0x18043e663  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18043e66a  mov     edx, 4D3h; void *
0x18043e66f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18043e674  mov     rcx, [rsp+140h+string]; string
0x18043e679  call    cs:__imp_WindowsDeleteString
0x18043e680  nop     dword ptr [rax+rax+00h]
0x18043e685  mov     [rsp+140h+string], rsi
0x18043e68a  mov     rbx, qword ptr [rsp+140h+var_120]
0x18043e68f  mov     rcx, rbx
0x18043e692  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18043e697  test    eax, eax
0x18043e699  js      short loc_18043E6B0
0x18043e69b  mov     rax, [rbx]
0x18043e69e  lea     rdx, [rsp+140h+string]
0x18043e6a3  mov     rcx, rbx
0x18043e6a6  mov     rax, [rax+40h]
0x18043e6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18043e6af  nop
0x18043e6b0  jmp     short loc_18043E6CA
0x18043e6b2  mov     rax, [rsp+140h+string]
0x18043e6b7  mov     [rsp+140h+var_110], rax
0x18043e6bc  lea     rcx, [rdi+10h]; newString
0x18043e6c0  lea     rdx, [rsp+140h+var_110]; HSTRING *
0x18043e6c5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18043e6ca  mov     edx, eax; int
0x18043e6cc  mov     rcx, rdi; this
0x18043e6cf  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18043e6d4  mov     ebx, eax
0x18043e6d6  mov     rcx, [rsp+140h+string]; string
0x18043e6db  call    cs:__imp_WindowsDeleteString
0x18043e6e2  nop     dword ptr [rax+rax+00h]
0x18043e6e7  mov     [rsp+140h+string], rsi
0x18043e6ec  lea     rcx, [rsp+140h+var_120]
0x18043e6f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e6f6  nop
0x18043e6f7  lea     rcx, [rsp+140h+var_F8]
0x18043e6fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e701  jmp     loc_18043E7F7
0x18043e706  mov     edx, [rbx+14h]
0x18043e709  mov     ecx, [rbx+10h]
0x18043e70c  call    _anonymous_namespace___EncodingToByteOrderMark
0x18043e711  mov     [rsp+140h+var_120], eax; int
0x18043e715  mov     dword ptr [rsp+140h+string], esi
0x18043e719  mov     [rsp+140h+var_110], rsi
0x18043e71e  lea     rcx, [rsp+140h+var_110]
0x18043e723  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e728  lea     r9, [rsp+140h+var_120]
0x18043e72d  lea     r8, [rsp+140h+var_110]
0x18043e732  lea     rdx, [rsp+140h+string]
0x18043e737  mov     rcx, [rbx]; HSTRING
0x18043e73a  call    CPathIOStatics__s_LoadEntireFileIntoDataReaderSync
0x18043e73f  mov     ebx, eax
0x18043e741  test    eax, eax
0x18043e743  jns     short loc_18043E762
0x18043e745  mov     rcx, [rbp+48h]; this
0x18043e749  mov     r9d, eax; char *
0x18043e74c  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18043e753  mov     edx, 4DCh; void *
0x18043e758  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18043e75d  jmp     loc_18043E7EC
0x18043e762  mov     [rsp+140h+var_F0], rsi
0x18043e767  xor     ecx, ecx; string
0x18043e769  call    cs:__imp_WindowsDeleteString
0x18043e770  nop     dword ptr [rax+rax+00h]
0x18043e775  mov     [rsp+140h+var_F0], rsi
0x18043e77a  lea     r9, [rsp+140h+var_F0]
0x18043e77f  mov     r8d, [rsp+140h+var_120]
0x18043e784  mov     edx, dword ptr [rsp+140h+string]
0x18043e788  mov     rcx, [rsp+140h+var_110]
0x18043e78d  call    _anonymous_namespace___CStorageHelpers__s_ReadAllTextSync
0x18043e792  mov     ebx, eax
0x18043e794  test    eax, eax
0x18043e796  jns     short loc_18043E7B2
0x18043e798  mov     rcx, [rbp+48h]; this
0x18043e79c  mov     r9d, eax; char *
0x18043e79f  lea     r8, aOnecoreuapShel_155; "onecoreuap\\shell\\windows.storage\\sto"...
0x18043e7a6  mov     edx, 4DFh; void *
0x18043e7ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18043e7b0  jmp     short loc_18043E7D6
0x18043e7b2  mov     rax, [rsp+140h+var_F0]
0x18043e7b7  mov     [rsp+140h+var_F8], rax
0x18043e7bc  lea     rcx, [rdi+10h]; newString
0x18043e7c0  lea     rdx, [rsp+140h+var_F8]; HSTRING *
0x18043e7c5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18043e7ca  mov     edx, eax; int
0x18043e7cc  mov     rcx, rdi; this
0x18043e7cf  call    ?MapErrorIfCanceled@CResultBase@Internal@Windows@@QEBAJJ@Z; Windows::Internal::CResultBase::MapErrorIfCanceled(long)
0x18043e7d4  mov     ebx, eax
0x18043e7d6  mov     rcx, [rsp+140h+var_F0]; string
0x18043e7db  call    cs:__imp_WindowsDeleteString
0x18043e7e2  nop     dword ptr [rax+rax+00h]
0x18043e7e7  mov     [rsp+140h+var_F0], rsi
0x18043e7ec  lea     rcx, [rsp+140h+var_110]
0x18043e7f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18043e7f6  nop
0x18043e7f7  lea     rcx, [rsp+140h+var_E0]; this
0x18043e7fc  call    ??1ActivityThreadWatcherWithCapturedCallerContextReportOnExit@StorageTelemetry@@QEAA@XZ; StorageTelemetry::ActivityThreadWatcherWithCapturedCallerContextReportOnExit::~ActivityThreadWatcherWithCapturedCallerContextReportOnExit(void)
0x18043e801  mov     eax, ebx
0x18043e803  mov     rcx, [rbp+40h+var_20]
0x18043e807  xor     rcx, rsp; StackCookie
0x18043e80a  call    __security_check_cookie
0x18043e80f  mov     rbx, [rsp+140h+arg_10]
0x18043e817  add     rsp, 130h
0x18043e81e  pop     rdi
0x18043e81f  pop     rsi
0x18043e820  pop     rbp
0x18043e821  retn
```
