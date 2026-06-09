# CleanupPersistedServerSubkeys(void)

- ea: `0x1800538a8`
- end: `0x180053a74`
- name: `?CleanupPersistedServerSubkeys@@YAXXZ`
- size: `460`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180055430`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x180053080`
- `0x180053198`
- `0x1800538a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005392e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005392e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800539be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800539be`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800539f5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800539f5`

## string_xrefs

- `0x180053920`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient\Nts`
- `0x180053961`: `CleanupPersistedServerSubkeys: RegOpenKeyEx failed with error: %ld\n`
- `0x180053a38`: `CleanupPersistedServerSubkeys: Successfully cleaned up all subkeys of NTS config key\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
void CleanupPersistedServerSubkeys(void)
{
  unsigned int v0; // edi
  LSTATUS v1; // eax
  unsigned int v2; // edi
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  HKEY *p_hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  char v8; // [rsp+70h] [rbp-90h]
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v8 = 1;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient\\Nts",
         0,
         0x2001Fu,
         &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v0 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(200) )
      FileLogAdd(L"CleanupPersistedServerSubkeys: RegOpenKeyEx failed with error: %ld\n", v0);
  }
  else
  {
    while ( 1 )
    {
      cchName = 260;
      ftLastWriteTime = 0;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) == 259 )
        break;
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(L"CleanupPersistedServerSubkeys: Cleaning up subkey %s\n", Name);
      v1 = RegDeleteKeyW(hKey, Name);
      v2 = v1;
      if ( v1 )
      {
        if ( v1 != 259 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(200) )
            FileLogAdd(L"CleanupPersistedServerSubkeys: RegEnumKeyEx failed with error: %ld\n", v2);
          goto LABEL_14;
        }
        break;
      }
    }
    if ( (unsigned __int8)FileLogAllowEntry(200) )
      FileLogAdd(L"CleanupPersistedServerSubkeys: Successfully cleaned up all subkeys of NTS config key\n");
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800538a8  mov     [rsp-8+arg_0], rbx
0x1800538ad  mov     [rsp-8+arg_8], rdi
0x1800538b2  push    rbp
0x1800538b3  lea     rbp, [rsp-1A0h]
0x1800538bb  sub     rsp, 2A0h
0x1800538c2  mov     rax, cs:__security_cookie
0x1800538c9  xor     rax, rsp
0x1800538cc  mov     [rbp+1A0h+var_10], rax
0x1800538d3  mov     [rsp+2A0h+var_260], 0
0x1800538db  mov     [rsp+2A0h+hKey], 0
0x1800538e4  mov     [rsp+2A0h+hKey], 0
0x1800538ed  lea     rax, [rsp+2A0h+hKey]
0x1800538f2  mov     [rsp+2A0h+var_240], rax
0x1800538f7  mov     [rsp+2A0h+var_238], 0
0x180053900  mov     ebx, 1
0x180053905  mov     [rsp+2A0h+var_230], bl
0x180053909  mov     [rsp+2A0h+var_260], ebx
0x18005390d  lea     rax, [rsp+2A0h+var_238]
0x180053912  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180053917  mov     r9d, 2001Fh; samDesired
0x18005391d  xor     r8d, r8d; ulOptions
0x180053920  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services\\W3"...
0x180053927  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005392e  call    cs:__imp_RegOpenKeyExW
0x180053935  nop     dword ptr [rax+rax+00h]
0x18005393a  mov     edi, eax
0x18005393c  and     ebx, 0FFFFFFFEh
0x18005393f  mov     [rsp+2A0h+var_260], ebx
0x180053943  lea     rcx, [rsp+2A0h+var_240]
0x180053948  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005394d  test    edi, edi
0x18005394f  jz      short loc_180053973
0x180053951  mov     ecx, 0C8h
0x180053956  call    FileLogAllowEntry
0x18005395b  test    al, al
0x18005395d  jz      short loc_18005396E
0x18005395f  mov     edx, edi
0x180053961  lea     rcx, aCleanuppersist_0; "CleanupPersistedServerSubkeys: RegOpenK"...
0x180053968  call    FileLogAdd
0x18005396d  nop
0x18005396e  jmp     loc_180053A45
0x180053973  mov     ebx, 0C8h
0x180053978  mov     [rsp+2A0h+cchName], 104h
0x180053980  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], 0
0x180053989  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x18005398e  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180053993  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x18005399c  mov     [rsp+2A0h+lpClass], 0; lpClass
0x1800539a5  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x1800539ae  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x1800539b3  lea     r8, [rbp+1A0h+Name]; lpName
0x1800539b7  xor     edx, edx; dwIndex
0x1800539b9  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800539be  call    cs:__imp_RegEnumKeyExW
0x1800539c5  nop     dword ptr [rax+rax+00h]
0x1800539ca  cmp     eax, 103h
0x1800539cf  jz      short loc_180053A2D
0x1800539d1  mov     ecx, ebx
0x1800539d3  call    FileLogAllowEntry
0x1800539d8  test    al, al
0x1800539da  jz      short loc_1800539EC
0x1800539dc  lea     rdx, [rbp+1A0h+Name]
0x1800539e0  lea     rcx, aCleanuppersist; "CleanupPersistedServerSubkeys: Cleaning"...
0x1800539e7  call    FileLogAdd
0x1800539ec  lea     rdx, [rbp+1A0h+Name]; lpSubKey
0x1800539f0  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800539f5  call    cs:__imp_RegDeleteKeyW
0x1800539fc  nop     dword ptr [rax+rax+00h]
0x180053a01  mov     edi, eax
0x180053a03  test    eax, eax
0x180053a05  jz      loc_180053978
0x180053a0b  cmp     eax, 103h
0x180053a10  jz      short loc_180053A2D
0x180053a12  mov     ecx, ebx
0x180053a14  call    FileLogAllowEntry
0x180053a19  test    al, al
0x180053a1b  jz      short loc_180053A45
0x180053a1d  mov     edx, edi
0x180053a1f  lea     rcx, aCleanuppersist_1; "CleanupPersistedServerSubkeys: RegEnumK"...
0x180053a26  call    FileLogAdd
0x180053a2b  jmp     short loc_180053A45
0x180053a2d  mov     ecx, ebx
0x180053a2f  call    FileLogAllowEntry
0x180053a34  test    al, al
0x180053a36  jz      short loc_180053A45
0x180053a38  lea     rcx, aCleanuppersist_2; "CleanupPersistedServerSubkeys: Successf"...
0x180053a3f  call    FileLogAdd
0x180053a44  nop
0x180053a45  lea     rcx, [rsp+2A0h+hKey]
0x180053a4a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180053a4f  mov     rcx, [rbp+1A0h+var_10]
0x180053a56  xor     rcx, rsp; StackCookie
0x180053a59  call    __security_check_cookie
0x180053a5e  lea     r11, [rsp+2A0h+var_s0]
0x180053a66  mov     rbx, [r11+10h]
0x180053a6a  mov     rdi, [r11+18h]
0x180053a6e  mov     rsp, r11
0x180053a71  pop     rbp
0x180053a72  retn
```
