# CIlKernel32::GetCurrentThreadId(void)

- ea: `0x18000e730`
- end: `0x18000e737`
- name: `?GetCurrentThreadId@CIlKernel32@@UEAAKXZ`
- size: `7`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e730`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall CIlKernel32::GetCurrentThreadId()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x18000e730  jmp     cs:__imp_GetCurrentThreadId
```
