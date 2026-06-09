# DllUnregisterServer

- ea: `0x180005de0`
- end: `0x180005e39`
- name: `DllUnregisterServer`
- size: `89`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180005834`
- `0x1800058d0`
- `0x180005de0`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180005dfd`
- `KERNEL32!SetThreadLocale` at `0x180005e1f`
- `KERNEL32!SetThreadLocale` at `0x180005dfd`
- `KERNEL32!SetThreadLocale` at `0x180005e1f`
- `KERNEL32!GetThreadLocale` at `0x180005dea`
- `KERNEL32!GetThreadLocale` at `0x180005dea`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT updated; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  updated = ATL::CAtlModuleT<CWdsTptMgmtModule>::UnregisterServer();
  if ( updated >= 0 )
    updated = CWdsTptMgmtModule::UpdateRegistryAppId(0);
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180005de0  mov     [rsp+arg_0], rbx
0x180005de5  push    rdi
0x180005de6  sub     rsp, 20h
0x180005dea  call    cs:__imp_GetThreadLocale
0x180005df1  nop     dword ptr [rax+rax+00h]
0x180005df6  mov     ecx, 800h; Locale
0x180005dfb  mov     edi, eax
0x180005dfd  call    cs:__imp_SetThreadLocale
0x180005e04  nop     dword ptr [rax+rax+00h]
0x180005e09  call    ?UnregisterServer@?$CAtlModuleT@VCWdsTptMgmtModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CWdsTptMgmtModule>::UnregisterServer(int,_GUID const *)
0x180005e0e  mov     ebx, eax
0x180005e10  test    eax, eax
0x180005e12  js      short loc_180005E1D
0x180005e14  xor     ecx, ecx; int
0x180005e16  call    ?UpdateRegistryAppId@CWdsTptMgmtModule@@SAJH@Z; CWdsTptMgmtModule::UpdateRegistryAppId(int)
0x180005e1b  mov     ebx, eax
0x180005e1d  mov     ecx, edi; Locale
0x180005e1f  call    cs:__imp_SetThreadLocale
0x180005e26  nop     dword ptr [rax+rax+00h]
0x180005e2b  mov     eax, ebx
0x180005e2d  mov     rbx, [rsp+28h+arg_0]
0x180005e32  add     rsp, 20h
0x180005e36  pop     rdi
0x180005e37  retn
```
