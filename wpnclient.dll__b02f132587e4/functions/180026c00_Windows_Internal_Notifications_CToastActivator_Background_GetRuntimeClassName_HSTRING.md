# Windows::Internal::Notifications::CToastActivator_Background::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180026c00`
- end: `0x180026c1d`
- name: `?GetRuntimeClassName@CToastActivator_Background@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivator_Background *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026c30`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026c16`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CToastActivator_Background::GetRuntimeClassName(
        Windows::Internal::Notifications::CToastActivator_Background *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.ToastActivator_Background", 0x38u, a2);
}

```

## disassembly

```asm
0x180026c00  mov     qword ptr [rdx], 0
0x180026c07  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivator_Background@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180026c0e  mov     r8, rdx
0x180026c11  mov     edx, 38h ; '8'
0x180026c16  jmp     cs:__imp_WindowsCreateString
```
