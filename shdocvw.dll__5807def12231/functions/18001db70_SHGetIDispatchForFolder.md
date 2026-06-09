# SHGetIDispatchForFolder

- ea: `0x18001db70`
- end: `0x18001db82`
- name: `SHGetIDispatchForFolder`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `SHELL32!__imp_SHOpenOrGetWebBrowserApp` at `0x18001db7b`

## pseudocode

```c
__int64 __fastcall SHGetIDispatchForFolder(__int64 a1, __int64 a2)
{
  return SHOpenOrGetWebBrowserApp(1, a1, a2);
}

```

## disassembly

```asm
0x18001db70  mov     r8, rdx
0x18001db73  mov     rdx, rcx
0x18001db76  mov     ecx, 1
0x18001db7b  jmp     cs:__imp_SHOpenOrGetWebBrowserApp
```
