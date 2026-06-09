# tar_mode_c

- ea: `0x1400061dc`
- end: `0x1400063b3`
- name: `tar_mode_c`
- size: `471`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140001f9c`

## callees

- `0x140001b96`
- `0x140001d10`
- `0x140003768`
- `0x140004154`
- `0x140004160`
- `0x1400060d4`
- `0x1400061dc`
- `0x1400069a8`
- `0x1400071a4`

## import_xrefs

- `archiveint!archive_write_add_filter_by_name` at `0x14000628e`
- `archiveint!archive_write_add_filter_by_name` at `0x14000628e`
- `archiveint!archive_write_add_filter_program` at `0x140006286`
- `archiveint!archive_write_add_filter_program` at `0x140006286`
- `archiveint!archive_write_set_passphrase_callback` at `0x1400062e6`
- `archiveint!archive_write_set_passphrase_callback` at `0x1400062e6`
- `archiveint!archive_write_set_format_by_name` at `0x140006236`
- `archiveint!archive_write_set_format_by_name` at `0x140006236`
- `archiveint!archive_write_set_bytes_in_last_block` at `0x140006258`
- `archiveint!archive_write_set_bytes_in_last_block` at `0x140006258`
- `archiveint!archive_write_new` at `0x140006204`
- `archiveint!archive_write_new` at `0x140006204`
- `archiveint!archive_write_set_passphrase` at `0x1400062d4`
- `archiveint!archive_write_set_passphrase` at `0x1400062d4`
- `archiveint!archive_write_set_bytes_per_block` at `0x14000624c`
- `archiveint!archive_write_set_bytes_per_block` at `0x14000624c`
- `archiveint!archive_write_set_format_pax_restricted` at `0x14000621c`
- `archiveint!archive_write_set_format_pax_restricted` at `0x14000621c`
- `archiveint!archive_write_open_filename` at `0x1400062fa`
- `archiveint!archive_write_open_filename` at `0x1400062fa`
- `archiveint!archive_error_string` at `0x140006335`
- `archiveint!archive_error_string` at `0x14000637f`
- `archiveint!archive_error_string` at `0x140006399`
- `archiveint!archive_error_string` at `0x140006335`
- `archiveint!archive_error_string` at `0x14000637f`
- `archiveint!archive_error_string` at `0x140006399`

## string_xrefs

- `0x14000636e`: `Unsupported compression option --%s`

## pseudocode

```c
__int64 __fastcall tar_mode_c(__int64 a1)
{
  __int64 v2; // rdi
  int v3; // esi
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r15
  int v7; // ebp
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  __int64 v13; // rbx
  const char *v14; // rdi
  const char *format; // rbx
  FILE *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8

  if ( !**(_QWORD **)(a1 + 152) && !*(_QWORD *)(a1 + 16) )
    lafe_errc(1);
  v2 = archive_write_new();
  if ( **(_QWORD **)(a1 + 120) )
  {
    v3 = archive_write_set_format_by_name(v2);
  }
  else
  {
    v3 = archive_write_set_format_pax_restricted(v2);
    cset_set_format(*(_QWORD *)(a1 + 120), "pax restricted", v4, v5);
  }
  if ( v3 )
  {
    v13 = *(_QWORD *)(a1 + 120);
    v14 = (const char *)archive_error_string(v2);
    format = (const char *)cset_get_format(v13);
    v16 = o___acrt_iob_func_0(2u);
    fprintf(v16, "Can't use format %s: %s\n", format, v14);
    usage(v18, v17, v19);
  }
  archive_write_set_bytes_per_block(v2, *(unsigned int *)(a1 + 24));
  archive_write_set_bytes_in_last_block(v2, *(unsigned int *)(a1 + 28));
  v6 = *(_QWORD *)(a1 + 120);
  v7 = 0;
  if ( *(int *)(v6 + 16) > 0 )
  {
    while ( 1 )
    {
      v8 = *(_QWORD *)(v6 + 8);
      v9 = *(_QWORD *)(v8 + 16LL * v7 + 8);
      v10 = *(_DWORD *)(v8 + 16LL * v7)
          ? archive_write_add_filter_program(v2, v9)
          : archive_write_add_filter_by_name(v2, v9);
      if ( v10 < -20 )
        break;
      if ( ++v7 >= *(_DWORD *)(v6 + 16) )
        goto LABEL_13;
    }
LABEL_24:
    lafe_errc(1);
  }
LABEL_13:
  if ( v7 < -20 )
    goto LABEL_24;
  set_writer_options(a1, v2);
  if ( *(_QWORD *)(a1 + 80) )
    v11 = archive_write_set_passphrase(v2);
  else
    v11 = archive_write_set_passphrase_callback(v2, a1, passphrase_callback);
  if ( v11 )
  {
    archive_error_string(v2);
    lafe_errc(1);
  }
  if ( (unsigned int)archive_write_open_filename(v2, *(_QWORD *)a1) )
  {
    archive_error_string(v2);
    lafe_errc(1);
  }
  return write_archive(v2, a1);
}

