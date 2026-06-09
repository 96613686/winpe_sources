# Windows::System::Internal::Launch::StateRepositorySource::GetKey(ulong,HKEY__ * *)

- ea: `0x180033bf0`
- end: `0x180033f31`
- name: `?GetKey@StateRepositorySource@Launch@Internal@System@Windows@@UEAAJKPEAPEAUHKEY__@@@Z`
- size: `833`
- prototype: `int(Windows::System::Internal::Launch::StateRepositorySource *__hidden this, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033570`

## callees

- `0x180010c04`
- `0x18001d10c`
- `0x180023fcc`
- `0x180033bf0`
- `0x18003440c`
- `0x180066ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033c84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033edf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033c84`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033edf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033cd3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033cd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033c18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033f14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033c18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033f14`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033d1d`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033d70`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033dc0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033e11`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033e62`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033d1d`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033d70`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033dc0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033e11`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180033e62`

## string_xrefs

- `0x180033e5b`: `command`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::StateRepositorySource::GetKey(
        Windows::System::Internal::Launch::StateRepositorySource *this,
        REGSAM a2,
        HKEY *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  HKEY *v11; // rbx
  unsigned int Key; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  LSTATUS v18; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  HKEY v21; // [rsp+50h] [rbp-20h] BYREF
  HKEY v22; // [rsp+58h] [rbp-18h] BYREF
  HKEY v23; // [rsp+60h] [rbp-10h] BYREF
  HSTRING string; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  HKEY v26; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF

  string = 0;
  WindowsDeleteString(0);
  v6 = *((_QWORD *)this + 11);
  string = 0;
  v7 = LookupValueStringForKey(v6, L"Progid", &string);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 246;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
      (const char *)v9,
      phkResult);
    goto LABEL_30;
  }
  v11 = (HKEY *)((char *)this + 96);
  if ( !*((_QWORD *)this + 12) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      (char *)this + 96,
      0);
    if ( RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Launcher\\Activati"
            "on\\UWARegAssociationInteropProgId",
           0,
           0x20019u,
           v11) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        v11,
        0);
      Key = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Launcher\\Activ"
               "ation\\UWARegAssociationInteropProgId",
              0,
              0,
              0,
              0xF003Fu,
              0,
              v11,
              0);
      if ( Key )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xFE,
               (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
               (const char *)Key,
               phkResult);
        goto LABEL_30;
      }
      v26 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v26,
        0);
      v13 = RegCreateKeyW(*v11, L"Application", &v26);
      if ( v13 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x101,
               (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
               (const char *)v13,
               phkResult);
LABEL_9:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        goto LABEL_30;
      }
      v21 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v21,
        0);
      v14 = RegCreateKeyW(*v11, L"DefaultIcon", &v21);
      if ( v14 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x103,
               (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
               (const char *)v14,
               phkResult);
LABEL_12:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
        goto LABEL_9;
      }
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v15 = RegCreateKeyW(*v11, L"Shell", &hKey);
      if ( v15 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x105,
               (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
               (const char *)v15,
               phkResult);
LABEL_15:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_12;
      }
      v22 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v22,
        0);
      v16 = RegCreateKeyW(hKey, L"open", &v22);
      if ( v16 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x107,
               (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
               (const char *)v16,
               phkResult);
LABEL_18:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
        goto LABEL_15;
      }
      v23 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v23,
        0);
      v17 = RegCreateKeyW(v22, L"command", &v23);
      if ( v17 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x109,
               (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
               (const char *)v17,
               phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        goto LABEL_18;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
    }
  }
  if ( !*v11 )
  {
    v8 = -2147024894;
    v10 = 270;
LABEL_28:
    v9 = v8;
    goto LABEL_29;
  }
  v18 = RegOpenKeyExW(*v11, 0, 0, a2, a3);
  v8 = v18;
  if ( v18 > 0 )
    v8 = (unsigned __int16)v18 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    v10 = 271;
    goto LABEL_28;
  }
LABEL_30:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x180033bf0  mov     [rsp-18h+arg_8], rbx
0x180033bf5  mov     [rsp-18h+arg_10], rsi
0x180033bfa  push    rbp
0x180033bfb  push    rdi
0x180033bfc  push    r14
0x180033bfe  mov     rbp, rsp
0x180033c01  sub     rsp, 70h
0x180033c05  mov     rdi, rcx
0x180033c08  mov     [rbp+string], 0
0x180033c10  xor     ecx, ecx; string
0x180033c12  mov     rsi, r8
0x180033c15  mov     r14d, edx
0x180033c18  call    cs:__imp_WindowsDeleteString
0x180033c1e  mov     rcx, [rdi+58h]
0x180033c22  lea     r8, [rbp+string]
0x180033c26  lea     rdx, aProgid; "Progid"
0x180033c2d  mov     [rbp+string], 0
0x180033c35  call    ?LookupValueStringForKey@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; LookupValueStringForKey(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180033c3a  mov     ebx, eax
0x180033c3c  test    eax, eax
0x180033c3e  jns     short loc_180033C4D
0x180033c40  mov     r9d, eax
0x180033c43  mov     edx, 0F6h
0x180033c48  jmp     loc_180033F00
0x180033c4d  lea     rbx, [rdi+60h]
0x180033c51  cmp     qword ptr [rbx], 0
0x180033c55  jnz     loc_180033EBE
0x180033c5b  xor     edx, edx
0x180033c5d  mov     rcx, rbx
0x180033c60  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033c65  mov     rdi, 0FFFFFFFF80000001h
0x180033c6c  mov     [rsp+70h+phkResult], rbx; phkResult
0x180033c71  mov     rcx, rdi; hKey
0x180033c74  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\Local Settings\\Soft"...
0x180033c7b  mov     r9d, 20019h; samDesired
0x180033c81  xor     r8d, r8d; ulOptions
0x180033c84  call    cs:__imp_RegOpenKeyExW
0x180033c8a  test    eax, eax
0x180033c8c  jz      loc_180033EBE
0x180033c92  xor     edx, edx
0x180033c94  mov     rcx, rbx
0x180033c97  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033c9c  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180033ca5  lea     rdx, aSoftwareClasse; "SOFTWARE\\Classes\\Local Settings\\Soft"...
0x180033cac  mov     [rsp+70h+var_38], rbx; phkResult
0x180033cb1  xor     r9d, r9d; lpClass
0x180033cb4  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180033cbd  xor     r8d, r8d; Reserved
0x180033cc0  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180033cc8  mov     rcx, rdi; hKey
0x180033ccb  mov     dword ptr [rsp+70h+phkResult], 0; unsigned int
0x180033cd3  call    cs:__imp_RegCreateKeyExW
0x180033cd9  test    eax, eax
0x180033cdb  jz      short loc_180033CFC
0x180033cdd  mov     rcx, [rbp+18h]; this
0x180033ce1  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033ce8  mov     r9d, eax; char *
0x180033ceb  mov     edx, 0FEh; void *
0x180033cf0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033cf5  mov     ebx, eax
0x180033cf7  jmp     loc_180033F10
0x180033cfc  xor     edx, edx
0x180033cfe  mov     [rbp+arg_0], 0
0x180033d06  lea     rcx, [rbp+arg_0]
0x180033d0a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033d0f  mov     rcx, [rbx]; hKey
0x180033d12  lea     r8, [rbp+arg_0]; phkResult
0x180033d16  lea     rdx, aApplication_0; "Application"
0x180033d1d  call    cs:__imp_RegCreateKeyW
0x180033d23  test    eax, eax
0x180033d25  jz      short loc_180033D4F
0x180033d27  mov     rcx, [rbp+18h]; this
0x180033d2b  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033d32  mov     r9d, eax; char *
0x180033d35  mov     edx, 101h; void *
0x180033d3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033d3f  mov     ebx, eax
0x180033d41  lea     rcx, [rbp+arg_0]
0x180033d45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033d4a  jmp     loc_180033F10
0x180033d4f  xor     edx, edx
0x180033d51  mov     [rbp+var_20], 0
0x180033d59  lea     rcx, [rbp+var_20]
0x180033d5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033d62  mov     rcx, [rbx]; hKey
0x180033d65  lea     r8, [rbp+var_20]; phkResult
0x180033d69  lea     rdx, aDefaulticon_0; "DefaultIcon"
0x180033d70  call    cs:__imp_RegCreateKeyW
0x180033d76  test    eax, eax
0x180033d78  jz      short loc_180033D9F
0x180033d7a  mov     rcx, [rbp+18h]; this
0x180033d7e  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033d85  mov     r9d, eax; char *
0x180033d88  mov     edx, 103h; void *
0x180033d8d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033d92  mov     ebx, eax
0x180033d94  lea     rcx, [rbp+var_20]
0x180033d98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033d9d  jmp     short loc_180033D41
0x180033d9f  xor     edx, edx
0x180033da1  mov     [rbp+hKey], 0
0x180033da9  lea     rcx, [rbp+hKey]
0x180033dad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033db2  mov     rcx, [rbx]; hKey
0x180033db5  lea     r8, [rbp+hKey]; phkResult
0x180033db9  lea     rdx, String2; "Shell"
0x180033dc0  call    cs:__imp_RegCreateKeyW
0x180033dc6  test    eax, eax
0x180033dc8  jz      short loc_180033DEF
0x180033dca  mov     rcx, [rbp+18h]; this
0x180033dce  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033dd5  mov     r9d, eax; char *
0x180033dd8  mov     edx, 105h; void *
0x180033ddd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033de2  mov     ebx, eax
0x180033de4  lea     rcx, [rbp+hKey]
0x180033de8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ded  jmp     short loc_180033D94
0x180033def  xor     edx, edx
0x180033df1  mov     [rbp+var_18], 0
0x180033df9  lea     rcx, [rbp+var_18]
0x180033dfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033e02  mov     rcx, [rbp+hKey]; hKey
0x180033e06  lea     r8, [rbp+var_18]; phkResult
0x180033e0a  lea     rdx, aOpen_0; "open"
0x180033e11  call    cs:__imp_RegCreateKeyW
0x180033e17  test    eax, eax
0x180033e19  jz      short loc_180033E40
0x180033e1b  mov     rcx, [rbp+18h]; this
0x180033e1f  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033e26  mov     r9d, eax; char *
0x180033e29  mov     edx, 107h; void *
0x180033e2e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e33  mov     ebx, eax
0x180033e35  lea     rcx, [rbp+var_18]
0x180033e39  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033e3e  jmp     short loc_180033DE4
0x180033e40  xor     edx, edx
0x180033e42  mov     [rbp+var_10], 0
0x180033e4a  lea     rcx, [rbp+var_10]
0x180033e4e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180033e53  mov     rcx, [rbp+var_18]; hKey
0x180033e57  lea     r8, [rbp+var_10]; phkResult
0x180033e5b  lea     rdx, aCommand; "command"
0x180033e62  call    cs:__imp_RegCreateKeyW
0x180033e68  test    eax, eax
0x180033e6a  jz      short loc_180033E91
0x180033e6c  mov     rcx, [rbp+18h]; this
0x180033e70  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033e77  mov     r9d, eax; char *
0x180033e7a  mov     edx, 109h; void *
0x180033e7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033e84  lea     rcx, [rbp+var_10]
0x180033e88  mov     ebx, eax
0x180033e8a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033e8f  jmp     short loc_180033E35
0x180033e91  lea     rcx, [rbp+var_10]
0x180033e95  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033e9a  lea     rcx, [rbp+var_18]
0x180033e9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ea3  lea     rcx, [rbp+hKey]
0x180033ea7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033eac  lea     rcx, [rbp+var_20]
0x180033eb0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033eb5  lea     rcx, [rbp+arg_0]
0x180033eb9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180033ebe  mov     rcx, [rbx]; hKey
0x180033ec1  test    rcx, rcx
0x180033ec4  jnz     short loc_180033ED2
0x180033ec6  mov     ebx, 80070002h
0x180033ecb  mov     edx, 10Eh
0x180033ed0  jmp     short loc_180033EFD
0x180033ed2  mov     r9d, r14d; samDesired
0x180033ed5  mov     [rsp+70h+phkResult], rsi; int
0x180033eda  xor     r8d, r8d; ulOptions
0x180033edd  xor     edx, edx; lpSubKey
0x180033edf  call    cs:__imp_RegOpenKeyExW
0x180033ee5  mov     ebx, eax
0x180033ee7  test    eax, eax
0x180033ee9  jle     short loc_180033EF4
0x180033eeb  movzx   ebx, ax
0x180033eee  or      ebx, 80070000h
0x180033ef4  test    ebx, ebx
0x180033ef6  jns     short loc_180033F10
0x180033ef8  mov     edx, 10Fh; void *
0x180033efd  mov     r9d, ebx; char *
0x180033f00  mov     rcx, [rbp+18h]; this
0x180033f04  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x180033f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f10  mov     rcx, [rbp+string]; string
0x180033f14  call    cs:__imp_WindowsDeleteString
0x180033f1a  lea     r11, [rsp+70h+var_s0]
0x180033f1f  mov     eax, ebx
0x180033f21  mov     rbx, [r11+28h]
0x180033f25  mov     rsi, [r11+30h]
0x180033f29  mov     rsp, r11
0x180033f2c  pop     r14
0x180033f2e  pop     rdi
0x180033f2f  pop     rbp
0x180033f30  retn
```
