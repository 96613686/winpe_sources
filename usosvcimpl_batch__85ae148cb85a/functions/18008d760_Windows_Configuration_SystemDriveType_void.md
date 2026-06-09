# Windows::Configuration::SystemDriveType(void)

- ea: `0x18008d760`
- end: `0x18008d925`
- name: `?SystemDriveType@Configuration@Windows@@UEAA?AW4DriveType@1SystemInterface@@XZ`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180010f24`
- `0x180011680`
- `0x18001c6b4`
- `0x18002b918`
- `0x18002dedc`
- `0x18008d760`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008d8db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008d8db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008d7ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008d7ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008d849`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008d849`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008d89a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008d89a`

## string_xrefs

- `0x18008d8ab`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`
- `0x18008d910`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Configuration::SystemDriveType()
{
  unsigned int v0; // edi
  const char *v1; // r9
  WCHAR v2; // bx
  const WCHAR *v3; // rcx
  char *FileW; // rbx
  const char *v5; // r9
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v8; // [rsp+58h] [rbp-A8h]
  __int64 v9; // [rsp+60h] [rbp-A0h]
  __int64 *v10; // [rsp+68h] [rbp-98h]
  DWORD BytesReturned; // [rsp+70h] [rbp-90h] BYREF
  int InBuffer; // [rsp+78h] [rbp-88h] BYREF
  __int64 v13; // [rsp+7Ch] [rbp-84h]
  __int64 OutBuffer; // [rsp+88h] [rbp-78h] BYREF
  int v15; // [rsp+90h] [rbp-70h]
  LPCWSTR lpFileName[5]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v0 = 0;
  memset(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x81,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      v1);
  v2 = Buffer[0];
  std::_Format_arg_index::_Format_arg_index((std::_Format_arg_index *)&v7);
  v8 = v2;
  v7 = 0x6000000000000000LL;
  v9 = 1;
  v10 = &v7;
  std::vformat<0>(lpFileName);
  v3 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v3 = lpFileName[0];
  FileW = (char *)CreateFileW(v3, 0, 3u, 0, 3u, 0, 0);
  v13 = 0;
  InBuffer = 7;
  OutBuffer = 0;
  v15 = 0;
  BytesReturned = 0;
  if ( DeviceIoControl(FileW, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0xCu, &BytesReturned, 0) )
  {
    v0 = 1;
    if ( !(_BYTE)v15 )
      v0 = 2;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x9D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      v5);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  std::wstring::~wstring(lpFileName);
  return v0;
}

```

## disassembly

