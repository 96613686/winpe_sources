# DllRegisterServer

- ea: `0x18000ced0`
- end: `0x18000ced5`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cff4`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return RtfRegisterServer();
}

```

## disassembly

```asm
0x18000ced0  jmp     RtfRegisterServer
```
