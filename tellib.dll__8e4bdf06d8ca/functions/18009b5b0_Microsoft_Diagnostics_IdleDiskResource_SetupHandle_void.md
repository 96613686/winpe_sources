# Microsoft::Diagnostics::IdleDiskResource::SetupHandle(void)

- ea: `0x18009b5b0`
- end: `0x18009b954`
- name: `?SetupHandle@IdleDiskResource@Diagnostics@Microsoft@@EEAAXXZ`
- size: `932`
- prototype: `void __fastcall(Microsoft::Diagnostics::IdleDiskResource *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001d160`
- `0x180032718`
- `0x180034d94`
- `0x1800866b8`
- `0x18009b5b0`
- `0x18009bd1c`
- `0x1800a1e24`
- `0x1800bc2e0`
- `0x1800d0d7c`
- `0x1800dbc78`
- `0x18012de40`
- `0x18012e324`
- `0x18013079c`
- `0x180170014`
- `0x180201d94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b6f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b668`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b82b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b668`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009b82b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009b6e1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009b789`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009b6e1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18009b789`

## string_xrefs

- `0x18009b62e`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x18009b68d`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x18009b729`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x18009b79d`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x18009b92d`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`
- `0x18009b942`: `onecore\base\telemetry\utc\service\metadata\idlediskresource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::Diagnostics::IdleDiskResource::SetupHandle(Microsoft::Diagnostics::IdleDiskResource *this)
{
  unsigned __int16 *v2; // rax
  wchar_t *v3; // rcx
  int v4; // eax
  const WCHAR *v5; // rcx
  char *FileW; // rbx
  const char *v7; // r9
  unsigned int *v8; // rdi
  signed int LastError; // eax
  char v10; // cl
  const struct std::nothrow_t *v11; // rdx
  unsigned int *v12; // rsi
  unsigned int *v13; // rcx
  const char *v14; // r9
  unsigned int i; // ebx
  wchar_t *v16; // rax
  int v17; // eax
  const WCHAR *v18; // rcx
  const char *v19; // r9
  __int64 v20; // r8
  const wchar_t *v21; // rax
  __int64 v22; // rcx
  int v23; // ecx
  int dwCreationDisposition; // [rsp+20h] [rbp-A9h]
  char *dwCreationDispositiona; // [rsp+20h] [rbp-A9h]
  DWORD BytesReturned; // [rsp+40h] [rbp-89h] BYREF
  LPVOID lpOutBuffer; // [rsp+48h] [rbp-81h] BYREF
  char *v28; // [rsp+50h] [rbp-79h] BYREF
  char *v29; // [rsp+58h] [rbp-71h] BYREF
  LPCWSTR v30[2]; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int64 v31; // [rsp+70h] [rbp-59h]
  unsigned __int64 v32; // [rsp+78h] [rbp-51h]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int64 v34; // [rsp+90h] [rbp-39h]
  unsigned __int64 v35; // [rsp+98h] [rbp-31h]
  _QWORD Src[4]; // [rsp+A0h] [rbp-29h] BYREF
  char v37; // [rsp+C0h] [rbp-9h] BYREF
  const wchar_t *v38; // [rsp+D0h] [rbp+7h]
  int v39; // [rsp+D8h] [rbp+Fh]
  int v40; // [rsp+DCh] [rbp+13h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  Microsoft::Diagnostics::Utils::FileSystem::GetSystemPath(Src);
  std::wstring::wstring(lpFileName, 10, 0);
  v2 = (unsigned __int16 *)Src;
  if ( Src[3] > 7u )
    v2 = (unsigned __int16 *)Src[0];
  v3 = (wchar_t *)lpFileName;
  if ( v35 > 7 )
    v3 = (wchar_t *)lpFileName[0];
  v4 = StringCchPrintfW(v3, (unsigned int)v34, L"\\\\.\\%c:", *v2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
  v5 = (const WCHAR *)lpFileName;
  if ( v35 > 7 )
    v5 = lpFileName[0];
  FileW = (char *)CreateFileW(v5, 0, 3u, 0, 3u, 0, 0);
  v29 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
      v7);
  std::make_unique<unsigned char [0],0>(&lpOutBuffer, 32);
  BytesReturned = 0;
  v8 = (unsigned int *)lpOutBuffer;
  if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, lpOutBuffer, 0x20u, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 122 || (v10 = 1, LastError == 234) )
      v10 = 0;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        (const char *)(unsigned int)LastError,
        (int)dwCreationDispositiona);
    v12 = (unsigned int *)operator new[](BytesReturned);
    v13 = v8;
    v8 = v12;
    lpOutBuffer = v12;
    if ( v13 )
      operator delete(v13, v11);
    if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, v12, BytesReturned, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        v14);
  }
  for ( i = 0; i < *v8; ++i )
  {
    std::wstring::wstring(v30, 260, 0);
    v16 = (wchar_t *)v30;
    if ( v32 > 7 )
      v16 = (wchar_t *)v30[0];
    v17 = StringCchPrintfW(v16, (unsigned int)v31, L"\\\\.\\PhysicalDrive%u", v8[6 * i + 2]);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        (const char *)(unsigned int)v17,
        (int)dwCreationDispositiona);
    v18 = (const WCHAR *)v30;
    if ( v32 > 7 )
      v18 = v30[0];
    v28 = (char *)CreateFileW(v18, 0, 3u, 0, 3u, 0, 0);
    if ( (unsigned __int64)(v28 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\idlediskresource.cpp",
        v19);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
      (char *)this + 56,
      &v28);
    if ( (Microsoft_Windows_Diagnostics_PerfTrackEnableBits & 8) != 0 )
    {
      v21 = (const wchar_t *)v30;
      if ( v32 > 7 )
        v21 = v30[0];
      if ( v21 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v21[v22] );
        v23 = 2 * v22 + 2;
      }
      else
      {
        v21 = L"NULL";
        v23 = 10;
      }
      v38 = v21;
      v39 = v23;
      v40 = 0;
      dwCreationDispositiona = &v37;
      McGenEventWrite_EventWriteTransfer(&PerfTrackScenarioProvider_Context, &IdleDetection_Disk_OpenedDisk, v20, 2);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v30);
  }
  std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpOutBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
}

```

