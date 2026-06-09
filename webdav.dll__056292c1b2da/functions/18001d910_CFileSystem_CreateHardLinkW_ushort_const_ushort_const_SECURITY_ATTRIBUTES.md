# CFileSystem::CreateHardLinkW(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18001d910`
- end: `0x18001d923`
- name: `?CreateHardLinkW@CFileSystem@@UEAAHPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `19`
- prototype: `BOOL __fastcall(CFileSystem *this, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path, broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x18001d91c`

## pseudocode

```c
BOOL __fastcall CFileSystem::CreateHardLinkW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  return CreateHardLinkW(a2, a3, a4);
}

```

## disassembly

```asm
0x18001d910  mov     rax, r8
0x18001d913  mov     rcx, rdx
0x18001d916  mov     rdx, rax
0x18001d919  mov     r8, r9
0x18001d91c  jmp     cs:__imp_CreateHardLinkW
```
