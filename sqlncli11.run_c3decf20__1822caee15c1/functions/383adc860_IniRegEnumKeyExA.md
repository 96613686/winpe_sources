# IniRegEnumKeyExA

- ea: `0x383adc860`
- end: `0x383adca7b`
- name: `IniRegEnumKeyExA`
- size: `539`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, LPSTR lpMultiByteStr@<r8>, LPDWORD lpReserved, LPSTR lpClass, LPDWORD lpcchClass, PFILETIME lpftLastWriteTime)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x383ad74e0`

## callees

- `0x383adc860`
- `0x383adca90`

## import_xrefs

- `KERNEL32!SetLastError` at `0x383adca04`
- `KERNEL32!SetLastError` at `0x383adca04`
- `KERNEL32!WideCharToMultiByte` at `0x383adc97e`
- `KERNEL32!WideCharToMultiByte` at `0x383adc9ae`
- `KERNEL32!WideCharToMultiByte` at `0x383adc9de`
- `KERNEL32!WideCharToMultiByte` at `0x383adc97e`
- `KERNEL32!WideCharToMultiByte` at `0x383adc9ae`
- `KERNEL32!WideCharToMultiByte` at `0x383adc9de`
- `KERNEL32!HeapAlloc` at `0x383adc90e`
- `KERNEL32!HeapAlloc` at `0x383adc90e`
- `KERNEL32!HeapFree` at `0x383adc8f8`
- `KERNEL32!HeapFree` at `0x383adc9f5`
- `KERNEL32!HeapFree` at `0x383adc8f8`
- `KERNEL32!HeapFree` at `0x383adc9f5`
- `KERNEL32!GetProcessHeap` at `0x383adc8ea`
- `KERNEL32!GetProcessHeap` at `0x383adc900`
- `KERNEL32!GetProcessHeap` at `0x383adc9e7`
- `KERNEL32!GetProcessHeap` at `0x383adc8ea`
- `KERNEL32!GetProcessHeap` at `0x383adc900`
- `KERNEL32!GetProcessHeap` at `0x383adc9e7`
- `KERNEL32!DebugBreak` at `0x383adc8a1`
- `KERNEL32!DebugBreak` at `0x383adc8b2`
- `KERNEL32!DebugBreak` at `0x383adc8c3`
- `KERNEL32!DebugBreak` at `0x383adc8d4`
- `KERNEL32!DebugBreak` at `0x383adc8a1`
- `KERNEL32!DebugBreak` at `0x383adc8b2`
- `KERNEL32!DebugBreak` at `0x383adc8c3`
- `KERNEL32!DebugBreak` at `0x383adc8d4`
- `ADVAPI32!RegEnumKeyExA` at `0x383adca69`
- `ADVAPI32!RegEnumKeyExA` at `0x383adca69`

## pseudocode

```c

```
