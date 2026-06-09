# append_archive

- ea: `0x14000583c`
- end: `0x140005a6c`
- name: `append_archive`
- size: `560`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140005a74`

## callees

- `0x140001b96`
- `0x140001d10`
- `0x140004bd4`
- `0x140004d0c`
- `0x1400050fc`
- `0x140005680`
- `0x14000583c`
- `0x140005d7c`
- `0x140007298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x140005a65`
- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x140005a65`
- `archiveint!archive_entry_size` at `0x1400059e1`
- `archiveint!archive_entry_size` at `0x1400059e1`
- `archiveint!archive_read_data_skip` at `0x1400059ef`
- `archiveint!archive_read_data_skip` at `0x1400059ef`
- `archiveint!archive_entry_pathname` at `0x1400058b8`
- `archiveint!archive_entry_pathname` at `0x140005944`
- `archiveint!archive_entry_pathname` at `0x140005990`
- `archiveint!archive_entry_pathname` at `0x1400058b8`
- `archiveint!archive_entry_pathname` at `0x140005944`
- `archiveint!archive_entry_pathname` at `0x140005990`
- `archiveint!archive_read_next_header` at `0x14000586d`
- `archiveint!archive_read_next_header` at `0x140005a31`
- `archiveint!archive_read_next_header` at `0x14000586d`
- `archiveint!archive_read_next_header` at `0x140005a31`
- `archiveint!archive_match_excluded` at `0x14000588c`
- `archiveint!archive_match_excluded` at `0x14000588c`
- `archiveint!archive_entry_mtime` at `0x1400058e2`
- `archiveint!archive_entry_mtime` at `0x1400058e2`
- `archiveint!archive_entry_set_mtime` at `0x1400058fe`
- `archiveint!archive_entry_set_mtime` at `0x1400058fe`
- `archiveint!archive_write_header` at `0x14000596e`
- `archiveint!archive_write_header` at `0x14000596e`
- `archiveint!archive_error_string` at `0x140005983`
- `archiveint!archive_error_string` at `0x1400059ac`
- `archiveint!archive_error_string` at `0x140005983`
- `archiveint!archive_error_string` at `0x1400059ac`

## string_xrefs

- `0x1400058c1`: `copy '%s'`

## pseudocode

```c
__int64 __fastcall append_archive(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int i; // ecx
  const char *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  FILE *v12; // rax
  int v13; // esi
  const char *v14; // rbx
  const char *v15; // rax
  const char *v16; // rbx
  FILE *v17; // rax
  FILE *v18; // rax
  __int64 result; // rax
  __int64 v20; // [rsp+68h] [rbp+48h] BYREF

  v20 = 0;
  for ( i = archive_read_next_header(a3, &v20); !i; i = archive_read_next_header(a3, &v20) )
  {
    if ( !(unsigned int)archive_match_excluded(*(_QWORD *)(a1 + 256), v20) && !(unsigned int)edit_pathname(a1, v20) )
    {
      if ( (*(_BYTE *)(a1 + 36) & 0x20) == 0
        || (v7 = (const char *)archive_entry_pathname(v20), (unsigned int)yes("copy '%s'", v7)) )
      {
        if ( *(_BYTE *)(a1 + 105) )
        {
          v8 = v20;
          v9 = archive_entry_mtime(v20);
          if ( !*(_BYTE *)(a1 + 106) || v9 > *(_QWORD *)(a1 + 112) )
            archive_entry_set_mtime(v8, *(_QWORD *)(a1 + 112), 0);
        }
        if ( *(int *)(a1 + 32) <= 1 )
        {
          if ( *(int *)(a1 + 32) > 0 )
          {
            archive_entry_pathname(v20);
            v12 = o___acrt_iob_func_0(2u);
            safe_fprintf(v12, "a %s");
          }
        }
        else
        {
          v10 = o___acrt_iob_func_0(2u);
          safe_fprintf(v10, "a ");
          v11 = o___acrt_iob_func_0(2u);
          list_item_verbose(a1, v11, v20);
        }
        v13 = archive_write_header(a2, v20);
        if ( !v13 )
          goto LABEL_32;
        if ( *(_DWORD *)(a1 + 32) )
        {
          v16 = (const char *)archive_error_string(a2);
          v17 = o___acrt_iob_func_0(2u);
          fprintf(v17, ": %s", v16);
        }
        else
        {
          v14 = (const char *)archive_error_string(a2);
          v15 = (const char *)archive_entry_pathname(v20);
          lafe_warnc(0, "%s: %s", v15, v14);
        }
        if ( v13 == -30 )
LABEL_29:
          exit(1);
        if ( v13 >= -20 )
        {
LABEL_32:
          if ( archive_entry_size(v20) )
          {
            if ( (unsigned int)copy_file_data_block(a1, a2, a3, v20) )
              goto LABEL_29;
          }
          else
          {
            archive_read_data_skip(a3);
          }
        }
        if ( *(_DWORD *)(a1 + 32) )
        {
          v18 = o___acrt_iob_func_0(2u);
          fprintf(v18, "\n");
        }
      }
    }
  }
  result = 0;
  if ( i != 1 )
    return i;
  return result;
}

```

