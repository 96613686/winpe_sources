# com::uri_reputation::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x14003e080`
- end: `0x14003e09d`
- name: `?GetRuntimeClassName@uri_reputation@com@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(com::uri_reputation *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003e096`

## string_xrefs

- `0x14003e087`: `Windows.Internal.Security.SmartScreen.UriReputationService`

## pseudocode

```c
HRESULT __fastcall com::uri_reputation::GetRuntimeClassName(com::uri_reputation *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.UriReputationService", 0x3Au, a2);
}

```

## disassembly

```asm
0x14003e080  mov     qword ptr [rdx], 0
0x14003e087  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_UriReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.U"...
0x14003e08e  mov     r8, rdx
0x14003e091  mov     edx, 3Ah ; ':'
0x14003e096  jmp     cs:__imp_WindowsCreateString
```
