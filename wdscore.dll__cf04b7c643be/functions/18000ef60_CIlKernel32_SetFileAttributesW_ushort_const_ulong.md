# CIlKernel32::SetFileAttributesW(ushort const *,ulong)

- ea: `0x18000ef60`
- end: `0x18000ef6d`
- name: `?SetFileAttributesW@CIlKernel32@@UEAAHPEBGK@Z`
- size: `13`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ef66`

## pseudocode

```c
BOOL __fastcall CIlKernel32::SetFileAttributesW(CIlKernel32 *this, const unsigned __int16 *a2, DWORD a3)
{
  return SetFileAttributesW(a2, a3);
}

```

## disassembly

```asm
0x18000ef60  mov     rcx, rdx
0x18000ef63  mov     edx, r8d
0x18000ef66  jmp     cs:__imp_SetFileAttributesW
```
