# DllUnregisterServer

- ea: `0x180003750`
- end: `0x180003794`
- name: `DllUnregisterServer`
- size: `68`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003750`
- `0x18000379c`
- `0x18002d010`

## string_xrefs

- `0x180003762`: `Adapter_UnRegisterDLL`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax
  __int128 v1; // [rsp+20h] [rbp-18h] BYREF

  result = GetFunctionPointer("Adapter_UnRegisterDLL");
  if ( !result )
  {
    v1 = g_providerClassID;
    return MEMORY[0](&v1);
  }
  return result;
}

```

## disassembly

```asm
0x180003750  sub     rsp, 38h
0x180003754  lea     rdx, [rsp+38h+arg_0]
0x180003759  mov     [rsp+38h+arg_0], 0
0x180003762  lea     rcx, aAdapterUnregis; "Adapter_UnRegisterDLL"
0x180003769  call    GetFunctionPointer
0x18000376e  test    eax, eax
0x180003770  jnz     short loc_18000378E
0x180003772  movups  xmm0, cs:g_providerClassID
0x180003779  mov     rax, [rsp+38h+arg_0]
0x18000377e  lea     rcx, [rsp+38h+var_18]
0x180003783  movdqu  [rsp+38h+var_18], xmm0
0x180003789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378e  add     rsp, 38h
0x180003792  retn
```