## disassembly

```asm
0x14000583c  mov     [rsp-28h+arg_0], rbx
0x140005841  mov     [rsp-28h+arg_8], rsi
0x140005846  push    rbp
0x140005847  push    rdi
0x140005848  push    r13
0x14000584a  push    r14
0x14000584c  push    r15
0x14000584e  mov     rbp, rsp
0x140005851  sub     rsp, 20h
0x140005855  mov     r15, rdx
0x140005858  mov     [rbp+arg_18], 0
0x140005860  mov     rdi, rcx
0x140005863  lea     rdx, [rbp+arg_18]
0x140005867  mov     rcx, r8
0x14000586a  mov     r14, r8
0x14000586d  call    cs:__imp_archive_read_next_header
0x140005873  mov     ecx, eax
0x140005875  test    eax, eax
0x140005877  jnz     loc_140005A41
0x14000587d  lea     r13d, [rax+2]
0x140005881  mov     rdx, [rbp+arg_18]
0x140005885  mov     rcx, [rdi+100h]
0x14000588c  call    cs:__imp_archive_match_excluded
0x140005892  test    eax, eax
0x140005894  jnz     loc_140005A2A
0x14000589a  mov     rdx, [rbp+arg_18]
0x14000589e  mov     rcx, rdi
0x1400058a1  call    edit_pathname
0x1400058a6  test    eax, eax
0x1400058a8  jnz     loc_140005A2A
0x1400058ae  test    byte ptr [rdi+24h], 20h
0x1400058b2  jz      short loc_1400058D5
0x1400058b4  mov     rcx, [rbp+arg_18]
0x1400058b8  call    cs:__imp_archive_entry_pathname
0x1400058be  mov     rdx, rax
0x1400058c1  lea     rcx, aCopyS; "copy '%s'"
0x1400058c8  call    yes
0x1400058cd  test    eax, eax
0x1400058cf  jz      loc_140005A2A
0x1400058d5  cmp     byte ptr [rdi+69h], 0
0x1400058d9  jz      short loc_140005904
0x1400058db  mov     rbx, [rbp+arg_18]
0x1400058df  mov     rcx, rbx
0x1400058e2  call    cs:__imp_archive_entry_mtime
0x1400058e8  cmp     byte ptr [rdi+6Ah], 0
0x1400058ec  jz      short loc_1400058F4
0x1400058ee  cmp     rax, [rdi+70h]
0x1400058f2  jle     short loc_140005904
0x1400058f4  mov     rdx, [rdi+70h]
0x1400058f8  xor     r8d, r8d
0x1400058fb  mov     rcx, rbx
0x1400058fe  call    cs:__imp_archive_entry_set_mtime
0x140005904  cmp     dword ptr [rdi+20h], 1
0x140005908  jle     short loc_14000593A
0x14000590a  mov     ecx, r13d; Ix
0x14000590d  call    _o___acrt_iob_func_0
0x140005912  mov     rcx, rax; Stream
0x140005915  lea     rdx, aA_0; "a "
0x14000591c  call    safe_fprintf
0x140005921  mov     ecx, r13d; Ix
0x140005924  call    _o___acrt_iob_func_0
0x140005929  mov     r8, [rbp+arg_18]
0x14000592d  mov     rdx, rax
0x140005930  mov     rcx, rdi
0x140005933  call    list_item_verbose
0x140005938  jmp     short loc_140005967
0x14000593a  cmp     dword ptr [rdi+20h], 0
0x14000593e  jle     short loc_140005967
0x140005940  mov     rcx, [rbp+arg_18]
0x140005944  call    cs:__imp_archive_entry_pathname
0x14000594a  mov     ecx, r13d; Ix
0x14000594d  mov     rbx, rax
0x140005950  call    _o___acrt_iob_func_0
0x140005955  mov     rcx, rax; Stream
0x140005958  lea     rdx, aAS; "a %s"
0x14000595f  mov     r8, rbx
0x140005962  call    safe_fprintf
0x140005967  mov     rdx, [rbp+arg_18]
0x14000596b  mov     rcx, r15
0x14000596e  call    cs:__imp_archive_write_header
0x140005974  mov     esi, eax
0x140005976  test    eax, eax
0x140005978  jz      short loc_1400059DD
0x14000597a  cmp     dword ptr [rdi+20h], 0
0x14000597e  mov     rcx, r15
0x140005981  jnz     short loc_1400059AC
0x140005983  call    cs:__imp_archive_error_string
0x140005989  mov     rcx, [rbp+arg_18]
0x14000598d  mov     rbx, rax
0x140005990  call    cs:__imp_archive_entry_pathname
0x140005996  mov     r9, rbx
0x140005999  lea     rdx, aSS_1; "%s: %s"
0x1400059a0  mov     r8, rax
0x1400059a3  xor     ecx, ecx
0x1400059a5  call    lafe_warnc
0x1400059aa  jmp     short loc_1400059CF
0x1400059ac  call    cs:__imp_archive_error_string
0x1400059b2  mov     ecx, r13d; Ix
0x1400059b5  mov     rbx, rax
0x1400059b8  call    _o___acrt_iob_func_0
0x1400059bd  mov     rcx, rax; Stream
0x1400059c0  lea     rdx, aS_1; ": %s"
0x1400059c7  mov     r8, rbx
0x1400059ca  call    fprintf
0x1400059cf  cmp     esi, 0FFFFFFE2h
0x1400059d2  jz      loc_140005A60
0x1400059d8  cmp     esi, 0FFFFFFECh
0x1400059db  jl      short loc_140005A0D
0x1400059dd  mov     rcx, [rbp+arg_18]
0x1400059e1  call    cs:__imp_archive_entry_size
0x1400059e7  test    rax, rax
0x1400059ea  jnz     short loc_1400059F7
0x1400059ec  mov     rcx, r14
0x1400059ef  call    cs:__imp_archive_read_data_skip
0x1400059f5  jmp     short loc_140005A0D
0x1400059f7  mov     r9, [rbp+arg_18]
0x1400059fb  mov     r8, r14
0x1400059fe  mov     rdx, r15
0x140005a01  mov     rcx, rdi
0x140005a04  call    copy_file_data_block
0x140005a09  test    eax, eax
0x140005a0b  jnz     short loc_140005A60
0x140005a0d  cmp     dword ptr [rdi+20h], 0
0x140005a11  jz      short loc_140005A2A
0x140005a13  mov     ecx, r13d; Ix
0x140005a16  call    _o___acrt_iob_func_0
0x140005a1b  mov     rcx, rax; Stream
0x140005a1e  lea     rdx, asc_14000B8DC; "\n"
0x140005a25  call    fprintf
0x140005a2a  lea     rdx, [rbp+arg_18]
0x140005a2e  mov     rcx, r14
0x140005a31  call    cs:__imp_archive_read_next_header
0x140005a37  mov     ecx, eax
0x140005a39  test    eax, eax
0x140005a3b  jz      loc_140005881
0x140005a41  mov     rbx, [rsp+20h+arg_0]
0x140005a46  xor     eax, eax
0x140005a48  mov     rsi, [rsp+20h+arg_8]
0x140005a4d  cmp     ecx, 1
0x140005a50  cmovnz  eax, ecx
0x140005a53  add     rsp, 20h
0x140005a57  pop     r15
0x140005a59  pop     r14
0x140005a5b  pop     r13
0x140005a5d  pop     rdi
0x140005a5e  pop     rbp
0x140005a5f  retn
0x140005a60  mov     ecx, 1; Code
0x140005a65  call    cs:__imp_exit
```
