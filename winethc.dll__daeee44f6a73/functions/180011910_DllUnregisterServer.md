# DllUnregisterServer

- ea: `0x180011910`
- end: `0x1800119a7`
- name: `DllUnregisterServer`
- size: `151`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ce24`
- `0x1800114b4`
- `0x180011910`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18001191a`
- `KERNEL32!GetThreadLocale` at `0x18001191a`
- `KERNEL32!SetThreadLocale` at `0x18001192d`
- `KERNEL32!SetThreadLocale` at `0x18001198d`
- `KERNEL32!SetThreadLocale` at `0x18001192d`
- `KERNEL32!SetThreadLocale` at `0x18001198d`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // edx
  ATL::CAtlComModule *v2; // rcx
  const struct _GUID *v3; // r8
  HRESULT updated; // ebx
  unsigned int v5; // edx
  ATL::CAtlModule *v6; // rcx
  _QWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (updated = ATL::_pPerfUnRegFunc(), updated >= 0) )
  {
    updated = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
    if ( updated >= 0 )
    {
      v8[0] = L"APPID";
      v8[1] = L"{832701D5-B081-4790-93A7-5BCC7EE0755E}";
      v9 = 0;
      updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v6, v5, 0, (struct ATL::_ATL_REGMAP_ENTRY *)v8);
    }
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180011910  mov     [rsp+arg_0], rbx
0x180011915  push    rdi
0x180011916  sub     rsp, 40h
0x18001191a  call    cs:__imp_GetThreadLocale
0x180011921  nop     dword ptr [rax+rax+00h]
0x180011926  mov     ecx, 800h; Locale
0x18001192b  mov     edi, eax
0x18001192d  call    cs:__imp_SetThreadLocale
0x180011934  nop     dword ptr [rax+rax+00h]
0x180011939  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180011940  test    rax, rax
0x180011943  jz      short loc_180011950
0x180011945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194a  mov     ebx, eax
0x18001194c  test    eax, eax
0x18001194e  js      short loc_18001198B
0x180011950  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x180011955  mov     ebx, eax
0x180011957  test    eax, eax
0x180011959  js      short loc_18001198B
0x18001195b  lea     rax, aAppid_0; "APPID"
0x180011962  xorps   xmm0, xmm0
0x180011965  mov     [rsp+48h+var_28], rax
0x18001196a  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x18001196f  lea     rax, a832701d5B08147; "{832701D5-B081-4790-93A7-5BCC7EE0755E}"
0x180011976  xor     r8d, r8d; int
0x180011979  mov     [rsp+48h+var_20], rax
0x18001197e  movdqu  [rsp+48h+var_18], xmm0
0x180011984  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180011989  mov     ebx, eax
0x18001198b  mov     ecx, edi; Locale
0x18001198d  call    cs:__imp_SetThreadLocale
0x180011994  nop     dword ptr [rax+rax+00h]
0x180011999  mov     eax, ebx
0x18001199b  mov     rbx, [rsp+48h+arg_0]
0x1800119a0  add     rsp, 40h
0x1800119a4  pop     rdi
0x1800119a5  retn
```
