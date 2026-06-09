# DllCanUnloadNow

- ea: `0x1800036b0`
- end: `0x1800036e1`
- name: `DllCanUnloadNow`
- size: `49`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800036b0`
- `0x18000386c`
- `0x18002d010`

## string_xrefs

- `0x1800036c2`: `Adapter_DllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = GetFunctionPointer("Adapter_DllCanUnloadNow");
  if ( !result )
    return MEMORY[0]();
  return result;
}

```

## disassembly

```asm
0x1800036b0  sub     rsp, 28h
0x1800036b4  lea     rdx, [rsp+28h+arg_0]
0x1800036b9  mov     [rsp+28h+arg_0], 0
0x1800036c2  lea     rcx, aAdapterDllcanu; "Adapter_DllCanUnloadNow"
0x1800036c9  call    GetFunctionPointer
0x1800036ce  test    eax, eax
0x1800036d0  jnz     short loc_1800036DC
0x1800036d2  mov     rax, [rsp+28h+arg_0]
0x1800036d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036dc  add     rsp, 28h
0x1800036e0  retn
```
