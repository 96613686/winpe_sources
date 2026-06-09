# Windows::Internal::Notifications::CToastActivator_Protocol::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180026ce0`
- end: `0x180026cfd`
- name: `?GetRuntimeClassName@CToastActivator_Protocol@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CToastActivator_Protocol *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180026d10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180026cf6`

## string_xrefs

- `0x180026ce7`: `Windows.Internal.Notifications.ToastActivator_Protocol`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CToastActivator_Protocol::GetRuntimeClassName(
        Windows::Internal::Notifications::CToastActivator_Protocol *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.ToastActivator_Protocol", 0x36u, a2);
}

```

## disassembly

```asm
0x180026ce0  mov     qword ptr [rdx], 0
0x180026ce7  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_ToastActivator_Protocol@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180026cee  mov     r8, rdx
0x180026cf1  mov     edx, 36h ; '6'
0x180026cf6  jmp     cs:__imp_WindowsCreateString
```
