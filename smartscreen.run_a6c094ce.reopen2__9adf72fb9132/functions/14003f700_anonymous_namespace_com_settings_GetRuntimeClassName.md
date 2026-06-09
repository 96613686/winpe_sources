# _anonymous_namespace_::com_settings::GetRuntimeClassName

- ea: `0x14003f700`
- end: `0x14003f71d`
- name: `_anonymous_namespace_::com_settings::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003f716`

## string_xrefs

- `0x14003f707`: `Windows.Internal.Security.SmartScreen.UriReputationSettings`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::com_settings::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.UriReputationSettings", 0x3Bu, a2);
}

```

## disassembly

```asm
0x14003f700  mov     qword ptr [rdx], 0
0x14003f707  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_UriReputationSettings@@3QBGB; "Windows.Internal.Security.SmartScreen.U"...
0x14003f70e  mov     r8, rdx
0x14003f711  mov     edx, 3Bh ; ';'
0x14003f716  jmp     cs:__imp_WindowsCreateString
```
