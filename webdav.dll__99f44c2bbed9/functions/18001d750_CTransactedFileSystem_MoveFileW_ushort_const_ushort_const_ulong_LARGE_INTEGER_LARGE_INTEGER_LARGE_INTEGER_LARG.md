# CTransactedFileSystem::MoveFileW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,ulong)

- ea: `0x18001d750`
- end: `0x18001d78a`
- name: `?MoveFileW@CTransactedFileSystem@@UEAAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2K@Z`
- size: `58`
- prototype: `int(CTransactedFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!MoveFileTransactedW` at `0x18001d77e`
- `KERNEL32!MoveFileTransactedW` at `0x18001d77e`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::MoveFileW(
        HANDLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int (*a4)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *lpData,
        DWORD dwFlags)
{
  return MoveFileTransactedW(a2, a3, a4, lpData, dwFlags, this[1]);
}

```

## disassembly

```asm
0x18001d750  push    rbx
0x18001d752  sub     rsp, 30h
0x18001d756  mov     rax, [rcx+8]
0x18001d75a  mov     r10, r9
0x18001d75d  mov     r9, [rsp+38h+lpData]; lpData
0x18001d762  mov     r11, r8
0x18001d765  mov     rbx, rdx
0x18001d768  mov     [rsp+38h+hTransaction], rax; hTransaction
0x18001d76d  mov     eax, [rsp+38h+arg_28]
0x18001d771  mov     r8, r10; lpProgressRoutine
0x18001d774  mov     rdx, r11; lpNewFileName
0x18001d777  mov     [rsp+38h+dwFlags], eax; dwFlags
0x18001d77b  mov     rcx, rbx; lpExistingFileName
0x18001d77e  call    cs:__imp_MoveFileTransactedW
0x18001d784  add     rsp, 30h
0x18001d788  pop     rbx
0x18001d789  retn
```
