# CIlKernel32::GetCommandLineW(void)

- ea: `0x18000e6d0`
- end: `0x18000e6d7`
- name: `?GetCommandLineW@CIlKernel32@@UEAAPEAGXZ`
- size: `7`
- prototype: `LPWSTR __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18000e6d0`

## pseudocode

```c
// attributes: thunk
LPWSTR __stdcall CIlKernel32::GetCommandLineW()
{
  return GetCommandLineW();
}

```

## disassembly

```asm
0x18000e6d0  jmp     cs:__imp_GetCommandLineW
```
