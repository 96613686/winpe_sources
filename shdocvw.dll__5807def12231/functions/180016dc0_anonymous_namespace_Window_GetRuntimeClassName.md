# _anonymous_namespace_::Window::GetRuntimeClassName

- ea: `0x180016dc0`
- end: `0x180016ddd`
- name: `_anonymous_namespace_::Window::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016dd6`

## string_xrefs

- `0x180016dc7`: `Windows.Internal.Security.SmartScreen.IWindow`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::Window::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.IWindow", 0x2Du, a2);
}

```

## disassembly

```asm
0x180016dc0  mov     qword ptr [rdx], 0
0x180016dc7  lea     rcx, ?InterfaceName_Windows_Internal_Security_SmartScreen_IWindow@@3QBGB; "Windows.Internal.Security.SmartScreen.I"...
0x180016dce  mov     r8, rdx
0x180016dd1  mov     edx, 2Dh ; '-'
0x180016dd6  jmp     cs:__imp_WindowsCreateString
```
