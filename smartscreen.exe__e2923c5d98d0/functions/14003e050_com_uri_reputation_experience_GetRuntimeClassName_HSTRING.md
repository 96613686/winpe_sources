# com::uri_reputation::experience::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x14003e050`
- end: `0x14003e06d`
- name: `?GetRuntimeClassName@experience@uri_reputation@com@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(com::uri_reputation::experience *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14003e066`

## string_xrefs

- `0x14003e057`: `Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo`

## pseudocode

```c
HRESULT __fastcall com::uri_reputation::experience::GetRuntimeClassName(
        com::uri_reputation::experience *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo", 0x41u, a2);
}

```

## disassembly

```asm
0x14003e050  mov     qword ptr [rdx], 0
0x14003e057  lea     rcx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_UriReputationExperienceInfo@@3QBGB; "Windows.Internal.Security.SmartScreen.U"...
0x14003e05e  mov     r8, rdx
0x14003e061  mov     edx, 41h ; 'A'
0x14003e066  jmp     cs:__imp_WindowsCreateString
```
