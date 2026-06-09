# WerRemoveExcludedApplication

- ea: `0x180062e00`
- end: `0x180062f94`
- name: `WerRemoveExcludedApplication`
- size: `404`
- prototype: `HRESULT __stdcall(PCWSTR pwzExeName, BOOL bAllUsers)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x18001cb20`
- `0x1800201f0`
- `0x180020680`
- `0x18002219c`
- `0x180062e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062efc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180062eab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180062eab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062e8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062e8e`

## pseudocode

```c
HRESULT __stdcall WerRemoveExcludedApplication(PCWSTR pwzExeName, BOOL bAllUsers)
{
  wchar_t *v3; // rcx
  __int64 v4; // rdx
  const wchar_t *v5; // rax
  const WCHAR *v6; // rbx
  HKEY *phkResult; // rax
  DWORD v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  DWORD LastError; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( !pwzExeName )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v4 = 41;
LABEL_21:
    WPP_SF_(*((_QWORD *)v3 + 2), v4, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids);
LABEL_22:
    v9 = -2147024809;
    goto LABEL_23;
  }
  v5 = UtilPathTail(pwzExeName);
  v6 = v5;
  if ( !v5 || !*v5 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v4 = 42;
    goto LABEL_21;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(
         (HKEY)(bAllUsers - 0x7FFFFFFFLL),
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\ExcludedApplications",
         0,
         0x102u,
         phkResult)
    || !hKey )
  {
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 43;
      goto LABEL_17;
    }
  }
  else if ( RegDeleteValueW(hKey, v6) )
  {
    v8 = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 44;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids, v9);
    }
  }
  else
  {
    v9 = 0;
  }
LABEL_23:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x180062e00  mov     [rsp+arg_8], rbx
0x180062e05  mov     [rsp+arg_10], rsi
0x180062e0a  push    rdi
0x180062e0b  sub     rsp, 30h
0x180062e0f  xor     esi, esi
0x180062e11  mov     edi, edx
0x180062e13  mov     [rsp+38h+hKey], rsi
0x180062e18  test    rcx, rcx
0x180062e1b  jnz     short loc_180062E46
0x180062e1d  mov     rcx, cs:WPP_GLOBAL_Control; wchar_t *
0x180062e24  lea     rax, WPP_GLOBAL_Control
0x180062e2b  cmp     rcx, rax
0x180062e2e  jz      loc_180062F72
0x180062e34  test    byte ptr [rcx+1Ch], 1
0x180062e38  jz      loc_180062F72
0x180062e3e  lea     edx, [rsi+29h]
0x180062e41  jmp     loc_180062F62
0x180062e46  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x180062e4b  mov     rbx, rax
0x180062e4e  test    rax, rax
0x180062e51  jz      loc_180062F44
0x180062e57  cmp     [rax], si
0x180062e5a  jz      loc_180062F44
0x180062e60  lea     rcx, [rsp+38h+hKey]
0x180062e65  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180062e6a  neg     edi
0x180062e6c  mov     [rsp+38h+phkResult], rax; phkResult
0x180062e71  mov     r9d, 102h; samDesired
0x180062e77  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\Windows E"...
0x180062e7e  sbb     rcx, rcx
0x180062e81  xor     r8d, r8d; ulOptions
0x180062e84  neg     rcx
0x180062e87  add     rcx, 0FFFFFFFF80000001h; hKey
0x180062e8e  call    cs:__imp_RegOpenKeyExW
0x180062e95  nop     dword ptr [rax+rax+00h]
0x180062e9a  test    eax, eax
0x180062e9c  jnz     short loc_180062EFC
0x180062e9e  mov     rcx, [rsp+38h+hKey]; hKey
0x180062ea3  test    rcx, rcx
0x180062ea6  jz      short loc_180062EFC
0x180062ea8  mov     rdx, rbx; lpValueName
0x180062eab  call    cs:__imp_RegDeleteValueW
0x180062eb2  nop     dword ptr [rax+rax+00h]
0x180062eb7  test    eax, eax
0x180062eb9  jz      short loc_180062EF8
0x180062ebb  call    cs:__imp_GetLastError
0x180062ec2  nop     dword ptr [rax+rax+00h]
0x180062ec7  mov     ecx, eax; unsigned int
0x180062ec9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180062ece  mov     ebx, eax
0x180062ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ed7  lea     rax, WPP_GLOBAL_Control
0x180062ede  cmp     rcx, rax
0x180062ee1  jz      loc_180062F77
0x180062ee7  test    byte ptr [rcx+1Ch], 1
0x180062eeb  jz      loc_180062F77
0x180062ef1  mov     edx, 2Ch ; ','
0x180062ef6  jmp     short loc_180062F2F
0x180062ef8  mov     ebx, esi
0x180062efa  jmp     short loc_180062F77
0x180062efc  call    cs:__imp_GetLastError
0x180062f03  nop     dword ptr [rax+rax+00h]
0x180062f08  mov     ecx, eax; unsigned int
0x180062f0a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180062f0f  mov     ebx, eax
0x180062f11  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f18  lea     rax, WPP_GLOBAL_Control
0x180062f1f  cmp     rcx, rax
0x180062f22  jz      short loc_180062F77
0x180062f24  test    byte ptr [rcx+1Ch], 1
0x180062f28  jz      short loc_180062F77
0x180062f2a  mov     edx, 2Bh ; '+'
0x180062f2f  mov     rcx, [rcx+10h]
0x180062f33  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180062f3a  mov     r9d, ebx
0x180062f3d  call    WPP_SF_d
0x180062f42  jmp     short loc_180062F77
0x180062f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f4b  lea     rax, WPP_GLOBAL_Control
0x180062f52  cmp     rcx, rax
0x180062f55  jz      short loc_180062F72
0x180062f57  test    byte ptr [rcx+1Ch], 1
0x180062f5b  jz      short loc_180062F72
0x180062f5d  mov     edx, 2Ah ; '*'
0x180062f62  mov     rcx, [rcx+10h]
0x180062f66  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180062f6d  call    WPP_SF_
0x180062f72  mov     ebx, 80070057h
0x180062f77  lea     rcx, [rsp+38h+hKey]
0x180062f7c  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180062f81  mov     rsi, [rsp+38h+arg_10]
0x180062f86  mov     eax, ebx
0x180062f88  mov     rbx, [rsp+38h+arg_8]
0x180062f8d  add     rsp, 30h
0x180062f91  pop     rdi
0x180062f92  retn
```
