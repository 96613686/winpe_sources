# DllGetClassObject

- ea: `0x180027c10`
- end: `0x180027c89`
- name: `DllGetClassObject`
- size: `121`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180023d9c`
- `0x180025c24`
- `0x180027c10`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180027c73`
- `RPCRT4!NdrDllGetClassObject` at `0x180027c73`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v6; // eax
  HRESULT result; // eax

  *ppv = 0;
  v6 = sub_180025C24();
  result = sub_180023D9C(v6, ppv);
  if ( result < 0 )
    return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&pProxyFileList, &pclsid, &pPSFactoryBuffer);
  return result;
}

```

## disassembly

```asm
0x180027c10  mov     [rsp+arg_0], rbx
0x180027c15  mov     [rsp+arg_8], rsi
0x180027c1a  push    rdi
0x180027c1b  sub     rsp, 30h
0x180027c1f  mov     rbx, r8
0x180027c22  mov     qword ptr [r8], 0
0x180027c29  mov     rdi, rdx
0x180027c2c  mov     rsi, rcx
0x180027c2f  call    sub_180025C24
0x180027c34  mov     r9, rdi
0x180027c37  mov     [rsp+38h+pclsid], rbx; PVOID
0x180027c3c  mov     r8, rsi
0x180027c3f  mov     rcx, rax; int
0x180027c42  call    sub_180023D9C
0x180027c47  test    eax, eax
0x180027c49  jns     short loc_180027C79
0x180027c4b  lea     rax, pPSFactoryBuffer
0x180027c52  mov     r8, rbx; ppv
0x180027c55  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180027c5a  lea     r9, pProxyFileList; pProxyFileList
0x180027c61  lea     rax, pclsid
0x180027c68  mov     rdx, rdi; riid
0x180027c6b  mov     rcx, rsi; rclsid
0x180027c6e  mov     [rsp+38h+pclsid], rax; pclsid
0x180027c73  call    cs:NdrDllGetClassObject
0x180027c79  mov     rbx, [rsp+38h+arg_0]
0x180027c7e  mov     rsi, [rsp+38h+arg_8]
0x180027c83  add     rsp, 30h
0x180027c87  pop     rdi
0x180027c88  retn
```
