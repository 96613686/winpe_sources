# DllUnregisterServer

- ea: `0x1800088f0`
- end: `0x1800088f5`
- name: `DllUnregisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000821c`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rdx
  ATL::CComModule *v1; // rcx
  const struct _GUID *v2; // r8

  return ATL::CComModule::UnregisterServer(v1, v0, v2);
}

```

## disassembly

```asm
0x1800088f0  jmp     ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
```
