# Windows::Internal::Notifications::CAppInfoProvider_UWP::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800272c0`
- end: `0x1800272dd`
- name: `?GetRuntimeClassName@CAppInfoProvider_UWP@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CAppInfoProvider_UWP *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800272f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800272d6`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CAppInfoProvider_UWP::GetRuntimeClassName(
        Windows::Internal::Notifications::CAppInfoProvider_UWP *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.WpnAppInfoProvider_UWP", 0x35u, a2);
}

```

## disassembly

```asm
0x1800272c0  mov     qword ptr [rdx], 0
0x1800272c7  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_WpnAppInfoProvider_UWP@@3QBGB; "Windows.Internal.Notifications.WpnAppIn"...
0x1800272ce  mov     r8, rdx
0x1800272d1  mov     edx, 35h ; '5'
0x1800272d6  jmp     cs:__imp_WindowsCreateString
```