```asm
0x18008d760  mov     [rsp-8+arg_0], rbx
0x18008d765  mov     [rsp-8+arg_8], rdi
0x18008d76a  push    rbp
0x18008d76b  lea     rbp, [rsp-1E0h]
0x18008d773  sub     rsp, 2E0h
0x18008d77a  mov     rax, cs:__security_cookie
0x18008d781  xor     rax, rsp
0x18008d784  mov     [rbp+1E0h+var_10], rax
0x18008d78b  xor     edi, edi
0x18008d78d  xor     edx, edx; Val
0x18008d78f  mov     r8d, 208h; Size
0x18008d795  lea     rcx, [rbp+1E0h+Buffer]; void *
0x18008d799  call    memset
0x18008d79e  mov     rbx, [rbp+1E8h]
0x18008d7a5  mov     edx, 104h; uSize
0x18008d7aa  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x18008d7ae  call    cs:__imp_GetSystemDirectoryW
0x18008d7b4  test    eax, eax
0x18008d7b6  jz      loc_18008D910
0x18008d7bc  movzx   ebx, [rbp+1E0h+Buffer]
0x18008d7c0  lea     rcx, [rsp+2E0h+var_290]; this
0x18008d7c5  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x18008d7ca  mov     [rsp+2E0h+var_288], bx
0x18008d7cf  mov     rax, 6000000000000000h
0x18008d7d9  mov     [rsp+2E0h+var_290], rax
0x18008d7de  lea     rax, asc_180124150; "\\\\.\\{}:"
0x18008d7e5  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x18008d7ea  mov     qword ptr [rsp+2E0h+var_2A0+8], 7
0x18008d7f3  mov     [rsp+2E0h+var_280], 1
0x18008d7fc  lea     rax, [rsp+2E0h+var_290]
0x18008d801  mov     [rsp+2E0h+var_278], rax
0x18008d806  movaps  xmm0, [rsp+2E0h+var_2A0]
0x18008d80b  movdqa  [rsp+2E0h+var_2A0], xmm0
0x18008d811  lea     r8, [rsp+2E0h+var_280]
0x18008d816  lea     rdx, [rsp+2E0h+var_2A0]
0x18008d81b  lea     rcx, [rbp+1E0h+lpFileName]; Src
0x18008d81f  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18008d824  lea     rcx, [rbp+1E0h+lpFileName]
0x18008d828  cmp     [rbp+1E0h+var_230], 7
0x18008d82d  cmova   rcx, [rbp+1E0h+lpFileName]; lpFileName
0x18008d832  mov     [rsp+2E0h+hTemplateFile], rdi; hTemplateFile
0x18008d837  mov     [rsp+2E0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18008d83b  lea     r8d, [rdi+3]; dwShareMode
0x18008d83f  mov     [rsp+2E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18008d844  xor     r9d, r9d; lpSecurityAttributes
0x18008d847  xor     edx, edx; dwDesiredAccess
0x18008d849  call    cs:__imp_CreateFileW
0x18008d84f  mov     rbx, rax
0x18008d852  mov     [rsp+2E0h+var_264], rdi
0x18008d857  mov     [rsp+2E0h+InBuffer], 7
0x18008d85f  xor     eax, eax
0x18008d861  mov     [rbp+1E0h+OutBuffer], rax
0x18008d865  mov     [rbp+1E0h+var_250], eax
0x18008d868  mov     [rsp+2E0h+BytesReturned], edi
0x18008d86c  mov     [rsp+2E0h+lpOverlapped], rdi; lpOverlapped
0x18008d871  lea     rax, [rsp+2E0h+BytesReturned]
0x18008d876  mov     [rsp+2E0h+hTemplateFile], rax; lpBytesReturned
0x18008d87b  lea     r9d, [rdi+0Ch]; nInBufferSize
0x18008d87f  mov     [rsp+2E0h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x18008d884  lea     rax, [rbp+1E0h+OutBuffer]
0x18008d888  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; lpOutBuffer
0x18008d88d  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x18008d892  mov     edx, 2D1400h; dwIoControlCode
0x18008d897  mov     rcx, rbx; hDevice
0x18008d89a  call    cs:__imp_DeviceIoControl
0x18008d8a0  test    eax, eax
0x18008d8a2  jnz     short loc_18008D8BE
0x18008d8a4  mov     rcx, [rbp+1E8h]; this
0x18008d8ab  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008d8b2  mov     edx, 9Dh; void *
0x18008d8b7  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18008d8bc  jmp     short loc_18008D8CE
0x18008d8be  cmp     byte ptr [rbp+1E0h+var_250], dil
0x18008d8c2  mov     edi, 1
0x18008d8c7  jnz     short loc_18008D8CE
0x18008d8c9  mov     edi, 2
0x18008d8ce  lea     rcx, [rbx-1]
0x18008d8d2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18008d8d6  ja      short loc_18008D8E1
0x18008d8d8  mov     rcx, rbx; hObject
0x18008d8db  call    cs:__imp_CloseHandle
0x18008d8e1  lea     rcx, [rbp+1E0h+lpFileName]; void *
0x18008d8e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008d8ea  mov     eax, edi
0x18008d8ec  mov     rcx, [rbp+1E0h+var_10]
0x18008d8f3  xor     rcx, rsp; StackCookie
0x18008d8f6  call    __security_check_cookie
0x18008d8fb  lea     r11, [rsp+2E0h+var_s0]
0x18008d903  mov     rbx, [r11+10h]
0x18008d907  mov     rdi, [r11+18h]
0x18008d90b  mov     rsp, r11
0x18008d90e  pop     rbp
0x18008d90f  retn
0x18008d910  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008d917  mov     edx, 81h; void *
0x18008d91c  mov     rcx, rbx; this
0x18008d91f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
