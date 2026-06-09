# UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)

- ea: `0x18009d3ec`
- end: `0x18009d55e`
- name: `?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z`
- size: `370`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800507d8`

## callees

- `0x180004c64`
- `0x18001c368`
- `0x18001cb20`
- `0x18004b3d4`
- `0x18004cc54`
- `0x18009d3ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009d4ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009d4ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009d467`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009d467`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009d506`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009d506`

## pseudocode

```c
__int64 __fastcall UtilRegSetCurrentTime(HKEY a1, const wchar_t *a2, const wchar_t *a3)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // ebx
  unsigned int v5; // ebx
  wchar_t *v6; // rcx
  __int64 v7; // rdx
  HKEY v8; // rbx
  LSTATUS v9; // eax
  _BYTE v11[32]; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+18h] BYREF
  struct _FILETIME Data; // [rsp+90h] [rbp+20h] BYREF

  hKey = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  phkResult = (HKEY *)utl::out_ptr<void,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>,>(
                        v11,
                        &hKey);
  Key = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0,
          0,
          0x20106u,
          0,
          phkResult,
          0);
  utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>,HKEY__ *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>,HKEY__ *,>(v11);
  if ( Key )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 88;
LABEL_5:
      WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
  }
  else
  {
    v8 = hKey;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Data = SystemTimeAsFileTime;
    v9 = RegSetValueExW(v8, L"LastRateLimitedDumpGenerationTime", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( !v9 )
    {
      v5 = 0;
      goto LABEL_11;
    }
    v5 = ERROR_HR_FROM_WIN32(v9);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 89;
      goto LABEL_5;
    }
  }
LABEL_11:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x18009d3ec  mov     rax, rsp
0x18009d3ef  mov     [rax+20h], rbx
0x18009d3f3  mov     [rax+18h], r8
0x18009d3f7  mov     [rax+10h], rdx
0x18009d3fb  mov     [rax+8], rcx
0x18009d3ff  push    rbp
0x18009d400  mov     rbp, rsp
0x18009d403  sub     rsp, 70h
0x18009d407  lea     rdx, [rbp+hKey]
0x18009d40b  mov     [rbp+hKey], 0
0x18009d413  lea     rcx, [rbp+var_20]
0x18009d417  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18009d41f  mov     [rbp+Data], 0
0x18009d427  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z
0x18009d42c  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18009d435  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x18009d43c  mov     [rsp+70h+phkResult], rax; phkResult
0x18009d441  xor     r9d, r9d; lpClass
0x18009d444  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009d44d  xor     r8d, r8d; Reserved
0x18009d450  mov     [rsp+70h+samDesired], 20106h; samDesired
0x18009d458  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009d45f  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18009d467  call    cs:__imp_RegCreateKeyExW
0x18009d46e  nop     dword ptr [rax+rax+00h]
0x18009d473  lea     rcx, [rbp+var_20]
0x18009d477  mov     ebx, eax
0x18009d479  call    ??1?$out_ptr_t@V?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@PEAUHKEY__@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>,HKEY__ *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>,HKEY__ *,>(void)
0x18009d47e  test    ebx, ebx
0x18009d480  jz      short loc_18009D4C2
0x18009d482  mov     ebx, 80004005h
0x18009d487  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d48e  lea     rax, WPP_GLOBAL_Control
0x18009d495  cmp     rcx, rax
0x18009d498  jz      loc_18009D544
0x18009d49e  test    byte ptr [rcx+1Ch], 1
0x18009d4a2  jz      loc_18009D544
0x18009d4a8  mov     edx, 58h ; 'X'
0x18009d4ad  mov     rcx, [rcx+10h]
0x18009d4b1  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009d4b8  call    WPP_SF_
0x18009d4bd  jmp     loc_18009D544
0x18009d4c2  mov     rbx, [rbp+hKey]
0x18009d4c6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009d4ca  call    cs:__imp_GetSystemTimeAsFileTime
0x18009d4d1  nop     dword ptr [rax+rax+00h]
0x18009d4d6  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18009d4d9  lea     rdx, aLastratelimite; "LastRateLimitedDumpGenerationTime"
0x18009d4e0  mov     dword ptr [rbp+Data+4], eax
0x18009d4e3  mov     r9d, 0Bh; dwType
0x18009d4e9  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18009d4ec  xor     r8d, r8d; Reserved
0x18009d4ef  mov     dword ptr [rbp+Data], eax
0x18009d4f2  mov     rcx, rbx; hKey
0x18009d4f5  lea     rax, [rbp+Data]
0x18009d4f9  mov     [rsp+70h+samDesired], 8; cbData
0x18009d501  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18009d506  call    cs:__imp_RegSetValueExW
0x18009d50d  nop     dword ptr [rax+rax+00h]
0x18009d512  test    eax, eax
0x18009d514  jz      short loc_18009D542
0x18009d516  mov     ecx, eax; unsigned int
0x18009d518  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009d51d  mov     ebx, eax
0x18009d51f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d526  lea     rax, WPP_GLOBAL_Control
0x18009d52d  cmp     rcx, rax
0x18009d530  jz      short loc_18009D544
0x18009d532  test    byte ptr [rcx+1Ch], 1
0x18009d536  jz      short loc_18009D544
0x18009d538  mov     edx, 59h ; 'Y'
0x18009d53d  jmp     loc_18009D4AD
0x18009d542  xor     ebx, ebx
0x18009d544  lea     rcx, [rbp+hKey]
0x18009d548  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18009d54d  mov     eax, ebx
0x18009d54f  mov     rbx, [rsp+70h+arg_18]
0x18009d557  add     rsp, 70h
0x18009d55b  pop     rbp
0x18009d55c  retn
```
