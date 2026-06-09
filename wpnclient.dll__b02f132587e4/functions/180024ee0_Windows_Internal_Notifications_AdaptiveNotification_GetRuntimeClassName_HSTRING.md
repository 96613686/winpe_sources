# Windows::Internal::Notifications::AdaptiveNotification::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180024ee0`
- end: `0x180024efd`
- name: `?GetRuntimeClassName@AdaptiveNotification@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180024f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180024ef6`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::AdaptiveNotification::GetRuntimeClassName(
        Windows::Internal::Notifications::AdaptiveNotification *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.AdaptiveNotification", 0x33u, a2);
}

```

## disassembly

```asm
0x180024ee0  mov     qword ptr [rdx], 0
0x180024ee7  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_AdaptiveNotification@@3QBGB; "Windows.Internal.Notifications.Adaptive"...
0x180024eee  mov     r8, rdx
0x180024ef1  mov     edx, 33h ; '3'
0x180024ef6  jmp     cs:__imp_WindowsCreateString
```
