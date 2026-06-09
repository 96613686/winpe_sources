# PostMessageW

- ea: `0x180020990`
- end: `0x180020b60`
- name: `PostMessageW`
- size: `464`
- prototype: `BOOL __stdcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `16`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180008ab0`
- `0x18000f140`
- `0x180011c6c`
- `0x180011f38`
- `0x18003ae48`
- `0x18005ba14`
- `0x18005e2b4`
- `0x18005e380`
- `0x180060370`
- `0x180063cc8`
- `0x1800657d4`
- `0x1800794ec`
- `0x18007c6c4`
- `0x180084d60`
- `0x180085ab4`
- `0x18009095c`

## callees

- `0x18000cf20`
- `0x180020990`
- `0x180020b70`
- `0x180020c20`
- `0x180020c40`
- `0x180021cb4`

## import_xrefs

- `win32u!NtUserQueryWindow` at `0x180020ad7`
- `win32u!NtUserQueryWindow` at `0x180020ad7`
- `win32u!NtUserPostMessage` at `0x1800209ed`
- `win32u!NtUserPostMessage` at `0x180020abd`
- `win32u!NtUserPostMessage` at `0x1800209ed`
- `win32u!NtUserPostMessage` at `0x180020abd`
- `ntdll!RtlSetLastWin32Error` at `0x180020a34`
- `ntdll!RtlSetLastWin32Error` at `0x180020a34`
- `ntdll!RtlFreeHeap` at `0x180020a9f`
- `ntdll!RtlFreeHeap` at `0x180020a9f`
- `ntdll!RtlAllocateHeap` at `0x180020a5e`
- `ntdll!RtlAllocateHeap` at `0x180020a5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180020ae9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180020ae9`

## pseudocode

```c

```
