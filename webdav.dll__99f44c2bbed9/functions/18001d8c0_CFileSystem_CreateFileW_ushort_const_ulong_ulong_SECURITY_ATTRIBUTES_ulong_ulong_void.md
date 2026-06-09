# CFileSystem::CreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18001d8c0`
- end: `0x18001d906`
- name: `?CreateFileW@CFileSystem@@UEAAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `70`
- prototype: `void *(CFileSystem *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d8fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d8fa`

## pseudocode

```c
HANDLE __fastcall CFileSystem::CreateFileW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  return CreateFileW(a2, a3, a4, lpSecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
}

```

## disassembly

```asm
0x18001d8c0  push    rbx
0x18001d8c2  sub     rsp, 40h
0x18001d8c6  mov     rax, [rsp+48h+arg_38]
0x18001d8ce  mov     r10d, r9d
0x18001d8d1  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x18001d8d6  mov     r11d, r8d
0x18001d8d9  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18001d8de  mov     rcx, rdx; lpFileName
0x18001d8e1  mov     eax, [rsp+48h+arg_30]
0x18001d8e8  mov     r8d, r10d; dwShareMode
0x18001d8eb  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18001d8ef  mov     edx, r11d; dwDesiredAccess
0x18001d8f2  mov     eax, [rsp+48h+arg_28]
0x18001d8f6  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18001d8fa  call    cs:__imp_CreateFileW
0x18001d900  add     rsp, 40h
0x18001d904  pop     rbx
0x18001d905  retn
```
