# DllRegisterServer

- ea: `0x180007620`
- end: `0x180007625`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000e280`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  struct _GUID *v0; // rdx
  __int64 v1; // rcx

  return TaDllRegisterServer(v1, v0);
}

```

## disassembly

```asm
0x180007620  jmp     ?TaDllRegisterServer@@YAJIPEAU_GUID@@@Z; TaDllRegisterServer(uint,_GUID *)
```
