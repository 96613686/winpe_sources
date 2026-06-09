# GetProxyDllInfo

- ea: `0x180001eb0`
- end: `0x180001ed4`
- name: `GetProxyDllInfo`
- size: `36`
- prototype: `PCInterfaceStubVtblList __fastcall(_QWORD *, PCInterfaceStubVtblList *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001eb0`

## pseudocode

```c
PCInterfaceStubVtblList __fastcall GetProxyDllInfo(_QWORD *a1, PCInterfaceStubVtblList *a2)
{
  PCInterfaceStubVtblList result; // rax

  *a1 = &aProxyFileList;
  result = *aProxyFileList->pStubVtblList;
  if ( result )
    result = (PCInterfaceStubVtblList)result->header.piid;
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x180001eb0  lea     rax, aProxyFileList
0x180001eb7  mov     [rcx], rax
0x180001eba  mov     rax, cs:aProxyFileList
0x180001ec1  mov     rcx, [rax+8]
0x180001ec5  mov     rax, [rcx]
0x180001ec8  test    rax, rax
0x180001ecb  jz      short loc_180001ED0
0x180001ecd  mov     rax, [rax]
0x180001ed0  mov     [rdx], rax
0x180001ed3  retn
```
