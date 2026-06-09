# CTransactedFileSystem::CopyFileW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,ulong)

- ea: `0x18001d480`
- end: `0x18001d4c7`
- name: `?CopyFileW@CTransactedFileSystem@@UEAAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2PEAHK@Z`
- size: `71`
- prototype: `int(CTransactedFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, int *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!CopyFileTransactedW` at `0x18001d4bb`
- `KERNEL32!CopyFileTransactedW` at `0x18001d4bb`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::CopyFileW(
        HANDLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int (*a4)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *lpData,
        int *pbCancel,
        DWORD dwCopyFlags)
{
  return CopyFileTransactedW(a2, a3, a4, lpData, pbCancel, dwCopyFlags, this[1]);
}

```

## disassembly

```asm
0x18001d480  push    rbx
0x18001d482  sub     rsp, 40h
0x18001d486  mov     rax, [rcx+8]
0x18001d48a  mov     r10, r9
0x18001d48d  mov     r9, [rsp+48h+lpData]; lpData
0x18001d492  mov     r11, r8
0x18001d495  mov     [rsp+48h+hTransaction], rax; hTransaction
0x18001d49a  mov     rbx, rdx
0x18001d49d  mov     eax, [rsp+48h+arg_30]
0x18001d4a4  mov     r8, r10; lpProgressRoutine
0x18001d4a7  mov     [rsp+48h+dwCopyFlags], eax; dwCopyFlags
0x18001d4ab  mov     rdx, r11; lpNewFileName
0x18001d4ae  mov     rax, [rsp+48h+arg_28]
0x18001d4b3  mov     rcx, rbx; lpExistingFileName
0x18001d4b6  mov     [rsp+48h+pbCancel], rax; pbCancel
0x18001d4bb  call    cs:__imp_CopyFileTransactedW
0x18001d4c1  add     rsp, 40h
0x18001d4c5  pop     rbx
0x18001d4c6  retn
```
