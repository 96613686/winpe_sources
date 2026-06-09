# SearchSettings::SearchSettingsHelper::SetUnprotectedDaclRecursive(HKEY__ *,_ACL *)

- ea: `0x1804623c8`
- end: `0x180462533`
- name: `?SetUnprotectedDaclRecursive@SearchSettingsHelper@SearchSettings@@CAXPEAUHKEY__@@PEAU_ACL@@@Z`
- size: `363`
- prototype: `void __fastcall(HKEY, struct _ACL *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180461be8`
- `0x1804623c8`

## callees

- `0x18000fea0`
- `0x180010940`
- `0x18015cb00`
- `0x18015d868`
- `0x1803c3710`
- `0x1804623c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1804624fe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1804624fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18046245c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18046245c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180462495`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180462495`

## string_xrefs

- `0x1804624ae`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SearchSettings::SearchSettingsHelper::SetUnprotectedDaclRecursive(HKEY a1, struct _ACL *a2)
{
  DWORD v4; // ebx
  DWORD i; // edx
  HKEY *phkResult; // rax
  DWORD Key; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  memset_0(SubKey, 0, 0x208u);
  cchName = 260;
  v4 = 0;
  for ( i = 0; !RegEnumKeyExW(a1, i, SubKey, &cchName, 0, 0, 0, 0); i = v4 )
  {
    hKey = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(a1, SubKey, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
    v8 = retaddr;
    if ( Key )
    {
      v9 = 916;
    }
    else
    {
      Key = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 0x20000004u, 0, 0, a2, 0);
      v8 = retaddr;
      if ( !Key )
        goto LABEL_7;
      v9 = 919;
    }
    wil::details::in1diag3::_Log_Win32(
      v8,
      (void *)v9,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
      (const char *)Key,
      dwOptions);
LABEL_7:
    SearchSettings::SearchSettingsHelper::SetUnprotectedDaclRecursive(hKey, a2);
    cchName = 260;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    ++v4;
  }
}

```

## disassembly

```asm
0x1804623c8  mov     [rsp-8+arg_10], rbx
0x1804623cd  mov     [rsp-8+arg_18], rsi
0x1804623d2  push    rbp
0x1804623d3  push    rdi
0x1804623d4  push    r14
0x1804623d6  lea     rbp, [rsp-180h]
0x1804623de  sub     rsp, 280h
0x1804623e5  mov     rax, cs:__security_cookie
0x1804623ec  xor     rax, rsp
0x1804623ef  mov     [rbp+190h+var_20], rax
0x1804623f6  mov     rsi, rdx
0x1804623f9  mov     rdi, rcx
0x1804623fc  xor     edx, edx; Val
0x1804623fe  mov     r8d, 208h; Size
0x180462404  lea     rcx, [rsp+290h+SubKey]; void *
0x180462409  call    memset_0
0x18046240e  mov     [rsp+290h+cchName], 104h
0x180462416  xor     r14d, r14d
0x180462419  mov     ebx, r14d
0x18046241c  xor     edx, edx
0x18046241e  jmp     loc_1804624DD
0x180462423  mov     [rsp+290h+hKey], r14
0x180462428  lea     rcx, [rsp+290h+hKey]
0x18046242d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180462432  mov     [rsp+290h+lpdwDisposition], r14; lpdwDisposition
0x180462437  mov     [rsp+290h+phkResult], rax; phkResult
0x18046243c  mov     [rsp+290h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180462441  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180462449  mov     [rsp+290h+dwOptions], r14d; dwOptions
0x18046244e  xor     r9d, r9d; lpClass
0x180462451  xor     r8d, r8d; Reserved
0x180462454  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180462459  mov     rcx, rdi; hKey
0x18046245c  call    cs:__imp_RegCreateKeyExW
0x180462462  mov     rcx, [rbp+198h]
0x180462469  test    eax, eax
0x18046246b  jz      short loc_180462474
0x18046246d  mov     edx, 394h
0x180462472  jmp     short loc_1804624AB
0x180462474  mov     [rsp+290h+lpSecurityAttributes], r14; pSacl
0x180462479  mov     qword ptr [rsp+290h+samDesired], rsi; pDacl
0x18046247e  mov     qword ptr [rsp+290h+dwOptions], r14; unsigned int
0x180462483  xor     r9d, r9d; psidOwner
0x180462486  lea     edx, [r9+4]; ObjectType
0x18046248a  mov     r8d, 20000004h; SecurityInfo
0x180462490  mov     rcx, [rsp+290h+hKey]; handle
0x180462495  call    cs:__imp_SetSecurityInfo
0x18046249b  mov     rcx, [rbp+198h]; this
0x1804624a2  test    eax, eax
0x1804624a4  jz      short loc_1804624BA
0x1804624a6  mov     edx, 397h; void *
0x1804624ab  mov     r9d, eax; char *
0x1804624ae  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x1804624b5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1804624ba  mov     rdx, rsi; struct _ACL *
0x1804624bd  mov     rcx, [rsp+290h+hKey]; HKEY
0x1804624c2  call    ?SetUnprotectedDaclRecursive@SearchSettingsHelper@SearchSettings@@CAXPEAUHKEY__@@PEAU_ACL@@@Z; SearchSettings::SearchSettingsHelper::SetUnprotectedDaclRecursive(HKEY__ *,_ACL *)
0x1804624c7  mov     [rsp+290h+cchName], 104h
0x1804624cf  lea     rcx, [rsp+290h+hKey]
0x1804624d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1804624d9  inc     ebx
0x1804624db  mov     edx, ebx; dwIndex
0x1804624dd  mov     [rsp+290h+phkResult], r14; lpftLastWriteTime
0x1804624e2  mov     [rsp+290h+lpSecurityAttributes], r14; lpcchClass
0x1804624e7  mov     qword ptr [rsp+290h+samDesired], r14; lpClass
0x1804624ec  mov     qword ptr [rsp+290h+dwOptions], r14; lpReserved
0x1804624f1  lea     r9, [rsp+290h+cchName]; lpcchName
0x1804624f6  lea     r8, [rsp+290h+SubKey]; lpName
0x1804624fb  mov     rcx, rdi; hKey
0x1804624fe  call    cs:__imp_RegEnumKeyExW
0x180462504  test    eax, eax
0x180462506  jz      loc_180462423
0x18046250c  mov     rcx, [rbp+190h+var_20]
0x180462513  xor     rcx, rsp; StackCookie
0x180462516  call    __security_check_cookie
0x18046251b  lea     r11, [rsp+290h+var_10]
0x180462523  mov     rbx, [r11+30h]
0x180462527  mov     rsi, [r11+38h]
0x18046252b  mov     rsp, r11
0x18046252e  pop     r14
0x180462530  pop     rdi
0x180462531  pop     rbp
0x180462532  retn
```
