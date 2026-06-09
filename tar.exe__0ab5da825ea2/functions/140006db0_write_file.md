# write_file

- ea: `0x140006db0`
- end: `0x140006e9d`
- name: `write_file`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400069a8`
- `0x140006ea4`

## callees

- `0x140001b96`
- `0x140004d0c`
- `0x1400050fc`
- `0x140005d7c`
- `0x140006db0`
- `0x140007298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x140006e8b`
- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x140006e8b`
- `archiveint!archive_entry_size` at `0x140006e62`
- `archiveint!archive_entry_size` at `0x140006e62`
- `archiveint!archive_entry_pathname` at `0x140006e3b`
- `archiveint!archive_entry_pathname` at `0x140006e3b`
- `archiveint!archive_write_header` at `0x140006dca`
- `archiveint!archive_write_header` at `0x140006dca`
- `archiveint!archive_error_string` at `0x140006e13`
- `archiveint!archive_error_string` at `0x140006e2f`
- `archiveint!archive_error_string` at `0x140006e13`
- `archiveint!archive_error_string` at `0x140006e2f`

## pseudocode

```c
__int64 __fastcall write_file(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // ebp
  FILE *v7; // rax
  FILE *v8; // rax
  const char *v9; // rax
  __int64 result; // rax
  const char *v11; // rbx
  const char *v12; // rax

  v6 = archive_write_header(a2, a3);
  if ( !v6 )
    goto LABEL_7;
  if ( *(int *)(a1 + 32) <= 1 )
  {
    v11 = (const char *)archive_error_string(a2);
    v12 = (const char *)archive_entry_pathname(a3);
    result = lafe_warnc(0, "%s: %s", v12, v11);
  }
  else
  {
    v7 = o___acrt_iob_func_0(2u);
    safe_fprintf(v7, "a ");
    v8 = o___acrt_iob_func_0(2u);
    list_item_verbose(a1, v8, a3);
    v9 = (const char *)archive_error_string(a2);
    result = lafe_warnc(0, ": %s", v9);
  }
  if ( v6 == -30 )
LABEL_9:
    exit(1);
  if ( v6 >= -20 )
  {
LABEL_7:
    result = archive_entry_size(a3);
    if ( result > 0 )
    {
      result = copy_file_data_block(a1, a2, *(_QWORD *)(a1 + 200), a3);
      if ( (_DWORD)result )
        goto LABEL_9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006db0  push    rbx
0x140006db2  push    rbp
0x140006db3  push    rsi
0x140006db4  push    rdi
0x140006db5  push    r14
0x140006db7  sub     rsp, 20h
0x140006dbb  mov     r14, rdx
0x140006dbe  mov     rsi, rcx
0x140006dc1  mov     rcx, r14
0x140006dc4  mov     rdx, r8
0x140006dc7  mov     rdi, r8
0x140006dca  call    cs:__imp_archive_write_header
0x140006dd0  mov     ebp, eax
0x140006dd2  test    eax, eax
0x140006dd4  jz      loc_140006E5F
0x140006dda  cmp     dword ptr [rsi+20h], 1
0x140006dde  jle     short loc_140006E2C
0x140006de0  mov     ebx, 2
0x140006de5  mov     ecx, ebx; Ix
0x140006de7  call    _o___acrt_iob_func_0
0x140006dec  mov     rcx, rax; Stream
0x140006def  lea     rdx, aA_0; "a "
0x140006df6  call    safe_fprintf
0x140006dfb  mov     ecx, ebx; Ix
0x140006dfd  call    _o___acrt_iob_func_0
0x140006e02  mov     rdx, rax
0x140006e05  mov     r8, rdi
0x140006e08  mov     rcx, rsi
0x140006e0b  call    list_item_verbose
0x140006e10  mov     rcx, r14
0x140006e13  call    cs:__imp_archive_error_string
0x140006e19  lea     rdx, aS_1; ": %s"
0x140006e20  xor     ecx, ecx
0x140006e22  mov     r8, rax
0x140006e25  call    lafe_warnc
0x140006e2a  jmp     short loc_140006E55
0x140006e2c  mov     rcx, r14
0x140006e2f  call    cs:__imp_archive_error_string
0x140006e35  mov     rcx, rdi
0x140006e38  mov     rbx, rax
0x140006e3b  call    cs:__imp_archive_entry_pathname
0x140006e41  mov     r9, rbx
0x140006e44  lea     rdx, aSS_1; "%s: %s"
0x140006e4b  mov     r8, rax
0x140006e4e  xor     ecx, ecx
0x140006e50  call    lafe_warnc
0x140006e55  cmp     ebp, 0FFFFFFE2h
0x140006e58  jz      short loc_140006E86
0x140006e5a  cmp     ebp, 0FFFFFFECh
0x140006e5d  jl      short loc_140006E92
0x140006e5f  mov     rcx, rdi
0x140006e62  call    cs:__imp_archive_entry_size
0x140006e68  test    rax, rax
0x140006e6b  jle     short loc_140006E92
0x140006e6d  mov     r8, [rsi+0C8h]
0x140006e74  mov     r9, rdi
0x140006e77  mov     rdx, r14
0x140006e7a  mov     rcx, rsi
0x140006e7d  call    copy_file_data_block
0x140006e82  test    eax, eax
0x140006e84  jz      short loc_140006E92
0x140006e86  mov     ecx, 1; Code
0x140006e8b  call    cs:__imp_exit
0x140006e92  add     rsp, 20h
0x140006e96  pop     r14
0x140006e98  pop     rdi
0x140006e99  pop     rsi
0x140006e9a  pop     rbp
0x140006e9b  pop     rbx
0x140006e9c  retn
```
