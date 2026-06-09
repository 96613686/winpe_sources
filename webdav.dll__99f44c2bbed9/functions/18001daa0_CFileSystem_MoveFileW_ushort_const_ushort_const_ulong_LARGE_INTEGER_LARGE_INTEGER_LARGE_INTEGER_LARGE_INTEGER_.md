# CFileSystem::MoveFileW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,ulong)

- ea: `0x18001daa0`
- end: `0x18001dac6`
- name: `?MoveFileW@CFileSystem@@UEAAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2K@Z`
- size: `38`
- prototype: `__int64 __fastcall(CFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!MoveFileWithProgressW` at `0x18001dabf`

## pseudocode

```c
BOOL __fastcall CFileSystem::MoveFileW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int (*a4)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *a5,
        DWORD a6)
{
  return MoveFileWithProgressW(a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18001daa0  push    rbx
0x18001daa2  mov     eax, [rsp+8+arg_28]
0x18001daa6  mov     r10, r9
0x18001daa9  mov     r9, [rsp+8+arg_20]
0x18001daae  mov     r11, r8
0x18001dab1  mov     rcx, rdx
0x18001dab4  mov     dword ptr [rsp+8+arg_20], eax
0x18001dab8  mov     r8, r10
0x18001dabb  mov     rdx, r11
0x18001dabe  pop     rbx
0x18001dabf  jmp     cs:__imp_MoveFileWithProgressW
```
