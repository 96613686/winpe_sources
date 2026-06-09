# DllCanUnloadNow

- ea: `0x1800048e0`
- end: `0x1800048fd`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800048e0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800048f6`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( dword_18000A288 )
    return 1;
  else
    return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x1800048e0  cmp     cs:dword_18000A288, 0
0x1800048e7  jz      short loc_1800048EF
0x1800048e9  mov     eax, 1
0x1800048ee  retn
0x1800048ef  lea     rcx, gPFactory
0x1800048f6  jmp     cs:__imp_NdrDllCanUnloadNow
```
