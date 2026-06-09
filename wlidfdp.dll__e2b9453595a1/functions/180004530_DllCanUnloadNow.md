# DllCanUnloadNow

- ea: `0x180004530`
- end: `0x180004559`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180012010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return (*(__int64 (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) != 0;
}

```

## disassembly

```asm
0x180004530  sub     rsp, 28h
0x180004534  mov     rax, cs:?_AtlModule@@3VCPrincipalProviderLibModule@@A; CPrincipalProviderLibModule _AtlModule
0x18000453b  lea     rcx, ?_AtlModule@@3VCPrincipalProviderLibModule@@A; CPrincipalProviderLibModule _AtlModule
0x180004542  mov     rax, [rax+18h]
0x180004546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454b  xor     ecx, ecx
0x18000454d  test    eax, eax
0x18000454f  setnz   cl
0x180004552  mov     eax, ecx
0x180004554  add     rsp, 28h
0x180004558  retn
```
