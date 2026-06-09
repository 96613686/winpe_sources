# SetCoInstall(void)

- ea: `0x18008f6dc`
- end: `0x18008f83b`
- name: `?SetCoInstall@@YAJXZ`
- size: `351`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a694`
- `0x1800bc5c0`

## callees

- `0x18008f6dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008f827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008f827`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008f6f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008f6f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008f7ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008f7ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008f742`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008f742`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18008f776`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18008f776`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f7a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f7ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f7a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008f7ae`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008f7cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18008f7cd`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18008f80d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18008f80d`

## string_xrefs

- `0x18008f757`: `UseCoInstall`
- `0x18008f7c6`: `ole32.dll`
- `0x18008f7e5`: `CoInstall`

## pseudocode

```c
__int64 SetCoInstall(void)
{
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  EnterCriticalSection(&g_mxsCodeDownloadGlobals);
  if ( !g_bCheckedForCoInstall && !Ptr )
  {
    g_bCheckedForCoInstall = 1;
    if ( !RegOpenKeyExA(
            HKEY_LOCAL_MACHINE,
            "Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
            0,
            0x20019u,
            &hKey) )
    {
      if ( RegQueryValueExA(hKey, "UseCoInstall", 0, 0, 0, 0) )
      {
        g_bUseOLECoInstall = 0;
        Ptr = 0;
        RegCloseKey(hKey);
        goto LABEL_11;
      }
      RegCloseKey(hKey);
    }
    LibraryA = qword_18016B5B8;
    if ( qword_18016B5B8 || (LibraryA = LoadLibraryA("ole32.dll"), (qword_18016B5B8 = LibraryA) != 0) )
    {
      ProcAddress = GetProcAddress(LibraryA, "CoInstall");
      if ( ProcAddress )
      {
        g_bUseOLECoInstall = 1;
        Ptr = EncodePointer(ProcAddress);
      }
    }
  }
LABEL_11:
  LeaveCriticalSection(&g_mxsCodeDownloadGlobals);
  return 0;
}

```

## disassembly

```asm
0x18008f6dc  sub     rsp, 38h
0x18008f6e0  lea     rcx, ?g_mxsCodeDownloadGlobals@@3VCMutexSem@@A; lpCriticalSection
0x18008f6e7  mov     [rsp+38h+hKey], 0
0x18008f6f0  call    cs:__imp_EnterCriticalSection
0x18008f6f7  nop     dword ptr [rax+rax+00h]
0x18008f6fc  cmp     cs:?g_bCheckedForCoInstall@@3HA, 0; int g_bCheckedForCoInstall
0x18008f703  jnz     loc_18008F820
0x18008f709  cmp     cs:Ptr, 0
0x18008f711  jnz     loc_18008F820
0x18008f717  lea     rax, [rsp+38h+hKey]
0x18008f71c  mov     cs:?g_bCheckedForCoInstall@@3HA, 1; int g_bCheckedForCoInstall
0x18008f726  mov     r9d, 20019h; samDesired
0x18008f72c  mov     [rsp+38h+phkResult], rax; phkResult
0x18008f731  xor     r8d, r8d; ulOptions
0x18008f734  lea     rdx, aSoftwareMicros_61; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18008f73b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008f742  call    cs:__imp_RegOpenKeyExA
0x18008f749  nop     dword ptr [rax+rax+00h]
0x18008f74e  test    eax, eax
0x18008f750  jnz     short loc_18008F7BA
0x18008f752  mov     rcx, [rsp+38h+hKey]; hKey
0x18008f757  lea     rdx, aUsecoinstall; "UseCoInstall"
0x18008f75e  mov     [rsp+38h+lpcbData], 0; lpcbData
0x18008f767  xor     r9d, r9d; lpType
0x18008f76a  xor     r8d, r8d; lpReserved
0x18008f76d  mov     [rsp+38h+phkResult], 0; lpData
0x18008f776  call    cs:__imp_RegQueryValueExA
0x18008f77d  nop     dword ptr [rax+rax+00h]
0x18008f782  mov     rcx, [rsp+38h+hKey]; hKey
0x18008f787  test    eax, eax
0x18008f789  jz      short loc_18008F7AE
0x18008f78b  mov     cs:?g_bUseOLECoInstall@@3HA, 0; int g_bUseOLECoInstall
0x18008f795  mov     cs:Ptr, 0
0x18008f7a0  call    cs:__imp_RegCloseKey
0x18008f7a7  nop     dword ptr [rax+rax+00h]
0x18008f7ac  jmp     short loc_18008F820
0x18008f7ae  call    cs:__imp_RegCloseKey
0x18008f7b5  nop     dword ptr [rax+rax+00h]
0x18008f7ba  mov     rax, cs:qword_18016B5B8
0x18008f7c1  test    rax, rax
0x18008f7c4  jnz     short loc_18008F7E5
0x18008f7c6  lea     rcx, aOle32Dll; "ole32.dll"
0x18008f7cd  call    cs:__imp_LoadLibraryA
0x18008f7d4  nop     dword ptr [rax+rax+00h]
0x18008f7d9  mov     cs:qword_18016B5B8, rax
0x18008f7e0  test    rax, rax
0x18008f7e3  jz      short loc_18008F820
0x18008f7e5  lea     rdx, aCoinstall_0; "CoInstall"
0x18008f7ec  mov     rcx, rax; hModule
0x18008f7ef  call    cs:__imp_GetProcAddress
0x18008f7f6  nop     dword ptr [rax+rax+00h]
0x18008f7fb  test    rax, rax
0x18008f7fe  jz      short loc_18008F820
0x18008f800  mov     rcx, rax; Ptr
0x18008f803  mov     cs:?g_bUseOLECoInstall@@3HA, 1; int g_bUseOLECoInstall
0x18008f80d  call    cs:__imp_EncodePointer
0x18008f814  nop     dword ptr [rax+rax+00h]
0x18008f819  mov     cs:Ptr, rax
0x18008f820  lea     rcx, ?g_mxsCodeDownloadGlobals@@3VCMutexSem@@A; lpCriticalSection
0x18008f827  call    cs:__imp_LeaveCriticalSection
0x18008f82e  nop     dword ptr [rax+rax+00h]
0x18008f833  xor     eax, eax
0x18008f835  add     rsp, 38h
0x18008f839  retn
```
