# DllRegisterServer

- ea: `0x180040130`
- end: `0x18004017c`
- name: `DllRegisterServer`
- size: `76`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18003ff90`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18004014d`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180040162`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18004014d`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180040162`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004013a`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004013a`

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
0x180040130  mov     [rsp+arg_0], rbx
0x180040135  push    rdi
0x180040136  sub     rsp, 20h
0x18004013a  call    cs:__imp_GetThreadLocale
0x180040141  nop     dword ptr [rax+rax+00h]
0x180040146  mov     ecx, 800h; Locale
0x18004014b  mov     edi, eax
0x18004014d  call    cs:__imp_SetThreadLocale
0x180040154  nop     dword ptr [rax+rax+00h]
0x180040159  call    ?RegisterServer@?$CAtlModuleT@VCBuilderModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CBuilderModule>::RegisterServer(int,_GUID const *)
0x18004015e  mov     ecx, edi; Locale
0x180040160  mov     ebx, eax
0x180040162  call    cs:__imp_SetThreadLocale
0x180040169  nop     dword ptr [rax+rax+00h]
0x18004016e  mov     eax, ebx
0x180040170  mov     rbx, [rsp+28h+arg_0]
0x180040175  add     rsp, 20h
0x180040179  pop     rdi
0x18004017a  retn
```
