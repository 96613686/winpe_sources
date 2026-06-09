# CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllUnregisterServer(void)

- ea: `0x180003600`
- end: `0x1800037a0`
- name: `?DllUnregisterServer@?$CWinTaskModuleT@VCUsbCeipTask@@$1?CLSID_UsbCeipTask@@3U_GUID@@B@@QEAAJXZ`
- size: `416`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003c60`

## callees

- `0x180002410`
- `0x180002e6e`
- `0x180003600`
- `0x180003a80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000365b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000365b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800036f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800036f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003760`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800036df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003745`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800036df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003745`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003720`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800036af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003720`

## string_xrefs

- `0x180003670`: `CLSID\\%s`
- `0x180003712`: `CLSID`

## pseudocode

```c
__int64 CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllUnregisterServer()
{
  int v0; // ebx
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  v0 = StringFromCLSID(&CLSID_UsbCeipTask, &lpsz);
  if ( v0 >= 0 )
  {
    v0 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s", lpsz);
    if ( v0 >= 0 )
    {
      v1 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey);
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
      if ( v0 >= 0 )
      {
        v2 = RegDeleteKeyExW(hKey, L"InprocServer32", 0, 0);
        v0 = v2;
        if ( v2 > 0 )
          v0 = (unsigned __int16)v2 | 0x80070000;
        if ( v0 >= 0 )
        {
          RegCloseKey(hKey);
          v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2000000u, &hKey);
          v0 = v3;
          if ( v3 > 0 )
            v0 = (unsigned __int16)v3 | 0x80070000;
          if ( v0 >= 0 )
          {
            v4 = RegDeleteKeyExW(hKey, lpsz, 0, 0);
            v0 = v4;
            if ( v4 > 0 )
              v0 = (unsigned __int16)v4 | 0x80070000;
          }
        }
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CoTaskMemFree(lpsz);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180003600  mov     [rsp-8+arg_0], rbx
0x180003605  mov     [rsp-8+arg_8], rsi
0x18000360a  push    rbp
0x18000360b  lea     rbp, [rsp-160h]
0x180003613  sub     rsp, 260h
0x18000361a  mov     rax, cs:__security_cookie
0x180003621  xor     rax, rsp
0x180003624  mov     [rbp+160h+var_10], rax
0x18000362b  xor     edx, edx; Val
0x18000362d  mov     [rsp+260h+hKey], 0
0x180003636  mov     r8d, 208h; Size
0x18000363c  lea     rcx, [rsp+260h+SubKey]; void *
0x180003641  call    memset_0
0x180003646  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000364b  mov     [rsp+260h+lpsz], 0
0x180003654  lea     rcx, CLSID_UsbCeipTask; rclsid
0x18000365b  call    cs:__imp_StringFromCLSID
0x180003661  mov     ebx, eax
0x180003663  test    eax, eax
0x180003665  js      loc_180003756
0x18000366b  mov     r9, [rsp+260h+lpsz]
0x180003670  lea     r8, aClsidS; "CLSID\\\\%s"
0x180003677  mov     edx, 104h; unsigned __int64
0x18000367c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180003681  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003686  mov     ebx, eax
0x180003688  test    eax, eax
0x18000368a  js      loc_180003756
0x180003690  lea     rax, [rsp+260h+hKey]
0x180003695  mov     r9d, 2000000h; samDesired
0x18000369b  xor     r8d, r8d; ulOptions
0x18000369e  mov     [rsp+260h+phkResult], rax; phkResult
0x1800036a3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1800036a8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800036af  call    cs:__imp_RegOpenKeyExW
0x1800036b5  mov     ebx, eax
0x1800036b7  mov     esi, 80070000h
0x1800036bc  test    eax, eax
0x1800036be  jle     short loc_1800036C5
0x1800036c0  movzx   ebx, ax
0x1800036c3  or      ebx, esi
0x1800036c5  test    ebx, ebx
0x1800036c7  js      loc_180003756
0x1800036cd  mov     rcx, [rsp+260h+hKey]; hKey
0x1800036d2  lea     rdx, SubKey; "InprocServer32"
0x1800036d9  xor     r9d, r9d; Reserved
0x1800036dc  xor     r8d, r8d; samDesired
0x1800036df  call    cs:__imp_RegDeleteKeyExW
0x1800036e5  mov     ebx, eax
0x1800036e7  test    eax, eax
0x1800036e9  jle     short loc_1800036F0
0x1800036eb  movzx   ebx, ax
0x1800036ee  or      ebx, esi
0x1800036f0  test    ebx, ebx
0x1800036f2  js      short loc_180003756
0x1800036f4  mov     rcx, [rsp+260h+hKey]; hKey
0x1800036f9  call    cs:__imp_RegCloseKey
0x1800036ff  lea     rax, [rsp+260h+hKey]
0x180003704  mov     r9d, 2000000h; samDesired
0x18000370a  xor     r8d, r8d; ulOptions
0x18000370d  mov     [rsp+260h+phkResult], rax; phkResult
0x180003712  lea     rdx, aClsid; "CLSID"
0x180003719  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003720  call    cs:__imp_RegOpenKeyExW
0x180003726  mov     ebx, eax
0x180003728  test    eax, eax
0x18000372a  jle     short loc_180003731
0x18000372c  movzx   ebx, ax
0x18000372f  or      ebx, esi
0x180003731  test    ebx, ebx
0x180003733  js      short loc_180003756
0x180003735  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000373a  xor     r9d, r9d; Reserved
0x18000373d  mov     rcx, [rsp+260h+hKey]; hKey
0x180003742  xor     r8d, r8d; samDesired
0x180003745  call    cs:__imp_RegDeleteKeyExW
0x18000374b  mov     ebx, eax
0x18000374d  test    eax, eax
0x18000374f  jle     short loc_180003756
0x180003751  movzx   ebx, ax
0x180003754  or      ebx, esi
0x180003756  mov     rcx, [rsp+260h+hKey]; hKey
0x18000375b  test    rcx, rcx
0x18000375e  jz      short loc_18000376F
0x180003760  call    cs:__imp_RegCloseKey
0x180003766  mov     [rsp+260h+hKey], 0
0x18000376f  mov     rcx, [rsp+260h+lpsz]; pv
0x180003774  call    cs:__imp_CoTaskMemFree
0x18000377a  mov     eax, ebx
0x18000377c  mov     rcx, [rbp+160h+var_10]
0x180003783  xor     rcx, rsp; StackCookie
0x180003786  call    __security_check_cookie
0x18000378b  lea     r11, [rsp+260h+var_s0]
0x180003793  mov     rbx, [r11+10h]
0x180003797  mov     rsi, [r11+18h]
0x18000379b  mov     rsp, r11
0x18000379e  pop     rbp
0x18000379f  retn
```
