# set_reader_options

- ea: `0x140005fc4`
- end: `0x1400060ce`
- name: `set_reader_options`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140005a74`
- `0x1400063bc`
- `0x140006650`

## callees

- `0x140005fc4`
- `0x1400071a4`
- `0x1400076d1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000607b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000607b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006041`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006041`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x140005fdc`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x140005fdc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140005fff`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140005fff`
- `archiveint!archive_read_set_options` at `0x140006036`
- `archiveint!archive_read_set_options` at `0x140006066`
- `archiveint!archive_read_set_options` at `0x140006036`
- `archiveint!archive_read_set_options` at `0x140006066`
- `archiveint!archive_clear_error` at `0x14000604f`
- `archiveint!archive_clear_error` at `0x14000604f`
- `archiveint!archive_error_string` at `0x140006095`
- `archiveint!archive_error_string` at `0x1400060b3`
- `archiveint!archive_error_string` at `0x140006095`
- `archiveint!archive_error_string` at `0x1400060b3`

## string_xrefs

- `0x140005fd5`: `TAR_READER_OPTIONS`
- `0x14000605c`: `read_concatenated_archives`

## pseudocode

```c
char *__fastcall set_reader_options(__int64 a1, __int64 a2)
{
  char *result; // rax
  char *v5; // rbx
  __int64 v6; // rdx
  size_t v7; // rbp
  void *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  void *v12; // rsi
  int set_options; // ebx

  result = getenv("TAR_READER_OPTIONS");
  v5 = result;
  if ( result )
  {
    v6 = -1;
    do
      ++v6;
    while ( result[v6] );
    v7 = v6 + 1;
    v8 = malloc(v6 + 30);
    v12 = v8;
    if ( !v8 )
    {
      _o__errno(v10, v9, v11);
      lafe_errc(1);
    }
    qmemcpy(v8, "__ignore_wrong_module_name__,", 29);
    memcpy_0(v8, v5, v7);
    set_options = archive_read_set_options(a2, v12);
    free(v12);
    if ( set_options < -20 )
    {
      archive_error_string(a2);
      lafe_errc(1);
    }
    result = (char *)archive_clear_error(a2);
  }
  if ( (*(_BYTE *)(a1 + 36) & 0x10) != 0 )
  {
    result = (char *)archive_read_set_options(a2, "read_concatenated_archives");
    if ( (_DWORD)result )
    {
      archive_error_string(a2);
      lafe_errc(1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140005fc4  push    rbx
0x140005fc6  push    rbp
0x140005fc7  push    rsi
0x140005fc8  push    rdi
0x140005fc9  push    r14
0x140005fcb  sub     rsp, 20h
0x140005fcf  mov     r14, rcx
0x140005fd2  mov     rdi, rdx
0x140005fd5  lea     rcx, aTarReaderOptio; "TAR_READER_OPTIONS"
0x140005fdc  call    cs:__imp_getenv
0x140005fe2  mov     rbx, rax
0x140005fe5  test    rax, rax
0x140005fe8  jz      short loc_140006055
0x140005fea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140005fee  inc     rdx
0x140005ff1  cmp     byte ptr [rax+rdx], 0
0x140005ff5  jnz     short loc_140005FEE
0x140005ff7  lea     rbp, [rdx+1]
0x140005ffb  lea     rcx, [rbp+1Dh]; Size
0x140005fff  call    cs:__imp_malloc
0x140006005  mov     rsi, rax
0x140006008  test    rax, rax
0x14000600b  jz      short loc_14000607B
0x14000600d  movups  xmm0, xmmword ptr cs:aIgnoreWrongMod; "__ignore_wrong_module_name__,"
0x140006014  mov     r8, rbp; Size
0x140006017  mov     rdx, rbx; Src
0x14000601a  mov     rcx, rax; void *
0x14000601d  movups  xmmword ptr [rax], xmm0
0x140006020  movups  xmm1, xmmword ptr cs:aIgnoreWrongMod+0Dh; "g_module_name__,"
0x140006027  movups  xmmword ptr [rax+0Dh], xmm1
0x14000602b  call    memcpy_0
0x140006030  mov     rdx, rsi
0x140006033  mov     rcx, rdi
0x140006036  call    cs:__imp_archive_read_set_options
0x14000603c  mov     rcx, rsi; Block
0x14000603f  mov     ebx, eax
0x140006041  call    cs:__imp_free
0x140006047  mov     rcx, rdi
0x14000604a  cmp     ebx, 0FFFFFFECh
0x14000604d  jl      short loc_140006095
0x14000604f  call    cs:__imp_archive_clear_error
0x140006055  test    byte ptr [r14+24h], 10h
0x14000605a  jz      short loc_140006070
0x14000605c  lea     rdx, aReadConcatenat; "read_concatenated_archives"
0x140006063  mov     rcx, rdi
0x140006066  call    cs:__imp_archive_read_set_options
0x14000606c  test    eax, eax
0x14000606e  jnz     short loc_1400060B0
0x140006070  add     rsp, 20h
0x140006074  pop     r14
0x140006076  pop     rdi
0x140006077  pop     rsi
0x140006078  pop     rbp
0x140006079  pop     rbx
0x14000607a  retn
0x14000607b  call    cs:__imp__o__errno
0x140006081  lea     r8, aOutOfMemory; "Out of memory"
0x140006088  mov     ecx, 1; Code
0x14000608d  mov     edx, [rax]
0x14000608f  call    lafe_errc
0x140006095  call    cs:__imp_archive_error_string
0x14000609b  xor     edx, edx
0x14000609d  lea     r8, aS_5; "%s"
0x1400060a4  mov     r9, rax
0x1400060a7  lea     ecx, [rdx+1]; Code
0x1400060aa  call    lafe_errc
0x1400060b0  mov     rcx, rdi
0x1400060b3  call    cs:__imp_archive_error_string
0x1400060b9  xor     edx, edx
0x1400060bb  lea     r8, aS_5; "%s"
0x1400060c2  mov     r9, rax
0x1400060c5  lea     ecx, [rdx+1]; Code
0x1400060c8  call    lafe_errc
```
