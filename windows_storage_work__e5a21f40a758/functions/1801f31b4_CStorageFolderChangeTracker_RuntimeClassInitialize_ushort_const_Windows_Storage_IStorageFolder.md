# CStorageFolderChangeTracker::RuntimeClassInitialize(ushort const *,Windows::Storage::IStorageFolder *)

- ea: `0x1801f31b4`
- end: `0x1801f34d9`
- name: `?RuntimeClassInitialize@CStorageFolderChangeTracker@@QEAAJPEBGPEAUIStorageFolder@Storage@Windows@@@Z`
- size: `805`
- prototype: `__int64 __fastcall(CStorageFolderChangeTracker *__hidden this, const unsigned __int16 *, struct Windows::Storage::IStorageFolder *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180396868`
- `0x18057c944`

## callees

- `0x18000d6cc`
- `0x18001b390`
- `0x180028e78`
- `0x1800432f0`
- `0x180060a10`
- `0x1800d13a0`
- `0x18014be50`
- `0x1801f31b4`
- `0x1801f34e0`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1805f9cc4`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801f33a4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801f33a4`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801f33f5`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801f33f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f320d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f33cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f3436`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f348e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f320d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f33cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f3436`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801f348e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f3356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f3356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f32fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f3344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f3442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f349a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f32fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f3344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f3442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f349a`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801f3409`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801f3409`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageFolderChangeTracker::RuntimeClassInitialize(
        CStorageFolderChangeTracker *this,
        const unsigned __int16 *a2,
        struct Windows::Storage::IStorageFolder *a3)
{
  unsigned int LastError; // edi
  int CallingProcessId; // ebx
  __int64 v7; // rdx
  CallerIdentity *v9; // rax
  unsigned __int16 **v10; // rdx
  __int64 (__fastcall *v11)(struct Windows::Storage::IStorageFolder *, GUID *, _QWORD *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  PCWSTR StringRawBuffer; // rax
  void *v19; // rbx
  const char *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v25[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  if ( !a2 )
  {
    CallingProcessId = CallerIdentity::GetCallingProcessId(0, &pv);
    if ( CallingProcessId >= 0 )
    {
      v9 = (CallerIdentity *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put((char *)this + 96);
      CallingProcessId = CallerIdentity::GetCallerProcessImageNameAlloc(v9, v10);
      if ( CallingProcessId >= 0 )
        goto LABEL_11;
      v7 = 122;
    }
    else
    {
      v7 = 119;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
      (const char *)(unsigned int)CallingProcessId,
      (int)pv);
    return (unsigned int)CallingProcessId;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    a2,
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 96,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( *((_QWORD *)this + 12) )
  {
LABEL_11:
    v25[0] = 0;
    v11 = **(__int64 (__fastcall ***)(struct Windows::Storage::IStorageFolder *, GUID *, _QWORD *))a3;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
    v12 = v11(a3, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, v25);
    LastError = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
        (const char *)(unsigned int)v12,
        (int)pv);
LABEL_32:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
      return LastError;
    }
    string = 0;
    v13 = v25[0];
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25[0] + 96LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    LastError = v15;
    if ( v15 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        StringRawBuffer,
        -1);
      v19 = pv;
      if ( pv )
      {
        memset_0(szVolumePathName, 0, 0x208u);
        if ( GetVolumePathNameW((LPCWSTR)v19, szVolumePathName, 0x104u) )
        {
          memset_0(szVolumeName, 0, 0x64u);
          if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u) )
          {
            if ( !PathIsDirectoryW((LPCWSTR)v19) )
            {
              LastError = -2147023728;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x93,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
                (const char *)0x80070490LL,
                (int)pv);
              CoTaskMemFree(v19);
              WindowsDeleteString(string);
              string = 0;
              v22 = v25[0];
              if ( v25[0] )
              {
                v25[0] = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              }
              return LastError;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
              (char *)this + 136,
              &pv);
            if ( pv )
              CoTaskMemFree(pv);
            WindowsDeleteString(string);
            LastError = 0;
            goto LABEL_31;
          }
          v21 = 143;
        }
        else
        {
          v21 = 140;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v21,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
                      v20);
        CoTaskMemFree(v19);
LABEL_16:
        WindowsDeleteString(string);
LABEL_31:
        string = 0;
        goto LABEL_32;
      }
      LastError = -2147024882;
      v16 = 2147942414LL;
      v17 = 134;
    }
    else
    {
      v16 = (unsigned int)v15;
      v17 = 131;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
      (const char *)v16,
      (int)pv);
    goto LABEL_16;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
    (const char *)0x8007000ELL,
    (int)pv);
  return LastError;
}

