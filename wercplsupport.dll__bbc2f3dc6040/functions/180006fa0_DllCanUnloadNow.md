# DllCanUnloadNow

- ea: `0x180006fa0`
- end: `0x180006fcf`
- name: `DllCanUnloadNow`
- size: `47`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006fa0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180006fab`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180006fab`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory) || _InterlockedCompareExchange(&dword_18001C958, 0, 0);
}

```

## disassembly

```asm
0x180006fa0  sub     rsp, 28h
0x180006fa4  lea     rcx, gPFactory; pPSFactoryBuffer
0x180006fab  call    cs:__imp_NdrDllCanUnloadNow
0x180006fb1  test    eax, eax
0x180006fb3  jnz     short loc_180006FC5
0x180006fb5  xor     ecx, ecx
0x180006fb7  lock cmpxchg cs:dword_18001C958, ecx
0x180006fbf  jnz     short loc_180006FC5
0x180006fc1  xor     eax, eax
0x180006fc3  jmp     short loc_180006FCA
0x180006fc5  mov     eax, 1
0x180006fca  add     rsp, 28h
0x180006fce  retn
```
