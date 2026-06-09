# CTransactedFileSystem::CreateSymbolicLinkW(ushort const *,ushort const *,ulong)

- ea: `0x18001d5a0`
- end: `0x18001d5c8`
- name: `?CreateSymbolicLinkW@CTransactedFileSystem@@UEAAHPEBG0K@Z`
- size: `40`
- prototype: `int(CTransactedFileSystem *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path`

## import_xrefs

- `KERNEL32!CreateSymbolicLinkTransactedW` at `0x18001d5ba`
- `KERNEL32!CreateSymbolicLinkTransactedW` at `0x18001d5ba`

## pseudocode

```c
__int64 __fastcall CTransactedFileSystem::CreateSymbolicLinkW(
        HANDLE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4)
{
  return CreateSymbolicLinkTransactedW(a2, a3, a4, this[1]);
}

```

## disassembly

```asm
0x18001d5a0  sub     rsp, 28h
0x18001d5a4  mov     eax, r9d
0x18001d5a7  mov     r10, r8
0x18001d5aa  mov     r9, [rcx+8]; hTransaction
0x18001d5ae  mov     r11, rdx
0x18001d5b1  mov     r8d, eax; dwFlags
0x18001d5b4  mov     rdx, r10; lpTargetFileName
0x18001d5b7  mov     rcx, r11; lpSymlinkFileName
0x18001d5ba  call    cs:__imp_CreateSymbolicLinkTransactedW
0x18001d5c0  movzx   eax, al
0x18001d5c3  add     rsp, 28h
0x18001d5c7  retn
```
