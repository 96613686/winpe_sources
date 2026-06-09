# CIlKernel32::GetWindowsDirectoryW(ushort *,uint)

- ea: `0x18000eb40`
- end: `0x18000eb4d`
- name: `?GetWindowsDirectoryW@CIlKernel32@@UEAAIPEAGI@Z`
- size: `13`
- prototype: `unsigned int __fastcall(CIlKernel32 *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18000eb46`

## pseudocode

```c
UINT __fastcall CIlKernel32::GetWindowsDirectoryW(CIlKernel32 *this, unsigned __int16 *a2, UINT a3)
{
  return GetWindowsDirectoryW(a2, a3);
}

```

## disassembly

```asm
0x18000eb40  mov     rcx, rdx
0x18000eb43  mov     edx, r8d
0x18000eb46  jmp     cs:__imp_GetWindowsDirectoryW
```
