# com::event_logger::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x140038e20`
- end: `0x140038e3d`
- name: `?GetRuntimeClassName@event_logger@com@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(com::event_logger *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140038e36`

## string_xrefs

- `0x140038e27`: `Windows.Internal.Security.SmartScreen.EventLogger`

## pseudocode

```c
HRESULT __fastcall com::event_logger::GetRuntimeClassName(com::event_logger *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.EventLogger", 0x31u, a2);
}

```

## disassembly

```asm
0x140038e20  mov     qword ptr [rdx], 0
0x140038e27  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_EventLogger@@3QBGB; "Windows.Internal.Security.SmartScreen.E"...
0x140038e2e  mov     r8, rdx
0x140038e31  mov     edx, 31h ; '1'
0x140038e36  jmp     cs:__imp_WindowsCreateString
```
