# CTransactedFileSystem::CreateDirectoryW(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18001d4d0`
- end: `0x18001d4ed`
- name: `?CreateDirectoryW@CTransactedFileSystem@@UEAAHPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!CreateDirectoryTransactedW` at `0x18001d4e6`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::CreateDirectoryW(
        HANDLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  return CreateDirectoryTransactedW(a2, a3, a4, this[1]);
}

```

## disassembly

```asm
0x18001d4d0  mov     rax, r9
0x18001d4d3  mov     r10, r8
0x18001d4d6  mov     r9, [rcx+8]
0x18001d4da  mov     r11, rdx
0x18001d4dd  mov     r8, rax
0x18001d4e0  mov     rdx, r10
0x18001d4e3  mov     rcx, r11
0x18001d4e6  jmp     cs:__imp_CreateDirectoryTransactedW
```
