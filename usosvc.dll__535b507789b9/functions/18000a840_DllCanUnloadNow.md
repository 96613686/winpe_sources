# DllCanUnloadNow

- ea: `0x18000a840`
- end: `0x18000a857`
- name: `DllCanUnloadNow`
- size: `23`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a840`
- `0x18000f010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( g_DllCanUnloadNow )
    return g_DllCanUnloadNow();
  else
    return 1;
}

```

## disassembly

```asm
0x18000a840  mov     rax, cs:?g_DllCanUnloadNow@@3P6AJXZEA; long (*g_DllCanUnloadNow)(void)
0x18000a847  test    rax, rax
0x18000a84a  jnz     short loc_18000A852
0x18000a84c  mov     eax, 1
0x18000a851  retn
0x18000a852  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
