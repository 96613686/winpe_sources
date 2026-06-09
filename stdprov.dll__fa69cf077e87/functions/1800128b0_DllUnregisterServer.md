# DllUnregisterServer

- ea: `0x1800128b0`
- end: `0x18001293d`
- name: `DllUnregisterServer`
- size: `141`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `wbemcomn!UnRegisterDLL` at `0x1800128c8`
- `wbemcomn!UnRegisterDLL` at `0x1800128e2`
- `wbemcomn!UnRegisterDLL` at `0x1800128fc`
- `wbemcomn!UnRegisterDLL` at `0x180012916`
- `wbemcomn!UnRegisterDLL` at `0x180012930`
- `wbemcomn!UnRegisterDLL` at `0x1800128c8`
- `wbemcomn!UnRegisterDLL` at `0x1800128e2`
- `wbemcomn!UnRegisterDLL` at `0x1800128fc`
- `wbemcomn!UnRegisterDLL` at `0x180012916`
- `wbemcomn!UnRegisterDLL` at `0x180012930`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  GUID v1; // [rsp+20h] [rbp-18h] BYREF

  v1 = CLSID_RegProvider;
  UnRegisterDLL(&v1, 0);
  v1 = CLSID_RegPropProv;
  UnRegisterDLL(&v1, 0);
  v1 = CLSID_PerfProvider;
  UnRegisterDLL(&v1, 0);
  v1 = CLSID_PerfPropProv;
  UnRegisterDLL(&v1, 0);
  v1 = CLSID_RegistryEventProvider;
  UnRegisterDLL(&v1, 0);
  return 0;
}

```

## disassembly

```asm
0x1800128b0  sub     rsp, 38h
0x1800128b4  movups  xmm0, xmmword ptr cs:CLSID_RegProvider.Data1
0x1800128bb  xor     edx, edx
0x1800128bd  lea     rcx, [rsp+38h+var_18]
0x1800128c2  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1800128c8  call    cs:__imp_?UnRegisterDLL@@YAXU_GUID@@PEAG@Z; UnRegisterDLL(_GUID,ushort *)
0x1800128ce  movups  xmm0, xmmword ptr cs:CLSID_RegPropProv.Data1
0x1800128d5  xor     edx, edx
0x1800128d7  lea     rcx, [rsp+38h+var_18]
0x1800128dc  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1800128e2  call    cs:__imp_?UnRegisterDLL@@YAXU_GUID@@PEAG@Z; UnRegisterDLL(_GUID,ushort *)
0x1800128e8  movups  xmm0, xmmword ptr cs:CLSID_PerfProvider.Data1
0x1800128ef  xor     edx, edx
0x1800128f1  lea     rcx, [rsp+38h+var_18]
0x1800128f6  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x1800128fc  call    cs:__imp_?UnRegisterDLL@@YAXU_GUID@@PEAG@Z; UnRegisterDLL(_GUID,ushort *)
0x180012902  movups  xmm0, xmmword ptr cs:CLSID_PerfPropProv.Data1
0x180012909  xor     edx, edx
0x18001290b  lea     rcx, [rsp+38h+var_18]
0x180012910  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x180012916  call    cs:__imp_?UnRegisterDLL@@YAXU_GUID@@PEAG@Z; UnRegisterDLL(_GUID,ushort *)
0x18001291c  movups  xmm0, xmmword ptr cs:?CLSID_RegistryEventProvider@@3U_GUID@@B.Data1; _GUID const CLSID_RegistryEventProvider ...
0x180012923  xor     edx, edx
0x180012925  lea     rcx, [rsp+38h+var_18]
0x18001292a  movdqu  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x180012930  call    cs:__imp_?UnRegisterDLL@@YAXU_GUID@@PEAG@Z; UnRegisterDLL(_GUID,ushort *)
0x180012936  xor     eax, eax
0x180012938  add     rsp, 38h
0x18001293c  retn
```
