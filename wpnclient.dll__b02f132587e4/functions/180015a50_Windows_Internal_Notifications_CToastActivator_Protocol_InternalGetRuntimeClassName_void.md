# Windows::Internal::Notifications::CToastActivator_Protocol::InternalGetRuntimeClassName(void)

- ea: `0x180015a50`
- end: `0x180015a58`
- name: `?InternalGetRuntimeClassName@CToastActivator_Protocol@Notifications@Internal@Windows@@SAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x180015a50`: `Windows.Internal.Notifications.ToastActivator_Protocol`

## pseudocode

```c
const unsigned __int16 *Windows::Internal::Notifications::CToastActivator_Protocol::InternalGetRuntimeClassName(void)
{
  return L"Windows.Internal.Notifications.ToastActivator_Protocol";
}

```

## disassembly

```asm
0x180015a50  lea     rax, ?RuntimeClass_Windows_Internal_Notifications_ToastActivator_Protocol@@3QBGB; "Windows.Internal.Notifications.ToastAct"...
0x180015a57  retn
```
