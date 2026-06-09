# UpdateHandler::RemoteUHProcessHostWrapper::ShutdownDynamicCOMServer(void)

- ea: `0x180036620`
- end: `0x1800367d4`
- name: `?ShutdownDynamicCOMServer@RemoteUHProcessHostWrapper@UpdateHandler@@AEAAJXZ`
- size: `436`
- prototype: `__int64 __fastcall(UpdateHandler::RemoteUHProcessHostWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003583c`

## callees

- `0x180003950`
- `0x18000c0b4`
- `0x18000e74c`
- `0x1800311f4`
- `0x180036620`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800366e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800366e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800366d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003679b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800367af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003679b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800367af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036716`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036676`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036716`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800366ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003674d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800366ad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003674d`

## string_xrefs

- `0x180036668`: `Software\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UpdateHandler::RemoteUHProcessHostWrapper::ShutdownDynamicCOMServer(
        UpdateHandler::RemoteUHProcessHostWrapper *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // r8d
  HKEY v5; // rsi
  DWORD LastError; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // edx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*((_BYTE *)this + 144) )
    return 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20006u, &hKey);
  if ( v2 >= 0 )
  {
    v3 = RegDeleteKeyExW(hKey, (LPCWSTR)this + 73, 0, 0);
    if ( v3 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x236, v4, (const char *)v3, phkResult);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
  }
  v5 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v5);
    SetLastError(LastError);
  }
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0, 0x20006u, &hKey);
  if ( v7 >= 0 )
  {
    v9 = RegDeleteKeyExW(hKey, (LPCWSTR)this + 120, 0, 0);
    if ( v9 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x23F, v10, (const char *)v9, phkResulta);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v7,
      phkResulta);
  }
  v11 = CWuaClassFactoryBase::UnregisterClassFactory(this, v8);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x242,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
    (const char *)(unsigned int)v11,
    phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x180036620  mov     r11, rsp
0x180036623  mov     [r11+10h], rbx
0x180036627  mov     [r11+18h], rsi
0x18003662b  push    rdi
0x18003662c  sub     rsp, 40h
0x180036630  mov     rax, cs:__security_cookie
0x180036637  xor     rax, rsp
0x18003663a  mov     [rsp+48h+var_10], rax
0x18003663f  mov     rdi, rcx
0x180036642  cmp     byte ptr [rcx+90h], 0
0x180036649  jz      loc_1800367B5
0x18003664f  mov     qword ptr [r11-18h], 0
0x180036657  lea     rax, [r11-18h]
0x18003665b  mov     [r11-28h], rax
0x18003665f  mov     r9d, 20006h; samDesired
0x180036665  xor     r8d, r8d; ulOptions
0x180036668  lea     rdx, ?c_szDynamicCLSIDKey@@3QB_WB; "Software\\Classes\\CLSID"
0x18003666f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036676  call    cs:__imp_RegOpenKeyExW
0x18003667c  mov     rcx, [rsp+48h]; this
0x180036681  test    eax, eax
0x180036683  jns     short loc_18003669B
0x180036685  mov     r9d, eax; char *
0x180036688  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003668f  mov     edx, 234h; void *
0x180036694  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036699  jmp     short loc_1800366C9
0x18003669b  lea     rdx, [rdi+92h]; lpSubKey
0x1800366a2  xor     r9d, r9d; Reserved
0x1800366a5  xor     r8d, r8d; samDesired
0x1800366a8  mov     rcx, [rsp+48h+hKey]; hKey
0x1800366ad  call    cs:__imp_RegDeleteKeyExW
0x1800366b3  mov     rcx, [rsp+48h]; this
0x1800366b8  test    eax, eax
0x1800366ba  jz      short loc_1800366C9
0x1800366bc  mov     r9d, eax; char *
0x1800366bf  mov     edx, 236h; void *
0x1800366c4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800366c9  mov     rsi, [rsp+48h+hKey]
0x1800366ce  test    rsi, rsi
0x1800366d1  jz      short loc_1800366EC
0x1800366d3  call    cs:__imp_GetLastError
0x1800366d9  mov     ebx, eax
0x1800366db  mov     rcx, rsi; hKey
0x1800366de  call    cs:__imp_RegCloseKey
0x1800366e4  mov     ecx, ebx; dwErrCode
0x1800366e6  call    cs:__imp_SetLastError
0x1800366ec  mov     [rsp+48h+hKey], 0
0x1800366f5  lea     rax, [rsp+48h+hKey]
0x1800366fa  mov     qword ptr [rsp+48h+phkResult], rax; int
0x1800366ff  mov     r9d, 20006h; samDesired
0x180036705  xor     r8d, r8d; ulOptions
0x180036708  lea     rdx, ?c_szDynamicAppIDKey@@3QB_WB; "Software\\Classes\\AppID"
0x18003670f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036716  call    cs:__imp_RegOpenKeyExW
0x18003671c  mov     rcx, [rsp+48h]; this
0x180036721  test    eax, eax
0x180036723  jns     short loc_18003673B
0x180036725  mov     r9d, eax; char *
0x180036728  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003672f  mov     edx, 23Dh; void *
0x180036734  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036739  jmp     short loc_180036769
0x18003673b  lea     rdx, [rdi+0F0h]; lpSubKey
0x180036742  xor     r9d, r9d; Reserved
0x180036745  xor     r8d, r8d; samDesired
0x180036748  mov     rcx, [rsp+48h+hKey]; hKey
0x18003674d  call    cs:__imp_RegDeleteKeyExW
0x180036753  mov     rcx, [rsp+48h]; this
0x180036758  test    eax, eax
0x18003675a  jz      short loc_180036769
0x18003675c  mov     r9d, eax; char *
0x18003675f  mov     edx, 23Fh; void *
0x180036764  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180036769  mov     rcx, rdi; this
0x18003676c  call    ?UnregisterClassFactory@CWuaClassFactoryBase@@QEAAJK@Z; CWuaClassFactoryBase::UnregisterClassFactory(ulong)
0x180036771  mov     ebx, eax
0x180036773  test    eax, eax
0x180036775  jns     short loc_1800367A5
0x180036777  mov     rcx, [rsp+48h]; this
0x18003677c  mov     r9d, eax; char *
0x18003677f  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180036786  mov     edx, 242h; void *
0x18003678b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036790  nop
0x180036791  mov     rcx, [rsp+48h+hKey]; hKey
0x180036796  test    rcx, rcx
0x180036799  jz      short loc_1800367A1
0x18003679b  call    cs:__imp_RegCloseKey
0x1800367a1  mov     eax, ebx
0x1800367a3  jmp     short loc_1800367B7
0x1800367a5  mov     rcx, [rsp+48h+hKey]; hKey
0x1800367aa  test    rcx, rcx
0x1800367ad  jz      short loc_1800367B5
0x1800367af  call    cs:__imp_RegCloseKey
0x1800367b5  xor     eax, eax
0x1800367b7  mov     rcx, [rsp+48h+var_10]
0x1800367bc  xor     rcx, rsp; StackCookie
0x1800367bf  call    __security_check_cookie
0x1800367c4  mov     rbx, [rsp+48h+arg_8]
0x1800367c9  mov     rsi, [rsp+48h+arg_10]
0x1800367ce  add     rsp, 40h
0x1800367d2  pop     rdi
0x1800367d3  retn
```
