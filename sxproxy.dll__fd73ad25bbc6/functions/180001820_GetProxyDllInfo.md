# GetProxyDllInfo

- ea: `0x180001820`
- end: `0x180001844`
- name: `GetProxyDllInfo`
- size: `36`
- prototype: `PCInterfaceStubVtblList __fastcall(_QWORD *, PCInterfaceStubVtblList *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001820`

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
0x180001820  lea     rax, aProxyFileList
0x180001827  mov     [rcx], rax
0x18000182a  mov     rax, cs:aProxyFileList
0x180001831  mov     rcx, [rax+8]
0x180001835  mov     rax, [rcx]
0x180001838  test    rax, rax
0x18000183b  jz      short loc_180001840
0x18000183d  mov     rax, [rax]
0x180001840  mov     [rdx], rax
0x180001843  retn
```
