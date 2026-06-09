# write_archive

- ea: `0x1400069a8`
- end: `0x140006da9`
- name: `write_archive`
- size: `1025`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path`

## callers

- `0x1400061dc`
- `0x1400063bc`
- `0x140006650`

## callees

- `0x140001b96`
- `0x140001d10`
- `0x140004b20`
- `0x140005390`
- `0x14000561c`
- `0x140005a74`
- `0x140005bbc`
- `0x1400069a8`
- `0x140006db0`
- `0x140006ea4`
- `0x1400071a4`
- `0x140007298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006ce7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006ce7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400069f5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400069f5`
- `archiveint!archive_errno` at `0x140006be2`
- `archiveint!archive_errno` at `0x140006c3a`
- `archiveint!archive_errno` at `0x140006be2`
- `archiveint!archive_errno` at `0x140006c3a`
- `archiveint!archive_read_free` at `0x140006d0c`
- `archiveint!archive_read_free` at `0x140006d0c`
- `archiveint!archive_filter_bytes` at `0x140006d2c`
- `archiveint!archive_filter_bytes` at `0x140006d2c`
- `archiveint!archive_write_free` at `0x140006d5c`
- `archiveint!archive_write_free` at `0x140006d5c`
- `archiveint!archive_read_close` at `0x140006c75`
- `archiveint!archive_read_close` at `0x140006c75`
- `archiveint!archive_entry_linkresolver_set_strategy` at `0x140006a32`
- `archiveint!archive_entry_linkresolver_set_strategy` at `0x140006a32`
- `archiveint!archive_read_disk_set_matching` at `0x140006a8b`
- `archiveint!archive_read_disk_set_matching` at `0x140006b52`
- `archiveint!archive_read_disk_set_matching` at `0x140006a8b`
- `archiveint!archive_read_disk_set_matching` at `0x140006b52`
- `archiveint!archive_entry_free` at `0x140006c20`
- `archiveint!archive_entry_free` at `0x140006c7f`
- `archiveint!archive_entry_free` at `0x140006c20`
- `archiveint!archive_entry_free` at `0x140006c7f`
- `archiveint!archive_read_disk_new` at `0x140006a38`
- `archiveint!archive_read_disk_new` at `0x140006a38`
- `archiveint!archive_entry_linkresolver_free` at `0x140006cf4`
- `archiveint!archive_entry_linkresolver_free` at `0x140006cf4`
- `archiveint!archive_entry_linkify` at `0x140006c9c`
- `archiveint!archive_entry_linkify` at `0x140006c9c`
- `archiveint!archive_read_next_header2` at `0x140006c14`
- `archiveint!archive_read_next_header2` at `0x140006c14`
- `archiveint!archive_read_disk_set_symlink_hybrid` at `0x140006a6d`
- `archiveint!archive_read_disk_set_symlink_hybrid` at `0x140006a6d`
- `archiveint!archive_format` at `0x140006a27`
- `archiveint!archive_format` at `0x140006a27`
- `archiveint!archive_read_disk_open` at `0x140006bc9`
- `archiveint!archive_read_disk_open` at `0x140006bc9`
- `archiveint!archive_entry_linkresolver_new` at `0x140006a0b`
- `archiveint!archive_entry_linkresolver_new` at `0x140006a0b`
- `archiveint!archive_entry_sourcepath` at `0x140006bbd`
- `archiveint!archive_entry_sourcepath` at `0x140006bbd`
- `archiveint!archive_entry_new` at `0x140006c05`
- `archiveint!archive_entry_new` at `0x140006c05`
- `archiveint!archive_read_disk_set_behavior` at `0x140006ab2`
- `archiveint!archive_read_disk_set_behavior` at `0x140006ab2`
- `archiveint!archive_read_disk_set_symlink_physical` at `0x140006a5d`
- `archiveint!archive_read_disk_set_symlink_physical` at `0x140006a5d`
- `archiveint!archive_read_disk_set_symlink_logical` at `0x140006a65`
- `archiveint!archive_read_disk_set_symlink_logical` at `0x140006a65`
- `archiveint!archive_read_disk_set_metadata_filter_callback` at `0x140006aa2`
- `archiveint!archive_read_disk_set_metadata_filter_callback` at `0x140006b64`
- `archiveint!archive_read_disk_set_metadata_filter_callback` at `0x140006aa2`
- `archiveint!archive_read_disk_set_metadata_filter_callback` at `0x140006b64`
- `archiveint!archive_read_disk_set_standard_lookup` at `0x140006abf`
- `archiveint!archive_read_disk_set_standard_lookup` at `0x140006abf`
- `archiveint!archive_write_close` at `0x140006cb2`
- `archiveint!archive_write_close` at `0x140006cb2`
- `archiveint!archive_error_string` at `0x140006bd6`
- `archiveint!archive_error_string` at `0x140006c2e`
- `archiveint!archive_error_string` at `0x140006cbf`
- `archiveint!archive_error_string` at `0x140006bd6`
- `archiveint!archive_error_string` at `0x140006c2e`
- `archiveint!archive_error_string` at `0x140006cbf`

## string_xrefs

- `0x140006d87`: `cannot create link resolver`
- `0x140006d99`: `Cannot create read_disk object`

## pseudocode

```c
__int64 __fastcall write_archive(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v4; // rcx
  size_t v6; // rcx
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned int v10; // eax
  __int64 disk_new; // rax
  __int64 v12; // r8
  _BYTE *v13; // rdx
  _BYTE **v14; // rax
  _BYTE **v15; // rax
  _BYTE *v16; // rbx
  const char *v17; // r8
  __int64 v18; // r14
  __int64 v19; // rax
  const char *v20; // rbx
  unsigned int v21; // eax
  __int64 v22; // rbx
  int next_header2; // r15d
  const char *v24; // rbx
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  bool v28; // zf
  __int64 v29; // rax
  const char *v30; // rbx
  FILE *v31; // rax
  __int64 v33; // [rsp+58h] [rbp+38h] BYREF
  __int64 i; // [rsp+60h] [rbp+40h] BYREF

  v2 = *(int *)(a2 + 24);
  v4 = 0x10000;
  v33 = 0;
  for ( i = 0; v4 < v2; v4 *= 2LL )
    ;
  v6 = v4 + 0x4000;
  *(_QWORD *)(a2 + 240) = v6;
  v7 = malloc(v6);
  *(_QWORD *)(a2 + 232) = v7;
  if ( !v7 )
    lafe_errc(1);
  v8 = archive_entry_linkresolver_new();
  *(_QWORD *)(a2 + 208) = v8;
  if ( !v8 )
    lafe_errc(1);
  v9 = v8;
  v10 = archive_format(a1);
  archive_entry_linkresolver_set_strategy(v9, v10);
  disk_new = archive_read_disk_new();
  *(_QWORD *)(a2 + 200) = disk_new;
  if ( !disk_new )
    lafe_errc(1);
  if ( *(_BYTE *)(a2 + 92) == 72 )
  {
    archive_read_disk_set_symlink_hybrid(disk_new);
  }
  else if ( *(_BYTE *)(a2 + 92) == 76 )
  {
    archive_read_disk_set_symlink_logical(disk_new);
  }
  else
  {
    archive_read_disk_set_symlink_physical(disk_new);
  }
  archive_read_disk_set_matching(*(_QWORD *)(a2 + 200), *(_QWORD *)(a2 + 256), excluded_callback, a2);
  archive_read_disk_set_metadata_filter_callback(*(_QWORD *)(a2 + 200), metadata_filter, a2);
  archive_read_disk_set_behavior(*(_QWORD *)(a2 + 200), *(unsigned int *)(a2 + 44));
  archive_read_disk_set_standard_lookup(*(_QWORD *)(a2 + 200));
  if ( *(_QWORD *)(a2 + 16) )
    archive_names_from_file(a2, a1);
  while ( 1 )
  {
    v15 = *(_BYTE ***)(a2 + 152);
    v16 = *v15;
    if ( !*v15 )
      break;
    if ( *v16 != 45 )
    {
      if ( *v16 != 47 )
LABEL_20:
        do_chdir(a2);
      if ( *v16 == 64 )
      {
        if ( (unsigned int)append_archive_filename(a2, a1, v16 + 1) )
          break;
      }
      else
      {
        write_hierarchy(a2, a1, v16);
      }
      goto LABEL_25;
    }
    if ( v16[1] != 67 )
      goto LABEL_20;
    v13 = v16 + 2;
    if ( !v16[2] )
    {
      v14 = v15 + 1;
      *(_QWORD *)(a2 + 152) = v14;
      v13 = *v14;
      if ( !*v14 )
      {
        v17 = "Missing argument for -C";
LABEL_41:
        lafe_warnc(0, "%s", v17);
        goto LABEL_42;
      }
      if ( !*v13 )
      {
        lafe_warnc(0, "Meaningless argument for -C: ''");
LABEL_42:
        *(_DWORD *)(a2 + 188) = 1;
        goto LABEL_43;
      }
    }
    set_chdir(a2, v13, v12);
LABEL_25:
    *(_QWORD *)(a2 + 152) += 8LL;
  }
  archive_read_disk_set_matching(*(_QWORD *)(a2 + 200), 0, 0, 0);
  archive_read_disk_set_metadata_filter_callback(*(_QWORD *)(a2 + 200), 0, 0);
  while ( 1 )
  {
    v26 = *(_QWORD *)(a2 + 208);
    v33 = 0;
    archive_entry_linkify(v26, &v33, &i);
    if ( !v33 )
      break;
    v18 = *(_QWORD *)(a2 + 200);
    v19 = archive_entry_sourcepath(v33);
    if ( (unsigned int)archive_read_disk_open(v18, v19) )
    {
      v20 = (const char *)archive_error_string(v18);
      v21 = archive_errno(v18);
      lafe_warnc(v21, "%s", v20);
      *(_DWORD *)(a2 + 188) = 1;
    }
    else
    {
      v22 = archive_entry_new();
      next_header2 = archive_read_next_header2(v18, v22);
      archive_entry_free(v22);
      if ( next_header2 )
      {
        v24 = (const char *)archive_error_string(v18);
        v25 = archive_errno(v18);
        lafe_warnc(v25, "%s", v24);
        if ( next_header2 == -30 )
          *(_DWORD *)(a2 + 188) = 1;
      }
      else
      {
        write_file(a2, a1, v33);
      }
      archive_read_close(v18);
    }
    archive_entry_free(v33);
  }
  if ( (unsigned int)archive_write_close(a1) )
  {
    v17 = (const char *)archive_error_string(a1);
    goto LABEL_41;
  }
LABEL_43:
  free(*(void **)(a2 + 232));
  archive_entry_linkresolver_free(*(_QWORD *)(a2 + 208));
  v27 = *(_QWORD *)(a2 + 200);
  *(_QWORD *)(a2 + 208) = 0;
  archive_read_free(v27);
  v28 = (*(_DWORD *)(a2 + 36) & 0x1000) == 0;
  *(_QWORD *)(a2 + 200) = 0;
  if ( !v28 )
  {
    v29 = archive_filter_bytes(a1, 0xFFFFFFFFLL);
    v30 = (const char *)tar_i64toa(v29);
    v31 = o___acrt_iob_func_0(2u);
    fprintf(v31, "Total bytes written: %s\n", v30);
  }
  return archive_write_free(a1);
}

