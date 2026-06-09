# DllUnregisterServer

- ea: `0x18000ab60`
- end: `0x18000abb1`
- name: `DllUnregisterServer`
- size: `81`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ab60`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000ab8d`
- `RPCRT4!NdrDllUnregisterProxy` at `0x18000ab8d`
- `ADVPACK!RegInstallW` at `0x18000aba4`
- `ADVPACK!RegInstallW` at `0x18000aba4`

## string_xrefs

- `0x18000ab9a`: `DefaultUninstall`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  RegInstallW(g_hInstance, L"DefaultUninstall", 0);
  return 0;
}

```

## disassembly

```asm
0x18000ab60  sub     rsp, 28h
0x18000ab64  mov     rax, cs:aProxyFileList
0x18000ab6b  mov     rcx, [rax+8]
0x18000ab6f  mov     rax, [rcx]
0x18000ab72  test    rax, rax
0x18000ab75  jz      short loc_18000AB7C
0x18000ab77  mov     r8, [rax]
0x18000ab7a  jmp     short loc_18000AB7F
0x18000ab7c  xor     r8d, r8d; pclsid
0x18000ab7f  mov     rcx, cs:hProxyDll; hDll
0x18000ab86  lea     rdx, aProxyFileList; pProxyFileList
0x18000ab8d  call    cs:__imp_NdrDllUnregisterProxy
0x18000ab93  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hmod
0x18000ab9a  lea     rdx, aDefaultuninsta; "DefaultUninstall"
0x18000aba1  xor     r8d, r8d; pstTable
0x18000aba4  call    cs:__imp_RegInstallW
0x18000abaa  xor     eax, eax
0x18000abac  add     rsp, 28h
0x18000abb0  retn
```
