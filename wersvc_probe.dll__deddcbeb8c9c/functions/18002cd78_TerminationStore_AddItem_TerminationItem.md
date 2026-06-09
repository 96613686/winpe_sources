# TerminationStore::AddItem(TerminationItem)

- ea: `0x18002cd78`
- end: `0x18002d07e`
- name: `?AddItem@TerminationStore@@QEAAJUTerminationItem@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018af8`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180004a44`
- `0x180007cc8`
- `0x18000cb10`
- `0x18002ccc0`
- `0x18002cd78`
- `0x18002d9d8`
- `0x18002dad8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002cfe9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002cfe9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ce1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cee3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ce1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cee3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d052`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ce67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cf47`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ce67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cf47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cf90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cfc9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d01c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cf90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cfc9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d01c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cefa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cefa`

## string_xrefs

- `0x18002cde4`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002ce7a`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

## pseudocode

```c
__int64 __fastcall TerminationStore::AddItem(__int64 a1, unsigned int *a2)
{
  __int64 v2; // r9
  int v4; // eax
  unsigned int v5; // ebx
  HKEY *phkResult; // rax
  unsigned int v8; // eax
  __int64 v9; // rdx
  HKEY v10; // rbx
  TerminationStore *v11; // rcx
  HKEY *v12; // rax
  __int64 v13; // rax
  int dwOptions; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-9h] BYREF
  _WORD v19[8]; // [rsp+70h] [rbp+7h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+88h] [rbp+1Fh] BYREF
  wchar_t v22[12]; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v2 = *a2;
  lpSubKey[0] = v19;
  hKey = 0;
  lpSubKey[1] = v19;
  dwDisposition = 0;
  v19[0] = 0;
  v4 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"%ls\\%u",
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\TermReason",
         v2);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
      (const char *)(unsigned int)v4,
      dwOptions);
LABEL_3:
    if ( lpSubKey[0] != v19 )
      operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0, 1u, 0xF003Fu, 0, phkResult, &dwDisposition);
  if ( v8 )
  {
    v9 = 402;
LABEL_10:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
           (const char *)v8,
           dwOptionsa);
    goto LABEL_3;
  }
  if ( dwDisposition == 2 )
  {
    v10 = hKey;
    swprintf_s<11>(v22, L"%u", *a2);
    if ( TerminationStore::KeyIsValidItem(v11, v10, v22) )
    {
      if ( lpSubKey[0] != v19 )
        operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( hKey )
        RegCloseKey(hKey);
      return 1;
    }
    v8 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey[0]);
    if ( v8 )
    {
      v9 = 414;
      goto LABEL_10;
    }
    v12 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0, 1u, 0xF003Fu, 0, v12, &dwDisposition);
    if ( v8 )
    {
      v9 = 424;
      goto LABEL_10;
    }
  }
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)a2 + v13 + 2) );
  v8 = RegSetValueExW(hKey, L"Terminator", 0, 1u, (const BYTE *)a2 + 4, 2 * v13 + 2);
  if ( v8 )
  {
    v9 = 432;
    goto LABEL_10;
  }
  v8 = RegSetValueExW(hKey, L"Reason", 0, 4u, (const BYTE *)a2 + 132, 4u);
  if ( v8 )
  {
    v9 = 439;
    goto LABEL_10;
  }
  SystemTimeAsFileTime = 0;
  *(_QWORD *)Data = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)Data = SystemTimeAsFileTime;
  v8 = RegSetValueExW(hKey, L"CreationTime", 0, 0xBu, Data, 8u);
  if ( v8 )
  {
    v9 = 453;
    goto LABEL_10;
  }
  if ( lpSubKey[0] != v19 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002cd78  mov     [rsp-8+arg_0], rbx
0x18002cd7d  mov     [rsp-8+arg_10], rsi
0x18002cd82  push    rbp
0x18002cd83  push    rdi
0x18002cd84  push    r15
0x18002cd86  lea     rbp, [rsp-47h]
0x18002cd8b  sub     rsp, 0B0h
0x18002cd92  mov     rax, cs:__security_cookie
0x18002cd99  xor     rax, rsp
0x18002cd9c  mov     [rbp+57h+var_18], rax
0x18002cda0  mov     r9d, [rdx]
0x18002cda3  lea     rax, [rbp+57h+var_50]
0x18002cda7  xor     esi, esi
0x18002cda9  mov     [rbp+57h+lpSubKey], rax
0x18002cdad  lea     rax, [rbp+57h+var_50]
0x18002cdb1  mov     [rbp+57h+hKey], rsi
0x18002cdb5  mov     rdi, rdx
0x18002cdb8  mov     [rbp+57h+var_58], rax
0x18002cdbc  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x18002cdc3  mov     [rbp+57h+dwDisposition], esi
0x18002cdc6  lea     rdx, aLsU; "%ls\\%u"
0x18002cdcd  mov     [rbp+57h+var_50], si
0x18002cdd1  lea     rcx, [rbp+57h+lpSubKey]
0x18002cdd5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002cdda  mov     ebx, eax
0x18002cddc  test    eax, eax
0x18002cdde  jns     short loc_18002CE27
0x18002cde0  mov     rcx, [rbp+5Fh]; this
0x18002cde4  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002cdeb  mov     r9d, eax; char *
0x18002cdee  mov     edx, 188h; void *
0x18002cdf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdf8  mov     rcx, [rbp+57h+lpSubKey]; void *
0x18002cdfc  lea     rax, [rbp+57h+var_50]
0x18002ce00  cmp     rcx, rax
0x18002ce03  jz      short loc_18002CE11
0x18002ce05  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ce0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ce11  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ce15  test    rcx, rcx
0x18002ce18  jz      short loc_18002CE20
0x18002ce1a  call    cs:__imp_RegCloseKey
0x18002ce20  mov     eax, ebx
0x18002ce22  jmp     loc_18002D05A
0x18002ce27  lea     rcx, [rbp+57h+hKey]
0x18002ce2b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002ce30  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002ce34  lea     rcx, [rbp+57h+dwDisposition]
0x18002ce38  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x18002ce3d  mov     r15, 0FFFFFFFF80000002h
0x18002ce44  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002ce49  xor     r9d, r9d; lpClass
0x18002ce4c  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002ce51  xor     r8d, r8d; Reserved
0x18002ce54  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x18002ce5c  mov     rcx, r15; hKey
0x18002ce5f  mov     [rsp+0C0h+dwOptions], 1; unsigned int
0x18002ce67  call    cs:__imp_RegCreateKeyExW
0x18002ce6d  test    eax, eax
0x18002ce6f  jz      short loc_18002CE90
0x18002ce71  mov     edx, 192h; void *
0x18002ce76  mov     rcx, [rbp+5Fh]; this
0x18002ce7a  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002ce81  mov     r9d, eax; char *
0x18002ce84  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ce89  mov     ebx, eax
0x18002ce8b  jmp     loc_18002CDF8
0x18002ce90  cmp     [rbp+57h+dwDisposition], 2
0x18002ce94  jnz     loc_18002CF5B
0x18002ce9a  mov     r8d, [rdi]
0x18002ce9d  lea     rdx, aU_0; "%u"
0x18002cea4  mov     rbx, [rbp+57h+hKey]
0x18002cea8  lea     rcx, [rbp+57h+var_30]
0x18002ceac  call    ??$swprintf_s@$0L@@@YAHAEAY0L@_WPEB_WZZ; swprintf_s<11>(wchar_t (&)[11],wchar_t const *,...)
0x18002ceb1  lea     r8, [rbp+57h+var_30]; wchar_t *
0x18002ceb5  mov     rdx, rbx; HKEY
0x18002ceb8  call    ?KeyIsValidItem@TerminationStore@@AEAA_NPEAUHKEY__@@PEB_W@Z; TerminationStore::KeyIsValidItem(HKEY__ *,wchar_t const *)
0x18002cebd  test    al, al
0x18002cebf  jz      short loc_18002CEF3
0x18002cec1  mov     rcx, [rbp+57h+lpSubKey]; void *
0x18002cec5  lea     rax, [rbp+57h+var_50]
0x18002cec9  cmp     rcx, rax
0x18002cecc  jz      short loc_18002CEDA
0x18002cece  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ced5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002ceda  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cede  test    rcx, rcx
0x18002cee1  jz      short loc_18002CEE9
0x18002cee3  call    cs:__imp_RegCloseKey
0x18002cee9  mov     eax, 1
0x18002ceee  jmp     loc_18002D05A
0x18002cef3  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002cef7  mov     rcx, r15; hKey
0x18002cefa  call    cs:__imp_RegDeleteKeyW
0x18002cf00  test    eax, eax
0x18002cf02  jz      short loc_18002CF0E
0x18002cf04  mov     edx, 19Eh
0x18002cf09  jmp     loc_18002CE76
0x18002cf0e  lea     rcx, [rbp+57h+hKey]
0x18002cf12  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002cf17  lea     rdx, [rbp+57h+dwDisposition]
0x18002cf1b  xor     r9d, r9d; lpClass
0x18002cf1e  mov     [rsp+0C0h+lpdwDisposition], rdx; lpdwDisposition
0x18002cf23  xor     r8d, r8d; Reserved
0x18002cf26  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002cf2a  mov     rcx, r15; hKey
0x18002cf2d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002cf32  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002cf37  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x18002cf3f  mov     [rsp+0C0h+dwOptions], 1; dwOptions
0x18002cf47  call    cs:__imp_RegCreateKeyExW
0x18002cf4d  test    eax, eax
0x18002cf4f  jz      short loc_18002CF5B
0x18002cf51  mov     edx, 1A8h
0x18002cf56  jmp     loc_18002CE76
0x18002cf5b  lea     rcx, [rdi+4]
0x18002cf5f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cf63  inc     rax
0x18002cf66  cmp     [rcx+rax*2], si
0x18002cf6a  jnz     short loc_18002CF63
0x18002cf6c  lea     eax, ds:2[rax*2]
0x18002cf73  mov     r9d, 1; dwType
0x18002cf79  mov     [rsp+0C0h+samDesired], eax; cbData
0x18002cf7d  lea     rdx, ValueName; "Terminator"
0x18002cf84  mov     qword ptr [rsp+0C0h+dwOptions], rcx; lpData
0x18002cf89  xor     r8d, r8d; Reserved
0x18002cf8c  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cf90  call    cs:__imp_RegSetValueExW
0x18002cf96  test    eax, eax
0x18002cf98  jz      short loc_18002CFA4
0x18002cf9a  mov     edx, 1B0h
0x18002cf9f  jmp     loc_18002CE76
0x18002cfa4  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cfa8  lea     rax, [rdi+84h]
0x18002cfaf  mov     r9d, 4; dwType
0x18002cfb5  lea     rdx, aReason; "Reason"
0x18002cfbc  mov     [rsp+0C0h+samDesired], r9d; cbData
0x18002cfc1  xor     r8d, r8d; Reserved
0x18002cfc4  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18002cfc9  call    cs:__imp_RegSetValueExW
0x18002cfcf  test    eax, eax
0x18002cfd1  jz      short loc_18002CFDD
0x18002cfd3  mov     edx, 1B7h
0x18002cfd8  jmp     loc_18002CE76
0x18002cfdd  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002cfe1  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18002cfe5  mov     qword ptr [rbp+57h+Data], rsi
0x18002cfe9  call    cs:__imp_GetSystemTimeAsFileTime
0x18002cfef  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18002cff3  lea     rdx, Value; "CreationTime"
0x18002cffa  mov     rcx, [rbp+57h+hKey]; hKey
0x18002cffe  mov     r9d, 0Bh; dwType
0x18002d004  mov     qword ptr [rbp+57h+Data], rax
0x18002d008  xor     r8d, r8d; Reserved
0x18002d00b  lea     rax, [rbp+57h+Data]
0x18002d00f  mov     [rsp+0C0h+samDesired], 8; cbData
0x18002d017  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x18002d01c  call    cs:__imp_RegSetValueExW
0x18002d022  test    eax, eax
0x18002d024  jz      short loc_18002D030
0x18002d026  mov     edx, 1C5h
0x18002d02b  jmp     loc_18002CE76
0x18002d030  mov     rcx, [rbp+57h+lpSubKey]; void *
0x18002d034  lea     rax, [rbp+57h+var_50]
0x18002d038  cmp     rcx, rax
0x18002d03b  jz      short loc_18002D049
0x18002d03d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d044  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d049  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d04d  test    rcx, rcx
0x18002d050  jz      short loc_18002D058
0x18002d052  call    cs:__imp_RegCloseKey
0x18002d058  xor     eax, eax
0x18002d05a  mov     rcx, [rbp+57h+var_18]
0x18002d05e  xor     rcx, rsp; StackCookie
0x18002d061  call    __security_check_cookie
0x18002d066  lea     r11, [rsp+0C0h+var_10]
0x18002d06e  mov     rbx, [r11+20h]
0x18002d072  mov     rsi, [r11+30h]
0x18002d076  mov     rsp, r11
0x18002d079  pop     r15
0x18002d07b  pop     rdi
0x18002d07c  pop     rbp
0x18002d07d  retn
```
