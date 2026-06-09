# Windows::Internal::Notifications::CToastActivator_Foreground::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180026130`
- end: `0x18002614d`
- name: `?GetRuntimeClassName@CToastActivator_Foreground@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivator_Foreground *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026160`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026146`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CToastActivator_Foreground::GetRuntimeClassName(
        Windows::Internal::Notifications::CToastActivator_Foreground *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.ToastActivator_Foreground", 0x38u, a2);
}

```

## disassembly

```asm
0x180026130  mov     qword ptr [rdx], 0
0x180026137  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivator_Foreground@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x18002613e  mov     r8, rdx
0x180026141  mov     edx, 38h ; '8'
0x180026146  jmp     cs:__imp_WindowsCreateString
```
