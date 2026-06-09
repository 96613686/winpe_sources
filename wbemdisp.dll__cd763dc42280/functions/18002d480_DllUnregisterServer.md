# DllUnregisterServer

- ea: `0x18002d480`
- end: `0x18002d5a8`
- name: `DllUnregisterServer`
- size: `296`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002ce6c`
- `0x18002d1b4`
- `0x18002d480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d4c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d4c1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d4a0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002d4a0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d4b6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002d4b6`

## string_xrefs

- `0x18002d4e1`: `WbemScripting.SWbemSink.1`
- `0x18002d4e8`: `WbemScripting.SWbemSink`
- `0x18002d52f`: `WbemScripting.SWbemObjectPath.1`
- `0x18002d536`: `WbemScripting.SWbemObjectPath`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rcx
  HKEY phkResult; // [rsp+30h] [rbp+8h] BYREF

  phkResult = 0;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wbem", &phkResult) )
  {
    RegDeleteKeyW(phkResult, L"Scripting");
    RegCloseKey(phkResult);
  }
  UnregisterCoClass(&CLSID_SWbemLocator, L"WbemScripting.SWbemLocator", L"WbemScripting.SWbemLocator.1");
  UnregisterCoClass(&CLSID_SWbemSink, L"WbemScripting.SWbemSink", L"WbemScripting.SWbemSink.1");
  UnregisterCoClass(
    &CLSID_SWbemNamedValueSet,
    L"WbemScripting.SWbemNamedValueSet",
    L"WbemScripting.SWbemNamedValueSet.1");
  UnregisterCoClass(&CLSID_SWbemLastError, L"WbemScripting.SWbemLastError", L"WbemScripting.SWbemLastError.1");
  UnregisterCoClass(&CLSID_SWbemObjectPath, L"WbemScripting.SWbemObjectPath", L"WbemScripting.SWbemObjectPath.1");
  UnregisterCoClass(&CLSID_SWbemParseDN, L"WINMGMTS", L"WINMGMTS.1");
  UnregisterCoClass(&CLSID_SWbemDateTime, L"WbemScripting.SWbemDateTime", L"WbemScripting.SWbemDateTime.1");
  UnregisterCoClass(&CLSID_SWbemRefresher, L"WbemScripting.SWbemRefresher", L"WbemScripting.SWbemRefresher.1");
  UnregisterTypeLibrary(v0, 2);
  return 0;
}

```

## disassembly

```asm
0x18002d480  sub     rsp, 28h
0x18002d484  lea     r8, [rsp+28h+phkResult]; phkResult
0x18002d489  mov     [rsp+28h+phkResult], 0
0x18002d492  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Wbem"
0x18002d499  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d4a0  call    cs:__imp_RegOpenKeyW
0x18002d4a6  test    eax, eax
0x18002d4a8  jnz     short loc_18002D4C7
0x18002d4aa  mov     rcx, [rsp+28h+phkResult]; hKey
0x18002d4af  lea     rdx, aScripting; "Scripting"
0x18002d4b6  call    cs:__imp_RegDeleteKeyW
0x18002d4bc  mov     rcx, [rsp+28h+phkResult]; hKey
0x18002d4c1  call    cs:__imp_RegCloseKey
0x18002d4c7  lea     r8, aWbemscriptingS_12; "WbemScripting.SWbemLocator.1"
0x18002d4ce  lea     rdx, aWbemscriptingS_1; "WbemScripting.SWbemLocator"
0x18002d4d5  lea     rcx, CLSID_SWbemLocator; rguid
0x18002d4dc  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d4e1  lea     r8, aWbemscriptingS_7; "WbemScripting.SWbemSink.1"
0x18002d4e8  lea     rdx, aWbemscriptingS_3; "WbemScripting.SWbemSink"
0x18002d4ef  lea     rcx, CLSID_SWbemSink; rguid
0x18002d4f6  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d4fb  lea     r8, aWbemscriptingS_4; "WbemScripting.SWbemNamedValueSet.1"
0x18002d502  lea     rdx, aWbemscriptingS_5; "WbemScripting.SWbemNamedValueSet"
0x18002d509  lea     rcx, CLSID_SWbemNamedValueSet; rguid
0x18002d510  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d515  lea     r8, aWbemscriptingS_6; "WbemScripting.SWbemLastError.1"
0x18002d51c  lea     rdx, aWbemscriptingS_2; "WbemScripting.SWbemLastError"
0x18002d523  lea     rcx, CLSID_SWbemLastError; rguid
0x18002d52a  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d52f  lea     r8, aWbemscriptingS_0; "WbemScripting.SWbemObjectPath.1"
0x18002d536  lea     rdx, aWbemscriptingS_11; "WbemScripting.SWbemObjectPath"
0x18002d53d  lea     rcx, CLSID_SWbemObjectPath; rguid
0x18002d544  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d549  lea     r8, aWinmgmts1; "WINMGMTS.1"
0x18002d550  lea     rdx, aWinmgmts; "WINMGMTS"
0x18002d557  lea     rcx, CLSID_SWbemParseDN; rguid
0x18002d55e  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d563  lea     r8, aWbemscriptingS_8; "WbemScripting.SWbemDateTime.1"
0x18002d56a  lea     rdx, aWbemscriptingS_10; "WbemScripting.SWbemDateTime"
0x18002d571  lea     rcx, CLSID_SWbemDateTime; rguid
0x18002d578  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d57d  lea     r8, aWbemscriptingS; "WbemScripting.SWbemRefresher.1"
0x18002d584  lea     rdx, aWbemscriptingS_9; "WbemScripting.SWbemRefresher"
0x18002d58b  lea     rcx, CLSID_SWbemRefresher; rguid
0x18002d592  call    ?UnregisterCoClass@@YAXAEBU_GUID@@PEBG1@Z; UnregisterCoClass(_GUID const &,ushort const *,ushort const *)
0x18002d597  mov     edx, 2
0x18002d59c  call    UnregisterTypeLibrary
0x18002d5a1  xor     eax, eax
0x18002d5a3  add     rsp, 28h
0x18002d5a7  retn
```
