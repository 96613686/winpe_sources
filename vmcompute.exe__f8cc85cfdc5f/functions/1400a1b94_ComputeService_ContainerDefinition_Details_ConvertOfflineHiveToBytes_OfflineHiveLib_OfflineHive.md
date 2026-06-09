# ComputeService::ContainerDefinition::Details::ConvertOfflineHiveToBytes(OfflineHiveLib::OfflineHive &)

- ea: `0x1400a1b94`
- end: `0x1400a1dc5`
- name: `?ConvertOfflineHiveToBytes@Details@ContainerDefinition@ComputeService@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEAUOfflineHive@OfflineHiveLib@@@Z`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1400a2114`
- `0x140131efc`

## callees

- `0x140017040`
- `0x140024030`
- `0x1400421f0`
- `0x140042d50`
- `0x140080180`
- `0x1400a1b94`
- `0x1400a1dcc`
- `0x1400a1df8`
- `0x1400aaf6c`
- `0x1401332f0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1400a1c1b`
- `RPCRT4!UuidCreate` at `0x1400a1c1b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400a1ca6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400a1ca6`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a1cf2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1400a1cf2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400a1d58`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400a1d58`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1400a1bdf`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1400a1bdf`

## string_xrefs

- `0x1400a1bef`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a1cd1`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a1d09`: `onecore\vm\compute\shared\container\registrychanges.cpp`
- `0x1400a1d6f`: `onecore\vm\compute\shared\container\registrychanges.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComputeService::ContainerDefinition::Details::ConvertOfflineHiveToBytes(__int64 a1, const WCHAR *a2)
{
  const char *v4; // r9
  const WCHAR *v5; // r8
  const WCHAR *v6; // rcx
  HANDLE FileW; // rbx
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v13; // [rsp+60h] [rbp-A0h]
  UUID v14; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR pszMore[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v13 = a1;
  if ( !GetTempPathW(0x104u, Buffer) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
      v4);
  std::wstring::wstring(pszMore);
  Uuid = 0;
  UuidCreate(&Uuid);
  v14 = Uuid;
  Vml::VmGuid::ToString(&v14, pszMore, 0);
  v5 = (const WCHAR *)pszMore;
  if ( pszMore[3] > (PCWSTR)7 )
    v5 = pszMore[0];
  CommonUtilities::CombineFilePath((PWSTR)lpFileName, Buffer, v5);
  OfflineHiveLib::OfflineHive::Flush(a2);
  v6 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v6 = lpFileName[0];
  FileW = CreateFileW(v6, 0x80000000, 5u, 0, 3u, 0xC000000u, 0);
  *(_QWORD *)&Uuid.Data1 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
      v8);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
      v9);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  ((void (__fastcall *)(_QWORD, _QWORD))std::vector<unsigned char>::vector<unsigned char>)(
    a1,
    (union _LARGE_INTEGER)FileSize.QuadPart);
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, *(LPVOID *)a1, *(_DWORD *)(a1 + 8) - *(_DWORD *)a1, &NumberOfBytesRead, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\vm\\compute\\shared\\container\\registrychanges.cpp",
      v10);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Uuid);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszMore);
  return a1;
}

