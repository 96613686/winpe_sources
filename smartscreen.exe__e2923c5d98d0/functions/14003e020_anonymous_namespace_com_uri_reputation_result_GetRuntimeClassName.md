# _anonymous_namespace_::com_uri_reputation_result::GetRuntimeClassName

- ea: `0x14003e020`
- end: `0x14003e03d`
- name: `_anonymous_namespace_::com_uri_reputation_result::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003e036`

## string_xrefs

- `0x14003e027`: `Windows.Internal.Security.SmartScreen.UriReputationResult`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::com_uri_reputation_result::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.UriReputationResult", 0x39u, a2);
}

```

## disassembly

```asm
0x14003e020  mov     qword ptr [rdx], 0
0x14003e027  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_UriReputationResult@@3QBGB; "Windows.Internal.Security.SmartScreen.U"...
0x14003e02e  mov     r8, rdx
0x14003e031  mov     edx, 39h ; '9'
0x14003e036  jmp     cs:__imp_WindowsCreateString
```
