# DllRegisterServer

- ea: `0x1800037d0`
- end: `0x18000381a`
- name: `DllRegisterServer`
- size: `74`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800037d0`
- `0x18000386c`
- `0x18002d010`

## string_xrefs

- `0x1800037e2`: `Adapter_RegisterDLL`

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
0x1800037d0  sub     rsp, 38h
0x1800037d4  lea     rdx, [rsp+38h+arg_0]
0x1800037d9  mov     [rsp+38h+arg_0], 0
0x1800037e2  lea     rcx, aAdapterRegiste; "Adapter_RegisterDLL"
0x1800037e9  call    GetFunctionPointer
0x1800037ee  test    eax, eax
0x1800037f0  jnz     short loc_180003815
0x1800037f2  movups  xmm0, cs:g_providerClassID
0x1800037f9  mov     rcx, cs:g_hModule
0x180003800  lea     rdx, [rsp+38h+var_18]
0x180003805  mov     rax, [rsp+38h+arg_0]
0x18000380a  movdqu  [rsp+38h+var_18], xmm0
0x180003810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003815  add     rsp, 38h
0x180003819  retn
```