```

## disassembly

```asm
0x1400a1b94  mov     [rsp-8+arg_10], rbx
0x1400a1b99  push    rbp
0x1400a1b9a  push    rsi
0x1400a1b9b  push    rdi
0x1400a1b9c  lea     rbp, [rsp-1F0h]
0x1400a1ba4  sub     rsp, 2F0h
0x1400a1bab  mov     rax, cs:__security_cookie
0x1400a1bb2  xor     rax, rsp
0x1400a1bb5  mov     [rbp+200h+var_20], rax
0x1400a1bbc  mov     rsi, rdx
0x1400a1bbf  mov     rdi, rcx
0x1400a1bc2  mov     [rsp+300h+var_2A0], rcx
0x1400a1bc7  mov     [rsp+300h+var_2C0], 0
0x1400a1bcf  mov     rbx, [rbp+208h]
0x1400a1bd6  lea     rdx, [rbp+200h+Buffer]; lpBuffer
0x1400a1bda  mov     ecx, 104h; nBufferLength
0x1400a1bdf  call    cs:__imp_GetTempPathW
0x1400a1be6  nop     dword ptr [rax+rax+00h]
0x1400a1beb  test    eax, eax
0x1400a1bed  jnz     short loc_1400A1C04
0x1400a1bef  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a1bf6  mov     edx, 0A5h; void *
0x1400a1bfb  mov     rcx, rbx; this
0x1400a1bfe  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a1c04  lea     rcx, [rbp+200h+pszMore]; void *
0x1400a1c08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400a1c0d  nop
0x1400a1c0e  xorps   xmm0, xmm0
0x1400a1c11  movups  xmmword ptr [rsp+300h+Uuid.Data1], xmm0
0x1400a1c16  lea     rcx, [rsp+300h+Uuid]; Uuid
0x1400a1c1b  call    cs:__imp_UuidCreate
0x1400a1c22  nop     dword ptr [rax+rax+00h]
0x1400a1c27  movaps  xmm0, xmmword ptr [rsp+300h+Uuid.Data1]
0x1400a1c2c  movdqa  [rsp+300h+var_290], xmm0
0x1400a1c32  xor     r8d, r8d
0x1400a1c35  lea     rdx, [rbp+200h+pszMore]
0x1400a1c39  lea     rcx, [rsp+300h+var_290]
0x1400a1c3e  call    ?ToString@VmGuid@Vml@@SAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Vml::VmGuid::ToString(_GUID const &,std::wstring &,int)
0x1400a1c43  lea     r8, [rbp+200h+pszMore]
0x1400a1c47  cmp     [rbp+200h+var_238], 7
0x1400a1c4c  cmova   r8, [rbp+200h+pszMore]; pszMore
0x1400a1c51  lea     rdx, [rbp+200h+Buffer]; pszPathIn
0x1400a1c55  lea     rcx, [rbp+200h+lpFileName]; pszPathOut
0x1400a1c59  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400a1c5e  mov     [rsp+300h+var_2C0], 2
0x1400a1c66  lea     rdx, [rbp+200h+lpFileName]
0x1400a1c6a  mov     rcx, rsi; lpFileName
0x1400a1c6d  call    ?Flush@OfflineHive@OfflineHiveLib@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; OfflineHiveLib::OfflineHive::Flush(std::wstring const &)
0x1400a1c72  lea     rcx, [rbp+200h+lpFileName]
0x1400a1c76  cmp     [rbp+200h+var_258], 7
0x1400a1c7b  cmova   rcx, [rbp+200h+lpFileName]; lpFileName
0x1400a1c80  mov     [rsp+300h+hTemplateFile], 0; hTemplateFile
0x1400a1c89  mov     [rsp+300h+dwFlagsAndAttributes], 0C000000h; dwFlagsAndAttributes
0x1400a1c91  mov     esi, 3
0x1400a1c96  mov     [rsp+300h+dwCreationDisposition], esi; dwCreationDisposition
0x1400a1c9a  xor     r9d, r9d; lpSecurityAttributes
0x1400a1c9d  mov     edx, 80000000h; dwDesiredAccess
0x1400a1ca2  lea     r8d, [rsi+2]; dwShareMode
0x1400a1ca6  call    cs:__imp_CreateFileW
0x1400a1cad  nop     dword ptr [rax+rax+00h]
0x1400a1cb2  mov     rbx, rax
0x1400a1cb5  mov     qword ptr [rsp+300h+Uuid.Data1], rax
0x1400a1cba  inc     rax
0x1400a1cbd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400a1cc3  setz    al
0x1400a1cc6  mov     rcx, [rbp+208h]; this
0x1400a1ccd  test    al, al
0x1400a1ccf  jz      short loc_1400A1CE3
0x1400a1cd1  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a1cd8  mov     edx, 0B0h; void *
0x1400a1cdd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a1ce3  mov     qword ptr [rbp+200h+FileSize], 0
0x1400a1ceb  lea     rdx, [rbp+200h+FileSize]; lpFileSize
0x1400a1cef  mov     rcx, rbx; hFile
0x1400a1cf2  call    cs:__imp_GetFileSizeEx
0x1400a1cf9  nop     dword ptr [rax+rax+00h]
0x1400a1cfe  mov     rcx, [rbp+208h]; this
0x1400a1d05  test    eax, eax
0x1400a1d07  jnz     short loc_1400A1D1B
0x1400a1d09  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a1d10  mov     edx, 0B3h; void *
0x1400a1d15  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a1d1b  xorps   xmm0, xmm0
0x1400a1d1e  xor     eax, eax
0x1400a1d20  movups  xmmword ptr [rdi], xmm0
0x1400a1d23  mov     [rdi+10h], rax
0x1400a1d27  mov     rdx, qword ptr [rbp+200h+FileSize]
0x1400a1d2b  mov     rcx, rdi
0x1400a1d2e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1400a1d33  mov     [rsp+300h+var_2C0], esi
0x1400a1d37  mov     [rbp+200h+NumberOfBytesRead], 0
0x1400a1d3e  mov     r8d, [rdi+8]
0x1400a1d42  sub     r8d, [rdi]; nNumberOfBytesToRead
0x1400a1d45  mov     qword ptr [rsp+300h+dwCreationDisposition], 0; lpOverlapped
0x1400a1d4e  lea     r9, [rbp+200h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400a1d52  mov     rdx, [rdi]; lpBuffer
0x1400a1d55  mov     rcx, rbx; hFile
0x1400a1d58  call    cs:__imp_ReadFile
0x1400a1d5f  nop     dword ptr [rax+rax+00h]
0x1400a1d64  mov     rcx, [rbp+208h]; this
0x1400a1d6b  test    eax, eax
0x1400a1d6d  jnz     short loc_1400A1D81
0x1400a1d6f  lea     r8, aOnecoreVmCompu_119; "onecore\\vm\\compute\\shared\\container"...
0x1400a1d76  mov     edx, 0B7h; void *
0x1400a1d7b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a1d81  lea     rcx, [rsp+300h+Uuid]; void *
0x1400a1d86  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400a1d8b  nop
0x1400a1d8c  lea     rcx, [rbp+200h+lpFileName]; this
0x1400a1d90  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400a1d95  nop
0x1400a1d96  lea     rcx, [rbp+200h+pszMore]; this
0x1400a1d9a  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400a1d9f  mov     rax, rdi
0x1400a1da2  mov     rcx, [rbp+200h+var_20]
0x1400a1da9  xor     rcx, rsp; StackCookie
0x1400a1dac  call    __security_check_cookie
0x1400a1db1  mov     rbx, [rsp+300h+arg_10]
0x1400a1db9  add     rsp, 2F0h
0x1400a1dc0  pop     rdi
0x1400a1dc1  pop     rsi
0x1400a1dc2  pop     rbp
0x1400a1dc3  retn
```
