# CStorageFolderChangeTracker::RuntimeClassInitialize(ushort const *,Windows::Storage::IStorageFolder *)

- ea: `0x1801a5da4`
- end: `0x1801a60f8`
- name: `?RuntimeClassInitialize@CStorageFolderChangeTracker@@QEAAJPEBGPEAUIStorageFolder@Storage@Windows@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(CStorageFolderChangeTracker *__hidden this, const unsigned __int16 *, struct Windows::Storage::IStorageFolder *)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1803a4418`
- `0x180597bf0`

## callees

- `0x180009fc0`
- `0x180038f50`
- `0x180044320`
- `0x180063050`
- `0x180083c94`
- `0x1800c72b0`
- `0x1801720d0`
- `0x18017632c`
- `0x1801a5da4`
- `0x1801a6100`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x180619e5c`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801a5fae`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801a5fae`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801a5ff9`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801a5ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a5dfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a6046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a5dfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a6046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a5f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801a5f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a5ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a5f25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a6058`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a60b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a5ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a5f25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a6058`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801a60b2`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801a6013`
- `api-ms-win-shlwapi-ie-l1-1-0!PathIsDirectoryW` at `0x1801a6013`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageFolderChangeTracker::RuntimeClassInitialize(
        CStorageFolderChangeTracker *this,
        const unsigned __int16 *a2,
        struct Windows::Storage::IStorageFolder *a3)
{
  int CallingProcessId; // ebx
  __int64 v6; // rdx
  CallerIdentity *v7; // rax
  unsigned __int16 **v8; // rdx
  __int64 (__fastcall *v9)(struct Windows::Storage::IStorageFolder *, GUID *, _QWORD *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  PCWSTR StringRawBuffer; // rax
  WCHAR *v15; // rbx
  const char *v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumeName[56]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  if ( a2 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      a2,
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      (char *)this + 96,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    if ( !*((_QWORD *)this + 12) )
    {
      CallingProcessId = -2147024882;
      v6 = 114;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
        (const char *)(unsigned int)CallingProcessId,
        (int)pv);
      return (unsigned int)CallingProcessId;
    }
  }
  else
  {
    CallingProcessId = CallerIdentity::GetCallingProcessId(0, &pv);
    if ( CallingProcessId < 0 )
    {
      v6 = 119;
      goto LABEL_6;
    }
    v7 = (CallerIdentity *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put((char *)this + 96);
    CallingProcessId = CallerIdentity::GetCallerProcessImageNameAlloc(v7, v8);
    if ( CallingProcessId < 0 )
    {
      v6 = 122;
      goto LABEL_6;
    }
  }
  v22[0] = 0;
  v9 = **(__int64 (__fastcall ***)(struct Windows::Storage::IStorageFolder *, GUID *, _QWORD *))a3;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22);
  v10 = v9(a3, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, v22);
  CallingProcessId = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
      (const char *)(unsigned int)v10,
      (int)pv);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22);
    return (unsigned int)CallingProcessId;
  }
  string = 0;
  v11 = v22[0];
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22[0] + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(v11, &string);
  CallingProcessId = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
      (const char *)(unsigned int)v13,
      (int)pv);
LABEL_15:
    WindowsDeleteString(string);
LABEL_29:
    string = 0;
    goto LABEL_30;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    StringRawBuffer,
    -1);
  v15 = (WCHAR *)pv;
  if ( !pv )
  {
    CallingProcessId = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
      (const char *)0x8007000ELL,
      0);
