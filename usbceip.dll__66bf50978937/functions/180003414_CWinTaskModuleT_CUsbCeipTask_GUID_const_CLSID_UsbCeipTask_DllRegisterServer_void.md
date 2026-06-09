# CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllRegisterServer(void)

- ea: `0x180003414`
- end: `0x1800035f7`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCUsbCeipTask@@$1?CLSID_UsbCeipTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003c50`

## callees

- `0x180002410`
- `0x180002e6e`
- `0x180003414`
- `0x180003a80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800034b0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800034b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800035d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800035d4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000351b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000351b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000356b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000356b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000347c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000347c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000348b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000348b`

## string_xrefs

- `0x1800034c5`: `CLSID\\%s\InprocServer32`
- `0x180003594`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CUsbCeipTask,&_GUID const CLSID_UsbCeipTask>::DllRegisterServer()
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
  if ( GetModuleFileNameW((HMODULE)&_ImageBase, Filename, 0x104u) )
    goto LABEL_5;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v1 = StringFromCLSID(&CLSID_UsbCeipTask, &lpsz);
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
0x180003414  push    rbp
0x180003416  push    rbx
0x180003417  push    rsi
0x180003418  push    rdi
0x180003419  lea     rbp, [rsp-398h]
0x180003421  sub     rsp, 498h
0x180003428  mov     rax, cs:__security_cookie
0x18000342f  xor     rax, rsp
0x180003432  mov     [rbp+3B0h+var_30], rax
0x180003439  mov     ebx, 208h
0x18000343e  lea     rcx, [rsp+4B0h+Filename]; void *
0x180003443  xor     edi, edi
0x180003445  mov     r8d, ebx; Size
0x180003448  xor     edx, edx; Val
0x18000344a  mov     [rsp+4B0h+hKey], rdi
0x18000344f  call    memset_0
0x180003454  mov     r8d, ebx; Size
0x180003457  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000345e  xor     edx, edx; Val
0x180003460  call    memset_0
0x180003465  mov     r8d, 104h; nSize
0x18000346b  mov     [rsp+4B0h+lpsz], rdi
0x180003470  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180003475  lea     rcx, __ImageBase; hModule
0x18000347c  call    cs:__imp_GetModuleFileNameW
0x180003482  mov     esi, 80070000h
0x180003487  test    eax, eax
0x180003489  jnz     short loc_1800034A4
0x18000348b  call    cs:__imp_GetLastError
0x180003491  mov     ebx, eax
0x180003493  test    eax, eax
0x180003495  jle     short loc_18000349C
0x180003497  movzx   ebx, ax
0x18000349a  or      ebx, esi
0x18000349c  test    ebx, ebx
0x18000349e  js      loc_1800035BA
0x1800034a4  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800034a9  lea     rcx, CLSID_UsbCeipTask; rclsid
0x1800034b0  call    cs:__imp_StringFromCLSID
0x1800034b6  mov     ebx, eax
0x1800034b8  test    eax, eax
0x1800034ba  js      loc_1800035BA
0x1800034c0  mov     r9, [rsp+4B0h+lpsz]
0x1800034c5  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800034cc  mov     edx, 104h; unsigned __int64
0x1800034d1  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800034d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800034dd  mov     ebx, eax
0x1800034df  test    eax, eax
0x1800034e1  js      loc_1800035BA
0x1800034e7  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800034ec  lea     rax, [rsp+4B0h+hKey]
0x1800034f1  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800034f6  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x1800034fd  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003502  xor     r9d, r9d; lpClass
0x180003505  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18000350d  xor     r8d, r8d; Reserved
0x180003510  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003517  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18000351b  call    cs:__imp_RegCreateKeyExW
0x180003521  mov     ebx, eax
0x180003523  test    eax, eax
0x180003525  jle     short loc_18000352C
0x180003527  movzx   ebx, ax
0x18000352a  or      ebx, esi
0x18000352c  test    ebx, ebx
0x18000352e  js      loc_1800035BA
0x180003534  lea     rcx, [rsp+4B0h+Filename]
0x180003539  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000353d  inc     rax
0x180003540  cmp     [rcx+rax*2], di
0x180003544  jnz     short loc_18000353D
0x180003546  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000354b  lea     eax, ds:2[rax*2]
0x180003552  mov     [rsp+4B0h+samDesired], eax; cbData
0x180003556  mov     r9d, 1; dwType
0x18000355c  lea     rax, [rsp+4B0h+Filename]
0x180003561  xor     r8d, r8d; Reserved
0x180003564  xor     edx, edx; lpValueName
0x180003566  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000356b  call    cs:__imp_RegSetValueExW
0x180003571  mov     ebx, eax
0x180003573  test    eax, eax
0x180003575  jle     short loc_18000357C
0x180003577  movzx   ebx, ax
0x18000357a  or      ebx, esi
0x18000357c  test    ebx, ebx
0x18000357e  js      short loc_1800035BA
0x180003580  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003585  lea     rax, Data; "Both"
0x18000358c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180003594  lea     rdx, ValueName; "ThreadingModel"
0x18000359b  mov     r9d, 1; dwType
0x1800035a1  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800035a6  xor     r8d, r8d; Reserved
0x1800035a9  call    cs:__imp_RegSetValueExW
0x1800035af  mov     ebx, eax
0x1800035b1  test    eax, eax
0x1800035b3  jle     short loc_1800035BA
0x1800035b5  movzx   ebx, ax
0x1800035b8  or      ebx, esi
0x1800035ba  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800035bf  call    cs:__imp_CoTaskMemFree
0x1800035c5  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800035ca  mov     [rsp+4B0h+lpsz], rdi
0x1800035cf  test    rcx, rcx
0x1800035d2  jz      short loc_1800035DA
0x1800035d4  call    cs:__imp_RegCloseKey
0x1800035da  mov     eax, ebx
0x1800035dc  mov     rcx, [rbp+3B0h+var_30]
0x1800035e3  xor     rcx, rsp; StackCookie
0x1800035e6  call    __security_check_cookie
0x1800035eb  add     rsp, 498h
0x1800035f2  pop     rdi
0x1800035f3  pop     rsi
0x1800035f4  pop     rbx
0x1800035f5  pop     rbp
0x1800035f6  retn
```
