# _anonymous_namespace_::com_button::GetRuntimeClassName

- ea: `0x14003df60`
- end: `0x14003df7d`
- name: `_anonymous_namespace_::com_button::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003df76`

## string_xrefs

- `0x14003df67`: `Windows.Internal.Security.SmartScreen.ButtonInfo`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::com_button::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.ButtonInfo", 0x30u, a2);
}

```

## disassembly

```asm
0x14003df60  mov     qword ptr [rdx], 0
0x14003df67  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_ButtonInfo@@3QBGB; "Windows.Internal.Security.SmartScreen.B"...
0x14003df6e  mov     r8, rdx
0x14003df71  mov     edx, 30h ; '0'
0x14003df76  jmp     cs:__imp_WindowsCreateString
```
