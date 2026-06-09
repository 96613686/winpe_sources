# DllCanUnloadNow

- ea: `0x180003c10`
- end: `0x180003c1c`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043f8`

## string_xrefs

- `0x180003c10`: `DllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  UndockedModuleForwarder *v0; // rcx

  return UndockedModuleForwarder::InvokeExportMethod<long,>(v0, "DllCanUnloadNow");
}

```

## disassembly

```asm
0x180003c10  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x180003c17  jmp     ??$InvokeExportMethod@J$$V@UndockedModuleForwarder@@QEAAJPEBD@Z; UndockedModuleForwarder::InvokeExportMethod<long,>(char const *)
```