LABEL_18:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    goto LABEL_15;
  }
  memset_0(szVolumePathName, 0, 0x208u);
  if ( !GetVolumePathNameW(v15, szVolumePathName, 0x104u) )
  {
    v17 = 140;
LABEL_21:
    CallingProcessId = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)v17,
                         (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
                         v16);
    goto LABEL_18;
  }
  memset_0(szVolumeName, 0, 0x64u);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u) )
  {
    v17 = 143;
    goto LABEL_21;
  }
  if ( PathIsDirectoryW(v15) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
      (char *)this + 136,
      &pv);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    WindowsDeleteString(string);
    CallingProcessId = 0;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x93,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\storagefolderchangetracker.cpp",
    (const char *)0x80070490LL,
    (int)pv);
  CoTaskMemFree(v15);
  WindowsDeleteString(string);
  string = 0;
  v18 = v22[0];
  if ( v22[0] )
  {
    v22[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x1801a5da4  mov     [rsp-8+arg_18], rbx
0x1801a5da9  push    rbp
0x1801a5daa  push    rsi
0x1801a5dab  push    rdi
0x1801a5dac  lea     rbp, [rsp-1D0h]
0x1801a5db4  sub     rsp, 2D0h
0x1801a5dbb  mov     rax, cs:__security_cookie
0x1801a5dc2  xor     rax, rsp
0x1801a5dc5  mov     [rbp+1E0h+var_20], rax
0x1801a5dcc  mov     rdi, r8
0x1801a5dcf  mov     rsi, rcx
0x1801a5dd2  test    rdx, rdx
0x1801a5dd5  jz      short loc_1801A5E35
0x1801a5dd7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801a5ddb  lea     rcx, [rsp+2E0h+pv]
0x1801a5de0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801a5de5  lea     rdx, [rsp+2E0h+pv]
0x1801a5dea  lea     rcx, [rsi+60h]
0x1801a5dee  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1801a5df3  mov     rcx, [rsp+2E0h+pv]; pv
0x1801a5df8  test    rcx, rcx
0x1801a5dfb  jz      short loc_1801A5E09
0x1801a5dfd  call    cs:__imp_CoTaskMemFree
0x1801a5e04  nop     dword ptr [rax+rax+00h]
0x1801a5e09  cmp     qword ptr [rsi+60h], 0
0x1801a5e0e  jnz     short loc_1801A5E6C
0x1801a5e10  mov     ebx, 8007000Eh
0x1801a5e15  mov     edx, 72h ; 'r'; void *
0x1801a5e1a  mov     rcx, [rbp+1E8h]; this
0x1801a5e21  mov     r9d, ebx; char *
0x1801a5e24  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801a5e2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a5e30  jmp     loc_1801A60D3
0x1801a5e35  lea     rdx, [rsp+2E0h+pv]
0x1801a5e3a  xor     ecx, ecx
0x1801a5e3c  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x1801a5e41  mov     ebx, eax
0x1801a5e43  test    eax, eax
0x1801a5e45  jns     short loc_1801A5E4E
0x1801a5e47  mov     edx, 77h ; 'w'
0x1801a5e4c  jmp     short loc_1801A5E1A
0x1801a5e4e  lea     rcx, [rsi+60h]
0x1801a5e52  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801a5e57  mov     rcx, rax; this
0x1801a5e5a  call    ?GetCallerProcessImageNameAlloc@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallerProcessImageNameAlloc(ushort * *)
0x1801a5e5f  mov     ebx, eax
0x1801a5e61  test    eax, eax
0x1801a5e63  jns     short loc_1801A5E6C
0x1801a5e65  mov     edx, 7Ah ; 'z'
0x1801a5e6a  jmp     short loc_1801A5E1A
0x1801a5e6c  mov     [rsp+2E0h+var_2B0], 0
0x1801a5e75  mov     rax, [rdi]
0x1801a5e78  mov     rbx, [rax]
0x1801a5e7b  lea     rcx, [rsp+2E0h+var_2B0]
0x1801a5e80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a5e85  lea     r8, [rsp+2E0h+var_2B0]
0x1801a5e8a  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1801a5e91  mov     rcx, rdi
0x1801a5e94  mov     rax, rbx
0x1801a5e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5e9c  mov     ebx, eax
0x1801a5e9e  test    eax, eax
0x1801a5ea0  jns     short loc_1801A5EC2
0x1801a5ea2  mov     rcx, [rbp+1E8h]; this
0x1801a5ea9  mov     r9d, eax; char *
0x1801a5eac  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801a5eb3  mov     edx, 80h; void *
0x1801a5eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a5ebd  jmp     loc_1801A60C9
0x1801a5ec2  mov     [rsp+2E0h+string], 0
0x1801a5ecb  mov     rdi, [rsp+2E0h+var_2B0]
0x1801a5ed0  mov     rax, [rdi]
0x1801a5ed3  mov     rbx, [rax+60h]
0x1801a5ed7  xor     ecx, ecx; string
0x1801a5ed9  call    cs:__imp_WindowsDeleteString
0x1801a5ee0  nop     dword ptr [rax+rax+00h]
0x1801a5ee5  mov     [rsp+2E0h+string], 0
0x1801a5eee  lea     rdx, [rsp+2E0h+string]
0x1801a5ef3  mov     rcx, rdi
0x1801a5ef6  mov     rax, rbx
0x1801a5ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a5efe  mov     ebx, eax
0x1801a5f00  test    eax, eax
0x1801a5f02  jns     short loc_1801A5F36
0x1801a5f04  mov     rcx, [rbp+1E8h]; this
0x1801a5f0b  mov     r9d, eax; char *
0x1801a5f0e  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801a5f15  mov     edx, 83h; void *
0x1801a5f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a5f1f  nop
0x1801a5f20  mov     rcx, [rsp+2E0h+string]; string
0x1801a5f25  call    cs:__imp_WindowsDeleteString
0x1801a5f2c  nop     dword ptr [rax+rax+00h]
0x1801a5f31  jmp     loc_1801A60C0
0x1801a5f36  xor     edx, edx; length
0x1801a5f38  mov     rcx, [rsp+2E0h+string]; string
0x1801a5f3d  call    cs:__imp_WindowsGetStringRawBuffer
0x1801a5f44  nop     dword ptr [rax+rax+00h]
0x1801a5f49  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801a5f4d  mov     rdx, rax
0x1801a5f50  lea     rcx, [rsp+2E0h+pv]
0x1801a5f55  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801a5f5a  mov     rbx, [rsp+2E0h+pv]
0x1801a5f5f  test    rbx, rbx
0x1801a5f62  jnz     short loc_1801A5F90
0x1801a5f64  mov     rcx, [rbp+1E8h]; this
0x1801a5f6b  mov     ebx, 8007000Eh
0x1801a5f70  mov     r9d, ebx; char *
0x1801a5f73  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801a5f7a  mov     edx, 86h; void *
0x1801a5f7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a5f84  lea     rcx, [rsp+2E0h+pv]; void *
0x1801a5f89  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1801a5f8e  jmp     short loc_1801A5F20
0x1801a5f90  xor     edx, edx; Val
0x1801a5f92  mov     r8d, 208h; Size
0x1801a5f98  lea     rcx, [rbp+1E0h+szVolumePathName]; void *
0x1801a5f9c  call    memset_0
0x1801a5fa1  mov     r8d, 104h; cchBufferLength
0x1801a5fa7  lea     rdx, [rbp+1E0h+szVolumePathName]; lpszVolumePathName
0x1801a5fab  mov     rcx, rbx; lpszFileName
0x1801a5fae  call    cs:__imp_GetVolumePathNameW
0x1801a5fb5  nop     dword ptr [rax+rax+00h]
0x1801a5fba  test    eax, eax
0x1801a5fbc  jnz     short loc_1801A5FDA
0x1801a5fbe  mov     edx, 8Ch; void *
0x1801a5fc3  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801a5fca  mov     rcx, [rbp+1E8h]; this
0x1801a5fd1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a5fd6  mov     ebx, eax
0x1801a5fd8  jmp     short loc_1801A5F84
0x1801a5fda  xor     edx, edx; Val
0x1801a5fdc  lea     r8d, [rdx+64h]; Size
0x1801a5fe0  lea     rcx, [rsp+2E0h+szVolumeName]; void *
0x1801a5fe5  call    memset_0
0x1801a5fea  mov     r8d, 32h ; '2'; cchBufferLength
0x1801a5ff0  lea     rdx, [rsp+2E0h+szVolumeName]; lpszVolumeName
0x1801a5ff5  lea     rcx, [rbp+1E0h+szVolumePathName]; lpszVolumeMountPoint
0x1801a5ff9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801a6000  nop     dword ptr [rax+rax+00h]
0x1801a6005  test    eax, eax
0x1801a6007  jnz     short loc_1801A6010
0x1801a6009  mov     edx, 8Fh
0x1801a600e  jmp     short loc_1801A5FC3
0x1801a6010  mov     rcx, rbx; pszPath
0x1801a6013  call    cs:__imp_PathIsDirectoryW
0x1801a601a  nop     dword ptr [rax+rax+00h]
0x1801a601f  test    eax, eax
0x1801a6021  jnz     short loc_1801A6091
0x1801a6023  mov     rcx, [rbp+1E8h]; this
0x1801a602a  mov     edi, 80070490h
0x1801a602f  mov     r9d, edi; char *
0x1801a6032  lea     r8, aOnecoreuapShel_32; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801a6039  mov     edx, 93h; void *
0x1801a603e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6043  mov     rcx, rbx; pv
0x1801a6046  call    cs:__imp_CoTaskMemFree
0x1801a604d  nop     dword ptr [rax+rax+00h]
0x1801a6052  nop
0x1801a6053  mov     rcx, [rsp+2E0h+string]; string
0x1801a6058  call    cs:__imp_WindowsDeleteString
0x1801a605f  nop     dword ptr [rax+rax+00h]
0x1801a6064  mov     [rsp+2E0h+string], 0
0x1801a606d  mov     rcx, [rsp+2E0h+var_2B0]
0x1801a6072  test    rcx, rcx
0x1801a6075  jz      short loc_1801A608D
0x1801a6077  mov     [rsp+2E0h+var_2B0], 0
0x1801a6080  mov     rdx, [rcx]
0x1801a6083  mov     rax, [rdx+10h]
0x1801a6087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a608c  nop
0x1801a608d  mov     eax, edi
0x1801a608f  jmp     short loc_1801A60D5
0x1801a6091  lea     rcx, [rsi+88h]
0x1801a6098  lea     rdx, [rsp+2E0h+pv]
0x1801a609d  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801a60a2  lea     rcx, [rsp+2E0h+pv]; void *
0x1801a60a7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1801a60ac  nop
0x1801a60ad  mov     rcx, [rsp+2E0h+string]; string
0x1801a60b2  call    cs:__imp_WindowsDeleteString
0x1801a60b9  nop     dword ptr [rax+rax+00h]
0x1801a60be  xor     ebx, ebx
0x1801a60c0  mov     [rsp+2E0h+string], 0
0x1801a60c9  lea     rcx, [rsp+2E0h+var_2B0]
0x1801a60ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a60d3  mov     eax, ebx
0x1801a60d5  mov     rcx, [rbp+1E0h+var_20]
0x1801a60dc  xor     rcx, rsp; StackCookie
0x1801a60df  call    __security_check_cookie
0x1801a60e4  mov     rbx, [rsp+2E0h+arg_18]
0x1801a60ec  add     rsp, 2D0h
0x1801a60f3  pop     rdi
0x1801a60f4  pop     rsi
0x1801a60f5  pop     rbp
0x1801a60f6  retn
```
