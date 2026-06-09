# DllUnregisterServer

- ea: `0x18003ccf0`
- end: `0x18003cd2e`
- name: `DllUnregisterServer`
- size: `62`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18003cc14`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003cd07`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003cd1b`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003cd07`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18003cd1b`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18003ccfa`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18003ccfa`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // eax
  HRESULT v2; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CBuilderModule>::UnregisterServer();
  v2 = 0;
  if ( v1 < 0 )
    v2 = v1;
  SetThreadLocale(ThreadLocale);
  return v2;
}

```

## disassembly

```asm
0x18003ccf0  mov     [rsp+arg_0], rbx
0x18003ccf5  push    rdi
0x18003ccf6  sub     rsp, 20h
0x18003ccfa  call    cs:__imp_GetThreadLocale
0x18003cd00  mov     ecx, 800h; Locale
0x18003cd05  mov     edi, eax
0x18003cd07  call    cs:__imp_SetThreadLocale
0x18003cd0d  call    ?UnregisterServer@?$CAtlModuleT@VCBuilderModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CBuilderModule>::UnregisterServer(int,_GUID const *)
0x18003cd12  xor     ebx, ebx
0x18003cd14  mov     ecx, edi; Locale
0x18003cd16  test    eax, eax
0x18003cd18  cmovs   ebx, eax
0x18003cd1b  call    cs:__imp_SetThreadLocale
0x18003cd21  mov     eax, ebx
0x18003cd23  mov     rbx, [rsp+28h+arg_0]
0x18003cd28  add     rsp, 20h
0x18003cd2c  pop     rdi
0x18003cd2d  retn
```
