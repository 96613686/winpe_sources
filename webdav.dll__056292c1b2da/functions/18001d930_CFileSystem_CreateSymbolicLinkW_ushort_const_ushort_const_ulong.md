# CFileSystem::CreateSymbolicLinkW(ushort const *,ushort const *,ulong)

- ea: `0x18001d930`
- end: `0x18001d94e`
- name: `?CreateSymbolicLinkW@CFileSystem@@UEAAHPEBG0K@Z`
- size: `30`
- prototype: `__int64 __fastcall(CFileSystem *this, const unsigned __int16 *, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18001d940`
- `api-ms-win-core-file-l2-1-0!CreateSymbolicLinkW` at `0x18001d940`

## pseudocode

```c
__int64 __fastcall CFileSystem::CreateSymbolicLinkW(
        CFileSystem *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4)
{
  return CreateSymbolicLinkW(a2, a3, a4);
}

```

## disassembly

```asm
0x18001d930  sub     rsp, 28h
0x18001d934  mov     rax, r8
0x18001d937  mov     rcx, rdx; lpSymlinkFileName
0x18001d93a  mov     rdx, rax; lpTargetFileName
0x18001d93d  mov     r8d, r9d; dwFlags
0x18001d940  call    cs:__imp_CreateSymbolicLinkW
0x18001d946  movzx   eax, al
0x18001d949  add     rsp, 28h
0x18001d94d  retn
```
