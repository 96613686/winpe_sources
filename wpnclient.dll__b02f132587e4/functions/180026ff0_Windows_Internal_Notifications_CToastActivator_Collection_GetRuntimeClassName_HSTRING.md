# Windows::Internal::Notifications::CToastActivator_Collection::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180026ff0`
- end: `0x18002700d`
- name: `?GetRuntimeClassName@CToastActivator_Collection@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivator_Collection *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027006`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CToastActivator_Collection::GetRuntimeClassName(
        Windows::Internal::Notifications::CToastActivator_Collection *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.ToastActivator_Collection", 0x38u, a2);
}

```

## disassembly

```asm
0x180026ff0  mov     qword ptr [rdx], 0
0x180026ff7  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivator_Collection@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180026ffe  mov     r8, rdx
0x180027001  mov     edx, 38h ; '8'
0x180027006  jmp     cs:__imp_WindowsCreateString
```
