# WerAddExcludedApplication

- ea: `0x180062c30`
- end: `0x180062df8`
- name: `WerAddExcludedApplication`
- size: `456`
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
- `0x180062c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180062cd4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180062cd4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180062d0f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180062d0f`

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
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids, v9);
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
0x180062c30  mov     rax, rsp
0x180062c33  mov     [rax+10h], rbx
0x180062c37  mov     [rax+20h], rsi
0x180062c3b  push    rdi
0x180062c3c  sub     rsp, 50h
0x180062c40  xor     esi, esi
0x180062c42  mov     edi, edx
0x180062c44  mov     [rax+8], esi
0x180062c47  mov     [rax+18h], rsi
0x180062c4b  test    rcx, rcx
0x180062c4e  jnz     short loc_180062C79
0x180062c50  mov     rcx, cs:WPP_GLOBAL_Control; wchar_t *
0x180062c57  lea     rax, WPP_GLOBAL_Control
0x180062c5e  cmp     rcx, rax
0x180062c61  jz      loc_180062DD6
0x180062c67  test    byte ptr [rcx+1Ch], 1
0x180062c6b  jz      loc_180062DD6
0x180062c71  lea     edx, [rsi+25h]
0x180062c74  jmp     loc_180062DC6
0x180062c79  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x180062c7e  mov     rbx, rax
0x180062c81  test    rax, rax
0x180062c84  jz      loc_180062DA8
0x180062c8a  cmp     [rax], si
0x180062c8d  jz      loc_180062DA8
0x180062c93  lea     rcx, [rsp+58h+hKey]
0x180062c98  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180062c9d  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x180062ca2  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\Windows E"...
0x180062ca9  mov     [rsp+58h+phkResult], rax; phkResult
0x180062cae  neg     edi
0x180062cb0  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180062cb5  sbb     rcx, rcx
0x180062cb8  mov     [rsp+58h+samDesired], 0F013Fh; samDesired
0x180062cc0  neg     rcx
0x180062cc3  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180062cc7  add     rcx, 0FFFFFFFF80000001h; hKey
0x180062cce  xor     r9d, r9d; lpClass
0x180062cd1  xor     r8d, r8d; Reserved
0x180062cd4  call    cs:__imp_RegCreateKeyExW
0x180062cdb  nop     dword ptr [rax+rax+00h]
0x180062ce0  test    eax, eax
0x180062ce2  jnz     short loc_180062D60
0x180062ce4  mov     rcx, [rsp+58h+hKey]; hKey
0x180062ce9  test    rcx, rcx
0x180062cec  jz      short loc_180062D60
0x180062cee  lea     r9d, [rax+4]; dwType
0x180062cf2  mov     [rsp+58h+Data], 1
0x180062cfa  lea     rax, [rsp+58h+Data]
0x180062cff  mov     [rsp+58h+samDesired], r9d; cbData
0x180062d04  xor     r8d, r8d; Reserved
0x180062d07  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180062d0c  mov     rdx, rbx; lpValueName
0x180062d0f  call    cs:__imp_RegSetValueExW
0x180062d16  nop     dword ptr [rax+rax+00h]
0x180062d1b  test    eax, eax
0x180062d1d  jz      short loc_180062D5C
0x180062d1f  call    cs:__imp_GetLastError
0x180062d26  nop     dword ptr [rax+rax+00h]
0x180062d2b  mov     ecx, eax; unsigned int
0x180062d2d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180062d32  mov     ebx, eax
0x180062d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d3b  lea     rax, WPP_GLOBAL_Control
0x180062d42  cmp     rcx, rax
0x180062d45  jz      loc_180062DDB
0x180062d4b  test    byte ptr [rcx+1Ch], 1
0x180062d4f  jz      loc_180062DDB
0x180062d55  mov     edx, 28h ; '('
0x180062d5a  jmp     short loc_180062D93
0x180062d5c  mov     ebx, esi
0x180062d5e  jmp     short loc_180062DDB
0x180062d60  call    cs:__imp_GetLastError
0x180062d67  nop     dword ptr [rax+rax+00h]
0x180062d6c  mov     ecx, eax; unsigned int
0x180062d6e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180062d73  mov     ebx, eax
0x180062d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d7c  lea     rax, WPP_GLOBAL_Control
0x180062d83  cmp     rcx, rax
0x180062d86  jz      short loc_180062DDB
0x180062d88  test    byte ptr [rcx+1Ch], 1
0x180062d8c  jz      short loc_180062DDB
0x180062d8e  mov     edx, 27h ; '''
0x180062d93  mov     rcx, [rcx+10h]
0x180062d97  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180062d9e  mov     r9d, ebx
0x180062da1  call    WPP_SF_d
0x180062da6  jmp     short loc_180062DDB
0x180062da8  mov     rcx, cs:WPP_GLOBAL_Control
0x180062daf  lea     rax, WPP_GLOBAL_Control
0x180062db6  cmp     rcx, rax
0x180062db9  jz      short loc_180062DD6
0x180062dbb  test    byte ptr [rcx+1Ch], 1
0x180062dbf  jz      short loc_180062DD6
0x180062dc1  mov     edx, 26h ; '&'
0x180062dc6  mov     rcx, [rcx+10h]
0x180062dca  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180062dd1  call    WPP_SF_
0x180062dd6  mov     ebx, 80070057h
0x180062ddb  lea     rcx, [rsp+58h+hKey]
0x180062de0  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180062de5  mov     rsi, [rsp+58h+arg_18]
0x180062dea  mov     eax, ebx
0x180062dec  mov     rbx, [rsp+58h+arg_8]
0x180062df1  add     rsp, 50h
0x180062df5  pop     rdi
0x180062df6  retn
```
