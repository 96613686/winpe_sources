# WerRemoveExcludedApplication

- ea: `0x1800605b0`
- end: `0x18006072b`
- name: `WerRemoveExcludedApplication`
- size: `379`
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
- `0x1800605b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006065f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006069a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006065f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006069a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060655`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006063e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006063e`

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
0x1800605b0  mov     [rsp+arg_8], rbx
0x1800605b5  mov     [rsp+arg_10], rsi
0x1800605ba  push    rdi
0x1800605bb  sub     rsp, 30h
0x1800605bf  xor     esi, esi
0x1800605c1  mov     edi, edx
0x1800605c3  mov     [rsp+38h+hKey], rsi
0x1800605c8  test    rcx, rcx
0x1800605cb  jnz     short loc_1800605F6
0x1800605cd  mov     rcx, cs:WPP_GLOBAL_Control; wchar_t *
0x1800605d4  lea     rax, WPP_GLOBAL_Control
0x1800605db  cmp     rcx, rax
0x1800605de  jz      loc_18006070A
0x1800605e4  test    byte ptr [rcx+1Ch], 1
0x1800605e8  jz      loc_18006070A
0x1800605ee  lea     edx, [rsi+29h]
0x1800605f1  jmp     loc_1800606FA
0x1800605f6  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x1800605fb  mov     rbx, rax
0x1800605fe  test    rax, rax
0x180060601  jz      loc_1800606DC
0x180060607  cmp     [rax], si
0x18006060a  jz      loc_1800606DC
0x180060610  lea     rcx, [rsp+38h+hKey]
0x180060615  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18006061a  neg     edi
0x18006061c  mov     [rsp+38h+phkResult], rax; phkResult
0x180060621  mov     r9d, 102h; samDesired
0x180060627  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\Windows E"...
0x18006062e  sbb     rcx, rcx
0x180060631  xor     r8d, r8d; ulOptions
0x180060634  neg     rcx
0x180060637  add     rcx, 0FFFFFFFF80000001h; hKey
0x18006063e  call    cs:__imp_RegOpenKeyExW
0x180060644  test    eax, eax
0x180060646  jnz     short loc_18006069A
0x180060648  mov     rcx, [rsp+38h+hKey]; hKey
0x18006064d  test    rcx, rcx
0x180060650  jz      short loc_18006069A
0x180060652  mov     rdx, rbx; lpValueName
0x180060655  call    cs:__imp_RegDeleteValueW
0x18006065b  test    eax, eax
0x18006065d  jz      short loc_180060696
0x18006065f  call    cs:__imp_GetLastError
0x180060665  mov     ecx, eax; unsigned int
0x180060667  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006066c  mov     ebx, eax
0x18006066e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060675  lea     rax, WPP_GLOBAL_Control
0x18006067c  cmp     rcx, rax
0x18006067f  jz      loc_18006070F
0x180060685  test    byte ptr [rcx+1Ch], 1
0x180060689  jz      loc_18006070F
0x18006068f  mov     edx, 2Ch ; ','
0x180060694  jmp     short loc_1800606C7
0x180060696  mov     ebx, esi
0x180060698  jmp     short loc_18006070F
0x18006069a  call    cs:__imp_GetLastError
0x1800606a0  mov     ecx, eax; unsigned int
0x1800606a2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800606a7  mov     ebx, eax
0x1800606a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606b0  lea     rax, WPP_GLOBAL_Control
0x1800606b7  cmp     rcx, rax
0x1800606ba  jz      short loc_18006070F
0x1800606bc  test    byte ptr [rcx+1Ch], 1
0x1800606c0  jz      short loc_18006070F
0x1800606c2  mov     edx, 2Bh ; '+'
0x1800606c7  mov     rcx, [rcx+10h]
0x1800606cb  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x1800606d2  mov     r9d, ebx
0x1800606d5  call    WPP_SF_d
0x1800606da  jmp     short loc_18006070F
0x1800606dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800606e3  lea     rax, WPP_GLOBAL_Control
0x1800606ea  cmp     rcx, rax
0x1800606ed  jz      short loc_18006070A
0x1800606ef  test    byte ptr [rcx+1Ch], 1
0x1800606f3  jz      short loc_18006070A
0x1800606f5  mov     edx, 2Ah ; '*'
0x1800606fa  mov     rcx, [rcx+10h]
0x1800606fe  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180060705  call    WPP_SF_
0x18006070a  mov     ebx, 80070057h
0x18006070f  lea     rcx, [rsp+38h+hKey]
0x180060714  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180060719  mov     rsi, [rsp+38h+arg_10]
0x18006071e  mov     eax, ebx
0x180060720  mov     rbx, [rsp+38h+arg_8]
0x180060725  add     rsp, 30h
0x180060729  pop     rdi
0x18006072a  retn
```
