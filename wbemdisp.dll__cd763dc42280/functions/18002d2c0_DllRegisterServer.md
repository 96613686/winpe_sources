# DllRegisterServer

- ea: `0x18002d2c0`
- end: `0x18002d477`
- name: `DllRegisterServer`
- size: `439`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002d2c0`
- `0x18002d5b0`
- `0x18002dca4`
- `0x18002dd48`

## string_xrefs

- `0x18002d30d`: `WbemScripting.SWbemSink.1`
- `0x18002d319`: `WbemScripting.SWbemSink`
- `0x18002d370`: `Wbem Object Path 1.0`
- `0x18002d38a`: `Wbem Scripting Object Path`
- `0x18002d3a5`: `WBEM Scripting Object Path 1.0`
- `0x18002d3ac`: `WbemScripting.SWbemObjectPath.1`
- `0x18002d3b8`: `WbemScripting.SWbemObjectPath`
- `0x18002d3bf`: `WBEM Scripting Object Path`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax

  result = RegisterScriptSettings();
  if ( !result )
  {
    result = RegisterCoClass(
               &CLSID_SWbemLocator,
               (BYTE *)L"WBEM Scripting Locator",
               (BYTE *)L"WbemScripting.SWbemLocator",
               (BYTE *)L"WbemScripting.SWbemLocator.1");
    if ( !result )
    {
      result = RegisterCoClass(
                 &CLSID_SWbemSink,
                 (BYTE *)L"WBEM Scripting Sink",
                 (BYTE *)L"WbemScripting.SWbemSink",
                 (BYTE *)L"WbemScripting.SWbemSink.1");
      if ( !result )
      {
        result = RegisterCoClass(
                   &CLSID_SWbemNamedValueSet,
                   (BYTE *)L"WBEM Scripting Named Value Collection",
                   (BYTE *)L"WbemScripting.SWbemNamedValueSet",
                   (BYTE *)L"WbemScripting.SWbemNamedValueSet.1");
        if ( !result )
        {
          result = RegisterCoClass(
                     &CLSID_SWbemParseDN,
                     (BYTE *)L"Wbem Scripting Object Path",
                     (BYTE *)L"WINMGMTS",
                     (BYTE *)L"WINMGMTS.1");
          if ( !result )
          {
            result = RegisterCoClass(
                       &CLSID_SWbemObjectPath,
                       (BYTE *)L"WBEM Scripting Object Path",
                       (BYTE *)L"WbemScripting.SWbemObjectPath",
                       (BYTE *)L"WbemScripting.SWbemObjectPath.1");
            if ( !result )
            {
              result = RegisterCoClass(
                         &CLSID_SWbemLastError,
                         (BYTE *)L"Wbem Scripting Last Error",
                         (BYTE *)L"WbemScripting.SWbemLastError",
                         (BYTE *)L"WbemScripting.SWbemLastError.1");
              if ( !result )
              {
                result = RegisterCoClass(
                           &CLSID_SWbemDateTime,
                           (BYTE *)L"WBEM Scripting DateTime",
                           (BYTE *)L"WbemScripting.SWbemDateTime",
                           (BYTE *)L"WbemScripting.SWbemDateTime.1");
                if ( !result )
                {
                  result = RegisterCoClass(
                             &CLSID_SWbemRefresher,
                             (BYTE *)L"WBEM Scripting Refresher",
                             (BYTE *)L"WbemScripting.SWbemRefresher",
                             (BYTE *)L"WbemScripting.SWbemRefresher.1");
                  if ( !result )
                    return RegisterTypeLibrary();
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d2c0  sub     rsp, 38h
0x18002d2c4  call    RegisterScriptSettings
0x18002d2c9  test    eax, eax
0x18002d2cb  jnz     loc_18002D472
0x18002d2d1  lea     rax, aWbemScriptingL_0; "WBEM Scripting Locator 1.0"
0x18002d2d8  lea     r9, aWbemscriptingS_12; "WbemScripting.SWbemLocator.1"
0x18002d2df  mov     [rsp+38h+var_10], rax; __int64
0x18002d2e4  lea     r8, aWbemscriptingS_1; "WbemScripting.SWbemLocator"
0x18002d2eb  lea     rdx, aWbemScriptingL; "WBEM Scripting Locator"
0x18002d2f2  lea     rcx, CLSID_SWbemLocator; rguid
0x18002d2f9  call    RegisterCoClass
0x18002d2fe  test    eax, eax
0x18002d300  jnz     loc_18002D472
0x18002d306  lea     rax, aWbemScriptingS_0; "WBEM Scripting Sink 1.0"
0x18002d30d  lea     r9, aWbemscriptingS_7; "WbemScripting.SWbemSink.1"
0x18002d314  mov     [rsp+38h+var_10], rax; __int64
0x18002d319  lea     r8, aWbemscriptingS_3; "WbemScripting.SWbemSink"
0x18002d320  lea     rdx, aWbemScriptingS; "WBEM Scripting Sink"
0x18002d327  lea     rcx, CLSID_SWbemSink; rguid
0x18002d32e  call    RegisterCoClass
0x18002d333  test    eax, eax
0x18002d335  jnz     loc_18002D472
0x18002d33b  lea     rax, aWbemScriptingN; "WBEM Scripting Named Value Collection 1"...
0x18002d342  lea     r9, aWbemscriptingS_4; "WbemScripting.SWbemNamedValueSet.1"
0x18002d349  mov     [rsp+38h+var_10], rax; __int64
0x18002d34e  lea     r8, aWbemscriptingS_5; "WbemScripting.SWbemNamedValueSet"
0x18002d355  lea     rdx, aWbemScriptingN_0; "WBEM Scripting Named Value Collection"
0x18002d35c  lea     rcx, CLSID_SWbemNamedValueSet; rguid
0x18002d363  call    RegisterCoClass
0x18002d368  test    eax, eax
0x18002d36a  jnz     loc_18002D472
0x18002d370  lea     rax, aWbemObjectPath; "Wbem Object Path 1.0"
0x18002d377  lea     r9, aWinmgmts1; "WINMGMTS.1"
0x18002d37e  mov     [rsp+38h+var_10], rax; __int64
0x18002d383  lea     r8, aWinmgmts; "WINMGMTS"
0x18002d38a  lea     rdx, aWbemScriptingO_0; "Wbem Scripting Object Path"
0x18002d391  lea     rcx, CLSID_SWbemParseDN; rguid
0x18002d398  call    RegisterCoClass
0x18002d39d  test    eax, eax
0x18002d39f  jnz     loc_18002D472
0x18002d3a5  lea     rax, aWbemScriptingO_1; "WBEM Scripting Object Path 1.0"
0x18002d3ac  lea     r9, aWbemscriptingS_0; "WbemScripting.SWbemObjectPath.1"
0x18002d3b3  mov     [rsp+38h+var_10], rax; __int64
0x18002d3b8  lea     r8, aWbemscriptingS_11; "WbemScripting.SWbemObjectPath"
0x18002d3bf  lea     rdx, aWbemScriptingO; "WBEM Scripting Object Path"
0x18002d3c6  lea     rcx, CLSID_SWbemObjectPath; rguid
0x18002d3cd  call    RegisterCoClass
0x18002d3d2  test    eax, eax
0x18002d3d4  jnz     loc_18002D472
0x18002d3da  lea     rax, aWbemLastError1; "Wbem Last Error 1.0"
0x18002d3e1  lea     r9, aWbemscriptingS_6; "WbemScripting.SWbemLastError.1"
0x18002d3e8  mov     [rsp+38h+var_10], rax; __int64
0x18002d3ed  lea     r8, aWbemscriptingS_2; "WbemScripting.SWbemLastError"
0x18002d3f4  lea     rdx, aWbemScriptingL_1; "Wbem Scripting Last Error"
0x18002d3fb  lea     rcx, CLSID_SWbemLastError; rguid
0x18002d402  call    RegisterCoClass
0x18002d407  test    eax, eax
0x18002d409  jnz     short loc_18002D472
0x18002d40b  lea     rax, aWbemScriptingD_0; "WBEM Scripting DateTime 1.0"
0x18002d412  lea     r9, aWbemscriptingS_8; "WbemScripting.SWbemDateTime.1"
0x18002d419  mov     [rsp+38h+var_10], rax; __int64
0x18002d41e  lea     r8, aWbemscriptingS_10; "WbemScripting.SWbemDateTime"
0x18002d425  lea     rdx, aWbemScriptingD; "WBEM Scripting DateTime"
0x18002d42c  lea     rcx, CLSID_SWbemDateTime; rguid
0x18002d433  call    RegisterCoClass
0x18002d438  test    eax, eax
0x18002d43a  jnz     short loc_18002D472
0x18002d43c  lea     rax, aWbemScriptingR_0; "WBEM Scripting Refresher 1.0"
0x18002d443  lea     r9, aWbemscriptingS; "WbemScripting.SWbemRefresher.1"
0x18002d44a  mov     [rsp+38h+var_10], rax; __int64
0x18002d44f  lea     r8, aWbemscriptingS_9; "WbemScripting.SWbemRefresher"
0x18002d456  lea     rdx, aWbemScriptingR; "WBEM Scripting Refresher"
0x18002d45d  lea     rcx, CLSID_SWbemRefresher; rguid
0x18002d464  call    RegisterCoClass
0x18002d469  test    eax, eax
0x18002d46b  jnz     short loc_18002D472
0x18002d46d  call    RegisterTypeLibrary
0x18002d472  add     rsp, 38h
0x18002d476  retn
```
