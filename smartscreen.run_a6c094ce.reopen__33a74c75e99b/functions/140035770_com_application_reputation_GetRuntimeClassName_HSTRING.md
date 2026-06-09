# com::application_reputation::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x140035770`
- end: `0x14003578d`
- name: `?GetRuntimeClassName@application_reputation@com@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(com::application_reputation *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400357a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140035786`

## string_xrefs

- `0x140035777`: `Windows.Internal.Security.SmartScreen.AppReputationService`

## pseudocode

```c
HRESULT __fastcall com::application_reputation::GetRuntimeClassName(com::application_reputation *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.AppReputationService", 0x3Au, a2);
}

```

## disassembly

```asm
0x140035770  mov     qword ptr [rdx], 0
0x140035777  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_AppReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.A"...
0x14003577e  mov     r8, rdx
0x140035781  mov     edx, 3Ah ; ':'
0x140035786  jmp     cs:__imp_WindowsCreateString
```
