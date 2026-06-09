# Windows::Internal::Notifications::CToastActivator_AppLaunch::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180026e90`
- end: `0x180026ead`
- name: `?GetRuntimeClassName@CToastActivator_AppLaunch@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivator_AppLaunch *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026ec0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026ea6`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CToastActivator_AppLaunch::GetRuntimeClassName(
        Windows::Internal::Notifications::CToastActivator_AppLaunch *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.ToastActivator_AppLaunch", 0x37u, a2);
}

```

## disassembly

```asm
0x180026e90  mov     qword ptr [rdx], 0
0x180026e97  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivator_AppLaunch@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180026e9e  mov     r8, rdx
0x180026ea1  mov     edx, 37h ; '7'
0x180026ea6  jmp     cs:__imp_WindowsCreateString
```
