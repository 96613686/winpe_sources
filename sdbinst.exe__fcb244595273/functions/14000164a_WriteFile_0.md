# WriteFile_0

- ea: `0x14000164a`
- end: `0x140001650`
- name: `WriteFile_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesWritten, LPOVERLAPPED lpOverlapped)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140009b9c`
- `0x140009e54`
- `0x14000a164`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14000164a`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WriteFile_0(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPDWORD lpNumberOfBytesWritten,
        LPOVERLAPPED lpOverlapped)
{
  return WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, lpNumberOfBytesWritten, lpOverlapped);
}

```

## disassembly

```asm
0x14000164a  jmp     cs:__imp_WriteFile
```
