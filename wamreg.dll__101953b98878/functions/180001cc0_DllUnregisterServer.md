# DllUnregisterServer

- ea: `0x180001cc0`
- end: `0x180001ccc`
- name: `DllUnregisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800066a4`

## string_xrefs

- `0x180001cc0`: `RemoveComponent`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const unsigned __int16 *v0; // rcx

  return CallRegisterComponent(v0, "RemoveComponent");
}

```

## disassembly

```asm
0x180001cc0  lea     rdx, aRemovecomponen; "RemoveComponent"
0x180001cc7  jmp     ?CallRegisterComponent@@YAJPEBGPEAD@Z; CallRegisterComponent(ushort const *,char *)
```
