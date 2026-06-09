# Windows::Registry::VolatileKeyExists(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x1800840a0`
- end: `0x1800842be`
- name: `?VolatileKeyExists@Registry@Windows@@QEAA?AV?$optional@_N@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18006e630`

## callees

- `0x180011680`
- `0x18001be20`
- `0x18001c6b4`
- `0x18002deb8`
- `0x180083c20`
- `0x1800840a0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008415b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008415b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008416e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008416e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008427c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008428c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008427c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008428c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084123`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084123`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800841b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800841b8`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18008423d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18008423d`

## string_xrefs

- `0x180084141`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x1800841da`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18008424e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x1800841ad`: `ToBeDeleted`
- `0x180084204`: `{}\ToBeDeleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Registry::VolatileKeyExists(__int64 a1, __int64 a2, __int64 a3, __int128 *a4, __int128 *a5)
{
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  HKEY v8; // rsi
  DWORD LastError; // ebx
  unsigned int v10; // eax
  __int64 v11; // rax
  const WCHAR *v12; // rdx
  unsigned int v13; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-81h]
  unsigned int phkResulta; // [rsp+20h] [rbp-81h]
  __int128 v17; // [rsp+50h] [rbp-51h] BYREF
  __int128 v18; // [rsp+60h] [rbp-41h] BYREF
  LPCWSTR Src[4]; // [rsp+70h] [rbp-31h] BYREF
  _BYTE v20[24]; // [rsp+90h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+7h] BYREF
  HKEY v22; // [rsp+B0h] [rbp+Fh] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v18 = *a5;
  v17 = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, (__int64)lpSubKey, (const char **)&v17, (__int64)&v18);
  hKey = 0;
  v22 = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20006u, &v22);
  if ( v7 - 2 <= 1 )
  {
    *(_BYTE *)(a2 + 1) = 0;
  }
  else
  {
    if ( v7 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x125,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v7,
        phkResult);
    v8 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v8);
      SetLastError(LastError);
    }
    hKey = 0;
    v10 = RegCreateKeyExW(v22, L"ToBeDeleted", 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v10 == 1021 )
    {
      *(_WORD *)a2 = 257;
    }
    else
    {
      if ( v10 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x138,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
          (const char *)v10,
          phkResulta);
      v11 = std::make_wformat_args<std::wstring>(v20, lpSubKey);
      *(_QWORD *)&v17 = 1;
      *((_QWORD *)&v17 + 1) = v11;
      *(_QWORD *)&v18 = L"{}\\ToBeDeleted";
      *((_QWORD *)&v18 + 1) = 14;
      std::vformat<0>(Src);
      v12 = (const WCHAR *)Src;
      if ( Src[3] > (LPCWSTR)7 )
        v12 = Src[0];
      v13 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v12);
      if ( v13 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x13B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
          (const char *)v13,
          phkResulta);
      std::wstring::~wstring(Src);
      *(_WORD *)a2 = 256;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v22 )
    RegCloseKey(v22);
  std::wstring::~wstring(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x1800840a0  mov     [rsp-8+arg_0], rbx
0x1800840a5  push    rbp
0x1800840a6  push    rsi
0x1800840a7  push    rdi
0x1800840a8  lea     rbp, [rsp-3Fh]
0x1800840ad  sub     rsp, 0E0h
0x1800840b4  mov     rax, cs:__security_cookie
0x1800840bb  xor     rax, rsp
0x1800840be  mov     [rbp+4Fh+var_18], rax
0x1800840c2  mov     rdi, rdx
0x1800840c5  mov     rax, [rbp+4Fh+arg_20]
0x1800840c9  movaps  xmm0, xmmword ptr [rax]
0x1800840cc  movdqa  [rbp+4Fh+var_90], xmm0
0x1800840d1  movaps  xmm1, xmmword ptr [r9]
0x1800840d5  movdqa  [rbp+4Fh+var_A0], xmm1
0x1800840da  lea     r9, [rbp+4Fh+var_90]
0x1800840de  lea     r8, [rbp+4Fh+var_A0]
0x1800840e2  lea     rdx, [rbp+4Fh+lpSubKey]
0x1800840e6  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800840eb  nop
0x1800840ec  mov     [rbp+4Fh+hKey], 0
0x1800840f4  mov     [rbp+4Fh+var_40], 0
0x1800840fc  lea     rdx, [rbp+4Fh+lpSubKey]
0x180084100  cmp     [rbp+4Fh+var_20], 7
0x180084105  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18008410a  lea     rax, [rbp+4Fh+var_40]
0x18008410e  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x180084113  mov     r9d, 20006h; samDesired
0x180084119  xor     r8d, r8d; ulOptions
0x18008411c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084123  call    cs:__imp_RegOpenKeyExW
0x180084129  mov     r9d, eax; char *
0x18008412c  add     eax, 0FFFFFFFEh
0x18008412f  cmp     eax, 1
0x180084132  jbe     loc_18008426F
0x180084138  mov     rcx, [rbp+57h]; this
0x18008413c  test    r9d, r9d
0x18008413f  jz      short loc_180084152
0x180084141  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180084148  mov     edx, 125h; void *
0x18008414d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180084152  mov     rsi, [rbp+4Fh+hKey]
0x180084156  test    rsi, rsi
0x180084159  jz      short loc_180084174
0x18008415b  call    cs:__imp_GetLastError
0x180084161  mov     ebx, eax
0x180084163  mov     rcx, rsi; hKey
0x180084166  call    cs:__imp_RegCloseKey
0x18008416c  mov     ecx, ebx; dwErrCode
0x18008416e  call    cs:__imp_SetLastError
0x180084174  mov     [rbp+4Fh+hKey], 0
0x18008417c  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x180084185  lea     rax, [rbp+4Fh+hKey]
0x180084189  mov     [rsp+0F0h+var_B8], rax; phkResult
0x18008418e  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180084197  mov     [rsp+0F0h+samDesired], 20006h; samDesired
0x18008419f  mov     dword ptr [rsp+0F0h+phkResult], 0; unsigned int
0x1800841a7  xor     r9d, r9d; lpClass
0x1800841aa  xor     r8d, r8d; Reserved
0x1800841ad  lea     rdx, aTobedeleted; "ToBeDeleted"
0x1800841b4  mov     rcx, [rbp+4Fh+var_40]; hKey
0x1800841b8  call    cs:__imp_RegCreateKeyExW
0x1800841be  cmp     eax, 3FDh
0x1800841c3  jnz     short loc_1800841CF
0x1800841c5  mov     word ptr [rdi], 101h
0x1800841ca  jmp     loc_180084273
0x1800841cf  mov     rcx, [rbp+57h]; this
0x1800841d3  test    eax, eax
0x1800841d5  jz      short loc_1800841EB
0x1800841d7  mov     r9d, eax; char *
0x1800841da  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800841e1  mov     edx, 138h; void *
0x1800841e6  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800841eb  lea     rdx, [rbp+4Fh+lpSubKey]
0x1800841ef  lea     rcx, [rbp+4Fh+var_60]
0x1800841f3  call    ??$make_wformat_args@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?A_PAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z
0x1800841f8  mov     qword ptr [rbp+4Fh+var_A0], 1
0x180084200  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x180084204  lea     rax, aTobedeleted_0; "{}\\ToBeDeleted"
0x18008420b  mov     qword ptr [rbp+4Fh+var_90], rax
0x18008420f  mov     qword ptr [rbp+4Fh+var_90+8], 0Eh
0x180084217  lea     r8, [rbp+4Fh+var_A0]
0x18008421b  lea     rdx, [rbp+4Fh+var_90]
0x18008421f  lea     rcx, [rbp+4Fh+Src]; Src
0x180084223  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x180084228  lea     rdx, [rbp+4Fh+Src]
0x18008422c  cmp     [rbp+4Fh+var_68], 7
0x180084231  cmova   rdx, [rbp+4Fh+Src]; lpSubKey
0x180084236  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008423d  call    cs:__imp_RegDeleteKeyW
0x180084243  mov     rcx, [rbp+57h]; this
0x180084247  test    eax, eax
0x180084249  jz      short loc_18008425F
0x18008424b  mov     r9d, eax; char *
0x18008424e  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180084255  mov     edx, 13Bh; void *
0x18008425a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18008425f  lea     rcx, [rbp+4Fh+Src]; void *
0x180084263  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084268  mov     word ptr [rdi], 100h
0x18008426d  jmp     short loc_180084273
0x18008426f  mov     byte ptr [rdi+1], 0
0x180084273  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180084277  test    rcx, rcx
0x18008427a  jz      short loc_180084283
0x18008427c  call    cs:__imp_RegCloseKey
0x180084282  nop
0x180084283  mov     rcx, [rbp+4Fh+var_40]; hKey
0x180084287  test    rcx, rcx
0x18008428a  jz      short loc_180084293
0x18008428c  call    cs:__imp_RegCloseKey
0x180084292  nop
0x180084293  lea     rcx, [rbp+4Fh+lpSubKey]; void *
0x180084297  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008429c  mov     rax, rdi
0x18008429f  mov     rcx, [rbp+4Fh+var_18]
0x1800842a3  xor     rcx, rsp; StackCookie
0x1800842a6  call    __security_check_cookie
0x1800842ab  mov     rbx, [rsp+0F0h+arg_0]
0x1800842b3  add     rsp, 0E0h
0x1800842ba  pop     rdi
0x1800842bb  pop     rsi
0x1800842bc  pop     rbp
0x1800842bd  retn
```
