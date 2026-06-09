# DllCanUnloadNow

- ea: `0x18000a990`
- end: `0x18000a9b6`
- name: `DllCanUnloadNow`
- size: `38`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a990`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000a9a9`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( g_cServerLocks || g_cRefThisDll )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x18000a990  cmp     cs:?g_cServerLocks@@3JA, 0; long g_cServerLocks
0x18000a997  jnz     short loc_18000A9B0
0x18000a999  cmp     cs:?g_cRefThisDll@@3JA, 0; long g_cRefThisDll
0x18000a9a0  jnz     short loc_18000A9B0
0x18000a9a2  lea     rcx, gPFactory
0x18000a9a9  jmp     cs:__imp_NdrDllCanUnloadNow
0x18000a9b0  mov     eax, 1
0x18000a9b5  retn
```
