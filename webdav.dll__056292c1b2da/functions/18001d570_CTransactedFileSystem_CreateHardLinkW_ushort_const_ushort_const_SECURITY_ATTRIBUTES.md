# CTransactedFileSystem::CreateHardLinkW(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18001d570`
- end: `0x18001d58d`
- name: `?CreateHardLinkW@CTransactedFileSystem@@UEAAHPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(CTransactedFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path, broker_com_uri`

## import_xrefs

- `KERNEL32!CreateHardLinkTransactedW` at `0x18001d586`

## pseudocode

```c
BOOL __fastcall CTransactedFileSystem::CreateHardLinkW(
        HANDLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  return CreateHardLinkTransactedW(a2, a3, a4, this[1]);
}

```

## disassembly

```asm
0x18001d570  mov     rax, r9
0x18001d573  mov     r10, r8
0x18001d576  mov     r9, [rcx+8]
0x18001d57a  mov     r11, rdx
0x18001d57d  mov     r8, rax
0x18001d580  mov     rdx, r10
0x18001d583  mov     rcx, r11
0x18001d586  jmp     cs:__imp_CreateHardLinkTransactedW
```
