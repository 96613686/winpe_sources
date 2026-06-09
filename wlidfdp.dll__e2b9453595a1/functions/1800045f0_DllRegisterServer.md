# DllRegisterServer

- ea: `0x1800045f0`
- end: `0x180004629`
- name: `DllRegisterServer`
- size: `57`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004314`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800045fa`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800045fa`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004607`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004616`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004607`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004616`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT v1; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CPrincipalProviderLibModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x1800045f0  mov     [rsp+arg_0], rbx
0x1800045f5  push    rdi
0x1800045f6  sub     rsp, 20h
0x1800045fa  call    cs:__imp_GetThreadLocale
0x180004600  mov     ecx, 800h; Locale
0x180004605  mov     edi, eax
0x180004607  call    cs:__imp_SetThreadLocale
0x18000460d  call    ?RegisterServer@?$CAtlModuleT@VCPrincipalProviderLibModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CPrincipalProviderLibModule>::RegisterServer(int,_GUID const *)
0x180004612  mov     ecx, edi; Locale
0x180004614  mov     ebx, eax
0x180004616  call    cs:__imp_SetThreadLocale
0x18000461c  mov     eax, ebx
0x18000461e  mov     rbx, [rsp+28h+arg_0]
0x180004623  add     rsp, 20h
0x180004627  pop     rdi
0x180004628  retn
```
