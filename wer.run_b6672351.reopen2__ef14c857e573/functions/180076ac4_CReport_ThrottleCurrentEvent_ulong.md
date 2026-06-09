# CReport::ThrottleCurrentEvent(ulong)

- ea: `0x180076ac4`
- end: `0x180076ddc`
- name: `?ThrottleCurrentEvent@CReport@@QEAAJK@Z`
- size: `792`
- prototype: `__int64 __fastcall(CReport *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024840`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x1800170b0`
- `0x18001c368`
- `0x18001cb20`
- `0x1800201f0`
- `0x180020680`
- `0x180076ac4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180076b6a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180076b6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180076c76`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180076c76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180076c53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180076c53`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180076caf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180076d2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180076caf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180076d2e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180076cd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180076d54`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180076cd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180076d54`

## pseudocode

```c
__int64 __fastcall CReport::ThrottleCurrentEvent(CReport *this, int a2)
{
  bool v4; // zf
  int v5; // ebx
  __int64 v6; // rsi
  __int64 i; // rbx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LPCWSTR lpSubKey[5]; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+28h] BYREF
  int v17; // [rsp+A8h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+38h] BYREF
  struct _FILETIME Data; // [rsp+B8h] [rbp+40h] BYREF

  SystemTimeAsFileTime = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  v4 = *((_DWORD *)this + 1468) == 3;
  hKey = 0;
  Data = 0;
  v17 = a2;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
    goto LABEL_5;
  }
  v6 = *((_QWORD *)this + 70);
  if ( (unsigned int)(a2 - 315360001) <= 0xED33FCFD )
    v17 = 315360000;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 2 )
    {
      v5 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             lpSubKey,
             L"%s\\%s\\%s",
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"Throttling",
             *((_QWORD *)this + 70));
      if ( v5 >= 0 )
      {
        phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        Key = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0x20106u, 0, phkResult, 0);
        if ( Key || !hKey )
        {
          v5 = ERROR_HR_FROM_WIN32(Key);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_34;
          v9 = 297;
        }
        else
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          Data = SystemTimeAsFileTime;
          v12 = RegSetValueExW(hKey, L"LastTime", 0, 0xBu, (const BYTE *)&Data, 8u);
          if ( v12 )
          {
            v5 = ERROR_HR_FROM_WIN32(v12);
            RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_34;
            v9 = 298;
          }
          else
          {
            v13 = RegSetValueExW(hKey, L"Duration", 0, 4u, (const BYTE *)&v17, 4u);
            if ( !v13 )
            {
              v5 = 0;
              goto LABEL_34;
            }
            v5 = ERROR_HR_FROM_WIN32(v13);
            RegDeleteKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0);
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_34;
            v9 = 299;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_34;
        v9 = 296;
      }
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, (unsigned int)v5);
      goto LABEL_34;
    }
    if ( !(unsigned int)_o__wcsicmp(v6, off_1800B5138[i]) )
      break;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v6);
LABEL_5:
  v5 = -2147019873;
LABEL_34:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180076ac4  push    rbp
0x180076ac6  push    rbx
0x180076ac7  push    rsi
0x180076ac8  push    rdi
0x180076ac9  mov     rbp, rsp
0x180076acc  sub     rsp, 78h
0x180076ad0  mov     rdi, rcx
0x180076ad3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180076adb  lea     rcx, [rbp+lpSubKey]; void *
0x180076adf  mov     ebx, edx
0x180076ae1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076ae6  cmp     dword ptr [rdi+16F0h], 3
0x180076aed  mov     [rbp+hKey], 0
0x180076af5  mov     [rbp+Data], 0
0x180076afd  mov     [rbp+arg_8], ebx
0x180076b00  jnz     short loc_180076B3A
0x180076b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180076b09  lea     rax, WPP_GLOBAL_Control
0x180076b10  cmp     rcx, rax
0x180076b13  jz      short loc_180076B30
0x180076b15  test    byte ptr [rcx+1Ch], 1
0x180076b19  jz      short loc_180076B30
0x180076b1b  mov     rcx, [rcx+10h]
0x180076b1f  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180076b26  mov     edx, 126h
0x180076b2b  call    WPP_SF_
0x180076b30  mov     ebx, 8007139Fh
0x180076b35  jmp     loc_180076DBE
0x180076b3a  mov     rsi, [rdi+230h]
0x180076b41  lea     eax, [rbx-12CC0301h]
0x180076b47  cmp     eax, 0ED33FCFDh
0x180076b4c  ja      short loc_180076B55
0x180076b4e  mov     [rbp+arg_8], 12CC0300h
0x180076b55  xor     ebx, ebx
0x180076b57  cmp     ebx, 2
0x180076b5a  jnb     short loc_180076BB4
0x180076b5c  lea     rax, off_1800B5138; "APPCRASH"
0x180076b63  mov     rcx, rsi
0x180076b66  mov     rdx, [rax+rbx*8]
0x180076b6a  call    cs:__imp__o__wcsicmp
0x180076b71  nop     dword ptr [rax+rax+00h]
0x180076b76  test    eax, eax
0x180076b78  jz      short loc_180076B7E
0x180076b7a  inc     ebx
0x180076b7c  jmp     short loc_180076B57
0x180076b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180076b85  lea     rax, WPP_GLOBAL_Control
0x180076b8c  cmp     rcx, rax
0x180076b8f  jz      short loc_180076B30
0x180076b91  test    byte ptr [rcx+1Ch], 1
0x180076b95  jz      short loc_180076B30
0x180076b97  mov     rcx, [rcx+10h]
0x180076b9b  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180076ba2  mov     edx, 127h
0x180076ba7  mov     r9, rsi
0x180076baa  call    WPP_SF_S
0x180076baf  jmp     loc_180076B30
0x180076bb4  mov     rax, [rdi+230h]
0x180076bbb  lea     r9, aThrottling; "Throttling"
0x180076bc2  lea     r8, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x180076bc9  mov     qword ptr [rsp+78h+dwOptions], rax
0x180076bce  lea     rdx, aSSS; "%s\\%s\\%s"
0x180076bd5  lea     rcx, [rbp+lpSubKey]
0x180076bd9  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180076bde  mov     ebx, eax
0x180076be0  test    eax, eax
0x180076be2  jns     short loc_180076C0F
0x180076be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180076beb  lea     rax, WPP_GLOBAL_Control
0x180076bf2  cmp     rcx, rax
0x180076bf5  jz      loc_180076DBE
0x180076bfb  test    byte ptr [rcx+1Ch], 1
0x180076bff  jz      loc_180076DBE
0x180076c05  mov     edx, 128h
0x180076c0a  jmp     loc_180076DAB
0x180076c0f  lea     rcx, [rbp+hKey]
0x180076c13  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180076c18  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180076c1c  mov     rdi, 0FFFFFFFF80000001h
0x180076c23  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180076c2c  xor     r9d, r9d; lpClass
0x180076c2f  mov     [rsp+78h+phkResult], rax; phkResult
0x180076c34  xor     r8d, r8d; Reserved
0x180076c37  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180076c40  mov     rcx, rdi; hKey
0x180076c43  mov     [rsp+78h+samDesired], 20106h; samDesired
0x180076c4b  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180076c53  call    cs:__imp_RegCreateKeyExW
0x180076c5a  nop     dword ptr [rax+rax+00h]
0x180076c5f  test    eax, eax
0x180076c61  jnz     loc_180076D84
0x180076c67  cmp     [rbp+hKey], 0
0x180076c6c  jz      loc_180076D84
0x180076c72  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180076c76  call    cs:__imp_GetSystemTimeAsFileTime
0x180076c7d  nop     dword ptr [rax+rax+00h]
0x180076c82  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180076c86  lea     rdx, aLasttime; "LastTime"
0x180076c8d  mov     rcx, [rbp+hKey]; hKey
0x180076c91  mov     r9d, 0Bh; dwType
0x180076c97  mov     [rbp+Data], rax
0x180076c9b  xor     r8d, r8d; Reserved
0x180076c9e  lea     rax, [rbp+Data]
0x180076ca2  mov     [rsp+78h+samDesired], 8; cbData
0x180076caa  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180076caf  call    cs:__imp_RegSetValueExW
0x180076cb6  nop     dword ptr [rax+rax+00h]
0x180076cbb  test    eax, eax
0x180076cbd  jz      short loc_180076D0C
0x180076cbf  mov     ecx, eax; unsigned int
0x180076cc1  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180076cc6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180076cca  mov     rcx, rdi; hKey
0x180076ccd  xor     r9d, r9d; Reserved
0x180076cd0  xor     r8d, r8d; samDesired
0x180076cd3  mov     ebx, eax
0x180076cd5  call    cs:__imp_RegDeleteKeyExW
0x180076cdc  nop     dword ptr [rax+rax+00h]
0x180076ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180076ce8  lea     rax, WPP_GLOBAL_Control
0x180076cef  cmp     rcx, rax
0x180076cf2  jz      loc_180076DBE
0x180076cf8  test    byte ptr [rcx+1Ch], 1
0x180076cfc  jz      loc_180076DBE
0x180076d02  mov     edx, 12Ah
0x180076d07  jmp     loc_180076DAB
0x180076d0c  mov     rcx, [rbp+hKey]; hKey
0x180076d10  lea     rax, [rbp+arg_8]
0x180076d14  mov     r9d, 4; dwType
0x180076d1a  lea     rdx, aDuration; "Duration"
0x180076d21  mov     [rsp+78h+samDesired], r9d; cbData
0x180076d26  xor     r8d, r8d; Reserved
0x180076d29  mov     qword ptr [rsp+78h+dwOptions], rax; lpData
0x180076d2e  call    cs:__imp_RegSetValueExW
0x180076d35  nop     dword ptr [rax+rax+00h]
0x180076d3a  test    eax, eax
0x180076d3c  jz      short loc_180076D80
0x180076d3e  mov     ecx, eax; unsigned int
0x180076d40  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180076d45  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180076d49  mov     rcx, rdi; hKey
0x180076d4c  xor     r9d, r9d; Reserved
0x180076d4f  xor     r8d, r8d; samDesired
0x180076d52  mov     ebx, eax
0x180076d54  call    cs:__imp_RegDeleteKeyExW
0x180076d5b  nop     dword ptr [rax+rax+00h]
0x180076d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180076d67  lea     rax, WPP_GLOBAL_Control
0x180076d6e  cmp     rcx, rax
0x180076d71  jz      short loc_180076DBE
0x180076d73  test    byte ptr [rcx+1Ch], 1
0x180076d77  jz      short loc_180076DBE
0x180076d79  mov     edx, 12Bh
0x180076d7e  jmp     short loc_180076DAB
0x180076d80  xor     ebx, ebx
0x180076d82  jmp     short loc_180076DBE
0x180076d84  mov     ecx, eax; unsigned int
0x180076d86  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180076d8b  mov     ebx, eax
0x180076d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180076d94  lea     rax, WPP_GLOBAL_Control
0x180076d9b  cmp     rcx, rax
0x180076d9e  jz      short loc_180076DBE
0x180076da0  test    byte ptr [rcx+1Ch], 1
0x180076da4  jz      short loc_180076DBE
0x180076da6  mov     edx, 129h
0x180076dab  mov     rcx, [rcx+10h]
0x180076daf  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180076db6  mov     r9d, ebx
0x180076db9  call    WPP_SF_d
0x180076dbe  lea     rcx, [rbp+hKey]
0x180076dc2  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180076dc7  lea     rcx, [rbp+lpSubKey]; void *
0x180076dcb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076dd0  mov     eax, ebx
0x180076dd2  add     rsp, 78h
0x180076dd6  pop     rdi
0x180076dd7  pop     rsi
0x180076dd8  pop     rbx
0x180076dd9  pop     rbp
0x180076dda  retn
```
