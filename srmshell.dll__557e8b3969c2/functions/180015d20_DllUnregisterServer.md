# DllUnregisterServer

- ea: `0x180015d20`
- end: `0x180015d73`
- name: `DllUnregisterServer`
- size: `83`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015654`
- `0x180015d20`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015d37`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015d60`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015d37`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015d60`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180015d2a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180015d2a`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  const unsigned __int16 *v1; // rdx
  GUID *v2; // rcx
  struct ITypeLib *v3; // r8
  int v4; // eax
  HRESULT v5; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v4 = ATL::_pPerfUnRegFunc(), v4 >= 0) )
    v4 = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
  v5 = 0;
  if ( v4 < 0 )
    v5 = v4;
  SetThreadLocale(ThreadLocale);
  return v5;
}

```

## disassembly

```asm
0x180015d20  mov     [rsp+arg_0], rbx
0x180015d25  push    rdi
0x180015d26  sub     rsp, 20h
0x180015d2a  call    cs:__imp_GetThreadLocale
0x180015d30  mov     ecx, 800h; Locale
0x180015d35  mov     edi, eax
0x180015d37  call    cs:__imp_SetThreadLocale
0x180015d3d  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180015d44  test    rax, rax
0x180015d47  jz      short loc_180015D52
0x180015d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d4e  test    eax, eax
0x180015d50  js      short loc_180015D57
0x180015d52  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180015d57  xor     ebx, ebx
0x180015d59  mov     ecx, edi; Locale
0x180015d5b  test    eax, eax
0x180015d5d  cmovs   ebx, eax
0x180015d60  call    cs:__imp_SetThreadLocale
0x180015d66  mov     eax, ebx
0x180015d68  mov     rbx, [rsp+28h+arg_0]
0x180015d6d  add     rsp, 20h
0x180015d71  pop     rdi
0x180015d72  retn
```
