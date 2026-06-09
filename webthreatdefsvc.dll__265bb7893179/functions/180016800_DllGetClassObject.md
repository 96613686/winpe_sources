# DllGetClassObject

- ea: `0x180016800`
- end: `0x180016879`
- name: `DllGetClassObject`
- size: `121`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180013824`
- `0x1800143bc`
- `0x180016800`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180016863`
- `RPCRT4!NdrDllGetClassObject` at `0x180016863`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v6; // eax
  HRESULT result; // eax

  *ppv = 0;
  v6 = sub_1800143BC();
  result = sub_180013824(v6, ppv);
  if ( result < 0 )
    return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&pProxyFileList, &pclsid, &pPSFactoryBuffer);
  return result;
}

```

## disassembly

```asm
0x180016800  mov     [rsp+arg_0], rbx
0x180016805  mov     [rsp+arg_8], rsi
0x18001680a  push    rdi
0x18001680b  sub     rsp, 30h
0x18001680f  mov     rbx, r8
0x180016812  mov     qword ptr [r8], 0
0x180016819  mov     rdi, rdx
0x18001681c  mov     rsi, rcx
0x18001681f  call    sub_1800143BC
0x180016824  mov     r9, rdi
0x180016827  mov     [rsp+38h+pclsid], rbx; PVOID
0x18001682c  mov     r8, rsi
0x18001682f  mov     rcx, rax; int
0x180016832  call    sub_180013824
0x180016837  test    eax, eax
0x180016839  jns     short loc_180016869
0x18001683b  lea     rax, pPSFactoryBuffer
0x180016842  mov     r8, rbx; ppv
0x180016845  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18001684a  lea     r9, pProxyFileList; pProxyFileList
0x180016851  lea     rax, pclsid
0x180016858  mov     rdx, rdi; riid
0x18001685b  mov     rcx, rsi; rclsid
0x18001685e  mov     [rsp+38h+pclsid], rax; pclsid
0x180016863  call    cs:NdrDllGetClassObject
0x180016869  mov     rbx, [rsp+38h+arg_0]
0x18001686e  mov     rsi, [rsp+38h+arg_8]
0x180016873  add     rsp, 30h
0x180016877  pop     rdi
0x180016878  retn
```
