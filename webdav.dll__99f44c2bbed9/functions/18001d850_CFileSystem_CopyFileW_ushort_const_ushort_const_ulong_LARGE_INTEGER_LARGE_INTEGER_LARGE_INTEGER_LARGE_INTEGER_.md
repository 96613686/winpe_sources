# CFileSystem::CopyFileW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,ulong)

- ea: `0x18001d850`
- end: `0x18001d888`
- name: `?CopyFileW@CFileSystem@@UEAAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2PEAHK@Z`
- size: `56`
- prototype: `int(CFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, int *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001d87c`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18001d87c`

## pseudocode

```c
BOOL __fastcall CFileSystem::CopyFileW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int (*a4)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *lpData,
        int *pbCancel,
        DWORD dwCopyFlags)
{
  return CopyFileExW(a2, a3, a4, lpData, pbCancel, dwCopyFlags);
}

```

## disassembly

```asm
0x18001d850  push    rbx
0x18001d852  sub     rsp, 30h
0x18001d856  mov     eax, [rsp+38h+arg_30]
0x18001d85a  mov     r10, r9
0x18001d85d  mov     r9, [rsp+38h+lpData]; lpData
0x18001d862  mov     r11, r8
0x18001d865  mov     [rsp+38h+dwCopyFlags], eax; dwCopyFlags
0x18001d869  mov     rcx, rdx; lpExistingFileName
0x18001d86c  mov     rax, [rsp+38h+arg_28]
0x18001d871  mov     r8, r10; lpProgressRoutine
0x18001d874  mov     rdx, r11; lpNewFileName
0x18001d877  mov     [rsp+38h+pbCancel], rax; pbCancel
0x18001d87c  call    cs:__imp_CopyFileExW
0x18001d882  add     rsp, 30h
0x18001d886  pop     rbx
0x18001d887  retn
```
