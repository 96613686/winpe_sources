# tar_mode_r

- ea: `0x1400063bc`
- end: `0x140006647`
- name: `tar_mode_r`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001f9c`

## callees

- `0x140004154`
- `0x1400057d4`
- `0x140005fc4`
- `0x1400060d4`
- `0x1400063bc`
- `0x1400068f4`
- `0x1400069a8`
- `0x1400071a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x140006554`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x140006614`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x140006554`
- `api-ms-win-crt-private-l1-1-0!_o__close` at `0x140006614`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006577`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006594`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006577`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006594`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x140006505`
- `api-ms-win-crt-private-l1-1-0!_o__get_osfhandle` at `0x140006505`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140006517`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140006517`
- `archiveint!archive_errno` at `0x1400065c0`
- `archiveint!archive_errno` at `0x1400065c0`
- `archiveint!archive_read_new` at `0x140006400`
- `archiveint!archive_read_new` at `0x140006400`
- `archiveint!archive_read_support_filter_all` at `0x14000640c`
- `archiveint!archive_read_support_filter_all` at `0x14000640c`
- `archiveint!archive_read_free` at `0x1400064a2`
- `archiveint!archive_read_free` at `0x140006608`
- `archiveint!archive_read_free` at `0x1400064a2`
- `archiveint!archive_read_free` at `0x140006608`
- `archiveint!archive_read_next_header` at `0x140006489`
- `archiveint!archive_read_next_header` at `0x140006489`
- `archiveint!archive_write_open_fd` at `0x140006535`
- `archiveint!archive_write_open_fd` at `0x140006535`
- `archiveint!archive_read_support_format_tar` at `0x14000641e`
- `archiveint!archive_read_support_format_tar` at `0x14000641e`
- `archiveint!archive_write_set_format_by_name` at `0x1400064c0`
- `archiveint!archive_write_set_format_by_name` at `0x1400064c0`
- `archiveint!archive_read_support_format_gnutar` at `0x140006427`
- `archiveint!archive_read_support_format_gnutar` at `0x140006427`
- `archiveint!archive_write_set_format` at `0x1400064f9`
- `archiveint!archive_write_set_format` at `0x1400064f9`
- `archiveint!archive_write_new` at `0x1400064a8`
- `archiveint!archive_write_new` at `0x1400064a8`
- `archiveint!archive_filter_code` at `0x140006468`
- `archiveint!archive_filter_code` at `0x140006468`
- `archiveint!archive_read_open_fd` at `0x140006447`
- `archiveint!archive_read_open_fd` at `0x140006447`
- `archiveint!archive_format` at `0x140006479`
- `archiveint!archive_format` at `0x1400064d2`
- `archiveint!archive_format` at `0x140006479`
- `archiveint!archive_format` at `0x1400064d2`
- `archiveint!archive_read_support_format_empty` at `0x140006415`
- `archiveint!archive_read_support_format_empty` at `0x140006415`
- `archiveint!archive_read_header_position` at `0x140006496`
- `archiveint!archive_read_header_position` at `0x140006496`
- `archiveint!archive_error_string` at `0x1400065b4`
- `archiveint!archive_error_string` at `0x14000662c`
- `archiveint!archive_error_string` at `0x1400065b4`
- `archiveint!archive_error_string` at `0x14000662c`

## string_xrefs

- `0x14000659d`: `Cannot open %s`
- `0x1400065d0`: `Can't read archive %s: %s`
- `0x14000661c`: `Cannot append to compressed archive.`
- `0x1400065ed`: `Format %s is incompatible with the archive %s.`

## pseudocode

