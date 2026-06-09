# Windows::Internal::Notifications::AdaptiveImage::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800239d0`
- end: `0x1800239ed`
- name: `?GetRuntimeClassName@AdaptiveImage@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::AdaptiveImage *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180023a00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800239e6`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::AdaptiveImage::GetRuntimeClassName(
        Windows::Internal::Notifications::AdaptiveImage *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.AdaptiveImage", 0x2Cu, a2);
}

```

## disassembly

```asm
0x1800239d0  mov     qword ptr [rdx], 0
0x1800239d7  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_AdaptiveImage@@3QBGB; "Windows.Internal.Notifications.Adaptive"...
0x1800239de  mov     r8, rdx
0x1800239e1  mov     edx, 2Ch ; ','
0x1800239e6  jmp     cs:__imp_WindowsCreateString
```
