# Windows::Internal::Notifications::CAppInfoAggregator::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800286c0`
- end: `0x1800286dd`
- name: `?GetRuntimeClassName@CAppInfoAggregator@Notifications@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CAppInfoAggregator *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800286f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800286d6`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Notifications::CAppInfoAggregator::GetRuntimeClassName(
        Windows::Internal::Notifications::CAppInfoAggregator *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Notifications.WpnAppInfoAggregator", 0x33u, a2);
}

```

## disassembly

```asm
0x1800286c0  mov     qword ptr [rdx], 0
0x1800286c7  lea     rcx, ?RuntimeClass_Windows_Internal_Notifications_WpnAppInfoAggregator@@3QBGB; "Windows.Internal.Notifications.WpnAppIn"...
0x1800286ce  mov     r8, rdx
0x1800286d1  mov     edx, 33h ; '3'
0x1800286d6  jmp     cs:__imp_WindowsCreateString
```
