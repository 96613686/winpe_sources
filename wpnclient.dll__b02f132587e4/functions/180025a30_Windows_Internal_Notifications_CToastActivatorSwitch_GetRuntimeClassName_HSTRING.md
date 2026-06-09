# Windows::Internal::Notifications::CToastActivatorSwitch::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180025a30`
- end: `0x180025a4d`
- name: `?GetRuntimeClassName@CToastActivatorSwitch@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivatorSwitch *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180025a60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180025a46`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CToastActivatorSwitch::GetRuntimeClassName(
        Windows::Internal::Notifications::CToastActivatorSwitch *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.ToastActivatorSwitch", 0x33u, a2);
}

```

## disassembly

```asm
0x180025a30  mov     qword ptr [rdx], 0
0x180025a37  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivatorSwitch@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180025a3e  mov     r8, rdx
0x180025a41  mov     edx, 33h ; '3'
0x180025a46  jmp     cs:__imp_WindowsCreateString
```
