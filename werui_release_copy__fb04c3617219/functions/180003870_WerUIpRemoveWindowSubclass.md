# WerUIpRemoveWindowSubclass

- ea: `0x180003870`
- end: `0x18000387a`
- name: `WerUIpRemoveWindowSubclass`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `COMCTL32!__imp_RemoveWindowSubclass` at `0x180003873`

## pseudocode

```c
BOOL __fastcall WerUIpRemoveWindowSubclass(
        HWND a1,
        LRESULT (__stdcall *a2)(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData))
{
  return RemoveWindowSubclass(a1, a2, 0);
}

```

## disassembly

```asm
0x180003870  xor     r8d, r8d
0x180003873  jmp     cs:__imp_RemoveWindowSubclass
```
