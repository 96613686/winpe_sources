# _anonymous_namespace_::com_notification::GetRuntimeClassName

- ea: `0x14003f6d0`
- end: `0x14003f6ed`
- name: `_anonymous_namespace_::com_notification::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003f6e6`

## string_xrefs

- `0x14003f6d7`: `Windows.Internal.Security.SmartScreen.PopupButtonInfo`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::com_notification::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.PopupButtonInfo", 0x35u, a2);
}

```

## disassembly

```asm
0x14003f6d0  mov     qword ptr [rdx], 0
0x14003f6d7  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_PopupButtonInfo@@3QBGB; "Windows.Internal.Security.SmartScreen.P"...
0x14003f6de  mov     r8, rdx
0x14003f6e1  mov     edx, 35h ; '5'
0x14003f6e6  jmp     cs:__imp_WindowsCreateString
```
