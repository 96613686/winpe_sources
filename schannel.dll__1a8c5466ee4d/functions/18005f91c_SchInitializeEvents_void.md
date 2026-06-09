# SchInitializeEvents(void)

- ea: `0x18005f91c`
- end: `0x18005fa81`
- name: `?SchInitializeEvents@@YAKXZ`
- size: `357`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025c38`
- `0x18005f1e4`

## callees

- `0x18005f8b8`
- `0x18005f91c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f9fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005f9fa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f974`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005f974`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005f9b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005f9e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005f9b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005f9e4`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005f9ef`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005f9ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fa0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005fa0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fa4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fa4d`
- `ntdll!EtwEventRegister` at `0x18005fa66`
- `ntdll!EtwEventRegister` at `0x18005fa66`

## string_xrefs

- `0x18005f94b`: `System\CurrentControlSet\Services\EventLog\System\Schannel`
- `0x18005f98e`: `%SystemRoot%\system32\lsasrv.dll`
- `0x18005fa03`: `lsasrv.dll`

## pseudocode

```c
LSTATUS SchInitializeEvents(void)
{
  LSTATUS result; // eax
  HMODULE Library; // rax
  HMODULE v2; // rbx
  DWORD Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  Data = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\EventLog\\System\\Schannel",
             0,
             (LPWSTR)&Class,
             0,
             0x20006u,
             0,
             &hKey,
             &Data);
  if ( !result )
  {
    if ( Data == 1 )
    {
      RegSetValueExW(hKey, L"EventMessageFile", 0, 2u, L"%SystemRoot%\\system32\\lsasrv.dll", 0x42u);
      Data = 7;
      RegSetValueExW(hKey, L"TypesSupported", 0, 4u, (const BYTE *)&Data, 4u);
      RegFlushKey(hKey);
    }
    RegCloseKey(hKey);
    Library = LoadLibraryExW(L"lsasrv.dll", 0, 0);
    v2 = Library;
    if ( Library )
    {
      SchGetMessageString(Library, 0x80009080, (LPWSTR)&pszClientString);
      SchGetMessageString(v2, 0x80009081, (LPWSTR)&pszServerString);
      FreeLibrary(v2);
      result = EtwEventRegister(S_Microsoft_Windows_Schannel, 0, 0, &g_RegistrationHandle);
      if ( result )
        g_RegistrationHandle = 0;
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005f91c  mov     r11, rsp
0x18005f91f  push    rbx
0x18005f920  sub     rsp, 50h
0x18005f924  lea     rax, [r11+8]
0x18005f928  mov     qword ptr [r11+10h], 0
0x18005f930  mov     [r11-18h], rax
0x18005f934  lea     r9, Class; lpClass
0x18005f93b  lea     rax, [r11+10h]
0x18005f93f  mov     [rsp+58h+Data], 0
0x18005f947  mov     [r11-20h], rax
0x18005f94b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ev"...
0x18005f952  mov     qword ptr [r11-28h], 0
0x18005f95a  xor     r8d, r8d; Reserved
0x18005f95d  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18005f965  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f96c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18005f974  call    cs:__imp_RegCreateKeyExW
0x18005f97a  test    eax, eax
0x18005f97c  jnz     loc_18005FA7B
0x18005f982  cmp     [rsp+58h+Data], 1
0x18005f987  jnz     short loc_18005F9F5
0x18005f989  mov     rcx, [rsp+58h+hKey]; hKey
0x18005f98e  lea     rax, Data; "%SystemRoot%\\system32\\lsasrv.dll"
0x18005f995  mov     [rsp+58h+samDesired], 42h ; 'B'; cbData
0x18005f99d  lea     rdx, aEventmessagefi; "EventMessageFile"
0x18005f9a4  mov     r9d, 2; dwType
0x18005f9aa  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18005f9af  xor     r8d, r8d; Reserved
0x18005f9b2  call    cs:__imp_RegSetValueExW
0x18005f9b8  mov     rcx, [rsp+58h+hKey]; hKey
0x18005f9bd  lea     rax, [rsp+58h+Data]
0x18005f9c2  mov     r9d, 4; dwType
0x18005f9c8  mov     [rsp+58h+Data], 7
0x18005f9d0  mov     [rsp+58h+samDesired], r9d; cbData
0x18005f9d5  lea     rdx, aTypessupported; "TypesSupported"
0x18005f9dc  xor     r8d, r8d; Reserved
0x18005f9df  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18005f9e4  call    cs:__imp_RegSetValueExW
0x18005f9ea  mov     rcx, [rsp+58h+hKey]; hKey
0x18005f9ef  call    cs:__imp_RegFlushKey
0x18005f9f5  mov     rcx, [rsp+58h+hKey]; hKey
0x18005f9fa  call    cs:__imp_RegCloseKey
0x18005fa00  xor     r8d, r8d; dwFlags
0x18005fa03  lea     rcx, LibFileName; "lsasrv.dll"
0x18005fa0a  xor     edx, edx; hFile
0x18005fa0c  call    cs:__imp_LoadLibraryExW
0x18005fa12  mov     rbx, rax
0x18005fa15  test    rax, rax
0x18005fa18  jnz     short loc_18005FA22
0x18005fa1a  call    cs:__imp_GetLastError
0x18005fa20  jmp     short loc_18005FA7B
0x18005fa22  lea     r8, ?pszClientString@@3PEAGEA; lpBuffer
0x18005fa29  mov     edx, 80009080h; dwMessageId
0x18005fa2e  mov     rcx, rbx; lpSource
0x18005fa31  call    ?SchGetMessageString@@YAKPEAXKPEAPEAG@Z; SchGetMessageString(void *,ulong,ushort * *)
0x18005fa36  lea     r8, ?pszServerString@@3PEAGEA; lpBuffer
0x18005fa3d  mov     edx, 80009081h; dwMessageId
0x18005fa42  mov     rcx, rbx; lpSource
0x18005fa45  call    ?SchGetMessageString@@YAKPEAXKPEAPEAG@Z; SchGetMessageString(void *,ulong,ushort * *)
0x18005fa4a  mov     rcx, rbx; hLibModule
0x18005fa4d  call    cs:__imp_FreeLibrary
0x18005fa53  lea     r9, ?g_RegistrationHandle@@3_KA; unsigned __int64 g_RegistrationHandle
0x18005fa5a  xor     r8d, r8d
0x18005fa5d  xor     edx, edx
0x18005fa5f  lea     rcx, S_Microsoft_Windows_Schannel
0x18005fa66  call    cs:__imp_EtwEventRegister
0x18005fa6c  test    eax, eax
0x18005fa6e  jz      short loc_18005FA7B
0x18005fa70  mov     cs:?g_RegistrationHandle@@3_KA, 0; unsigned __int64 g_RegistrationHandle
0x18005fa7b  add     rsp, 50h
0x18005fa7f  pop     rbx
0x18005fa80  retn
```
