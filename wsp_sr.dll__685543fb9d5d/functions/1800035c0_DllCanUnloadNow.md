# DllCanUnloadNow

- ea: `0x1800035c0`
- end: `0x1800035f2`
- name: `DllCanUnloadNow`
- size: `50`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800035c0`
- `0x18000379c`
- `0x18002d010`

## string_xrefs

- `0x1800035d2`: `Adapter_DllCanUnloadNow`

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
0x1800035c0  sub     rsp, 28h
0x1800035c4  lea     rdx, [rsp+28h+arg_0]
0x1800035c9  mov     [rsp+28h+arg_0], 0
0x1800035d2  lea     rcx, aAdapterDllcanu; "Adapter_DllCanUnloadNow"
0x1800035d9  call    GetFunctionPointer
0x1800035de  test    eax, eax
0x1800035e0  jnz     short loc_1800035EC
0x1800035e2  mov     rax, [rsp+28h+arg_0]
0x1800035e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ec  add     rsp, 28h
0x1800035f0  retn
```
