# DllRegisterServer

- ea: `0x1800017a0`
- end: `0x1800017d0`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800017c9`

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
0x1800017a0  mov     rax, cs:aProxyFileList
0x1800017a7  mov     rcx, [rax+8]
0x1800017ab  mov     rax, [rcx]
0x1800017ae  test    rax, rax
0x1800017b1  jz      short loc_1800017B8
0x1800017b3  mov     r8, [rax]
0x1800017b6  jmp     short loc_1800017BB
0x1800017b8  xor     r8d, r8d
0x1800017bb  mov     rcx, cs:hProxyDll
0x1800017c2  lea     rdx, aProxyFileList
0x1800017c9  jmp     cs:__imp_NdrDllRegisterProxy
```
