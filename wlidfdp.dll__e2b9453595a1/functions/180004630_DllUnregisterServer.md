# DllUnregisterServer

- ea: `0x180004630`
- end: `0x18000466e`
- name: `DllUnregisterServer`
- size: `62`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004494`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000463a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000463a`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004647`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000465b`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180004647`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000465b`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // eax
  HRESULT v2; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CPrincipalProviderLibModule>::UnregisterServer();
  v2 = 0;
  if ( v1 < 0 )
    v2 = v1;
  SetThreadLocale(ThreadLocale);
  return v2;
}

```

## disassembly

```asm
0x180004630  mov     [rsp+arg_0], rbx
0x180004635  push    rdi
0x180004636  sub     rsp, 20h
0x18000463a  call    cs:__imp_GetThreadLocale
0x180004640  mov     ecx, 800h; Locale
0x180004645  mov     edi, eax
0x180004647  call    cs:__imp_SetThreadLocale
0x18000464d  call    ?UnregisterServer@?$CAtlModuleT@VCPrincipalProviderLibModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CPrincipalProviderLibModule>::UnregisterServer(int,_GUID const *)
0x180004652  xor     ebx, ebx
0x180004654  mov     ecx, edi; Locale
0x180004656  test    eax, eax
0x180004658  cmovs   ebx, eax
0x18000465b  call    cs:__imp_SetThreadLocale
0x180004661  mov     eax, ebx
0x180004663  mov     rbx, [rsp+28h+arg_0]
0x180004668  add     rsp, 20h
0x18000466c  pop     rdi
0x18000466d  retn
```
