# StopCoreWorker(void)

- ea: `0x18002f000`
- end: `0x18002f11a`
- name: `?StopCoreWorker@@YAXXZ`
- size: `282`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002faa0`

## callees

- `0x180008ea8`
- `0x18002f000`
- `0x18002fc94`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f0aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f0aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002f097`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18002f097`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f0cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f0cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f0e1`

## string_xrefs

- `0x18002f03a`: `taskkill.exe /f /im mousocoreworker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void StopCoreWorker(void)
{
  unsigned int v0; // r8d
  const char *v1; // r9
  unsigned int v2; // r8d
  const char *v3; // r9
  LPWSTR lpCommandLine; // [rsp+50h] [rbp-49h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-41h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  memset(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  lpCommandLine = 0;
  wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
    &lpCommandLine,
    L"taskkill.exe /f /im mousocoreworker.exe");
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(0, lpCommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    WaitForSingleObject(ProcessInformation.hProcess, 0x2710u);
  if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v0, v1);
  if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v2, v3);
  if ( lpCommandLine )
    CoTaskMemFree(lpCommandLine);
}

```

## disassembly

```asm
0x18002f000  push    rbp
0x18002f002  lea     rbp, [rsp-57h]
0x18002f007  sub     rsp, 0F0h
0x18002f00e  mov     rax, cs:__security_cookie
0x18002f015  xor     rax, rsp
0x18002f018  mov     [rbp+57h+var_10], rax
0x18002f01c  xor     edx, edx; Val
0x18002f01e  lea     r8d, [rdx+64h]; Size
0x18002f022  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18002f026  call    memset
0x18002f02b  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18002f032  mov     [rbp+57h+lpCommandLine], 0
0x18002f03a  lea     rdx, aTaskkillExeFIm; "taskkill.exe /f /im mousocoreworker.exe"
0x18002f041  lea     rcx, [rbp+57h+lpCommandLine]
0x18002f045  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x18002f04a  xorps   xmm0, xmm0
0x18002f04d  xor     eax, eax
0x18002f04f  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18002f053  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18002f057  lea     rax, [rbp+57h+ProcessInformation]
0x18002f05b  mov     [rsp+0F0h+lpProcessInformation], rax; lpProcessInformation
0x18002f060  lea     rax, [rbp+57h+StartupInfo]
0x18002f064  mov     [rsp+0F0h+lpStartupInfo], rax; lpStartupInfo
0x18002f069  mov     [rsp+0F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18002f072  mov     [rsp+0F0h+lpEnvironment], 0; lpEnvironment
0x18002f07b  mov     [rsp+0F0h+dwCreationFlags], 8000000h; dwCreationFlags
0x18002f083  mov     [rsp+0F0h+bInheritHandles], 0; bInheritHandles
0x18002f08b  xor     r9d, r9d; lpThreadAttributes
0x18002f08e  xor     r8d, r8d; lpProcessAttributes
0x18002f091  mov     rdx, [rbp+57h+lpCommandLine]; lpCommandLine
0x18002f095  xor     ecx, ecx; lpApplicationName
0x18002f097  call    cs:__imp_CreateProcessW
0x18002f09d  test    eax, eax
0x18002f09f  jz      short loc_18002F0B0
0x18002f0a1  mov     edx, 2710h; dwMilliseconds
0x18002f0a6  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18002f0aa  call    cs:__imp_WaitForSingleObject
0x18002f0b0  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18002f0b4  test    rcx, rcx
0x18002f0b7  jz      short loc_18002F0C3
0x18002f0b9  call    cs:__imp_CloseHandle
0x18002f0bf  test    eax, eax
0x18002f0c1  jz      short loc_18002F10B
0x18002f0c3  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18002f0c7  test    rcx, rcx
0x18002f0ca  jz      short loc_18002F0D6
0x18002f0cc  call    cs:__imp_CloseHandle
0x18002f0d2  test    eax, eax
0x18002f0d4  jz      short loc_18002F0FC
0x18002f0d6  cmp     [rbp+57h+lpCommandLine], 0
0x18002f0db  jz      short loc_18002F0E7
0x18002f0dd  mov     rcx, [rbp+57h+lpCommandLine]; pv
0x18002f0e1  call    cs:__imp_CoTaskMemFree
0x18002f0e7  mov     rcx, [rbp+57h+var_10]
0x18002f0eb  xor     rcx, rsp; StackCookie
0x18002f0ee  call    __security_check_cookie
0x18002f0f3  add     rsp, 0F0h
0x18002f0fa  pop     rbp
0x18002f0fb  retn
0x18002f0fc  mov     rcx, [rbp+5Fh]; this
0x18002f100  mov     edx, 9D1h; void *
0x18002f105  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f10b  mov     rcx, [rbp+5Fh]; this
0x18002f10f  mov     edx, 9D1h; void *
0x18002f114  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
