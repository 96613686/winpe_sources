# DllRegisterServer

- ea: `0x1800036f0`
- end: `0x18000373b`
- name: `DllRegisterServer`
- size: `75`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800036f0`
- `0x18000379c`
- `0x18002d010`

## string_xrefs

- `0x180003702`: `Adapter_RegisterDLL`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  __int128 v1; // [rsp+20h] [rbp-18h] BYREF

  result = GetFunctionPointer("Adapter_RegisterDLL");
  if ( !result )
  {
    v1 = g_providerClassID;
    return MEMORY[0](g_hModule, &v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800036f0  sub     rsp, 38h
0x1800036f4  lea     rdx, [rsp+38h+arg_0]
0x1800036f9  mov     [rsp+38h+arg_0], 0
0x180003702  lea     rcx, aAdapterRegiste; "Adapter_RegisterDLL"
0x180003709  call    GetFunctionPointer
0x18000370e  test    eax, eax
0x180003710  jnz     short loc_180003735
0x180003712  movups  xmm0, cs:g_providerClassID
0x180003719  mov     rcx, cs:g_hModule
0x180003720  lea     rdx, [rsp+38h+var_18]
0x180003725  mov     rax, [rsp+38h+arg_0]
0x18000372a  movdqu  [rsp+38h+var_18], xmm0
0x180003730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003735  add     rsp, 38h
0x180003739  retn
```
