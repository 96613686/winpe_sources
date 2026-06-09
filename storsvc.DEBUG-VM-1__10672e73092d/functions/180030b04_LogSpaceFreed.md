# LogSpaceFreed

- ea: `0x180030b04`
- end: `0x180030d81`
- name: `LogSpaceFreed`
- size: `637`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180032088`
- `0x18003253c`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180012ce0`
- `0x180019db4`
- `0x18002fa54`
- `0x180030b04`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030d3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030d3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030d01`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180030d01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030b7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180030b60`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180030b60`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180030c25`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180030c25`

## string_xrefs

- `0x180030bc0`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030c48`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180030cb4`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LogSpaceFreed(int a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  int v5; // eax
  int v6; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Value[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  phkResult = 0;
  SystemTime = 0;
  *(_DWORD *)Data = 0;
  pcbData = 4;
  GetSystemTime(&SystemTime);
  hKey = 0;
  v2 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"StoragePolicy", &hKey);
  v3 = v2;
  if ( v2 >= 0 )
  {
    phkResult = 0;
    v4 = RegCreateKeyW(hKey, L"SpaceHistory", &phkResult);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
    {
      CleanupSpaceFreedLogs(phkResult);
      v5 = StringCchPrintfW(
             Value,
             0x104u,
             L"%d",
             SystemTime.wDay + 100 * (SystemTime.wMonth + 100 * (unsigned int)SystemTime.wYear));
      v3 = v5;
      if ( v5 >= 0 )
      {
        if ( RegGetValueW(phkResult, 0, Value, 0x18u, 0, Data, &pcbData) )
          v6 = 0;
        else
          v6 = *(_DWORD *)Data;
        *(_DWORD *)Data = a1 + v6;
        RegSetValueExW(phkResult, Value, 0, 4u, Data, 4u);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        v3 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x574,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
          (const char *)(unsigned int)v5,
          pdwType);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56D,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)v3,
        pdwType);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56C,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v2,
      pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x180030b04  mov     [rsp-8+arg_8], rbx
0x180030b09  mov     [rsp-8+arg_10], rdi
0x180030b0e  push    rbp
0x180030b0f  lea     rbp, [rsp-1A0h]
0x180030b17  sub     rsp, 2A0h
0x180030b1e  mov     rax, cs:__security_cookie
0x180030b25  xor     rax, rsp
0x180030b28  mov     [rbp+1A0h+var_10], rax
0x180030b2f  mov     edi, ecx
0x180030b31  mov     [rsp+2A0h+hKey], 0
0x180030b3a  mov     [rsp+2A0h+phkResult], 0
0x180030b43  xorps   xmm0, xmm0
0x180030b46  movups  xmmword ptr [rsp+2A0h+SystemTime.wYear], xmm0
0x180030b4b  mov     dword ptr [rsp+2A0h+Data], 0
0x180030b53  mov     [rsp+2A0h+var_248], 4
0x180030b5b  lea     rcx, [rsp+2A0h+SystemTime]; lpSystemTime
0x180030b60  call    cs:__imp_GetSystemTime
0x180030b66  mov     rbx, [rsp+2A0h+hKey]
0x180030b6b  test    rbx, rbx
0x180030b6e  jz      short loc_180030B8F
0x180030b70  lea     rcx, [rsp+2A0h+var_240]; this
0x180030b75  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030b7a  nop
0x180030b7b  mov     rcx, rbx; hKey
0x180030b7e  call    cs:__imp_RegCloseKey
0x180030b84  nop
0x180030b85  lea     rcx, [rsp+2A0h+var_240]; this
0x180030b8a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030b8f  mov     [rsp+2A0h+hKey], 0
0x180030b98  lea     r8, [rsp+2A0h+hKey]; phkResult
0x180030b9d  lea     rdx, aStoragepolicy; "StoragePolicy"
0x180030ba4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180030bab  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180030bb0  mov     ebx, eax
0x180030bb2  test    eax, eax
0x180030bb4  jns     short loc_180030BE2
0x180030bb6  mov     rcx, [rbp+1A8h]; this
0x180030bbd  mov     r9d, eax; char *
0x180030bc0  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030bc7  mov     edx, 56Ch; void *
0x180030bcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030bd1  nop
0x180030bd2  lea     rcx, [rsp+2A0h+phkResult]
0x180030bd7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030bdc  nop
0x180030bdd  jmp     loc_180030D51
0x180030be2  mov     rbx, [rsp+2A0h+phkResult]
0x180030be7  test    rbx, rbx
0x180030bea  jz      short loc_180030C0B
0x180030bec  lea     rcx, [rsp+2A0h+var_240]; this
0x180030bf1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030bf6  nop
0x180030bf7  mov     rcx, rbx; hKey
0x180030bfa  call    cs:__imp_RegCloseKey
0x180030c00  nop
0x180030c01  lea     rcx, [rsp+2A0h+var_240]; this
0x180030c06  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030c0b  mov     [rsp+2A0h+phkResult], 0
0x180030c14  lea     r8, [rsp+2A0h+phkResult]; phkResult
0x180030c19  lea     rdx, aSpacehistory; "SpaceHistory"
0x180030c20  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180030c25  call    cs:__imp_RegCreateKeyW
0x180030c2b  mov     ebx, eax
0x180030c2d  test    eax, eax
0x180030c2f  jle     short loc_180030C3A
0x180030c31  movzx   ebx, ax
0x180030c34  or      ebx, 80070000h
0x180030c3a  test    ebx, ebx
0x180030c3c  jns     short loc_180030C6A
0x180030c3e  mov     rcx, [rbp+1A8h]; this
0x180030c45  mov     r9d, ebx; char *
0x180030c48  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030c4f  mov     edx, 56Dh; void *
0x180030c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c59  nop
0x180030c5a  lea     rcx, [rsp+2A0h+phkResult]
0x180030c5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030c64  nop
0x180030c65  jmp     loc_180030D51
0x180030c6a  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x180030c6f  call    CleanupSpaceFreedLogs
0x180030c74  movzx   eax, [rsp+2A0h+SystemTime.wYear]
0x180030c79  imul    ecx, eax, 64h ; 'd'
0x180030c7c  movzx   eax, [rsp+2A0h+SystemTime.wMonth]
0x180030c81  add     ecx, eax
0x180030c83  imul    r9d, ecx, 64h ; 'd'
0x180030c87  movzx   eax, [rsp+2A0h+SystemTime.wDay]
0x180030c8c  add     r9d, eax
0x180030c8f  lea     r8, aD; "%d"
0x180030c96  mov     edx, 104h; unsigned __int64
0x180030c9b  lea     rcx, [rbp+1A0h+Value]; unsigned __int16 *
0x180030c9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030ca4  mov     ebx, eax
0x180030ca6  test    eax, eax
0x180030ca8  jns     short loc_180030CD3
0x180030caa  mov     rcx, [rbp+1A8h]; this
0x180030cb1  mov     r9d, eax; char *
0x180030cb4  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180030cbb  mov     edx, 574h; void *
0x180030cc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030cc5  nop
0x180030cc6  lea     rcx, [rsp+2A0h+phkResult]
0x180030ccb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030cd0  nop
0x180030cd1  jmp     short loc_180030D51
0x180030cd3  lea     rax, [rsp+2A0h+var_248]
0x180030cd8  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180030cdd  lea     rax, [rsp+2A0h+Data]
0x180030ce2  mov     [rsp+2A0h+pvData], rax; pvData
0x180030ce7  mov     [rsp+2A0h+pdwType], 0; pdwType
0x180030cf0  mov     r9d, 18h; dwFlags
0x180030cf6  lea     r8, [rbp+1A0h+Value]; lpValue
0x180030cfa  xor     edx, edx; lpSubKey
0x180030cfc  mov     rcx, [rsp+2A0h+phkResult]; hkey
0x180030d01  call    cs:__imp_RegGetValueW
0x180030d07  test    eax, eax
0x180030d09  jz      short loc_180030D0F
0x180030d0b  xor     eax, eax
0x180030d0d  jmp     short loc_180030D13
0x180030d0f  mov     eax, dword ptr [rsp+2A0h+Data]
0x180030d13  add     eax, edi
0x180030d15  mov     dword ptr [rsp+2A0h+Data], eax
0x180030d19  mov     dword ptr [rsp+2A0h+pvData], 4; cbData
0x180030d21  lea     rax, [rsp+2A0h+Data]
0x180030d26  mov     [rsp+2A0h+pdwType], rax; lpData
0x180030d2b  mov     r9d, 4; dwType
0x180030d31  xor     r8d, r8d; Reserved
0x180030d34  lea     rdx, [rbp+1A0h+Value]; lpValueName
0x180030d38  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x180030d3d  call    cs:__imp_RegSetValueExW
0x180030d43  nop
0x180030d44  lea     rcx, [rsp+2A0h+phkResult]
0x180030d49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030d4e  nop
0x180030d4f  xor     ebx, ebx
0x180030d51  lea     rcx, [rsp+2A0h+hKey]
0x180030d56  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180030d5b  mov     eax, ebx
0x180030d5d  mov     rcx, [rbp+1A0h+var_10]
0x180030d64  xor     rcx, rsp; StackCookie
0x180030d67  call    __security_check_cookie
0x180030d6c  lea     r11, [rsp+2A0h+var_s0]
0x180030d74  mov     rbx, [r11+18h]
0x180030d78  mov     rdi, [r11+20h]
0x180030d7c  mov     rsp, r11
0x180030d7f  pop     rbp
0x180030d80  retn
```