```

## disassembly

```asm
0x1400069a8  mov     [rsp-28h+arg_0], rbx
0x1400069ad  push    rbp
0x1400069ae  push    rsi
0x1400069af  push    rdi
0x1400069b0  push    r14
0x1400069b2  push    r15
0x1400069b4  mov     rbp, rsp
0x1400069b7  sub     rsp, 20h
0x1400069bb  movsxd  rax, dword ptr [rdx+18h]
0x1400069bf  mov     rsi, rcx
0x1400069c2  mov     ecx, 10000h
0x1400069c7  mov     [rbp+arg_8], 0
0x1400069cf  mov     [rbp+arg_10], 0
0x1400069d7  mov     rdi, rdx
0x1400069da  cmp     rax, rcx
0x1400069dd  jbe     short loc_1400069E7
0x1400069df  add     rcx, rcx
0x1400069e2  cmp     rcx, rax
0x1400069e5  jb      short loc_1400069DF
0x1400069e7  add     rcx, 4000h; Size
0x1400069ee  mov     [rdx+0F0h], rcx
0x1400069f5  call    cs:__imp_malloc
0x1400069fb  mov     [rdi+0E8h], rax
0x140006a02  test    rax, rax
0x140006a05  jz      loc_140006D73
0x140006a0b  call    cs:__imp_archive_entry_linkresolver_new
0x140006a11  mov     [rdi+0D0h], rax
0x140006a18  test    rax, rax
0x140006a1b  jz      loc_140006D85
0x140006a21  mov     rcx, rsi
0x140006a24  mov     rbx, rax
0x140006a27  call    cs:__imp_archive_format
0x140006a2d  mov     edx, eax
0x140006a2f  mov     rcx, rbx
0x140006a32  call    cs:__imp_archive_entry_linkresolver_set_strategy
0x140006a38  call    cs:__imp_archive_read_disk_new
0x140006a3e  mov     [rdi+0C8h], rax
0x140006a45  test    rax, rax
0x140006a48  jz      loc_140006D97
0x140006a4e  cmp     byte ptr [rdi+5Ch], 48h ; 'H'
0x140006a52  mov     rcx, rax
0x140006a55  jz      short loc_140006A6D
0x140006a57  cmp     byte ptr [rdi+5Ch], 4Ch ; 'L'
0x140006a5b  jz      short loc_140006A65
0x140006a5d  call    cs:__imp_archive_read_disk_set_symlink_physical
0x140006a63  jmp     short loc_140006A73
0x140006a65  call    cs:__imp_archive_read_disk_set_symlink_logical
0x140006a6b  jmp     short loc_140006A73
0x140006a6d  call    cs:__imp_archive_read_disk_set_symlink_hybrid
0x140006a73  mov     rdx, [rdi+100h]
0x140006a7a  lea     r8, excluded_callback
0x140006a81  mov     rcx, [rdi+0C8h]
0x140006a88  mov     r9, rdi
0x140006a8b  call    cs:__imp_archive_read_disk_set_matching
0x140006a91  mov     rcx, [rdi+0C8h]
0x140006a98  lea     rdx, metadata_filter
0x140006a9f  mov     r8, rdi
0x140006aa2  call    cs:__imp_archive_read_disk_set_metadata_filter_callback
0x140006aa8  mov     edx, [rdi+2Ch]
0x140006aab  mov     rcx, [rdi+0C8h]
0x140006ab2  call    cs:__imp_archive_read_disk_set_behavior
0x140006ab8  mov     rcx, [rdi+0C8h]
0x140006abf  call    cs:__imp_archive_read_disk_set_standard_lookup
0x140006ac5  cmp     qword ptr [rdi+10h], 0
0x140006aca  jz      loc_140006B7F
0x140006ad0  mov     rdx, rsi
0x140006ad3  mov     rcx, rdi
0x140006ad6  call    archive_names_from_file
0x140006adb  jmp     loc_140006B7F
0x140006ae0  cmp     byte ptr [rbx], 2Dh ; '-'
0x140006ae3  jnz     short loc_140006B1E
0x140006ae5  cmp     byte ptr [rbx+1], 43h ; 'C'
0x140006ae9  jnz     short loc_140006B23
0x140006aeb  lea     rdx, [rbx+2]
0x140006aef  cmp     byte ptr [rdx], 0
0x140006af2  jnz     short loc_140006B14
0x140006af4  add     rax, 8
0x140006af8  mov     [rdi+98h], rax
0x140006aff  mov     rdx, [rax]
0x140006b02  test    rdx, rdx
0x140006b05  jz      loc_140006BA7
0x140006b0b  cmp     byte ptr [rdx], 0
0x140006b0e  jz      loc_140006B94
0x140006b14  mov     rcx, rdi
0x140006b17  call    set_chdir
0x140006b1c  jmp     short loc_140006B77
0x140006b1e  cmp     byte ptr [rbx], 2Fh ; '/'
0x140006b21  jz      short loc_140006B2B
0x140006b23  mov     rcx, rdi
0x140006b26  call    do_chdir
0x140006b2b  cmp     byte ptr [rbx], 40h ; '@'
0x140006b2e  mov     rdx, rsi
0x140006b31  mov     rcx, rdi
0x140006b34  jnz     short loc_140006B6F
0x140006b36  lea     r8, [rbx+1]
0x140006b3a  call    append_archive_filename
0x140006b3f  test    eax, eax
0x140006b41  jz      short loc_140006B77
0x140006b43  mov     rcx, [rdi+0C8h]
0x140006b4a  xor     r9d, r9d
0x140006b4d  xor     r8d, r8d
0x140006b50  xor     edx, edx
0x140006b52  call    cs:__imp_archive_read_disk_set_matching
0x140006b58  mov     rcx, [rdi+0C8h]
0x140006b5f  xor     r8d, r8d
0x140006b62  xor     edx, edx
0x140006b64  call    cs:__imp_archive_read_disk_set_metadata_filter_callback
0x140006b6a  jmp     loc_140006C85
0x140006b6f  mov     r8, rbx
0x140006b72  call    write_hierarchy
0x140006b77  add     qword ptr [rdi+98h], 8
0x140006b7f  mov     rax, [rdi+98h]
0x140006b86  mov     rbx, [rax]
0x140006b89  test    rbx, rbx
0x140006b8c  jnz     loc_140006AE0
0x140006b92  jmp     short loc_140006B43
0x140006b94  lea     rdx, aMeaninglessArg; "Meaningless argument for -C: ''"
0x140006b9b  xor     ecx, ecx
0x140006b9d  call    lafe_warnc
0x140006ba2  jmp     loc_140006CD6
0x140006ba7  lea     r8, aMissingArgumen; "Missing argument for -C"
0x140006bae  jmp     loc_140006CC8
0x140006bb3  mov     r14, [rdi+0C8h]
0x140006bba  mov     rcx, rax
0x140006bbd  call    cs:__imp_archive_entry_sourcepath
0x140006bc3  mov     rdx, rax
0x140006bc6  mov     rcx, r14
0x140006bc9  call    cs:__imp_archive_read_disk_open
0x140006bcf  test    eax, eax
0x140006bd1  jz      short loc_140006C05
0x140006bd3  mov     rcx, r14
0x140006bd6  call    cs:__imp_archive_error_string
0x140006bdc  mov     rcx, r14
0x140006bdf  mov     rbx, rax
0x140006be2  call    cs:__imp_archive_errno
0x140006be8  mov     r8, rbx
0x140006beb  lea     rdx, aS_5; "%s"
0x140006bf2  mov     ecx, eax
0x140006bf4  call    lafe_warnc
0x140006bf9  mov     dword ptr [rdi+0BCh], 1
0x140006c03  jmp     short loc_140006C7B
0x140006c05  call    cs:__imp_archive_entry_new
0x140006c0b  mov     rdx, rax
0x140006c0e  mov     rcx, r14
0x140006c11  mov     rbx, rax
0x140006c14  call    cs:__imp_archive_read_next_header2
0x140006c1a  mov     rcx, rbx
0x140006c1d  mov     r15d, eax
0x140006c20  call    cs:__imp_archive_entry_free
0x140006c26  test    r15d, r15d
0x140006c29  jz      short loc_140006C63
0x140006c2b  mov     rcx, r14
0x140006c2e  call    cs:__imp_archive_error_string
0x140006c34  mov     rcx, r14
0x140006c37  mov     rbx, rax
0x140006c3a  call    cs:__imp_archive_errno
0x140006c40  mov     r8, rbx
0x140006c43  lea     rdx, aS_5; "%s"
0x140006c4a  mov     ecx, eax
0x140006c4c  call    lafe_warnc
0x140006c51  cmp     r15d, 0FFFFFFE2h
0x140006c55  jnz     short loc_140006C72
0x140006c57  mov     dword ptr [rdi+0BCh], 1
0x140006c61  jmp     short loc_140006C72
0x140006c63  mov     r8, [rbp+arg_8]
0x140006c67  mov     rdx, rsi
0x140006c6a  mov     rcx, rdi
0x140006c6d  call    write_file
0x140006c72  mov     rcx, r14
0x140006c75  call    cs:__imp_archive_read_close
0x140006c7b  mov     rcx, [rbp+arg_8]
0x140006c7f  call    cs:__imp_archive_entry_free
0x140006c85  mov     rcx, [rdi+0D0h]
0x140006c8c  lea     r8, [rbp+arg_10]
0x140006c90  lea     rdx, [rbp+arg_8]
0x140006c94  mov     [rbp+arg_8], 0
0x140006c9c  call    cs:__imp_archive_entry_linkify
0x140006ca2  mov     rax, [rbp+arg_8]
0x140006ca6  test    rax, rax
0x140006ca9  jnz     loc_140006BB3
0x140006caf  mov     rcx, rsi
0x140006cb2  call    cs:__imp_archive_write_close
0x140006cb8  test    eax, eax
0x140006cba  jz      short loc_140006CE0
0x140006cbc  mov     rcx, rsi
0x140006cbf  call    cs:__imp_archive_error_string
0x140006cc5  mov     r8, rax
0x140006cc8  lea     rdx, aS_5; "%s"
0x140006ccf  xor     ecx, ecx
0x140006cd1  call    lafe_warnc
0x140006cd6  mov     dword ptr [rdi+0BCh], 1
0x140006ce0  mov     rcx, [rdi+0E8h]; Block
0x140006ce7  call    cs:__imp_free
0x140006ced  mov     rcx, [rdi+0D0h]
0x140006cf4  call    cs:__imp_archive_entry_linkresolver_free
0x140006cfa  mov     rcx, [rdi+0C8h]
0x140006d01  mov     qword ptr [rdi+0D0h], 0
0x140006d0c  call    cs:__imp_archive_read_free
0x140006d12  test    dword ptr [rdi+24h], 1000h
0x140006d19  mov     qword ptr [rdi+0C8h], 0
0x140006d24  jz      short loc_140006D59
0x140006d26  or      edx, 0FFFFFFFFh
0x140006d29  mov     rcx, rsi
0x140006d2c  call    cs:__imp_archive_filter_bytes
0x140006d32  mov     rcx, rax
0x140006d35  call    tar_i64toa
0x140006d3a  mov     ecx, 2; Ix
0x140006d3f  mov     rbx, rax
0x140006d42  call    _o___acrt_iob_func_0
0x140006d47  mov     rcx, rax; Stream
0x140006d4a  lea     rdx, aTotalBytesWrit; "Total bytes written: %s\n"
0x140006d51  mov     r8, rbx
0x140006d54  call    fprintf
0x140006d59  mov     rcx, rsi
0x140006d5c  call    cs:__imp_archive_write_free
0x140006d62  mov     rbx, [rsp+20h+arg_0]
0x140006d67  add     rsp, 20h
0x140006d6b  pop     r15
0x140006d6d  pop     r14
0x140006d6f  pop     rdi
0x140006d70  pop     rsi
0x140006d71  pop     rbp
0x140006d72  retn
0x140006d73  xor     edx, edx
0x140006d75  lea     r8, aCannotAllocate_0; "cannot allocate memory"
0x140006d7c  lea     ecx, [rdx+1]; Code
0x140006d7f  call    lafe_errc
0x140006d85  xor     edx, edx
0x140006d87  lea     r8, aCannotCreateLi; "cannot create link resolver"
0x140006d8e  lea     ecx, [rdx+1]; Code
0x140006d91  call    lafe_errc
0x140006d97  xor     edx, edx
0x140006d99  lea     r8, aCannotCreateRe; "Cannot create read_disk object"
0x140006da0  lea     ecx, [rdx+1]; Code
0x140006da3  call    lafe_errc
```
