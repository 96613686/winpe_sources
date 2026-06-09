# CFileSystem::CreateDirectoryW(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18001d890`
- end: `0x18001d8b8`
- name: `?CreateDirectoryW@CFileSystem@@UEAAHPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(CFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d890`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001d8a1`
- `api-ms-win-core-file-l2-1-0!CreateDirectoryExW` at `0x18001d8b1`

## pseudocode

```c
BOOL __fastcall CFileSystem::CreateDirectoryW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  if ( a2 )
    return CreateDirectoryExW(a2, a3, a4);
  else
    return CreateDirectoryW(a3, a4);
}

```

## disassembly

```asm
0x18001d890  mov     rax, r8
0x18001d893  mov     r10, rdx
0x18001d896  test    rdx, rdx
0x18001d899  jnz     short loc_18001D8A8
0x18001d89b  mov     rdx, r9
0x18001d89e  mov     rcx, rax
0x18001d8a1  jmp     cs:__imp_CreateDirectoryW
0x18001d8a8  mov     r8, r9
0x18001d8ab  mov     rdx, rax
0x18001d8ae  mov     rcx, r10
0x18001d8b1  jmp     cs:__imp_CreateDirectoryExW
```