```

## disassembly

```asm
0x1400061dc  push    rbx
0x1400061de  push    rbp
0x1400061df  push    rsi
0x1400061e0  push    rdi
0x1400061e1  push    r14
0x1400061e3  push    r15
0x1400061e5  sub     rsp, 28h
0x1400061e9  mov     rax, [rcx+98h]
0x1400061f0  mov     rbx, rcx
0x1400061f3  cmp     qword ptr [rax], 0
0x1400061f7  jnz     short loc_140006204
0x1400061f9  cmp     qword ptr [rcx+10h], 0
0x1400061fe  jz      loc_14000631F
0x140006204  call    cs:__imp_archive_write_new
0x14000620a  mov     rcx, [rbx+78h]
0x14000620e  mov     rdi, rax
0x140006211  mov     rdx, [rcx]
0x140006214  mov     rcx, rax
0x140006217  test    rdx, rdx
0x14000621a  jnz     short loc_140006236
0x14000621c  call    cs:__imp_archive_write_set_format_pax_restricted
0x140006222  mov     rcx, [rbx+78h]
0x140006226  lea     rdx, aPaxRestricted; "pax restricted"
0x14000622d  mov     esi, eax
0x14000622f  call    cset_set_format
0x140006234  jmp     short loc_14000623E
0x140006236  call    cs:__imp_archive_write_set_format_by_name
0x14000623c  mov     esi, eax
0x14000623e  mov     rcx, rdi
0x140006241  test    esi, esi
0x140006243  jnz     loc_140006331
0x140006249  mov     edx, [rbx+18h]
0x14000624c  call    cs:__imp_archive_write_set_bytes_per_block
0x140006252  mov     edx, [rbx+1Ch]
0x140006255  mov     rcx, rdi
0x140006258  call    cs:__imp_archive_write_set_bytes_in_last_block
0x14000625e  mov     r15, [rbx+78h]
0x140006262  xor     ebp, ebp
0x140006264  lea     esi, [rbp+1]
0x140006267  cmp     [r15+10h], ebp
0x14000626b  jle     short loc_1400062A1
0x14000626d  mov     rax, [r15+8]
0x140006271  mov     rcx, rdi
0x140006274  movsxd  r14, ebp
0x140006277  add     r14, r14
0x14000627a  cmp     dword ptr [rax+r14*8], 0
0x14000627f  mov     rdx, [rax+r14*8+8]
0x140006284  jz      short loc_14000628E
0x140006286  call    cs:__imp_archive_write_add_filter_program
0x14000628c  jmp     short loc_140006294
0x14000628e  call    cs:__imp_archive_write_add_filter_by_name
0x140006294  cmp     eax, 0FFFFFFECh
0x140006297  jl      short loc_1400062AF
0x140006299  add     ebp, esi
0x14000629b  cmp     ebp, [r15+10h]
0x14000629f  jl      short loc_14000626D
0x1400062a1  xor     r9d, r9d
0x1400062a4  cmp     ebp, 0FFFFFFECh
0x1400062a7  jl      loc_14000636E
0x1400062ad  jmp     short loc_1400062BD
0x1400062af  mov     rax, [r15+8]
0x1400062b3  mov     r9, [rax+r14*8+8]
0x1400062b8  jmp     loc_14000636E
0x1400062bd  mov     rdx, rdi
0x1400062c0  mov     rcx, rbx
0x1400062c3  call    set_writer_options
0x1400062c8  mov     rdx, [rbx+50h]
0x1400062cc  mov     rcx, rdi
0x1400062cf  test    rdx, rdx
0x1400062d2  jz      short loc_1400062DC
0x1400062d4  call    cs:__imp_archive_write_set_passphrase
0x1400062da  jmp     short loc_1400062EC
0x1400062dc  lea     r8, passphrase_callback
0x1400062e3  mov     rdx, rbx
0x1400062e6  call    cs:__imp_archive_write_set_passphrase_callback
0x1400062ec  mov     rcx, rdi
0x1400062ef  test    eax, eax
0x1400062f1  jnz     loc_14000637F
0x1400062f7  mov     rdx, [rbx]
0x1400062fa  call    cs:__imp_archive_write_open_filename
0x140006300  mov     rcx, rdi
0x140006303  test    eax, eax
0x140006305  jnz     loc_140006399
0x14000630b  mov     rdx, rbx
0x14000630e  add     rsp, 28h
0x140006312  pop     r15
0x140006314  pop     r14
0x140006316  pop     rdi
0x140006317  pop     rsi
0x140006318  pop     rbp
0x140006319  pop     rbx
0x14000631a  jmp     write_archive
0x14000631f  xor     edx, edx
0x140006321  lea     r8, aNoFilesOrDirec; "no files or directories specified"
0x140006328  lea     ecx, [rdx+1]; Code
0x14000632b  call    lafe_errc
0x140006331  mov     rbx, [rbx+78h]
0x140006335  call    cs:__imp_archive_error_string
0x14000633b  mov     rcx, rbx
0x14000633e  mov     rdi, rax
0x140006341  call    cset_get_format
0x140006346  mov     ecx, 2; Ix
0x14000634b  mov     rbx, rax
0x14000634e  call    _o___acrt_iob_func_0
0x140006353  mov     rcx, rax; Stream
0x140006356  lea     rdx, aCanTUseFormatS; "Can't use format %s: %s\n"
0x14000635d  mov     r9, rdi
0x140006360  mov     r8, rbx
0x140006363  call    fprintf
0x140006368  call    usage
0x14000636e  lea     r8, aUnsupportedCom; "Unsupported compression option --%s"
0x140006375  xor     edx, edx
0x140006377  mov     ecx, esi; Code
0x140006379  call    lafe_errc
0x14000637f  call    cs:__imp_archive_error_string
0x140006385  lea     r8, aS_5; "%s"
0x14000638c  xor     edx, edx
0x14000638e  mov     r9, rax
0x140006391  mov     ecx, esi; Code
0x140006393  call    lafe_errc
0x140006399  call    cs:__imp_archive_error_string
0x14000639f  lea     r8, aS_5; "%s"
0x1400063a6  xor     edx, edx
0x1400063a8  mov     r9, rax
0x1400063ab  mov     ecx, esi; Code
0x1400063ad  call    lafe_errc
```
