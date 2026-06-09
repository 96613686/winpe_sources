# ArchiveEntryTypeLoggingString(archive_entry *)

- ea: `0x180064734`
- end: `0x1800647f7`
- name: `?ArchiveEntryTypeLoggingString@@YAPEBGPEAUarchive_entry@@@Z`
- size: `195`
- prototype: `const unsigned __int16 *__fastcall(struct archive_entry *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180062d2c`

## callees

- `0x180064734`

## import_xrefs

- `archiveint!archive_entry_hardlink_w` at `0x180064794`
- `archiveint!archive_entry_hardlink_w` at `0x180064794`
- `archiveint!archive_entry_filetype` at `0x18006473d`
- `archiveint!archive_entry_filetype` at `0x18006473d`

## string_xrefs

- `0x1800647d8`: `directory`
- `0x1800647bd`: `symlink`
- `0x18006479d`: `hardlink`

## pseudocode

```c
const unsigned __int16 *__fastcall ArchiveEntryTypeLoggingString(struct archive_entry *a1)
{
  __int16 v2; // ax
  __int64 v3; // rax
  const wchar_t *v4; // rcx

  v2 = archive_entry_filetype(a1);
  switch ( v2 )
  {
    case 4096:
      return L"fifo";
    case 8192:
      return L"char";
    case 16384:
      return L"directory";
    case 24576:
      return L"block";
    case -32768:
      return L"file";
    case -24576:
      return L"symlink";
    case -16384:
      return L"socket";
  }
  v3 = archive_entry_hardlink_w(a1);
  v4 = L"file";
  if ( v3 )
    return L"hardlink";
  return v4;
}

```

## disassembly

```asm
0x180064734  push    rbx
0x180064736  sub     rsp, 20h
0x18006473a  mov     rbx, rcx
0x18006473d  call    cs:__imp_archive_entry_filetype
0x180064743  mov     ecx, 1000h
0x180064748  cmp     ax, cx
0x18006474b  jz      loc_1800647EA
0x180064751  mov     ecx, 2000h
0x180064756  cmp     ax, cx
0x180064759  jz      loc_1800647E1
0x18006475f  mov     ecx, 4000h
0x180064764  cmp     ax, cx
0x180064767  jz      short loc_1800647D8
0x180064769  mov     ecx, 6000h
0x18006476e  cmp     ax, cx
0x180064771  jz      short loc_1800647CF
0x180064773  mov     ecx, 8000h
0x180064778  cmp     ax, cx
0x18006477b  jz      short loc_1800647C6
0x18006477d  mov     ecx, 0A000h
0x180064782  cmp     ax, cx
0x180064785  jz      short loc_1800647BD
0x180064787  mov     ecx, 0C000h
0x18006478c  cmp     ax, cx
0x18006478f  jz      short loc_1800647B4
0x180064791  mov     rcx, rbx
0x180064794  call    cs:__imp_archive_entry_hardlink_w
0x18006479a  test    rax, rax
0x18006479d  lea     rdx, aHardlink; "hardlink"
0x1800647a4  lea     rcx, aFile; "file"
0x1800647ab  cmovnz  rcx, rdx
0x1800647af  mov     rax, rcx
0x1800647b2  jmp     short loc_1800647F1
0x1800647b4  lea     rax, aSocket; "socket"
0x1800647bb  jmp     short loc_1800647F1
0x1800647bd  lea     rax, aSymlink; "symlink"
0x1800647c4  jmp     short loc_1800647F1
0x1800647c6  lea     rax, aFile; "file"
0x1800647cd  jmp     short loc_1800647F1
0x1800647cf  lea     rax, aBlock; "block"
0x1800647d6  jmp     short loc_1800647F1
0x1800647d8  lea     rax, aDirectory; "directory"
0x1800647df  jmp     short loc_1800647F1
0x1800647e1  lea     rax, aChar; "char"
0x1800647e8  jmp     short loc_1800647F1
0x1800647ea  lea     rax, aFifo; "fifo"
0x1800647f1  add     rsp, 20h
0x1800647f5  pop     rbx
0x1800647f6  retn
```