## disassembly

```asm
0x18009b5b0  push    rbp
0x18009b5b2  push    rbx
0x18009b5b3  push    rsi
0x18009b5b4  push    rdi
0x18009b5b5  push    r14
0x18009b5b7  push    r15
0x18009b5b9  lea     rbp, [rsp-2Fh]
0x18009b5be  sub     rsp, 0F8h
0x18009b5c5  mov     rax, cs:__security_cookie
0x18009b5cc  xor     rax, rsp
0x18009b5cf  mov     [rbp+57h+var_40], rax
0x18009b5d3  mov     r14, rcx
0x18009b5d6  lea     rcx, [rbp+57h+Src]; Src
0x18009b5da  call    ?GetSystemPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetSystemPath(void)
0x18009b5df  nop
0x18009b5e0  xor     r8d, r8d
0x18009b5e3  lea     edx, [r8+0Ah]
0x18009b5e7  lea     rcx, [rbp+57h+lpFileName]
0x18009b5eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18009b5f0  nop
0x18009b5f1  lea     rax, [rbp+57h+Src]
0x18009b5f5  cmp     [rbp+57h+var_68], 7
0x18009b5fa  cmova   rax, [rbp+57h+Src]
0x18009b5ff  movzx   r9d, word ptr [rax]
0x18009b603  mov     edx, dword ptr [rbp+57h+var_90]; unsigned __int64
0x18009b606  lea     rcx, [rbp+57h+lpFileName]
0x18009b60a  cmp     [rbp+57h+var_88], 7
0x18009b60f  cmova   rcx, [rbp+57h+lpFileName]; wchar_t *
0x18009b614  lea     r8, aC; "\\\\.\\%c:"
0x18009b61b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009b620  mov     rcx, [rbp+5Fh]; this
0x18009b624  xor     r15d, r15d
0x18009b627  test    eax, eax
0x18009b629  jns     short loc_18009B63F
0x18009b62b  mov     r9d, eax; char *
0x18009b62e  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x18009b635  lea     edx, [r15+27h]; void *
0x18009b639  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b63f  lea     rcx, [rbp+57h+lpFileName]
0x18009b643  cmp     [rbp+57h+var_88], 7
0x18009b648  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18009b64d  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x18009b652  mov     [rsp+120h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18009b657  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18009b65f  xor     r9d, r9d; lpSecurityAttributes
0x18009b662  xor     edx, edx; dwDesiredAccess
0x18009b664  lea     r8d, [r9+3]; dwShareMode
0x18009b668  call    cs:__imp_CreateFileW
0x18009b66f  nop     dword ptr [rax+rax+00h]
0x18009b674  mov     rbx, rax
0x18009b677  mov     [rbp+57h+var_C8], rax
0x18009b67b  dec     rax
0x18009b67e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009b682  setnbe  al
0x18009b685  mov     rcx, [rbp+5Fh]; this
0x18009b689  test    al, al
0x18009b68b  jz      short loc_18009B69F
0x18009b68d  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x18009b694  mov     edx, 2Bh ; '+'; void *
0x18009b699  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b69f  mov     edi, 20h ; ' '
0x18009b6a4  mov     edx, edi
0x18009b6a6  lea     rcx, [rsp+120h+lpOutBuffer]
0x18009b6ab  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18009b6b0  nop
0x18009b6b1  mov     [rsp+120h+BytesReturned], r15d
0x18009b6b6  mov     [rsp+120h+lpOverlapped], r15; lpOverlapped
0x18009b6bb  lea     rax, [rsp+120h+BytesReturned]
0x18009b6c0  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x18009b6c5  mov     [rsp+120h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18009b6c9  mov     rdi, [rsp+120h+lpOutBuffer]
0x18009b6ce  mov     qword ptr [rsp+120h+dwCreationDisposition], rdi; int
0x18009b6d3  xor     r9d, r9d; nInBufferSize
0x18009b6d6  xor     r8d, r8d; lpInBuffer
0x18009b6d9  mov     edx, 560000h; dwIoControlCode
0x18009b6de  mov     rcx, rbx; hDevice
0x18009b6e1  call    cs:__imp_DeviceIoControl
0x18009b6e8  nop     dword ptr [rax+rax+00h]
0x18009b6ed  test    eax, eax
0x18009b6ef  jnz     loc_18009B7AD
0x18009b6f5  call    cs:__imp_GetLastError
0x18009b6fc  nop     dword ptr [rax+rax+00h]
0x18009b701  cmp     eax, 7Ah ; 'z'
0x18009b704  jz      short loc_18009B70F
0x18009b706  cmp     eax, 0EAh
0x18009b70b  mov     cl, 1
0x18009b70d  jnz     short loc_18009B712
0x18009b70f  mov     cl, r15b
0x18009b712  test    eax, eax
0x18009b714  jle     short loc_18009B71E
0x18009b716  movzx   eax, ax
0x18009b719  or      eax, 80070000h
0x18009b71e  mov     r10, [rbp+5Fh]
0x18009b722  test    cl, cl
0x18009b724  jz      short loc_18009B73E
0x18009b726  mov     r9d, eax; char *
0x18009b729  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x18009b730  mov     edx, 33h ; '3'; void *
0x18009b735  mov     rcx, r10; this
0x18009b738  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b73e  mov     ecx, [rsp+120h+BytesReturned]; unsigned __int64
0x18009b742  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009b747  mov     rsi, rax
0x18009b74a  mov     rcx, rdi; void *
0x18009b74d  mov     rdi, rax
0x18009b750  mov     [rsp+120h+lpOutBuffer], rax
0x18009b755  test    rcx, rcx
0x18009b758  jz      short loc_18009B75F
0x18009b75a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009b75f  mov     ecx, [rsp+120h+BytesReturned]
0x18009b763  mov     [rsp+120h+lpOverlapped], r15; lpOverlapped
0x18009b768  lea     rax, [rsp+120h+BytesReturned]
0x18009b76d  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x18009b772  mov     [rsp+120h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x18009b776  mov     qword ptr [rsp+120h+dwCreationDisposition], rsi; lpOutBuffer
0x18009b77b  xor     r9d, r9d; nInBufferSize
0x18009b77e  xor     r8d, r8d; lpInBuffer
0x18009b781  mov     edx, 560000h; dwIoControlCode
0x18009b786  mov     rcx, rbx; hDevice
0x18009b789  call    cs:__imp_DeviceIoControl
0x18009b790  nop     dword ptr [rax+rax+00h]
0x18009b795  test    eax, eax
0x18009b797  jnz     short loc_18009B7AD
0x18009b799  mov     rcx, [rbp+5Fh]; this
0x18009b79d  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x18009b7a4  lea     edx, [rax+39h]; void *
0x18009b7a7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b7ad  mov     ebx, r15d
0x18009b7b0  cmp     [rdi], r15d
0x18009b7b3  jbe     loc_18009B8E8
0x18009b7b9  xor     r8d, r8d
0x18009b7bc  mov     edx, 104h
0x18009b7c1  lea     rcx, [rbp+57h+var_C0]
0x18009b7c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18009b7ca  nop
0x18009b7cb  mov     eax, ebx
0x18009b7cd  lea     rcx, [rax+rax*2]
0x18009b7d1  mov     edx, dword ptr [rbp+57h+var_B0]; unsigned __int64
0x18009b7d4  lea     rax, [rbp+57h+var_C0]
0x18009b7d8  cmp     [rbp+57h+var_A8], 7
0x18009b7dd  cmova   rax, [rbp+57h+var_C0]
0x18009b7e2  mov     r9d, [rdi+rcx*8+8]
0x18009b7e7  lea     r8, aPhysicaldriveU; "\\\\.\\PhysicalDrive%u"
0x18009b7ee  mov     rcx, rax; wchar_t *
0x18009b7f1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009b7f6  mov     rcx, [rbp+5Fh]; this
0x18009b7fa  test    eax, eax
0x18009b7fc  js      loc_18009B93F
0x18009b802  lea     rcx, [rbp+57h+var_C0]
0x18009b806  cmp     [rbp+57h+var_A8], 7
0x18009b80b  cmova   rcx, [rbp+57h+var_C0]; lpFileName
0x18009b810  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x18009b815  mov     [rsp+120h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18009b81a  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18009b822  xor     r9d, r9d; lpSecurityAttributes
0x18009b825  xor     edx, edx; dwDesiredAccess
0x18009b827  lea     r8d, [r9+3]; dwShareMode
0x18009b82b  call    cs:__imp_CreateFileW
0x18009b832  nop     dword ptr [rax+rax+00h]
0x18009b837  mov     [rbp+57h+var_D0], rax
0x18009b83b  dec     rax
0x18009b83e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009b842  setnbe  al
0x18009b845  mov     rcx, [rbp+5Fh]; this
0x18009b849  test    al, al
0x18009b84b  jnz     loc_18009B92D
0x18009b851  lea     rcx, [r14+38h]
0x18009b855  lea     rdx, [rbp+57h+var_D0]
0x18009b859  call    ??$_Emplace_one_at_back@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace_one_at_back<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18009b85e  test    cs:Microsoft_Windows_Diagnostics_PerfTrackEnableBits, 8
0x18009b865  jz      short loc_18009B8CB
0x18009b867  lea     rax, [rbp+57h+var_C0]
0x18009b86b  cmp     [rbp+57h+var_A8], 7
0x18009b870  cmova   rax, [rbp+57h+var_C0]
0x18009b875  test    rax, rax
0x18009b878  jz      short loc_18009B891
0x18009b87a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009b87e  inc     rcx
0x18009b881  cmp     [rax+rcx*2], r15w
0x18009b886  jnz     short loc_18009B87E
0x18009b888  lea     ecx, ds:2[rcx*2]
0x18009b88f  jmp     short loc_18009B89D
0x18009b891  lea     rax, aNull_1; "NULL"
0x18009b898  mov     ecx, 0Ah
0x18009b89d  mov     [rbp+57h+var_50], rax
0x18009b8a1  mov     [rbp+57h+var_48], ecx
0x18009b8a4  mov     [rbp+57h+var_44], r15d
0x18009b8a8  lea     rax, [rbp+57h+var_60]
0x18009b8ac  mov     qword ptr [rsp+120h+dwCreationDisposition], rax
0x18009b8b1  mov     r9d, 2
0x18009b8b7  lea     rdx, IdleDetection_Disk_OpenedDisk
0x18009b8be  lea     rcx, PerfTrackScenarioProvider_Context
0x18009b8c5  call    McGenEventWrite_EventWriteTransfer
0x18009b8ca  nop
0x18009b8cb  lea     rcx, [rbp+57h+var_D0]
0x18009b8cf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009b8d4  nop
0x18009b8d5  lea     rcx, [rbp+57h+var_C0]; this
0x18009b8d9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009b8de  inc     ebx
0x18009b8e0  cmp     ebx, [rdi]
0x18009b8e2  jb      loc_18009B7B9
0x18009b8e8  lea     rcx, [rsp+120h+lpOutBuffer]
0x18009b8ed  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18009b8f2  nop
0x18009b8f3  lea     rcx, [rbp+57h+var_C8]
0x18009b8f7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009b8fc  nop
0x18009b8fd  lea     rcx, [rbp+57h+lpFileName]; this
0x18009b901  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009b906  nop
0x18009b907  lea     rcx, [rbp+57h+Src]; this
0x18009b90b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18009b910  mov     rcx, [rbp+57h+var_40]
0x18009b914  xor     rcx, rsp; StackCookie
0x18009b917  call    __security_check_cookie
0x18009b91c  add     rsp, 0F8h
0x18009b923  pop     r15
0x18009b925  pop     r14
0x18009b927  pop     rdi
0x18009b928  pop     rsi
0x18009b929  pop     rbx
0x18009b92a  pop     rbp
0x18009b92b  retn
0x18009b92d  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x18009b934  mov     edx, 47h ; 'G'; void *
0x18009b939  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009b93f  mov     r9d, eax; char *
0x18009b942  lea     r8, aOnecoreBaseTel_13; "onecore\\base\\telemetry\\utc\\service"...
0x18009b949  mov     edx, 43h ; 'C'; void *
0x18009b94e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