```c
__int64 __fastcall tar_mode_r(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rsi
  int open_fd; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebp
  LARGE_INTEGER v10; // rbx
  __int64 v11; // rsi
  int v12; // ebp
  void *osfhandle; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 result; // rax
  __int64 v18; // [rsp+50h] [rbp+8h] BYREF

  v18 = 0;
  test_for_append();
  v2 = open_wrap_sopen(*(_QWORD *)a1, 33026, 438);
  *(_DWORD *)(a1 + 144) = v2;
  if ( v2 < 0 )
  {
    _o__errno(v4, v3, v5);
    lafe_errc(1);
  }
  v6 = archive_read_new(v4, v3, v5);
  archive_read_support_filter_all(v6);
  archive_read_support_format_empty(v6);
  archive_read_support_format_tar(v6);
  archive_read_support_format_gnutar(v6);
  set_reader_options(a1, v6);
  open_fd = archive_read_open_fd(v6, *(unsigned int *)(a1 + 144), 10240);
  v8 = v6;
  if ( open_fd )
  {
    archive_error_string(v6);
    archive_errno(v6);
    lafe_errc(1);
  }
  v9 = 196611;
  while ( !(unsigned int)archive_read_next_header(v8, &v18) )
  {
    if ( (unsigned int)archive_filter_code(v6, 0) )
    {
      archive_read_free(v6);
      _o__close(*(unsigned int *)(a1 + 144));
      lafe_errc(1);
    }
    v9 = archive_format(v6);
    v8 = v6;
  }
  v10.QuadPart = archive_read_header_position(v6);
  archive_read_free(v6);
  v11 = archive_write_new();
  if ( **(_QWORD **)(a1 + 120) )
  {
    archive_write_set_format_by_name(v11);
    v12 = v9 & 0xFF0000;
    if ( v12 != (archive_format(v11) & 0xFF0000) && v12 != 393216 )
    {
      cset_get_format(*(_QWORD *)(a1 + 120));
      lafe_errc(1);
    }
  }
  else
  {
    if ( v9 == 393216 )
      v9 = 196611;
    archive_write_set_format(v11, v9);
  }
  osfhandle = (void *)_get_osfhandle(*(_DWORD *)(a1 + 144));
  if ( !SetFilePointerEx(osfhandle, v10, 0, 0) )
  {
    _o__errno(v15, v14, v16);
    lafe_errc(1);
  }
  set_writer_options(a1, v11);
  if ( (unsigned int)archive_write_open_fd(v11, *(unsigned int *)(a1 + 144)) )
  {
    archive_error_string(v11);
    lafe_errc(1);
  }
  write_archive(v11, a1);
  result = _o__close(*(unsigned int *)(a1 + 144));
  *(_DWORD *)(a1 + 144) = -1;
  return result;
}

```

## disassembly

