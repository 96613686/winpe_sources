# DllRegisterServer

- ea: `0x180005d70`
- end: `0x180005dcc`
- name: `DllRegisterServer`
- size: `92`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180004e70`
- `0x1800058d0`
- `0x180005d70`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180005d8d`
- `KERNEL32!SetThreadLocale` at `0x180005db2`
- `KERNEL32!SetThreadLocale` at `0x180005d8d`
- `KERNEL32!SetThreadLocale` at `0x180005db2`
- `KERNEL32!GetThreadLocale` at `0x180005d7a`
- `KERNEL32!GetThreadLocale` at `0x180005d7a`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT updated; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  updated = CWdsTptMgmtModule::UpdateRegistryAppId(1);
  if ( updated >= 0 )
    updated = ATL::CAtlModuleT<CWdsTptMgmtModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180005d70  mov     [rsp+arg_0], rbx
0x180005d75  push    rdi
0x180005d76  sub     rsp, 20h
0x180005d7a  call    cs:__imp_GetThreadLocale
0x180005d81  nop     dword ptr [rax+rax+00h]
0x180005d86  mov     ecx, 800h; Locale
0x180005d8b  mov     edi, eax
0x180005d8d  call    cs:__imp_SetThreadLocale
0x180005d94  nop     dword ptr [rax+rax+00h]
0x180005d99  mov     ecx, 1; int
0x180005d9e  call    ?UpdateRegistryAppId@CWdsTptMgmtModule@@SAJH@Z; CWdsTptMgmtModule::UpdateRegistryAppId(int)
0x180005da3  mov     ebx, eax
0x180005da5  test    eax, eax
0x180005da7  js      short loc_180005DB0
0x180005da9  call    ?RegisterServer@?$CAtlModuleT@VCWdsTptMgmtModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CWdsTptMgmtModule>::RegisterServer(int,_GUID const *)
0x180005dae  mov     ebx, eax
0x180005db0  mov     ecx, edi; Locale
0x180005db2  call    cs:__imp_SetThreadLocale
0x180005db9  nop     dword ptr [rax+rax+00h]
0x180005dbe  mov     eax, ebx
0x180005dc0  mov     rbx, [rsp+28h+arg_0]
0x180005dc5  add     rsp, 20h
0x180005dc9  pop     rdi
0x180005dca  retn
```
