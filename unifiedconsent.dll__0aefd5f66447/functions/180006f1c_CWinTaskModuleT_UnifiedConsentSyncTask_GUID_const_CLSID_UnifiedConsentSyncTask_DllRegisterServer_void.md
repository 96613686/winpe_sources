# CWinTaskModuleT<UnifiedConsentSyncTask,&_GUID const CLSID_UnifiedConsentSyncTask>::DllRegisterServer(void)

- ea: `0x180006f1c`
- end: `0x1800070ff`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VUnifiedConsentSyncTask@@$1?CLSID_UnifiedConsentSyncTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f3f0`

## callees

- `0x180002810`
- `0x180003384`
- `0x180006f1c`
- `0x18000d3b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180006fb8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180006fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006f84`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800070b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800070b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007023`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007023`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800070dc`

## string_xrefs

- `0x180006fcd`: `CLSID\\%s\InprocServer32`
- `0x18000709c`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<UnifiedConsentSyncTask,&_GUID const CLSID_UnifiedConsentSyncTask>::DllRegisterServer()
{
  signed int LastError; // eax
  int v1; // ebx
  LSTATUS v2; // eax
  __int64 v3; // rax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  memset_0(Filename, 0, 0x208u);
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  if ( GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u) )
    goto LABEL_5;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v1 = StringFromCLSID(&CLSID_UnifiedConsentSyncTask, &lpsz);
    if ( v1 >= 0 )
    {
      v1 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s\\InprocServer32", lpsz);
      if ( v1 >= 0 )
      {
        v2 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
        v1 = v2;
        if ( v2 > 0 )
          v1 = (unsigned __int16)v2 | 0x80070000;
        if ( v1 >= 0 )
        {
          v3 = -1;
          do
            ++v3;
          while ( Filename[v3] );
          v4 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)Filename, 2 * v3 + 2);
          v1 = v4;
          if ( v4 > 0 )
            v1 = (unsigned __int16)v4 | 0x80070000;
          if ( v1 >= 0 )
          {
            v5 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
            v1 = v5;
            if ( v5 > 0 )
              v1 = (unsigned __int16)v5 | 0x80070000;
          }
        }
      }
    }
  }
  CoTaskMemFree(lpsz);
  lpsz = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180006f1c  push    rbp
0x180006f1e  push    rbx
0x180006f1f  push    rsi
0x180006f20  push    rdi
0x180006f21  lea     rbp, [rsp-398h]
0x180006f29  sub     rsp, 498h
0x180006f30  mov     rax, cs:__security_cookie
0x180006f37  xor     rax, rsp
0x180006f3a  mov     [rbp+3B0h+var_30], rax
0x180006f41  mov     ebx, 208h
0x180006f46  lea     rcx, [rsp+4B0h+Filename]; void *
0x180006f4b  xor     edi, edi
0x180006f4d  mov     r8d, ebx; Size
0x180006f50  xor     edx, edx; Val
0x180006f52  mov     [rsp+4B0h+hKey], rdi
0x180006f57  call    memset_0
0x180006f5c  mov     r8d, ebx; Size
0x180006f5f  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180006f66  xor     edx, edx; Val
0x180006f68  call    memset_0
0x180006f6d  mov     r8d, 104h; nSize
0x180006f73  mov     [rsp+4B0h+lpsz], rdi
0x180006f78  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180006f7d  lea     rcx, cs:180000000h; hModule
0x180006f84  call    cs:__imp_GetModuleFileNameW
0x180006f8a  mov     esi, 80070000h
0x180006f8f  test    eax, eax
0x180006f91  jnz     short loc_180006FAC
0x180006f93  call    cs:__imp_GetLastError
0x180006f99  mov     ebx, eax
0x180006f9b  test    eax, eax
0x180006f9d  jle     short loc_180006FA4
0x180006f9f  movzx   ebx, ax
0x180006fa2  or      ebx, esi
0x180006fa4  test    ebx, ebx
0x180006fa6  js      loc_1800070C2
0x180006fac  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180006fb1  lea     rcx, CLSID_UnifiedConsentSyncTask; rclsid
0x180006fb8  call    cs:__imp_StringFromCLSID
0x180006fbe  mov     ebx, eax
0x180006fc0  test    eax, eax
0x180006fc2  js      loc_1800070C2
0x180006fc8  mov     r9, [rsp+4B0h+lpsz]
0x180006fcd  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180006fd4  mov     edx, 104h; unsigned __int64
0x180006fd9  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180006fe0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006fe5  mov     ebx, eax
0x180006fe7  test    eax, eax
0x180006fe9  js      loc_1800070C2
0x180006fef  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180006ff4  lea     rax, [rsp+4B0h+hKey]
0x180006ff9  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180006ffe  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180007005  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000700a  xor     r9d, r9d; lpClass
0x18000700d  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180007015  xor     r8d, r8d; Reserved
0x180007018  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000701f  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180007023  call    cs:__imp_RegCreateKeyExW
0x180007029  mov     ebx, eax
0x18000702b  test    eax, eax
0x18000702d  jle     short loc_180007034
0x18000702f  movzx   ebx, ax
0x180007032  or      ebx, esi
0x180007034  test    ebx, ebx
0x180007036  js      loc_1800070C2
0x18000703c  lea     rcx, [rsp+4B0h+Filename]
0x180007041  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007045  inc     rax
0x180007048  cmp     [rcx+rax*2], di
0x18000704c  jnz     short loc_180007045
0x18000704e  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180007053  lea     eax, ds:2[rax*2]
0x18000705a  mov     [rsp+4B0h+samDesired], eax; cbData
0x18000705e  mov     r9d, 1; dwType
0x180007064  lea     rax, [rsp+4B0h+Filename]
0x180007069  xor     r8d, r8d; Reserved
0x18000706c  xor     edx, edx; lpValueName
0x18000706e  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180007073  call    cs:__imp_RegSetValueExW
0x180007079  mov     ebx, eax
0x18000707b  test    eax, eax
0x18000707d  jle     short loc_180007084
0x18000707f  movzx   ebx, ax
0x180007082  or      ebx, esi
0x180007084  test    ebx, ebx
0x180007086  js      short loc_1800070C2
0x180007088  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000708d  lea     rax, Data; "Both"
0x180007094  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x18000709c  lea     rdx, ValueName; "ThreadingModel"
0x1800070a3  mov     r9d, 1; dwType
0x1800070a9  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800070ae  xor     r8d, r8d; Reserved
0x1800070b1  call    cs:__imp_RegSetValueExW
0x1800070b7  mov     ebx, eax
0x1800070b9  test    eax, eax
0x1800070bb  jle     short loc_1800070C2
0x1800070bd  movzx   ebx, ax
0x1800070c0  or      ebx, esi
0x1800070c2  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800070c7  call    cs:__imp_CoTaskMemFree
0x1800070cd  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800070d2  mov     [rsp+4B0h+lpsz], rdi
0x1800070d7  test    rcx, rcx
0x1800070da  jz      short loc_1800070E2
0x1800070dc  call    cs:__imp_RegCloseKey
0x1800070e2  mov     eax, ebx
0x1800070e4  mov     rcx, [rbp+3B0h+var_30]
0x1800070eb  xor     rcx, rsp; StackCookie
0x1800070ee  call    __security_check_cookie
0x1800070f3  add     rsp, 498h
0x1800070fa  pop     rdi
0x1800070fb  pop     rsi
0x1800070fc  pop     rbx
0x1800070fd  pop     rbp
0x1800070fe  retn
```
