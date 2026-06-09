# Windows::Internal::Notifications::CWpnClient::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180028700`
- end: `0x18002871d`
- name: `?GetRuntimeClassName@CWpnClient@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CWpnClient *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180028730`
- `0x180028740`
- `0x180028750`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180028716`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CWpnClient::GetRuntimeClassName(
        Windows::Internal::Notifications::CWpnClient *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.WpnClient", 0x28u, a2);
}

```

## disassembly

```asm
0x180028700  mov     qword ptr [rdx], 0
0x180028707  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_WpnClient@@3QBGB; "Windows.Internal.Notifications.WpnClien"...
0x18002870e  mov     r8, rdx
0x180028711  mov     edx, 28h ; '('
0x180028716  jmp     cs:__imp_WindowsCreateString
```
