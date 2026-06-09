# CWinTaskModuleT<UnifiedConsentSyncTask,&_GUID const CLSID_UnifiedConsentSyncTask>::DllUnregisterServer(void)

- ea: `0x180007108`
- end: `0x1800072a8`
- name: `?DllUnregisterServer@?$CWinTaskModuleT@VUnifiedConsentSyncTask@@$1?CLSID_UnifiedConsentSyncTask@@3U_GUID@@B@@QEAAJXZ`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f420`

## callees

- `0x180002810`
- `0x180003384`
- `0x180007108`
- `0x18000d3b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007163`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000727c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000727c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007228`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007228`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800071e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000724d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800071e7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000724d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007201`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007268`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007201`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007268`

## string_xrefs

- `0x180007178`: `CLSID\\%s`
- `0x18000721a`: `CLSID`

## pseudocode

```c
__int64 CWinTaskModuleT<UnifiedConsentSyncTask,&_GUID const CLSID_UnifiedConsentSyncTask>::DllUnregisterServer()
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
  v0 = StringFromCLSID(&CLSID_UnifiedConsentSyncTask, &lpsz);
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
0x180007108  mov     [rsp-8+arg_0], rbx
0x18000710d  mov     [rsp-8+arg_8], rsi
0x180007112  push    rbp
0x180007113  lea     rbp, [rsp-160h]
0x18000711b  sub     rsp, 260h
0x180007122  mov     rax, cs:__security_cookie
0x180007129  xor     rax, rsp
0x18000712c  mov     [rbp+160h+var_10], rax
0x180007133  xor     edx, edx; Val
0x180007135  mov     [rsp+260h+hKey], 0
0x18000713e  mov     r8d, 208h; Size
0x180007144  lea     rcx, [rsp+260h+SubKey]; void *
0x180007149  call    memset_0
0x18000714e  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180007153  mov     [rsp+260h+lpsz], 0
0x18000715c  lea     rcx, CLSID_UnifiedConsentSyncTask; rclsid
0x180007163  call    cs:__imp_StringFromCLSID
0x180007169  mov     ebx, eax
0x18000716b  test    eax, eax
0x18000716d  js      loc_18000725E
0x180007173  mov     r9, [rsp+260h+lpsz]
0x180007178  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000717f  mov     edx, 104h; unsigned __int64
0x180007184  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180007189  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000718e  mov     ebx, eax
0x180007190  test    eax, eax
0x180007192  js      loc_18000725E
0x180007198  lea     rax, [rsp+260h+hKey]
0x18000719d  mov     r9d, 2000000h; samDesired
0x1800071a3  xor     r8d, r8d; ulOptions
0x1800071a6  mov     [rsp+260h+phkResult], rax; phkResult
0x1800071ab  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1800071b0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800071b7  call    cs:__imp_RegOpenKeyExW
0x1800071bd  mov     ebx, eax
0x1800071bf  mov     esi, 80070000h
0x1800071c4  test    eax, eax
0x1800071c6  jle     short loc_1800071CD
0x1800071c8  movzx   ebx, ax
0x1800071cb  or      ebx, esi
0x1800071cd  test    ebx, ebx
0x1800071cf  js      loc_18000725E
0x1800071d5  mov     rcx, [rsp+260h+hKey]; hKey
0x1800071da  lea     rdx, SubKey; "InprocServer32"
0x1800071e1  xor     r9d, r9d; Reserved
0x1800071e4  xor     r8d, r8d; samDesired
0x1800071e7  call    cs:__imp_RegDeleteKeyExW
0x1800071ed  mov     ebx, eax
0x1800071ef  test    eax, eax
0x1800071f1  jle     short loc_1800071F8
0x1800071f3  movzx   ebx, ax
0x1800071f6  or      ebx, esi
0x1800071f8  test    ebx, ebx
0x1800071fa  js      short loc_18000725E
0x1800071fc  mov     rcx, [rsp+260h+hKey]; hKey
0x180007201  call    cs:__imp_RegCloseKey
0x180007207  lea     rax, [rsp+260h+hKey]
0x18000720c  mov     r9d, 2000000h; samDesired
0x180007212  xor     r8d, r8d; ulOptions
0x180007215  mov     [rsp+260h+phkResult], rax; phkResult
0x18000721a  lea     rdx, aClsid; "CLSID"
0x180007221  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007228  call    cs:__imp_RegOpenKeyExW
0x18000722e  mov     ebx, eax
0x180007230  test    eax, eax
0x180007232  jle     short loc_180007239
0x180007234  movzx   ebx, ax
0x180007237  or      ebx, esi
0x180007239  test    ebx, ebx
0x18000723b  js      short loc_18000725E
0x18000723d  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180007242  xor     r9d, r9d; Reserved
0x180007245  mov     rcx, [rsp+260h+hKey]; hKey
0x18000724a  xor     r8d, r8d; samDesired
0x18000724d  call    cs:__imp_RegDeleteKeyExW
0x180007253  mov     ebx, eax
0x180007255  test    eax, eax
0x180007257  jle     short loc_18000725E
0x180007259  movzx   ebx, ax
0x18000725c  or      ebx, esi
0x18000725e  mov     rcx, [rsp+260h+hKey]; hKey
0x180007263  test    rcx, rcx
0x180007266  jz      short loc_180007277
0x180007268  call    cs:__imp_RegCloseKey
0x18000726e  mov     [rsp+260h+hKey], 0
0x180007277  mov     rcx, [rsp+260h+lpsz]; pv
0x18000727c  call    cs:__imp_CoTaskMemFree
0x180007282  mov     eax, ebx
0x180007284  mov     rcx, [rbp+160h+var_10]
0x18000728b  xor     rcx, rsp; StackCookie
0x18000728e  call    __security_check_cookie
0x180007293  lea     r11, [rsp+260h+var_s0]
0x18000729b  mov     rbx, [r11+10h]
0x18000729f  mov     rsi, [r11+18h]
0x1800072a3  mov     rsp, r11
0x1800072a6  pop     rbp
0x1800072a7  retn
```
