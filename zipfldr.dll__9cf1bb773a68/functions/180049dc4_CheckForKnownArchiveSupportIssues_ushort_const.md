# CheckForKnownArchiveSupportIssues(ushort const *)

- ea: `0x180049dc4`
- end: `0x180049f1d`
- name: `?CheckForKnownArchiveSupportIssues@@YA?AW4ArchiveSupportLevel@@PEBG@Z`
- size: `345`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004a600`
- `0x1800683c8`

## callees

- `0x180035418`
- `0x180036f50`
- `0x1800390f1`
- `0x180049dc4`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x180049ecb`
- `archiveint!archive_read_has_encrypted_entries` at `0x180049ecb`
- `archiveint!archive_error_string` at `0x180049e73`
- `archiveint!archive_error_string` at `0x180049e73`
- `archiveint!archive_errno` at `0x180049e65`
- `archiveint!archive_errno` at `0x180049e65`
- `archiveint!archive_read_next_header` at `0x180049e43`
- `archiveint!archive_read_next_header` at `0x180049e43`
- `archiveint!archive_read_open_filename_w` at `0x180049e1d`
- `archiveint!archive_read_open_filename_w` at `0x180049e1d`
- `archiveint!archive_read_support_filter_all` at `0x180049e0b`
- `archiveint!archive_read_support_filter_all` at `0x180049e0b`
- `archiveint!archive_read_support_format_raw` at `0x180049e02`
- `archiveint!archive_read_support_format_raw` at `0x180049e02`
- `archiveint!archive_read_support_format_all` at `0x180049df9`
- `archiveint!archive_read_support_format_all` at `0x180049df9`
- `archiveint!archive_read_new` at `0x180049ddf`
- `archiveint!archive_read_new` at `0x180049ddf`

## pseudocode

```c
bool __fastcall CheckForKnownArchiveSupportIssues(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  int open_filename_w; // eax
  char v5; // di
  int v6; // esi
  int v7; // eax
  int v8; // ebp
  _BYTE *v9; // rax
  __int64 v10; // r8
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  __int64 v13; // [rsp+28h] [rbp-40h] BYREF

  v2 = archive_read_new();
  v12 = v2;
  v3 = v2;
  if ( !v2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v12);
    return 0;
  }
  archive_read_support_format_all(v2);
  archive_read_support_format_raw(v3);
  archive_read_support_filter_all(v3);
  open_filename_w = archive_read_open_filename_w(v3, a1, 10240);
  v5 = 2;
  if ( open_filename_w )
  {
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v12);
    return v5;
  }
  v6 = 0;
  while ( 1 )
  {
    v13 = 0;
    v7 = archive_read_next_header(v3, &v13);
    v8 = v7;
    if ( v7 == -30 )
      break;
    if ( v7 != 1 && v7 != -25 && ++v6 < 2 )
      continue;
    goto LABEL_19;
  }
  if ( (unsigned int)archive_errno(v3) == 42 )
  {
    v9 = (_BYTE *)archive_error_string(v3);
    if ( v9 )
    {
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      if ( v10 == 38 )
      {
        if ( !memcmp_0(v9, KnownArchiveErrors::SolidRAR, 0x26u) )
        {
          v5 = 4;
          goto LABEL_21;
        }
        goto LABEL_19;
      }
    }
    else
    {
      v10 = 0;
      v9 = 0;
    }
    if ( v10 == 27 && !memcmp_0(v9, KnownArchiveErrors::EncryptedRAR, 0x1Bu) )
      goto LABEL_20;
  }
LABEL_19:
  if ( (int)archive_read_has_encrypted_entries(v3) > 0 )
  {
LABEL_20:
    v5 = 3;
    goto LABEL_21;
  }
  wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(&v12);
  return v8 <= -25;
}

```

## disassembly

