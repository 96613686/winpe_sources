# _anonymous_namespace_::com_content::GetRuntimeClassName

- ea: `0x14003df90`
- end: `0x14003dfad`
- name: `_anonymous_namespace_::com_content::GetRuntimeClassName`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003dfa6`

## string_xrefs

- `0x14003df97`: `Windows.Internal.Security.SmartScreen.HtmlContentInfo`

## pseudocode

```c
HRESULT __fastcall anonymous_namespace_::com_content::GetRuntimeClassName(__int64 a1, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.HtmlContentInfo", 0x35u, a2);
}

```

## disassembly

```asm
0x14003df90  mov     qword ptr [rdx], 0
0x14003df97  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_HtmlContentInfo@@3QBGB; "Windows.Internal.Security.SmartScreen.H"...
0x14003df9e  mov     r8, rdx
0x14003dfa1  mov     edx, 35h ; '5'
0x14003dfa6  jmp     cs:__imp_WindowsCreateString
```
