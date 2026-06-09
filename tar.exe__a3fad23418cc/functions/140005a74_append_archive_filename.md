# append_archive_filename

- ea: `0x140005a74`
- end: `0x140005bb6`
- name: `append_archive_filename`
- size: `322`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400069a8`

## callees

- `0x14000583c`
- `0x140005a74`
- `0x140005fc4`
- `0x1400071a4`
- `0x140007298`

## import_xrefs

- `archiveint!archive_read_set_options` at `0x140005ad6`
- `archiveint!archive_read_set_options` at `0x140005ad6`
- `archiveint!archive_read_add_passphrase` at `0x140005ae8`
- `archiveint!archive_read_add_passphrase` at `0x140005ae8`
- `archiveint!archive_read_support_format_all` at `0x140005ab2`
- `archiveint!archive_read_support_format_all` at `0x140005ab2`
- `archiveint!archive_read_new` at `0x140005aa6`
- `archiveint!archive_read_new` at `0x140005aa6`
- `archiveint!archive_read_support_filter_all` at `0x140005abb`
- `archiveint!archive_read_support_filter_all` at `0x140005abb`
- `archiveint!archive_read_free` at `0x140005b85`
- `archiveint!archive_read_free` at `0x140005b85`
- `archiveint!archive_read_open_filename` at `0x140005b15`
- `archiveint!archive_read_open_filename` at `0x140005b15`
- `archiveint!archive_read_set_passphrase_callback` at `0x140005afd`
- `archiveint!archive_read_set_passphrase_callback` at `0x140005afd`
- `archiveint!archive_error_string` at `0x140005b22`
- `archiveint!archive_error_string` at `0x140005b5e`
- `archiveint!archive_error_string` at `0x140005b9b`
- `archiveint!archive_error_string` at `0x140005b22`
- `archiveint!archive_error_string` at `0x140005b5e`
- `archiveint!archive_error_string` at `0x140005b9b`

## string_xrefs

- `0x140005b67`: `Error reading archive %s: %s`

## pseudocode

```c
__int64 __fastcall append_archive_filename(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // cf
  int v7; // eax
  __int64 v8; // r14
  __int64 v9; // rbx
  int add_passphrase; // eax
  const char *v11; // rax
  __int64 result; // rax
  unsigned int appended; // ebp
  const char *v14; // rax

  v3 = *(_BYTE *)a3 < 0x2Du;
  if ( *(_BYTE *)a3 != 45 || (v3 = 0, *(_BYTE *)(a3 + 1)) )
    v7 = v3 ? -1 : 1;
  else
    v7 = 0;
  v8 = a3 & -(__int64)(v7 != 0);
  v9 = archive_read_new(a1, a2, a3);
  archive_read_support_format_all(v9);
  archive_read_support_filter_all(v9);
  set_reader_options(a1, v9);
  archive_read_set_options(v9, "mtree:checkfs");
  if ( *(_QWORD *)(a1 + 80) )
    add_passphrase = archive_read_add_passphrase(a2);
  else
    add_passphrase = archive_read_set_passphrase_callback(v9, a1, passphrase_callback);
  if ( add_passphrase )
  {
    archive_error_string(a2);
    lafe_errc(1);
  }
  if ( (unsigned int)archive_read_open_filename(v9, v8, *(int *)(a1 + 24)) )
  {
    v11 = (const char *)archive_error_string(v9);
    lafe_warnc(0, "%s", v11);
    result = 0;
    *(_DWORD *)(a1 + 188) = 1;
  }
  else
  {
    appended = append_archive(a1, a2, v9);
    if ( appended )
    {
      v14 = (const char *)archive_error_string(v9);
      lafe_warnc(0, "Error reading archive %s: %s", (const char *)a3, v14);
      *(_DWORD *)(a1 + 188) = 1;
    }
    archive_read_free(v9);
    return appended;
  }
  return result;
}

