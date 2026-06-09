# DllUnregisterServer

- ea: `0x180040190`
- end: `0x1800401e1`
- name: `DllUnregisterServer`
- size: `81`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004003c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800401ad`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800401c7`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800401ad`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x1800401c7`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004019a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004019a`

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
0x180040190  mov     [rsp+arg_0], rbx
0x180040195  push    rdi
0x180040196  sub     rsp, 20h
0x18004019a  call    cs:__imp_GetThreadLocale
0x1800401a1  nop     dword ptr [rax+rax+00h]
0x1800401a6  mov     ecx, 800h; Locale
0x1800401ab  mov     edi, eax
0x1800401ad  call    cs:__imp_SetThreadLocale
0x1800401b4  nop     dword ptr [rax+rax+00h]
0x1800401b9  call    ?UnregisterServer@?$CAtlModuleT@VCBuilderModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CBuilderModule>::UnregisterServer(int,_GUID const *)
0x1800401be  xor     ebx, ebx
0x1800401c0  mov     ecx, edi; Locale
0x1800401c2  test    eax, eax
0x1800401c4  cmovs   ebx, eax
0x1800401c7  call    cs:__imp_SetThreadLocale
0x1800401ce  nop     dword ptr [rax+rax+00h]
0x1800401d3  mov     eax, ebx
0x1800401d5  mov     rbx, [rsp+28h+arg_0]
0x1800401da  add     rsp, 20h
0x1800401de  pop     rdi
0x1800401df  retn
```