```asm
0x180049dc4  push    rbx
0x180049dc6  push    rbp
0x180049dc7  push    rsi
0x180049dc8  push    rdi
0x180049dc9  sub     rsp, 48h
0x180049dcd  mov     rax, cs:__security_cookie
0x180049dd4  xor     rax, rsp
0x180049dd7  mov     [rsp+68h+var_38], rax
0x180049ddc  mov     rdi, rcx
0x180049ddf  call    cs:__imp_archive_read_new
0x180049de5  mov     [rsp+68h+var_48], rax
0x180049dea  mov     rbx, rax
0x180049ded  test    rax, rax
0x180049df0  jz      loc_180049EFB
0x180049df6  mov     rcx, rax
0x180049df9  call    cs:__imp_archive_read_support_format_all
0x180049dff  mov     rcx, rbx
0x180049e02  call    cs:__imp_archive_read_support_format_raw
0x180049e08  mov     rcx, rbx
0x180049e0b  call    cs:__imp_archive_read_support_filter_all
0x180049e11  mov     r8d, 2800h
0x180049e17  mov     rdx, rdi
0x180049e1a  mov     rcx, rbx
0x180049e1d  call    cs:__imp_archive_read_open_filename_w
0x180049e23  mov     edi, 2
0x180049e28  test    eax, eax
0x180049e2a  jnz     loc_180049ED8
0x180049e30  xor     esi, esi
0x180049e32  lea     rdx, [rsp+68h+var_40]
0x180049e37  mov     [rsp+68h+var_40], 0
0x180049e40  mov     rcx, rbx
0x180049e43  call    cs:__imp_archive_read_next_header
0x180049e49  mov     ebp, eax
0x180049e4b  cmp     eax, 0FFFFFFE2h
0x180049e4e  jz      short loc_180049E62
0x180049e50  cmp     eax, 1
0x180049e53  jz      short loc_180049EC8
0x180049e55  cmp     eax, 0FFFFFFE7h
0x180049e58  jz      short loc_180049EC8
0x180049e5a  inc     esi
0x180049e5c  cmp     esi, edi
0x180049e5e  jl      short loc_180049E32
0x180049e60  jmp     short loc_180049EC8
0x180049e62  mov     rcx, rbx
0x180049e65  call    cs:__imp_archive_errno
0x180049e6b  cmp     eax, 2Ah ; '*'
0x180049e6e  jnz     short loc_180049EC8
0x180049e70  mov     rcx, rbx
0x180049e73  call    cs:__imp_archive_error_string
0x180049e79  test    rax, rax
0x180049e7c  jz      short loc_180049EAA
0x180049e7e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180049e82  inc     r8; Size
0x180049e85  cmp     byte ptr [rax+r8], 0
0x180049e8a  jnz     short loc_180049E82
0x180049e8c  cmp     r8, 26h ; '&'
0x180049e90  jnz     short loc_180049EAF
0x180049e92  mov     rdx, cs:?SolidRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x180049e99  mov     rcx, rax; Buf1
0x180049e9c  call    memcmp_0
0x180049ea1  test    eax, eax
0x180049ea3  jnz     short loc_180049EC8
0x180049ea5  mov     dil, 4
0x180049ea8  jmp     short loc_180049ED8
0x180049eaa  xor     r8d, r8d; Size
0x180049ead  xor     eax, eax
0x180049eaf  cmp     r8, 1Bh
0x180049eb3  jnz     short loc_180049EC8
0x180049eb5  mov     rdx, cs:?EncryptedRAR@KnownArchiveErrors@@3V?$basic_string_view@DU?$char_traits@D@std@@@std@@B; Buf2
0x180049ebc  mov     rcx, rax; Buf1
0x180049ebf  call    memcmp_0
0x180049ec4  test    eax, eax
0x180049ec6  jz      short loc_180049ED5
0x180049ec8  mov     rcx, rbx
0x180049ecb  call    cs:__imp_archive_read_has_encrypted_entries
0x180049ed1  test    eax, eax
0x180049ed3  jle     short loc_180049EE7
0x180049ed5  mov     dil, 3
0x180049ed8  lea     rcx, [rsp+68h+var_48]
0x180049edd  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180049ee2  mov     al, dil
0x180049ee5  jmp     short loc_180049F07
0x180049ee7  cmp     ebp, 0FFFFFFE7h
0x180049eea  lea     rcx, [rsp+68h+var_48]
0x180049eef  setle   bl
0x180049ef2  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180049ef7  mov     al, bl
0x180049ef9  jmp     short loc_180049F07
0x180049efb  lea     rcx, [rsp+68h+var_48]
0x180049f00  call    ??1?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_read_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_read_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>(void)
0x180049f05  xor     al, al
0x180049f07  mov     rcx, [rsp+68h+var_38]
0x180049f0c  xor     rcx, rsp; StackCookie
0x180049f0f  call    __security_check_cookie
0x180049f14  add     rsp, 48h
0x180049f18  pop     rdi
0x180049f19  pop     rsi
0x180049f1a  pop     rbp
0x180049f1b  pop     rbx
0x180049f1c  retn
```
