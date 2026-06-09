# DllRegisterServer

- ea: `0x18000ab00`
- end: `0x18000ab51`
- name: `DllRegisterServer`
- size: `81`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ab00`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x18000ab2d`
- `RPCRT4!NdrDllRegisterProxy` at `0x18000ab2d`
- `ADVPACK!RegInstallW` at `0x18000ab44`
- `ADVPACK!RegInstallW` at `0x18000ab44`

## string_xrefs

- `0x18000ab3a`: `DefaultInstall`

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
  NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
  RegInstallW(g_hInstance, L"DefaultInstall", 0);
  return 0;
}

```

## disassembly

```asm
0x18000ab00  sub     rsp, 28h
0x18000ab04  mov     rax, cs:aProxyFileList
0x18000ab0b  mov     rcx, [rax+8]
0x18000ab0f  mov     rax, [rcx]
0x18000ab12  test    rax, rax
0x18000ab15  jz      short loc_18000AB1C
0x18000ab17  mov     r8, [rax]
0x18000ab1a  jmp     short loc_18000AB1F
0x18000ab1c  xor     r8d, r8d; pclsid
0x18000ab1f  mov     rcx, cs:hProxyDll; hDll
0x18000ab26  lea     rdx, aProxyFileList; pProxyFileList
0x18000ab2d  call    cs:__imp_NdrDllRegisterProxy
0x18000ab33  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hmod
0x18000ab3a  lea     rdx, pszSection; "DefaultInstall"
0x18000ab41  xor     r8d, r8d; pstTable
0x18000ab44  call    cs:__imp_RegInstallW
0x18000ab4a  xor     eax, eax
0x18000ab4c  add     rsp, 28h
0x18000ab50  retn
```
