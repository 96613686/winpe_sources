# DllRegisterServer

- ea: `0x18003ccb0`
- end: `0x18003cce9`
- name: `DllRegisterServer`
- size: `57`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18003cb6c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003ccc7`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003ccd6`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003ccc7`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003ccd6`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18003ccba`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18003ccba`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT v1; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CBuilderModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x18003ccb0  mov     [rsp+arg_0], rbx
0x18003ccb5  push    rdi
0x18003ccb6  sub     rsp, 20h
0x18003ccba  call    cs:__imp_GetThreadLocale
0x18003ccc0  mov     ecx, 800h; Locale
0x18003ccc5  mov     edi, eax
0x18003ccc7  call    cs:__imp_SetThreadLocale
0x18003cccd  call    ?RegisterServer@?$CAtlModuleT@VCBuilderModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CBuilderModule>::RegisterServer(int,_GUID const *)
0x18003ccd2  mov     ecx, edi; Locale
0x18003ccd4  mov     ebx, eax
0x18003ccd6  call    cs:__imp_SetThreadLocale
0x18003ccdc  mov     eax, ebx
0x18003ccde  mov     rbx, [rsp+28h+arg_0]
0x18003cce3  add     rsp, 20h
0x18003cce7  pop     rdi
0x18003cce8  retn
```
