# DllUnregisterServer

- ea: `0x1800080c0`
- end: `0x1800080cc`
- name: `DllUnregisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008364`

## string_xrefs

- `0x1800080c0`: `DllUnregisterServer`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  UndockedModuleForwarder *v0; // rcx

  return UndockedModuleForwarder::InvokeExportMethod<long,>(v0, "DllUnregisterServer");
}

```

## disassembly

```asm
0x1800080c0  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x1800080c7  jmp     ??$InvokeExportMethod@J$$V@UndockedModuleForwarder@@QEAAJPEBD@Z; UndockedModuleForwarder::InvokeExportMethod<long,>(char const *)
```
