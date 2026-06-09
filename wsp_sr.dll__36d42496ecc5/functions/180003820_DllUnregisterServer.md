# DllUnregisterServer

- ea: `0x180003820`
- end: `0x180003863`
- name: `DllUnregisterServer`
- size: `67`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003820`
- `0x18000386c`
- `0x18002d010`

## string_xrefs

- `0x180003832`: `Adapter_UnRegisterDLL`

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
0x180003820  sub     rsp, 38h
0x180003824  lea     rdx, [rsp+38h+arg_0]
0x180003829  mov     [rsp+38h+arg_0], 0
0x180003832  lea     rcx, aAdapterUnregis; "Adapter_UnRegisterDLL"
0x180003839  call    GetFunctionPointer
0x18000383e  test    eax, eax
0x180003840  jnz     short loc_18000385E
0x180003842  movups  xmm0, cs:g_providerClassID
0x180003849  mov     rax, [rsp+38h+arg_0]
0x18000384e  lea     rcx, [rsp+38h+var_18]
0x180003853  movdqu  [rsp+38h+var_18], xmm0
0x180003859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385e  add     rsp, 38h
0x180003862  retn
```
