# DllCanUnloadNow

- ea: `0x180004b20`
- end: `0x180004b44`
- name: `DllCanUnloadNow`
- size: `36`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004b20`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180004b39`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180004b39`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 1;
  if ( !dword_18000C30C )
    return NdrDllCanUnloadNow(&gPFactory);
  return result;
}

```

## disassembly

```asm
0x180004b20  sub     rsp, 28h
0x180004b24  cmp     cs:dword_18000C30C, 0
0x180004b2b  mov     eax, 1
0x180004b30  jnz     short loc_180004B3F
0x180004b32  lea     rcx, gPFactory; pPSFactoryBuffer
0x180004b39  call    cs:__imp_NdrDllCanUnloadNow
0x180004b3f  add     rsp, 28h
0x180004b43  retn
```