```

## disassembly

```asm
0x140005a74  push    rbx
0x140005a76  push    rbp
0x140005a77  push    rsi
0x140005a78  push    rdi
0x140005a79  push    r14
0x140005a7b  sub     rsp, 20h
0x140005a7f  cmp     byte ptr [r8], 2Dh ; '-'
0x140005a83  mov     rsi, r8
0x140005a86  mov     rbp, rdx
0x140005a89  mov     rdi, rcx
0x140005a8c  jnz     short loc_140005A99
0x140005a8e  cmp     byte ptr [r8+1], 0
0x140005a93  jnz     short loc_140005A99
0x140005a95  xor     eax, eax
0x140005a97  jmp     short loc_140005A9E
0x140005a99  sbb     eax, eax
0x140005a9b  or      eax, 1
0x140005a9e  neg     eax
0x140005aa0  sbb     r14, r14
0x140005aa3  and     r14, rsi
0x140005aa6  call    cs:__imp_archive_read_new
0x140005aac  mov     rcx, rax
0x140005aaf  mov     rbx, rax
0x140005ab2  call    cs:__imp_archive_read_support_format_all
0x140005ab8  mov     rcx, rbx
0x140005abb  call    cs:__imp_archive_read_support_filter_all
0x140005ac1  mov     rdx, rbx
0x140005ac4  mov     rcx, rdi
0x140005ac7  call    set_reader_options
0x140005acc  lea     rdx, aMtreeCheckfs; "mtree:checkfs"
0x140005ad3  mov     rcx, rbx
0x140005ad6  call    cs:__imp_archive_read_set_options
0x140005adc  mov     rdx, [rdi+50h]
0x140005ae0  test    rdx, rdx
0x140005ae3  jz      short loc_140005AF0
0x140005ae5  mov     rcx, rbp
0x140005ae8  call    cs:__imp_archive_read_add_passphrase
0x140005aee  jmp     short loc_140005B03
0x140005af0  lea     r8, passphrase_callback
0x140005af7  mov     rdx, rdi
0x140005afa  mov     rcx, rbx
0x140005afd  call    cs:__imp_archive_read_set_passphrase_callback
0x140005b03  test    eax, eax
0x140005b05  jnz     loc_140005B98
0x140005b0b  movsxd  r8, dword ptr [rdi+18h]
0x140005b0f  mov     rdx, r14
0x140005b12  mov     rcx, rbx
0x140005b15  call    cs:__imp_archive_read_open_filename
0x140005b1b  test    eax, eax
0x140005b1d  jz      short loc_140005B47
0x140005b1f  mov     rcx, rbx
0x140005b22  call    cs:__imp_archive_error_string
0x140005b28  lea     rdx, aS_5; "%s"
0x140005b2f  xor     ecx, ecx
0x140005b31  mov     r8, rax
0x140005b34  call    lafe_warnc
0x140005b39  xor     eax, eax
0x140005b3b  mov     dword ptr [rdi+0BCh], 1
0x140005b45  jmp     short loc_140005B8D
0x140005b47  mov     r8, rbx
0x140005b4a  mov     rdx, rbp
0x140005b4d  mov     rcx, rdi
0x140005b50  call    append_archive
0x140005b55  mov     ebp, eax
0x140005b57  test    eax, eax
0x140005b59  jz      short loc_140005B82
0x140005b5b  mov     rcx, rbx
0x140005b5e  call    cs:__imp_archive_error_string
0x140005b64  mov     r8, rsi
0x140005b67  lea     rdx, aErrorReadingAr; "Error reading archive %s: %s"
0x140005b6e  mov     r9, rax
0x140005b71  xor     ecx, ecx
0x140005b73  call    lafe_warnc
0x140005b78  mov     dword ptr [rdi+0BCh], 1
0x140005b82  mov     rcx, rbx
0x140005b85  call    cs:__imp_archive_read_free
0x140005b8b  mov     eax, ebp
0x140005b8d  add     rsp, 20h
0x140005b91  pop     r14
0x140005b93  pop     rdi
0x140005b94  pop     rsi
0x140005b95  pop     rbp
0x140005b96  pop     rbx
0x140005b97  retn
0x140005b98  mov     rcx, rbp
0x140005b9b  call    cs:__imp_archive_error_string
0x140005ba1  xor     edx, edx
0x140005ba3  lea     r8, aS_5; "%s"
0x140005baa  mov     r9, rax
0x140005bad  lea     ecx, [rdx+1]; Code
0x140005bb0  call    lafe_errc
```
