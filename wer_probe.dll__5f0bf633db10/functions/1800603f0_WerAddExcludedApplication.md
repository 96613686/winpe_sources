# WerAddExcludedApplication

- ea: `0x1800603f0`
- end: `0x18006059f`
- name: `WerAddExcludedApplication`
- size: `431`
- prototype: `HRESULT __stdcall(PCWSTR pwzExeName, BOOL bAllUsers)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18001fe24`
- `0x180021634`
- `0x1800603f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800604d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006050e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800604d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006050e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060494`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060494`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800604c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800604c9`

## pseudocode

```c
HRESULT __stdcall WerAddExcludedApplication(PCWSTR pwzExeName, BOOL bAllUsers)
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
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = 0;
  hKey = 0;
  if ( !pwzExeName )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v4 = 37;
LABEL_21:
    WPP_SF_(*((_QWORD *)v3 + 2), v4, &WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids);
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
    v4 = 38;
    goto LABEL_21;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         (HKEY)(bAllUsers - 0x7FFFFFFFLL),
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\ExcludedApplications",
         0,
         0,
         0,
         0xF013Fu,
         0,
         phkResult,
         0)
    || !hKey )
  {
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 39;
      goto LABEL_17;
    }
  }
  else
  {
    Data = 1;
    if ( RegSetValueExW(hKey, v6, 0, 4u, (const BYTE *)&Data, 4u) )
    {
      v8 = GetLastError();
      v9 = ERROR_HR_FROM_WIN32(v8);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 40;
LABEL_17:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids, v9);
      }
    }
    else
    {
      v9 = 0;
    }
  }
LABEL_23:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x1800603f0  mov     rax, rsp
0x1800603f3  mov     [rax+10h], rbx
0x1800603f7  mov     [rax+20h], rsi
0x1800603fb  push    rdi
0x1800603fc  sub     rsp, 50h
0x180060400  xor     esi, esi
0x180060402  mov     edi, edx
0x180060404  mov     [rax+8], esi
0x180060407  mov     [rax+18h], rsi
0x18006040b  test    rcx, rcx
0x18006040e  jnz     short loc_180060439
0x180060410  mov     rcx, cs:WPP_GLOBAL_Control; wchar_t *
0x180060417  lea     rax, WPP_GLOBAL_Control
0x18006041e  cmp     rcx, rax
0x180060421  jz      loc_18006057E
0x180060427  test    byte ptr [rcx+1Ch], 1
0x18006042b  jz      loc_18006057E
0x180060431  lea     edx, [rsi+25h]
0x180060434  jmp     loc_18006056E
0x180060439  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18006043e  mov     rbx, rax
0x180060441  test    rax, rax
0x180060444  jz      loc_180060550
0x18006044a  cmp     [rax], si
0x18006044d  jz      loc_180060550
0x180060453  lea     rcx, [rsp+58h+hKey]
0x180060458  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18006045d  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x180060462  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\Windows E"...
0x180060469  mov     [rsp+58h+phkResult], rax; phkResult
0x18006046e  neg     edi
0x180060470  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180060475  sbb     rcx, rcx
0x180060478  mov     [rsp+58h+samDesired], 0F013Fh; samDesired
0x180060480  neg     rcx
0x180060483  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180060487  add     rcx, 0FFFFFFFF80000001h; hKey
0x18006048e  xor     r9d, r9d; lpClass
0x180060491  xor     r8d, r8d; Reserved
0x180060494  call    cs:__imp_RegCreateKeyExW
0x18006049a  test    eax, eax
0x18006049c  jnz     short loc_18006050E
0x18006049e  mov     rcx, [rsp+58h+hKey]; hKey
0x1800604a3  test    rcx, rcx
0x1800604a6  jz      short loc_18006050E
0x1800604a8  lea     r9d, [rax+4]; dwType
0x1800604ac  mov     [rsp+58h+Data], 1
0x1800604b4  lea     rax, [rsp+58h+Data]
0x1800604b9  mov     [rsp+58h+samDesired], r9d; cbData
0x1800604be  xor     r8d, r8d; Reserved
0x1800604c1  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800604c6  mov     rdx, rbx; lpValueName
0x1800604c9  call    cs:__imp_RegSetValueExW
0x1800604cf  test    eax, eax
0x1800604d1  jz      short loc_18006050A
0x1800604d3  call    cs:__imp_GetLastError
0x1800604d9  mov     ecx, eax; unsigned int
0x1800604db  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800604e0  mov     ebx, eax
0x1800604e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800604e9  lea     rax, WPP_GLOBAL_Control
0x1800604f0  cmp     rcx, rax
0x1800604f3  jz      loc_180060583
0x1800604f9  test    byte ptr [rcx+1Ch], 1
0x1800604fd  jz      loc_180060583
0x180060503  mov     edx, 28h ; '('
0x180060508  jmp     short loc_18006053B
0x18006050a  mov     ebx, esi
0x18006050c  jmp     short loc_180060583
0x18006050e  call    cs:__imp_GetLastError
0x180060514  mov     ecx, eax; unsigned int
0x180060516  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006051b  mov     ebx, eax
0x18006051d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060524  lea     rax, WPP_GLOBAL_Control
0x18006052b  cmp     rcx, rax
0x18006052e  jz      short loc_180060583
0x180060530  test    byte ptr [rcx+1Ch], 1
0x180060534  jz      short loc_180060583
0x180060536  mov     edx, 27h ; '''
0x18006053b  mov     rcx, [rcx+10h]
0x18006053f  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180060546  mov     r9d, ebx
0x180060549  call    WPP_SF_d
0x18006054e  jmp     short loc_180060583
0x180060550  mov     rcx, cs:WPP_GLOBAL_Control
0x180060557  lea     rax, WPP_GLOBAL_Control
0x18006055e  cmp     rcx, rax
0x180060561  jz      short loc_18006057E
0x180060563  test    byte ptr [rcx+1Ch], 1
0x180060567  jz      short loc_18006057E
0x180060569  mov     edx, 26h ; '&'
0x18006056e  mov     rcx, [rcx+10h]
0x180060572  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180060579  call    WPP_SF_
0x18006057e  mov     ebx, 80070057h
0x180060583  lea     rcx, [rsp+58h+hKey]
0x180060588  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18006058d  mov     rsi, [rsp+58h+arg_18]
0x180060592  mov     eax, ebx
0x180060594  mov     rbx, [rsp+58h+arg_8]
0x180060599  add     rsp, 50h
0x18006059d  pop     rdi
0x18006059e  retn
```
