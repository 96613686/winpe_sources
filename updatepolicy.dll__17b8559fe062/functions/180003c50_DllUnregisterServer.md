# DllUnregisterServer

- ea: `0x180003c50`
- end: `0x180003c5c`
- name: `DllUnregisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043f8`

## string_xrefs

- `0x180003c50`: `DllUnregisterServer`

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
0x180003c50  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x180003c57  jmp     ??$InvokeExportMethod@J$$V@UndockedModuleForwarder@@QEAAJPEBD@Z; UndockedModuleForwarder::InvokeExportMethod<long,>(char const *)
```