```

## disassembly

```asm
0x1801f31b4  mov     [rsp-8+arg_18], rbx
0x1801f31b9  push    rbp
0x1801f31ba  push    rsi
0x1801f31bb  push    rdi
0x1801f31bc  lea     rbp, [rsp-1D0h]
0x1801f31c4  sub     rsp, 2D0h
0x1801f31cb  mov     rax, cs:__security_cookie
0x1801f31d2  xor     rax, rsp
0x1801f31d5  mov     [rbp+1E0h+var_20], rax
0x1801f31dc  mov     rdi, r8
0x1801f31df  mov     rsi, rcx
0x1801f31e2  test    rdx, rdx
0x1801f31e5  jz      short loc_1801F323F
0x1801f31e7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801f31eb  lea     rcx, [rsp+2E0h+pv]
0x1801f31f0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801f31f5  lea     rdx, [rsp+2E0h+pv]
0x1801f31fa  lea     rcx, [rsi+60h]
0x1801f31fe  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801f3203  mov     rcx, [rsp+2E0h+pv]; pv
0x1801f3208  test    rcx, rcx
0x1801f320b  jz      short loc_1801F3213
0x1801f320d  call    cs:__imp_CoTaskMemFree
0x1801f3213  cmp     qword ptr [rsi+60h], 0
0x1801f3218  jnz     short loc_1801F3291
0x1801f321a  mov     rcx, [rbp+1E8h]; this
0x1801f3221  mov     edi, 8007000Eh
0x1801f3226  mov     r9d, edi; char *
0x1801f3229  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801f3230  mov     edx, 72h ; 'r'; void *
0x1801f3235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f323a  jmp     loc_1801F34B5
0x1801f323f  lea     rdx, [rsp+2E0h+pv]
0x1801f3244  xor     ecx, ecx
0x1801f3246  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x1801f324b  mov     ebx, eax
0x1801f324d  test    eax, eax
0x1801f324f  jns     short loc_1801F3273
0x1801f3251  mov     edx, 77h ; 'w'; void *
0x1801f3256  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801f325d  mov     r9d, ebx; char *
0x1801f3260  mov     rcx, [rbp+1E8h]; this
0x1801f3267  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f326c  mov     eax, ebx
0x1801f326e  jmp     loc_1801F34B7
0x1801f3273  lea     rcx, [rsi+60h]
0x1801f3277  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801f327c  mov     rcx, rax; this
0x1801f327f  call    ?GetCallerProcessImageNameAlloc@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallerProcessImageNameAlloc(ushort * *)
0x1801f3284  mov     ebx, eax
0x1801f3286  test    eax, eax
0x1801f3288  jns     short loc_1801F3291
0x1801f328a  mov     edx, 7Ah ; 'z'
0x1801f328f  jmp     short loc_1801F3256
0x1801f3291  mov     [rsp+2E0h+var_2B0], 0
0x1801f329a  mov     rax, [rdi]
0x1801f329d  mov     rbx, [rax]
0x1801f32a0  lea     rcx, [rsp+2E0h+var_2B0]
0x1801f32a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f32aa  lea     r8, [rsp+2E0h+var_2B0]
0x1801f32af  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1801f32b6  mov     rcx, rdi
0x1801f32b9  mov     rax, rbx
0x1801f32bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f32c1  mov     edi, eax
0x1801f32c3  test    eax, eax
0x1801f32c5  jns     short loc_1801F32E7
0x1801f32c7  mov     rcx, [rbp+1E8h]; this
0x1801f32ce  mov     r9d, eax; char *
0x1801f32d1  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801f32d8  mov     edx, 80h; void *
0x1801f32dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f32e2  jmp     loc_1801F34AB
0x1801f32e7  mov     [rsp+2E0h+string], 0
0x1801f32f0  mov     rdi, [rsp+2E0h+var_2B0]
0x1801f32f5  mov     rax, [rdi]
0x1801f32f8  mov     rbx, [rax+60h]
0x1801f32fc  xor     ecx, ecx; string
0x1801f32fe  call    cs:__imp_WindowsDeleteString
0x1801f3304  mov     [rsp+2E0h+string], 0
0x1801f330d  lea     rdx, [rsp+2E0h+string]
0x1801f3312  mov     rcx, rdi
0x1801f3315  mov     rax, rbx
0x1801f3318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f331d  mov     edi, eax
0x1801f331f  test    eax, eax
0x1801f3321  jns     short loc_1801F334F
0x1801f3323  mov     r9d, eax; char *
0x1801f3326  mov     edx, 83h; void *
0x1801f332b  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801f3332  mov     rcx, [rbp+1E8h]; this
0x1801f3339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f333e  nop
0x1801f333f  mov     rcx, [rsp+2E0h+string]; string
0x1801f3344  call    cs:__imp_WindowsDeleteString
0x1801f334a  jmp     loc_1801F34A2
0x1801f334f  xor     edx, edx; length
0x1801f3351  mov     rcx, [rsp+2E0h+string]; string
0x1801f3356  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f335c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801f3360  mov     rdx, rax
0x1801f3363  lea     rcx, [rsp+2E0h+pv]
0x1801f3368  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801f336d  mov     rbx, [rsp+2E0h+pv]
0x1801f3372  test    rbx, rbx
0x1801f3375  jnz     short loc_1801F3386
0x1801f3377  mov     edi, 8007000Eh
0x1801f337c  mov     r9d, edi
0x1801f337f  mov     edx, 86h
0x1801f3384  jmp     short loc_1801F332B
0x1801f3386  xor     edx, edx; Val
0x1801f3388  mov     r8d, 208h; Size
0x1801f338e  lea     rcx, [rbp+1E0h+szVolumePathName]; void *
0x1801f3392  call    memset_0
0x1801f3397  mov     r8d, 104h; cchBufferLength
0x1801f339d  lea     rdx, [rbp+1E0h+szVolumePathName]; lpszVolumePathName
0x1801f33a1  mov     rcx, rbx; lpszFileName
0x1801f33a4  call    cs:__imp_GetVolumePathNameW
0x1801f33aa  test    eax, eax
0x1801f33ac  jnz     short loc_1801F33D6
0x1801f33ae  mov     edx, 8Ch; void *
0x1801f33b3  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801f33ba  mov     rcx, [rbp+1E8h]; this
0x1801f33c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801f33c6  mov     edi, eax
0x1801f33c8  mov     rcx, rbx; pv
0x1801f33cb  call    cs:__imp_CoTaskMemFree
0x1801f33d1  jmp     loc_1801F333F
0x1801f33d6  xor     edx, edx; Val
0x1801f33d8  lea     r8d, [rdx+64h]; Size
0x1801f33dc  lea     rcx, [rsp+2E0h+szVolumeName]; void *
0x1801f33e1  call    memset_0
0x1801f33e6  mov     r8d, 32h ; '2'; cchBufferLength
0x1801f33ec  lea     rdx, [rsp+2E0h+szVolumeName]; lpszVolumeName
0x1801f33f1  lea     rcx, [rbp+1E0h+szVolumePathName]; lpszVolumeMountPoint
0x1801f33f5  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801f33fb  test    eax, eax
0x1801f33fd  jnz     short loc_1801F3406
0x1801f33ff  mov     edx, 8Fh
0x1801f3404  jmp     short loc_1801F33B3
0x1801f3406  mov     rcx, rbx; pszPath
0x1801f3409  call    cs:__imp_PathIsDirectoryW
0x1801f340f  test    eax, eax
0x1801f3411  jnz     short loc_1801F3473
0x1801f3413  mov     rcx, [rbp+1E8h]; this
0x1801f341a  mov     edi, 80070490h
0x1801f341f  mov     r9d, edi; char *
0x1801f3422  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801f3429  mov     edx, 93h; void *
0x1801f342e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f3433  mov     rcx, rbx; pv
0x1801f3436  call    cs:__imp_CoTaskMemFree
0x1801f343c  nop
0x1801f343d  mov     rcx, [rsp+2E0h+string]; string
0x1801f3442  call    cs:__imp_WindowsDeleteString
0x1801f3448  mov     [rsp+2E0h+string], 0
0x1801f3451  mov     rcx, [rsp+2E0h+var_2B0]
0x1801f3456  test    rcx, rcx
0x1801f3459  jz      short loc_1801F3471
0x1801f345b  mov     [rsp+2E0h+var_2B0], 0
0x1801f3464  mov     rdx, [rcx]
0x1801f3467  mov     rax, [rdx+10h]
0x1801f346b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f3470  nop
0x1801f3471  jmp     short loc_1801F34B5
0x1801f3473  lea     rcx, [rsi+88h]
0x1801f347a  lea     rdx, [rsp+2E0h+pv]
0x1801f347f  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801f3484  mov     rcx, [rsp+2E0h+pv]; pv
0x1801f3489  test    rcx, rcx
0x1801f348c  jz      short loc_1801F3495
0x1801f348e  call    cs:__imp_CoTaskMemFree
0x1801f3494  nop
0x1801f3495  mov     rcx, [rsp+2E0h+string]; string
0x1801f349a  call    cs:__imp_WindowsDeleteString
0x1801f34a0  xor     edi, edi
0x1801f34a2  mov     [rsp+2E0h+string], 0
0x1801f34ab  lea     rcx, [rsp+2E0h+var_2B0]
0x1801f34b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f34b5  mov     eax, edi
0x1801f34b7  mov     rcx, [rbp+1E0h+var_20]
0x1801f34be  xor     rcx, rsp; StackCookie
0x1801f34c1  call    __security_check_cookie
0x1801f34c6  mov     rbx, [rsp+2E0h+arg_18]
0x1801f34ce  add     rsp, 2D0h
0x1801f34d5  pop     rdi
0x1801f34d6  pop     rsi
0x1801f34d7  pop     rbp
0x1801f34d8  retn
```