```asm
0x1400063bc  mov     [rsp+arg_8], rbx
0x1400063c1  mov     [rsp+arg_10], rbp
0x1400063c6  push    rsi
0x1400063c7  push    rdi
0x1400063c8  push    r14
0x1400063ca  sub     rsp, 30h
0x1400063ce  mov     rdi, rcx
0x1400063d1  mov     [rsp+48h+arg_0], 0
0x1400063da  call    test_for_append
0x1400063df  mov     rcx, [rdi]
0x1400063e2  mov     edx, 8102h
0x1400063e7  mov     r8d, 1B6h
0x1400063ed  call    _open_wrap_sopen
0x1400063f2  mov     [rdi+90h], eax
0x1400063f8  test    eax, eax
0x1400063fa  js      loc_140006591
0x140006400  call    cs:__imp_archive_read_new
0x140006406  mov     rcx, rax
0x140006409  mov     rsi, rax
0x14000640c  call    cs:__imp_archive_read_support_filter_all
0x140006412  mov     rcx, rsi
0x140006415  call    cs:__imp_archive_read_support_format_empty
0x14000641b  mov     rcx, rsi
0x14000641e  call    cs:__imp_archive_read_support_format_tar
0x140006424  mov     rcx, rsi
0x140006427  call    cs:__imp_archive_read_support_format_gnutar
0x14000642d  mov     rdx, rsi
0x140006430  mov     rcx, rdi
0x140006433  call    set_reader_options
0x140006438  mov     edx, [rdi+90h]
0x14000643e  mov     r8d, 2800h
0x140006444  mov     rcx, rsi
0x140006447  call    cs:__imp_archive_read_open_fd
0x14000644d  mov     rcx, rsi
0x140006450  test    eax, eax
0x140006452  jnz     loc_1400065B1
0x140006458  mov     r14d, 30003h
0x14000645e  mov     ebp, r14d
0x140006461  jmp     short loc_140006484
0x140006463  xor     edx, edx
0x140006465  mov     rcx, rsi
0x140006468  call    cs:__imp_archive_filter_code
0x14000646e  mov     rcx, rsi
0x140006471  test    eax, eax
0x140006473  jnz     loc_140006608
0x140006479  call    cs:__imp_archive_format
0x14000647f  mov     ebp, eax
0x140006481  mov     rcx, rsi
0x140006484  lea     rdx, [rsp+48h+arg_0]
0x140006489  call    cs:__imp_archive_read_next_header
0x14000648f  test    eax, eax
0x140006491  jz      short loc_140006463
0x140006493  mov     rcx, rsi
0x140006496  call    cs:__imp_archive_read_header_position
0x14000649c  mov     rcx, rsi
0x14000649f  mov     rbx, rax
0x1400064a2  call    cs:__imp_archive_read_free
0x1400064a8  call    cs:__imp_archive_write_new
0x1400064ae  mov     rcx, [rdi+78h]
0x1400064b2  mov     rsi, rax
0x1400064b5  mov     rdx, [rcx]
0x1400064b8  mov     rcx, rax
0x1400064bb  test    rdx, rdx
0x1400064be  jz      short loc_1400064ED
0x1400064c0  call    cs:__imp_archive_write_set_format_by_name
0x1400064c6  mov     r14d, 0FF0000h
0x1400064cc  mov     rcx, rsi
0x1400064cf  and     ebp, r14d
0x1400064d2  call    cs:__imp_archive_format
0x1400064d8  and     eax, r14d
0x1400064db  cmp     ebp, eax
0x1400064dd  jz      short loc_1400064FF
0x1400064df  cmp     ebp, 60000h
0x1400064e5  jnz     loc_1400065E2
0x1400064eb  jmp     short loc_1400064FF
0x1400064ed  cmp     ebp, 60000h
0x1400064f3  cmovz   ebp, r14d
0x1400064f7  mov     edx, ebp
0x1400064f9  call    cs:__imp_archive_write_set_format
0x1400064ff  mov     ecx, [rdi+90h]; FileHandle
0x140006505  call    cs:__imp__get_osfhandle
0x14000650b  xor     r9d, r9d; dwMoveMethod
0x14000650e  xor     r8d, r8d; lpNewFilePointer
0x140006511  mov     rcx, rax; hFile
0x140006514  mov     rdx, rbx; liDistanceToMove
0x140006517  call    cs:__imp_SetFilePointerEx
0x14000651d  test    eax, eax
0x14000651f  jz      short loc_140006577
0x140006521  mov     rdx, rsi
0x140006524  mov     rcx, rdi
0x140006527  call    set_writer_options
0x14000652c  mov     edx, [rdi+90h]
0x140006532  mov     rcx, rsi
0x140006535  call    cs:__imp_archive_write_open_fd
0x14000653b  mov     rcx, rsi
0x14000653e  test    eax, eax
0x140006540  jnz     loc_14000662C
0x140006546  mov     rdx, rdi
0x140006549  call    write_archive
0x14000654e  mov     ecx, [rdi+90h]
0x140006554  call    cs:__imp__o__close
0x14000655a  mov     rbx, [rsp+48h+arg_8]
0x14000655f  mov     rbp, [rsp+48h+arg_10]
0x140006564  mov     dword ptr [rdi+90h], 0FFFFFFFFh
0x14000656e  add     rsp, 30h
0x140006572  pop     r14
0x140006574  pop     rdi
0x140006575  pop     rsi
0x140006576  retn
0x140006577  call    cs:__imp__o__errno
0x14000657d  lea     r8, aCouldNotSeekTo; "Could not seek to archive end"
0x140006584  mov     ecx, 1; Code
0x140006589  mov     edx, [rax]
0x14000658b  call    lafe_errc
0x140006591  mov     rbx, [rdi]
0x140006594  call    cs:__imp__o__errno
0x14000659a  mov     r9, rbx
0x14000659d  lea     r8, aCannotOpenS; "Cannot open %s"
0x1400065a4  mov     ecx, 1; Code
0x1400065a9  mov     edx, [rax]
0x1400065ab  call    lafe_errc
0x1400065b1  mov     rdi, [rdi]
0x1400065b4  call    cs:__imp_archive_error_string
0x1400065ba  mov     rcx, rsi
0x1400065bd  mov     rbx, rax
0x1400065c0  call    cs:__imp_archive_errno
0x1400065c6  mov     r9, rdi
0x1400065c9  mov     [rsp+48h+var_28], rbx
0x1400065ce  mov     edx, eax
0x1400065d0  lea     r8, aCanTReadArchiv; "Can't read archive %s: %s"
0x1400065d7  mov     ecx, 1; Code
0x1400065dc  call    lafe_errc
0x1400065e2  mov     rcx, [rdi+78h]
0x1400065e6  call    cset_get_format
0x1400065eb  xor     edx, edx
0x1400065ed  lea     r8, aFormatSIsIncom; "Format %s is incompatible with the arch"...
0x1400065f4  mov     r9, rax
0x1400065f7  mov     rax, [rdi]
0x1400065fa  mov     [rsp+48h+var_28], rax
0x1400065ff  lea     ecx, [rdx+1]; Code
0x140006602  call    lafe_errc
0x140006608  call    cs:__imp_archive_read_free
0x14000660e  mov     ecx, [rdi+90h]
0x140006614  call    cs:__imp__o__close
0x14000661a  xor     edx, edx
0x14000661c  lea     r8, aCannotAppendTo_1; "Cannot append to compressed archive."
0x140006623  lea     ecx, [rdx+1]; Code
0x140006626  call    lafe_errc
0x14000662c  call    cs:__imp_archive_error_string
0x140006632  xor     edx, edx
0x140006634  lea     r8, aS_5; "%s"
0x14000663b  mov     r9, rax
0x14000663e  lea     ecx, [rdx+1]; Code
0x140006641  call    lafe_errc
```
