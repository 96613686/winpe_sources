# DllUnregisterServer

- ea: `0x180008ab0`
- end: `0x180008b4c`
- name: `DllUnregisterServer`
- size: `156`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800050c8`
- `0x1800085d4`
- `0x180008ab0`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180008aba`
- `KERNEL32!GetThreadLocale` at `0x180008aba`
- `KERNEL32!SetThreadLocale` at `0x180008acd`
- `KERNEL32!SetThreadLocale` at `0x180008b32`
- `KERNEL32!SetThreadLocale` at `0x180008acd`
- `KERNEL32!SetThreadLocale` at `0x180008b32`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // edx
  ATL::CAtlComModule *v2; // rcx
  const struct _GUID *v3; // r8
  HRESULT updated; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
    updated = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
  if ( updated >= 0 )
  {
    v6[0] = L"APPID";
    v6[1] = L"70F829DE-656F-4EA9-B6BD-7D092099429C";
    v7 = 0;
    updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, 0xC9u, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v6);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180008ab0  mov     [rsp+arg_0], rbx
0x180008ab5  push    rdi
0x180008ab6  sub     rsp, 40h
0x180008aba  call    cs:__imp_GetThreadLocale
0x180008ac1  nop     dword ptr [rax+rax+00h]
0x180008ac6  mov     ecx, 800h; Locale
0x180008acb  mov     edi, eax
0x180008acd  call    cs:__imp_SetThreadLocale
0x180008ad4  nop     dword ptr [rax+rax+00h]
0x180008ad9  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180008ae0  test    rax, rax
0x180008ae3  jz      short loc_180008AF0
0x180008ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aea  mov     ebx, eax
0x180008aec  test    eax, eax
0x180008aee  js      short loc_180008AF7
0x180008af0  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180008af5  mov     ebx, eax
0x180008af7  test    ebx, ebx
0x180008af9  js      short loc_180008B30
0x180008afb  lea     rax, aAppid; "APPID"
0x180008b02  xorps   xmm0, xmm0
0x180008b05  mov     [rsp+48h+var_28], rax
0x180008b0a  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x180008b0f  lea     rax, a70f829de656f4e; "70F829DE-656F-4EA9-B6BD-7D092099429C"
0x180008b16  xor     r8d, r8d; int
0x180008b19  mov     edx, 0C9h; unsigned int
0x180008b1e  mov     [rsp+48h+var_20], rax
0x180008b23  movdqu  [rsp+48h+var_18], xmm0
0x180008b29  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180008b2e  mov     ebx, eax
0x180008b30  mov     ecx, edi; Locale
0x180008b32  call    cs:__imp_SetThreadLocale
0x180008b39  nop     dword ptr [rax+rax+00h]
0x180008b3e  mov     eax, ebx
0x180008b40  mov     rbx, [rsp+48h+arg_0]
0x180008b45  add     rsp, 40h
0x180008b49  pop     rdi
0x180008b4a  retn
```
