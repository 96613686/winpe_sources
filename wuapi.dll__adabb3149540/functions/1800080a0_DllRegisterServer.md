# DllRegisterServer

- ea: `0x1800080a0`
- end: `0x1800080ac`
- name: `DllRegisterServer`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008364`

## string_xrefs

- `0x1800080a0`: `DllRegisterServer`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx

  return UndockedModuleForwarder::InvokeExportMethod<long,>(v0, "DllRegisterServer");
}

```

## disassembly

```asm
0x1800080a0  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x1800080a7  jmp     ??$InvokeExportMethod@J$$V@UndockedModuleForwarder@@QEAAJPEBD@Z; UndockedModuleForwarder::InvokeExportMethod<long,>(char const *)
```
