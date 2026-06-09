# long_help

- ea: `0x140001ee4`
- end: `0x140001f95`
- name: `long_help`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140001f9c`

## callees

- `0x140001b96`
- `0x140001d64`
- `0x140001ee4`
- `0x14000380c`
- `0x1400071e0`
- `0x1400076ad`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x140001f08`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x140001f08`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x140001f6b`
- `api-ms-win-crt-private-l1-1-0!_o_fputs` at `0x140001f6b`
- `api-ms-win-crt-private-l1-1-0!_o_putchar` at `0x140001f80`
- `api-ms-win-crt-private-l1-1-0!_o_putchar` at `0x140001f80`

## string_xrefs

- `0x140001f40`: `First option must be a mode specifier:\n  -c Create  -r Add/Replace  -t List  -u Update  -x Extract\nCommon Options:\n  -b #  Use # 512-byte records per I/O block\n  -f <filename>  Location of archive (default \\.\tape0)\n  -v    Verbose\n  -w    Interactive\nCreate: %p -c [options] [<file> | <dir> | @<archive> | -C <dir> ]\n  <file>, <dir>  add these items to archive\n  -z, -j, -J, --lzma  Compress archive with gzip/bzip2/xz/lzma\n  --format {ustar|pax|cpio|shar}  Select archive format\n  --exc`
- `0x140001f4a`: `First option must be a mode specifier:\n  -c Create  -r Add/Replace  -t List  -u Update  -x Extract\nCommon Options:\n  -b #  Use # 512-byte records per I/O block\n  -f <filename>  Location of archive (default \\.\tape0)\n  -v    Verbose\n  -w    Interactive\nCreate: %p -c [options] [<file> | <dir> | @<archive> | -C <dir> ]\n  <file>, <dir>  add these items to archive\n  -z, -j, -J, --lzma  Compress archive with gzip/bzip2/xz/lzma\n  --format {ustar|pax|cpio|shar}  Select archive format\n  --exc`

## pseudocode

```c
void __noreturn long_help()
{
  const char *v0; // rsi
  FILE *v1; // rax
  int v2; // eax
  const char *v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  char v7; // al
  const char *v8; // rbx
  FILE *v9; // rax
  __int64 v10; // rcx

  v0 = (const char *)lafe_getprogname();
  v1 = o___acrt_iob_func_0(2u);
  fflush(v1);
  v2 = strcmp_0(v0, "bsdtar");
  v3 = "(bsdtar)";
  if ( !v2 )
    v3 = &byte_14000A36F;
  printf("%s%s: manipulate archive files\n", v0, v3);
  v7 = aFirstOptionMus[0];
  if ( !aFirstOptionMus[0] )
LABEL_12:
    version(v5, v4, v6);
  v8 = "First option must be a mode specifier:\n"
       "  -c Create  -r Add/Replace  -t List  -u Update  -x Extract\n"
       "Common Options:\n"
       "  -b #  Use # 512-byte records per I/O block\n"
       "  -f <filename>  Location of archive (default \\\\.\\tape0)\n"
       "  -v    Verbose\n"
       "  -w    Interactive\n"
       "Create: %p -c [options] [<file> | <dir> | @<archive> | -C <dir> ]\n"
       "  <file>, <dir>  add these items to archive\n"
       "  -z, -j, -J, --lzma  Compress archive with gzip/bzip2/xz/lzma\n"
       "  --format {ustar|pax|cpio|shar}  Select archive format\n"
       "  --exclude <pattern>  Skip files that match pattern\n"
       "  --mtime <date>  Set modification times for added files\n"
       "  --clamp-mtime   Only set modification times for files newer than --mtime\n"
       "  -C <dir>  Change to <dir> before processing remaining files\n"
       "  @<archive>  Add entries from <archive> to output\n"
       "List: %p -t [options] [<patterns>]\n"
       "  <patterns>  If specified, list only entries that match\n"
       "Extract: %p -x [options] [<patterns>]\n"
       "  <patterns>  If specified, extract only entries that match\n"
       "  -k    Keep (don't overwrite) existing files\n"
       "  -m    Don't restore modification times\n"
       "  -O    Write entries to stdout, don't restore to disk\n"
       "  -p    Restore permissions (including ACLs, owner, file flags)\n";
  while ( v7 == 37 )
  {
    if ( v8[1] != 112 )
    {
      v10 = 37;
LABEL_10:
      _o_putchar(v10);
      goto LABEL_11;
    }
    v9 = o___acrt_iob_func_0(1u);
    _o_fputs(v0, v9);
    ++v8;
LABEL_11:
    v7 = *++v8;
    if ( !*v8 )
      goto LABEL_12;
  }
  v10 = (unsigned int)v7;
  goto LABEL_10;
}

```

## disassembly

```asm
0x140001ee4  mov     [rsp+arg_0], rbx
0x140001ee9  mov     [rsp+arg_8], rsi
0x140001eee  push    rdi
0x140001eef  sub     rsp, 20h
0x140001ef3  call    lafe_getprogname
0x140001ef8  mov     ecx, 2; Ix
0x140001efd  mov     rsi, rax
0x140001f00  call    _o___acrt_iob_func_0
0x140001f05  mov     rcx, rax; Stream
0x140001f08  call    cs:__imp_fflush
0x140001f0e  lea     rdx, Str2; "bsdtar"
0x140001f15  mov     rcx, rsi; Str1
0x140001f18  call    strcmp_0
0x140001f1d  test    eax, eax
0x140001f1f  lea     rcx, byte_14000A36F
0x140001f26  lea     r8, aBsdtar_0; "(bsdtar)"
0x140001f2d  mov     rdx, rsi
0x140001f30  cmovz   r8, rcx
0x140001f34  lea     rcx, Format; "%s%s: manipulate archive files\n"
0x140001f3b  call    printf
0x140001f40  mov     al, byte ptr cs:aFirstOptionMus; "First option must be a mode specifier:"...
0x140001f46  test    al, al
0x140001f48  jz      short loc_140001F8F
0x140001f4a  lea     rbx, aFirstOptionMus; "First option must be a mode specifier:"...
0x140001f51  cmp     al, 25h ; '%'
0x140001f53  jnz     short loc_140001F7D
0x140001f55  cmp     byte ptr [rbx+1], 70h ; 'p'
0x140001f59  jnz     short loc_140001F76
0x140001f5b  mov     ecx, 1; Ix
0x140001f60  call    _o___acrt_iob_func_0
0x140001f65  mov     rdx, rax
0x140001f68  mov     rcx, rsi
0x140001f6b  call    cs:__imp__o_fputs
0x140001f71  inc     rbx
0x140001f74  jmp     short loc_140001F86
0x140001f76  mov     ecx, 25h ; '%'
0x140001f7b  jmp     short loc_140001F80
0x140001f7d  movsx   ecx, al
0x140001f80  call    cs:__imp__o_putchar
0x140001f86  inc     rbx
0x140001f89  mov     al, [rbx]
0x140001f8b  test    al, al
0x140001f8d  jnz     short loc_140001F51
0x140001f8f  call    version
```
