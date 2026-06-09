# DllRegisterServer

- ea: `0x18001b230`
- end: `0x18001b260`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001b230`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18001b259`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x18001b230  mov     rax, cs:aProxyFileList
0x18001b237  mov     rcx, [rax+8]
0x18001b23b  mov     rax, [rcx]
0x18001b23e  test    rax, rax
0x18001b241  jz      short loc_18001B248
0x18001b243  mov     r8, [rax]
0x18001b246  jmp     short loc_18001B24B
0x18001b248  xor     r8d, r8d
0x18001b24b  mov     rcx, cs:hProxyDll
0x18001b252  lea     rdx, aProxyFileList
0x18001b259  jmp     cs:__imp_NdrDllRegisterProxy
```
