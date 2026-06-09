# ToastActivationEventArgs::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180028760`
- end: `0x18002877d`
- name: `?GetRuntimeClassName@ToastActivationEventArgs@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(ToastActivationEventArgs *__hidden this, HSTRING *)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180028790`
- `0x1800287a0`
- `0x1800287b0`
- `0x1800287c0`
- `0x1800287e0`
- `0x180028800`
- `0x180028820`
- `0x180028840`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180028776`

## pseudocode

```c
HRESULT __fastcall ToastActivationEventArgs::GetRuntimeClassName(ToastActivationEventArgs *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.ApplicationModel.Activation.ToastNotificationActivatedEventArgs", 0x47u, a2);
}

```

## disassembly

```asm
0x180028760  mov     qword ptr [rdx], 0
0x180028767  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Activation_ToastNotificationActivatedEventArgs@@3QBGB; "Windows.ApplicationModel.Activation.Toa"...
0x18002876e  mov     r8, rdx
0x180028771  mov     edx, 47h ; 'G'
0x180028776  jmp     cs:__imp_WindowsCreateString
```
